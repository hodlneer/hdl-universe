# HODLNEER Badge PRD

**Status:** Draft v1
**Owner:** Core Canon Leadership
**Location:** `01_governance/vision/`

---

## 1. Product Overview

### Product Name

HODLNEER Badge

### Product Type

Identity + Proof + Status Artifact

### Core Definition

The HODLNEER Badge is a proof-bearing identity artifact that represents a user's participation, history, and standing within the HDL ecosystem.

**It is NOT:**
- a collectible gimmick
- a gamified badge system
- a ranking mechanism

**It IS:**
- a visible signal of identity, proof, and alignment with the crypto ethos of HODLing over time

### Core Principle

> The system does not create status.
> It reflects it.

---

## 2. Product Philosophy

### Badge-First Model

The badge is the product.

Tiers, validation, and classification exist to support meaning — but are not the primary user-facing narrative.

Users should say: **"I got my HODLNEER badge."**

Not: "I reached Tier X."

### Identity Layering

| Layer | Object |
|-------|--------|
| Base identity | HDL account |
| Proof layer | HODLNEER badge |

Users may have an HDL account without having a HODLNEER badge.

---

## 3. User Eligibility

### Launch Eligibility

All users can receive a HODLNEER badge if they opt into the Hodlneer onboarding flow.

- Badge is opt-in
- Badge represents intent + declared identity + submitted proof signals

### Key Rule

> Creating an HDL account does not grant a badge.
> Completing Hodlneer onboarding does.

---

## 4. Tier System

### Structure

The system uses a dual-layer tier model:

**Layer 1 — Canonical Meaning (Internal Truth)**
Defines what the tier represents.

**Layer 2 — Visual Material (User-Facing Expression)**
Defines how the badge looks.

### Visual Material System

| Tier | Material |
|------|----------|
| 1 | Bronze |
| 2 | Silver |
| 3 | Gold |
| 4 | Platinum (White / Pristine) |

### Tier Visibility Principle

- Tiers are visually expressed
- Tiers are recognizable without text
- Tiers enhance identity, not replace it
- Tiers must not dominate the product narrative

### Design Direction

Higher tiers should feel: more refined, more intentional, more premium.

They should NOT feel: louder, bigger, attention-seeking.

---

## 5. Origin / Platinum Tier (Recognition Tier)

### Definition

The highest tier (Platinum / Origin) represents individuals with recognized, verifiable impact on the crypto ecosystem.

### Assignment Model

Origin Tier is:
- **not** applied for
- **not** earned via onboarding
- **not** self-declared

It is: **recognized and granted.**

### Assignment Rule

The system assigns Origin Tier when:
- identity is verified
- contribution to crypto is publicly recognized
- impact aligns with canonical criteria

### Examples (Non-Exhaustive)

- Protocol builders
- Major advocates
- Ecosystem shapers
- Long-term influential figures

### Launch Strategy

At launch, Origin Tier is admin-controlled and seeded from:
- Known public figures
- Industry-recognized lists (e.g., CoinDesk Most Influential)

Origin Tier is not required for initial rollout completeness.

### Application Path

Users may:
- Request consideration for higher recognition
- Submit supporting evidence
- Enter a manual review queue

Verification may include documentation, references, and direct validation (including human verification if necessary).

### Key Rule

> Applying does not guarantee qualification.

---

## 6. Badge Behavior

### Launch Behavior

At launch, the badge functions as a social proof signal.

**What it does:**
- Signals identity and status
- Communicates participation and credibility
- Creates visible presence within HDL
- Enables pride and recognition

**What it does NOT do at launch:**
- No ranking system
- No comparative scoring
- No leaderboard behavior
- No financial utility
- No automatic gated ecosystem

### Future Behavior (Directional)

Possible future capabilities:
- Access to exclusive HDL content
- Webinars / crypto education
- Early feature access
- First tester privileges
- Insider awareness (e.g., early initiatives)
- Gated community experiences

These are not launch requirements.

