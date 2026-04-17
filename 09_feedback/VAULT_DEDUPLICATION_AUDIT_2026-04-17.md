# Vault Deduplication Audit — 2026-04-17

**Performed by:** Claude (senior architect pass)
**Scope:** All 79 .md files in hdl-universe vault (excluding archive)
**Status:** Completed — all fixes applied in same session

---

## 1. Duplicate Groups Found

### Group A — BTC Hex Network Files (RESOLVED)
**Severity:** High — three files, same subject, two explicitly deprecated

| File | Lines | Status |
|------|-------|--------|
| `02_canon/btc_world/BTC_HEX_NETWORK_CANON.md` | 317 | ⚠️ Deprecated header present → **Archived** |
| `02_canon/btc_world/BTC_HEX_NETWORK_CANON_FULL_SPEC.md` | 365 | ⚠️ Deprecated header present → **Archived** |
| `02_canon/btc_world/BTC_HEX_NETWORK_SPEC.md` | 92 | ✅ Explicit consolidated replacement → **Canonical** |

**Action taken:** Both deprecated files moved to `archive/btc_deprecated_2026-04-17/`. No content lost — the 92-line consolidated spec explicitly states it replaces both.

---

### Group B — CANON_INDEX Naming Collision (RESOLVED)
**Severity:** High — same filename at two different scopes, creates ambiguity in Obsidian wiki-links and agent references

| File | Scope |
|------|-------|
| `02_canon/CANON_INDEX.md` | Vault-level canon map — all worlds, all verticals |
| `02_canon/Hodlneer/CANON/CANON_INDEX.md` | Hodlneer-vertical-specific canon index |

**Action taken:** Hodlneer-scoped file renamed to `HODLNEER_CANON_INDEX.md`. All 8 internal `[[CANON_INDEX]]` wiki-links in CANON docs updated to `[[HODLNEER_CANON_INDEX]]`. HODLNEER_INDEX.md folder tree and table updated.

---

### Group C — PRD Scope Confusion (DOCUMENTED, not fully resolved)
**Severity:** Medium — one PRD exists in governance, a different PRD is still missing from canon

| File | Layer | Scope | Status |
|------|-------|-------|--------|
| `01_governance/vision/HODLNEER_BADGE_PRD.md` | Governance | Badge system: tiers, issuance, evolution, revocation | ✅ Exists, current (v2) |
| `02_canon/Hodlneer/CANON/HODLNEER_PRD.md` | Canon | iOS app: standalone product, 3D reveal, wallpaper, privacy, HDL integration | ❌ Still missing |

**Why they're different:** The governance PRD defines what the badge artifact *is* and how it works (the tier/proof system). The canon PRD defines what the *iOS app* is — the standalone product experience. Both are needed. Neither replaces the other.

**Action taken:** HODLNEER_INDEX.md and HODLNEER_CANON_INDEX.md updated to clearly distinguish what exists vs what is missing.

**Remaining action:** Write `CANON/HODLNEER_PRD.md` (app-level). Recommend running through OD before Claude writes it.

---

### Group D — Misplaced Files (RESOLVED)

| File | Was in | Moved to | Reason |
|------|--------|----------|--------|
| `MIGRATION_REPORT_2026-04-04.md` | `02_canon/Hodlneer/` | `09_feedback/` | Migration reports are operational records, not canon. Should not live under canon authority layer. |
| `2026-04-01.md` | Vault root | `00_inbox/` | Date-named notes belong in inbox for processing, not vault root. |

---

### Group E — Inbox Backlog Item (NOTED, no action taken)

`00_inbox/HDL_PLATFORM_BACKLOG_2026_04_13.md` — This is a platform implementation backlog, not a vault intake doc. It should eventually be processed into `08_bridges/hdl-platform/` or remain as a reference. Not a duplicate — just misrouted. Leaving in inbox for now; process at next platform-focused session.

---

## 2. Canonical Folder Structure

