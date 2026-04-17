# HODLNEER PRD

**Status:** Draft v1 — 2026-04-17
**Owner:** Core Canon Leadership
**Location:** `02_canon/`

This is the canonical app-level product requirements document for the Hodlneer system. It defines system boundaries, the onboarding flow, the badge generation lifecycle, HDL integration, and future expansion paths.

This document does NOT redefine badge logic. Badge artifact details live in [[01_governance/vision/HODLNEER_BADGE_PRD|HODLNEER_BADGE_PRD]] and [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]]. This document defines the system that surrounds and produces the badge.

See also: [[CANON_INDEX]] | [[Hodlneer/HODLNEER_INDEX|HODLNEER_INDEX]]

---

## 1. Product Overview

### Product Name

**Hodlneer**

### Product Type

Identity Infrastructure + Badge Generation System

### Core Definition

Hodlneer is a standalone system responsible for:

- Onboarding users into a proof-based identity layer
- Generating the HODLNEER badge
- Validating participation and credibility signals
- Integrating badge identity into the HDL ecosystem

**It is NOT:**
- A social platform
- A trading platform
- A content platform

**It IS:**
> The system that produces verifiable identity artifacts for the HDL ecosystem.

---

## 2. System Role in HDL Ecosystem

### Separation of Concerns

| System | Responsibility |
|--------|---------------|
| HDL | Social layer — profiles, content, interactions |
| Hodlneer | Identity layer — badge generation and validation |
| Paperclip | Orchestration layer — execution and routing |

### Core Principle

> Hodlneer creates identity.
> HDL expresses identity.

These systems strengthen each other. They must not collapse into each other.

---

## 3. Core User Journey

1. User creates HDL account
2. User opts into Hodlneer onboarding
3. User submits: crypto history signals, entry year, optional verification data
4. Hodlneer processes inputs
5. Badge is generated
6. Badge is attached to user identity
7. Badge becomes visible and shareable on HDL and external platforms

The badge generation step (5) is automated. Tier validation for higher tiers may be manual or hybrid. See [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]] for tier logic.

---

## 4. Onboarding System

### Purpose

Collect enough identity signal to generate a badge with the correct tier classification. Not a tutorial. Not a crypto education flow. A proof-intake system.

### Inputs

- Username / handle
- Claimed crypto entry year
- Optional wallet connection
- Optional exchange / account connection
- Optional verification signals (documents, references)

### Recognition Path

Users who believe they qualify for the Platinum (Origin) tier may:
- Flag themselves for review during onboarding
- Submit supporting evidence and references
- Enter a manual admin review queue

Flagging does not initiate a guaranteed process. See [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]] — Origin tier section.

### What onboarding must NOT become

- A crypto tutorial
- A wallet app setup clone
- An HDL.fun signup flow in disguise
- A data collection process that feels like surveillance

---

## 5. Badge Generation Lifecycle

### Automated Flow

```
onboarding complete
    ↓
system evaluates inputs
    ↓
tier assigned (Bronze / Silver / Gold / Platinum)
    ↓
badge template selected
    ↓
badge generated
    ↓
badge attached to user identity
    ↓
badge visible + shareable
```

### Key Rule

> Badge creation is automated.
> Tier validation for Platinum is manual and admin-controlled.

### Lifecycle Events

| Event | Trigger | Result |
|-------|---------|--------|
| Initial generation | Onboarding complete | Badge created at appropriate tier |
| Tier upgrade | User submits stronger proof | Badge updated to higher tier |
| Revocation | Evidence found to be false or fraudulent | Badge removed; user may re-enter onboarding |

For full evolution and revocation rules, see [[01_governance/vision/HODLNEER_BADGE_PRD|HODLNEER_BADGE_PRD]] — Section 9.

---

## 6. Badge Integration with HDL

### What Hodlneer sends to HDL

- Public badge identity result (`[Era] • [Verification]` or material tier)
- Badge display state (active / hidden / not yet generated)
- Optional approved presentation preferences

### What Hodlneer does NOT send to HDL

- Raw wallet data
- Private proof evidence
- Exchange account details
- Financial signals or balances
- Any data the user chose to keep private

### Display rule

> Hodlneer generates.
> HDL distributes.

HDL must display the badge as a high-value identity artifact, not flatten it into a minor profile decoration. See [[Hodlneer/INTEGRATION/HODLNEER_TO_HDL|HODLNEER_TO_HDL]] for the full integration spec.

---

## 7. Recognition Tier System