### Ranking Stance

Ranking is intentionally avoided.

**Reason:** Prevents social pressure, avoids unhealthy comparison, aligns with inclusive design philosophy.

---

## 7. Visibility Rules

### Default Visibility

Badge is visible on user profile by default.

### Additional Surfaces at Launch

- Profile page (primary)
- Share flows (user-triggered)

### Visibility Philosophy

- Visible by default
- Controlled by user when sharing
- Never forced into spammy surfaces

### Open Questions

- Can users hide badge?
- Should badge appear automatically in feed / comments?
- Per-tier visibility differences?

---

## 8. Share System (Critical)

### Purpose

Sharing is a core growth mechanism.

### Share Goals

- Enable user pride
- Create UGC-driven exposure
- Drive curiosity and inbound traffic
- Turn badge holders into organic distribution

### Share Behavior

Users can:
- Choose where to share badge
- Generate shareable outputs
- Publish externally or within HDL

### Share Targets

- External social platforms
- HDL surfaces
- Future campaign flows

### Product Stance

Sharing should feel like: **a flex, a celebration, a signal.**

It should NOT feel like: spam, forced promotion.

---

## 9. Issuance Model

### Launch Model

Badge generation is automated after onboarding.

### Inputs

- Username / handle
- Declared crypto entry year
- Onboarding responses
- Optional API verification (e.g., exchanges)
- Future proof integrations

### Process

1. User completes onboarding
2. System processes inputs
3. Badge template selected
4. Badge generated
5. Badge assigned to identity

### Key Design

Hodlneer is a standalone badge-generation system consumed by HDL.

---

## 10. Constraints

The badge must NOT become:
- Meaningless flair
- A vanity-only system
- A ranking mechanism
- A financial speculation device
- A celebrity worship signal
- Disconnected from proof

---

## 11. Dependencies

This PRD depends on:

- Identity model (HDL handle system)
- Proof system (future validation layers)
- Onboarding flow design
- Rendering system — see [[02_canon/Hodlneer/CANON/BADGE_VISUAL_SYSTEM|BADGE_VISUAL_SYSTEM]] and [[04_capabilities/3D_RENDERING_APPROACH|3D_RENDERING_APPROACH]]
- Paperclip orchestration system — see [[06_paperclip/HODLNEER_PAPERCLIP_SYSTEM_DESIGN|HODLNEER_PAPERCLIP_SYSTEM_DESIGN]]

---

## 12. Open Questions

- Canonical tier naming beyond materials
- Validation depth per tier
- Privacy-preserving verification (whales / institutions)
- Revocation triggers and process
- Badge transferability (likely no)
- Final share UX design
- Evolution rules for tier upgrades

---

## 13. Summary

**The HODLNEER Badge is:**
- A proof-bearing identity artifact
- A visible signal of participation and credibility
- A shareable object that drives network effects

**It is NOT:**
- A ranking system
- A gamification loop
- A vanity mechanic

**It IS:**
- A representation of truth, history, and identity within the HDL ecosystem

---

## Related Documents

- [[02_canon/Hodlneer/CANON/IDENTITY_MODEL|IDENTITY_MODEL]] — era and verification taxonomy this PRD depends on
- [[02_canon/Hodlneer/CANON/BADGE_VISUAL_SYSTEM|BADGE_VISUAL_SYSTEM]] — visual expression of tiers
- [[02_canon/Hodlneer/CANON/PRODUCT_PRINCIPLES|PRODUCT_PRINCIPLES]] — guardrails governing badge decisions
- [[02_canon/Hodlneer/EXECUTION/EPICS|EPICS]] — implementation lanes
- [[02_canon/Hodlneer/HODLNEER_INDEX|HODLNEER_INDEX]] — vertical entry point
- [[06_paperclip/HODLNEER_PAPERCLIP_SYSTEM_DESIGN|HODLNEER_PAPERCLIP_SYSTEM_DESIGN]] — agent orchestration system
