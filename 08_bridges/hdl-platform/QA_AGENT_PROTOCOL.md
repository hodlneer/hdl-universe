# HDL QA Agent Protocol

## Purpose

This document defines the reusable QA agent prompt and validation checklist for all HDL tasks.
Every task in the Notion HDL Task Management DB must pass this protocol before Status can be set to `PASS`.

The QA agent is separate from the build agent. It reads, greps, and validates — it does not write code.

---

## How to Invoke the QA Agent

Paste the following as a Claude Code prompt, substituting the task details:

```
You are the HDL QA Agent. Your job is to validate that a completed task meets canon requirements.
Do NOT write or modify any code. Only read, search, and report.

## Task to validate
[PASTE TASK NAME AND NOTION PAGE URL]

## Acceptance criteria
[PASTE the Validation Notes field from the Notion task]

## Run the following checks in order:

### CHECK 1 — File Existence
Confirm every file listed in "Files Created" (Notion field) exists on disk.
Report: PASS or FAIL with file path for each.

### CHECK 2 — No Hardcoded Hex / px Values
Run grep for hardcoded color values (#[0-9a-fA-F]{3,6}) and hardcoded pixel values
([0-9]+px) in every file listed. Ignore comments.
Report: PASS (zero matches) or FAIL (list each violation with line number).

### CHECK 3 — Design System Token Compliance
All color and spacing values must use --hdl-* CSS variables or hdl.* Tailwind utilities.
Check that no raw hex or hardcoded px remains in className or style props.
Report: PASS or FAIL with specifics.

### CHECK 4 — TypeScript Build
Report whether `npx tsc --noEmit` passes in the relevant project directory.
If it fails, list the errors. Do not fix them.
Report: PASS or FAIL.

### CHECK 5 — Canon Compliance
Check the relevant canon file for this task type:
- Identity tasks → canon/hdl_world/IDENTITY_ANCHOR.md
- Wallet tasks → canon/shared/WALLET_MODEL.md
- Routing tasks → canon/hdl_world/ROUTING_ENGINE.md
- Badge/Proof tasks → canon/hdl_world/PROOF_ENGINE.md
- Fiat tasks → HDL_PHASE_1_5_CANON.md

Confirm the implementation matches the canon contract. Flag any deviation.
Report: PASS or FAIL with specific canon rule violated if FAIL.

### CHECK 6 — API Contract (backend tasks only)
For any endpoint created or modified, verify:
- Route path matches HDL_BACKEND_INTEGRATION_PLAN.md spec exactly
- Request/response shape matches the plan
- No raw userId exposed in user-facing response fields
Report: PASS, FAIL, or N/A.

### CHECK 7 — No Hardcoded User Data (wallet/feed tasks)
Grep for hardcoded balance strings (e.g. '$47,284', 'hodlneer@', test wallet addresses).
Report: PASS or FAIL with line numbers.

## Final verdict
Output one of:
- QA PASS — all checks passed. List any minor notes.
- QA FAIL — list each failing check with specifics. Do not fix. Report back to the build agent.

## After completing the validation
Update the Notion task:
- Set "QA Agent ID" to your agent session ID
- Set "Validation Notes" to the full QA report summary
- Set "Status" to PASS or FAIL
- Set "Build Status" to Success or Failed
```

---

## Checks Reference Table

| Check | What it catches | Canon source |
|---|---|---|
| File Existence | Agent said it did the work but didn't | N/A |
| No Hardcoded Hex | Design system violations | `BRAND_SYSTEM.md` |
| DS Token Compliance | Tailwind/CSS token drift | `globals.css`, `tailwind.config.js` |
| TypeScript Build | Type errors introduced | N/A |
| Canon Compliance | Product diverging from doctrine | Relevant canon file |
| API Contract | Backend endpoints drifting from plan | `HDL_BACKEND_INTEGRATION_PLAN.md` |
| No Hardcoded User Data | Fake/static data shipped as real | `WALLET_MODEL.md` |

---

## QA Agent Rules

1. **Read-only.** The QA agent never modifies files. It reports findings only.
2. **Cite line numbers.** Every FAIL must include the exact file path and line number.
3. **No partial passes.** All checks must pass for the task to be PASS. One FAIL = overall FAIL.
4. **Update Notion.** The QA agent must write results back to the Notion task before finishing.
5. **Do not re-run the build agent.** If QA FAIL, return the report to the user. The user decides whether to re-open the task.

---

## Status Flow

```
Backlog → In Progress → Ready for QA → [QA Agent runs] → PASS or FAIL
                                                              ↓
                                                        FAIL → reopened → In Progress
                                                        PASS → Done / Deployed
```

---

## Notion Field Mapping

| Notion Field | Set by | When |
|---|---|---|
| Status | Build agent | After implementation |
| Build Status | Build agent | After `tsc` / `npm run build` |
| Files Created | Build agent | After implementation |
| QA Agent ID | QA agent | After validation run |
| Validation Notes | QA agent | After validation run |

---

## First Tasks for QA (priority order)

1. `[AUDIT]` Re-validate stale UI components — Card, Input, Modal, Button
2. `[EPIC-1]` Proof / Badge System — after implementation complete
3. `[EPIC-2]` Handle Enforcement — after implementation complete
4. `[EPIC-3]` Routing Engine — after implementation complete
5. `[EPIC-4]` Wallet Abstraction — specifically check WalletBalance.tsx for hardcoded data
6. `[EPIC-5]` Feed Identity Layer — verify real API calls and badge rendering