The vault structure is sound. No restructuring needed. The issues were operational hygiene, not architectural. The numbered folder system is the correct long-term approach for an AI-assisted vault.

```
hdl-universe/
├── 00_inbox/              ← AI session intake files, dated notes, unprocessed content
│   └── YYYY-MM-DD_[topic]_INTAKE.md
├── 01_governance/         ← Product truth: principles, decisions, PRDs, vision
│   ├── constraints/
│   ├── decisions/
│   ├── principles/
│   ├── terminology/
│   └── vision/
│       └── [PRODUCT]_[TYPE]_PRD.md    ← governance-layer PRDs (badge, product)
├── 02_canon/              ← Source of truth: world rules, entity canon, product vertical canon
│   ├── CANON_INDEX.md     ← vault-level only — never duplicate this name at subfolder level
│   ├── CANON_AUTHORITY.md
│   ├── HDL_PHASE_1_5_CANON.md
│   ├── shared/            ← cross-world rules
│   ├── hdl_world/         ← HDL world canon
│   ├── btc_world/         ← Bitcoin world canon
│   └── [Vertical]/        ← product vertical canon (e.g. Hodlneer/)
│       ├── [VERTICAL]_INDEX.md          ← top-level vertical navigation
│       ├── CANON/
│       │   ├── [VERTICAL]_CANON_INDEX.md  ← MUST include vertical prefix to avoid collision
│       │   ├── [VERTICAL]_PRD.md          ← app-level canon PRD
│       │   └── [TOPIC].md
│       ├── COPY/
│       ├── EXPERIENCE/
│       ├── EXECUTION/
│       └── INTEGRATION/
├── 03_personas/           ← user personas and lenses
├── 04_capabilities/       ← tech approach, system capabilities
├── 05_use_cases/          ← concrete use case documentation
├── 06_paperclip/          ← org structure, agent team design
├── 07_agents/             ← agent definitions (executive, domain)
├── 08_bridges/            ← canon → implementation translation
│   └── [product-repo]/    ← one subfolder per implementation repo
├── 09_feedback/           ← execution feedback, blockers, open questions, audit reports
└── archive/               ← deprecated content, preserved, date-stamped
    └── [topic]_YYYY-MM-DD/
```

---

## 3. Naming Conventions

### Files

| Type | Convention | Example |
|------|-----------|---------|
| Canon doc | `SCREAMING_SNAKE_CASE.md` | `IDENTITY_MODEL.md` |
| Vertical index | `[VERTICAL]_INDEX.md` | `HODLNEER_INDEX.md` |
| Vertical canon index | `[VERTICAL]_CANON_INDEX.md` | `HODLNEER_CANON_INDEX.md` |
| Governance PRD | `[VERTICAL]_[SCOPE]_PRD.md` | `HODLNEER_BADGE_PRD.md` |
| Canon PRD | `[VERTICAL]_PRD.md` | `HODLNEER_PRD.md` |
| Intake file | `YYYY-MM-DD_[topic-slug]_INTAKE.md` | `2026-04-17_badge-tiers_INTAKE.md` |
| Audit/report | `[TOPIC]_AUDIT_YYYY-MM-DD.md` | `VAULT_DEDUPLICATION_AUDIT_2026-04-17.md` |
| Bridge doc | `[REPO]_[TOPIC].md` | `HDL_PRODUCT_ALIGNMENT_GAPS.md` |
| Archive folder | `[topic]_YYYY-MM-DD/` | `btc_deprecated_2026-04-17/` |

### Critical rule: CANON_INDEX is reserved for vault-level only
Any canon index inside a vertical subfolder **must** include the vertical name as a prefix: `[VERTICAL]_CANON_INDEX.md`. Never use bare `CANON_INDEX.md` below `02_canon/`.

---

## 4. Version Rules