The Platinum (Origin) tier is the exception to the automated lifecycle. It is:
- Assigned via admin recognition, not onboarding
- Seeded from curated industry lists at launch (e.g. CoinDesk Most Influential)
- Extended manually to new qualifying individuals on a rolling basis
- Never self-awarded

For the complete tier model, see [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]].

---

## 8. System Boundaries

Hodlneer does NOT:

- Rank users against each other
- Create leaderboards or comparative scoring
- Assign or imply financial value to badges
- Function as a social network
- Gate core HDL.fun functionality

These constraints are permanent, not deferred. They define what Hodlneer is.

---

## 9. Future Expansion

These are directional — not launch requirements.

| Capability | Description |
|-----------|-------------|
| Gated content access | Badge holders gain access to exclusive HDL content or features |
| Early access | Higher-tier holders receive priority access to new features |
| Insider privileges | Awareness of early HDL initiatives before public announcement |
| Token-based extensions | HODLNEER token (HDLNR) tied to badge identity — future, not specified |
| Institutional onboarding | Privacy-preserving verification flows for whales and institutions |
| Cross-platform badge | Badge usable on surfaces outside HDL.fun |
| API exposure | Badge system exposed via API for third-party integrations |

None of these are commitments. None of them should be allowed to distort the launch scope.

---

## 10. Dependencies

| Dependency | Location | Status |
|-----------|----------|--------|
| HDL identity system (handle model) | `02_canon/hdl_world/IDENTITY_ANCHOR.md` | Exists |
| Badge artifact PRD | `01_governance/vision/HODLNEER_BADGE_PRD.md` | Exists (v2) |
| Tier system canon | `02_canon/Hodlneer/CANON/TIER_SYSTEM.md` | Exists |
| Verification engine | `02_canon/Hodlneer/EXECUTION/EPICS.md` — Epics 1–2 | Defined, not yet built |
| Onboarding flow design | `02_canon/Hodlneer/COPY/ONBOARDING_COPY_AND_REVEAL_NARRATION.md` | Copy exists |
| Reveal sequence | `02_canon/Hodlneer/EXPERIENCE/REVEAL_SEQUENCE_SPEC.md` | Exists |
| Paperclip orchestration | `06_paperclip/HODLNEER_PAPERCLIP_SYSTEM_DESIGN.md` | Exists |
| HDL integration spec | `02_canon/Hodlneer/INTEGRATION/HODLNEER_TO_HDL.md` | Exists |
| 3D rendering approach | `04_capabilities/3D_RENDERING_APPROACH.md` | Exists |

---

## 11. Open Questions

See `09_feedback/open-questions.md` for the full tracked list. Key system-level questions:

- Validation depth per tier — what evidence thresholds are required?
- Privacy-preserving proof path for whales and institutions
- Upgrade pathways — how does a user move from Silver to Gold?
- Cross-platform badge usage — can the badge appear outside HDL?
- API exposure — when and how is the badge system accessible externally?
- Account model — is Hodlneer account-based, device-local, or tied entirely to the HDL handle?

---

## 12. Summary

**Hodlneer is:**
- The identity infrastructure layer of the HDL ecosystem
- The system that generates proof-bearing badge artifacts
- The foundation for credibility within HDL

**It is NOT:**
- A ranking system
- A social platform
- A feature of HDL.fun

**It IS:**
> The engine behind the HODLNEER badge — and the system that ensures that engine is trustworthy.

---

## Related Documents

- [[01_governance/vision/HODLNEER_BADGE_PRD|HODLNEER_BADGE_PRD]] — badge artifact definition: tiers, issuance, evolution, revocation
- [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]] — material tier model, validation framework, Platinum assignment
- [[Hodlneer/CANON/IDENTITY_MODEL|IDENTITY_MODEL]] — era × verification formula this system executes
- [[Hodlneer/CANON/PRODUCT_PRINCIPLES|PRODUCT_PRINCIPLES]] — 15 guardrails governing all product decisions
- [[Hodlneer/EXECUTION/EPICS|EPICS]] — 10 epics defining implementation lanes
- [[Hodlneer/INTEGRATION/HODLNEER_TO_HDL|HODLNEER_TO_HDL]] — data boundaries and flow from Hodlneer into HDL
- [[Hodlneer/INTEGRATION/HDL_TO_HODLNEER|HDL_TO_HODLNEER]] — how HDL users are invited into Hodlneer
- [[06_paperclip/HODLNEER_PAPERCLIP_SYSTEM_DESIGN|HODLNEER_PAPERCLIP_SYSTEM_DESIGN]] — agent orchestration system
- [[Hodlneer/HODLNEER_INDEX|HODLNEER_INDEX]] — full Hodlneer vertical index