| Scenario | Action |
|----------|--------|
| Minor content update (copy, fix, addition) | Edit in place. Update status line at top of file. |
| Structural change to a canon doc | Edit in place. Increment version in status line. Note change in `09_feedback/`. |
| Breaking change to identity/tier/rules | Escalate to Core Canon Leadership before editing. Create a decision record in `01_governance/decisions/`. |
| New version of a PRD | Edit in place. Update status line (`Draft v2`, `Draft v3`). Do NOT create `_v2.md` duplicate files. |
| Deprecated file | Add deprecation notice to top of file, then `git mv` to `archive/[topic]_YYYY-MM-DD/`. |
| AI session output | Always land in `00_inbox/` first. Only Claude moves content from inbox into canon/governance. |

---

## 5. Rules for AI-Assisted Workflows (Preventing Future Duplication)

These rules exist because AI sessions are the primary source of duplication in this vault.

1. **One intake per session.** OD ends every working session with a single dated intake file dropped into `00_inbox/`. Claude processes it and moves content to the right folder. No raw content goes directly into canon from a chat session.

2. **Claude never creates a new file without checking if one already exists.** Before writing a new doc, search for the topic name across the vault. If a file exists, update it — do not create a parallel version.

3. **`CANON_INDEX.md` is a protected name.** Only one file in the entire vault may be named `CANON_INDEX.md`: `02_canon/CANON_INDEX.md`. All vertical-scoped indexes must use the prefixed form.

4. **PRDs have two homes, not one.** Governance PRDs live in `01_governance/vision/`. Canon PRDs live in `02_canon/[Vertical]/CANON/`. These serve different purposes. If a PRD exists in one location, it does not satisfy the requirement for the other.

5. **Deprecated files never get deleted — they get archived.** Use `git mv [file] archive/[topic]_YYYY-MM-DD/` and add a deprecation header. This preserves history and prevents confusion.

6. **The intake file is not a source of truth.** It captures decisions and context. Claude reads it, extracts the decisions, updates the canonical docs, and the intake stays in `00_inbox/` as a historical record. Never treat an intake file as a canonical reference.

---

## 6. Cleanup Checklist (This Session)

- [x] Archive `BTC_HEX_NETWORK_CANON.md` (deprecated)
- [x] Archive `BTC_HEX_NETWORK_CANON_FULL_SPEC.md` (deprecated)
- [x] Rename `CANON/CANON_INDEX.md` → `CANON/HODLNEER_CANON_INDEX.md`
- [x] Update all 8 `[[CANON_INDEX]]` wiki-links in CANON docs
- [x] Update HODLNEER_INDEX.md folder tree and table link
- [x] Update HODLNEER_CANON_INDEX.md — add TIER_SYSTEM to table, update PRD status section
- [x] Move `MIGRATION_REPORT_2026-04-04.md` from canon to `09_feedback/`
- [x] Move `2026-04-01.md` from vault root to `00_inbox/`
- [x] Update HODLNEER_INDEX.md Missing Documents section to distinguish governance PRD from missing canon PRD

### Still open after this session
- [ ] Write `02_canon/Hodlneer/CANON/HODLNEER_PRD.md` — app-level iOS product canon (recommend OD session first)
- [ ] Process `00_inbox/HDL_PLATFORM_BACKLOG_2026_04_13.md` into `08_bridges/` at next platform session
- [ ] Populate empty folders: `01_governance/decisions/`, `01_governance/principles/`, `03_personas/`, `05_use_cases/`, `07_agents/` — or remove `.gitkeep` files and note they are intentionally empty stubs

---

## Summary

**Real duplicates found:** 1 group (BTC files — resolved)
**Naming collisions:** 1 (CANON_INDEX — resolved)
**Misplaced files:** 3 (migration report, vault root note, PRD scope confusion — resolved or documented)
**Structural issues:** None — the folder architecture is correct and scalable
**Highest remaining risk:** The missing `CANON/HODLNEER_PRD.md` — every canon doc in the vertical references it, and it still does not exist
