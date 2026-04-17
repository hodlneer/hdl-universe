# Hodlneer Canon Index

This index covers all canonical source-of-truth documents for the Hodlneer product vertical. These files define how the system MUST behave and should never be modified for product convenience — product must adapt to canon.

See also: [[HODLNEER_INDEX]] | [[02_canon/CANON_INDEX|Vault Canon Index]]

---

## Canon Documents

| File | Purpose |
|------|---------|
| [[IDENTITY_MODEL]] | Era taxonomy, verification taxonomy, Badge = Era × Verification, public/private identity rules |
| [[TIER_SYSTEM]] | Material tier model (Bronze→Platinum), canonical meaning mapping, validation framework, evolution/revocation rules |
| [[BADGE_VISUAL_SYSTEM]] | Badge silhouette, geometry, materials, era/verification visual logic, card vs badge distinction |
| [[BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM]] | Visual relationship between individual badge (hex cell) and collective Bitcoin sphere |
| [[PRODUCT_PRINCIPLES]] | 15 operational guardrails for cross-team decision making |
| [[WALLPAPER_SYSTEM]] | Wallpaper as first-class product subsystem — modes, motion, privacy, composition rules |
| [[LAUNCH_STRATEGY]] | Standalone launch positioning, message hierarchy, phasing, channel strategy |
| [[ICON_SYSTEM]] | App icon, product mark, and supporting glyph system rules |
| [[ASSET_PRODUCTION_CHECKLIST]] | Tier 1/2/3 launch asset requirements and readiness checklist |

---

## Canon Hierarchy

1. [[IDENTITY_MODEL]] is the foundational backbone — all other canon derives from it
2. [[PRODUCT_PRINCIPLES]] translates identity canon into cross-team operational rules
3. [[BADGE_VISUAL_SYSTEM]] and [[BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM]] are peer visual canons that must stay aligned
4. [[WALLPAPER_SYSTEM]] and [[ICON_SYSTEM]] are subsystem canons derived from badge canon
5. [[LAUNCH_STRATEGY]] and [[ASSET_PRODUCTION_CHECKLIST]] are execution-facing canon

---

## Key Canon Rules

- **Badge Identity = Era × Verification** — these two axes must never be collapsed
- The badge is the hero object; the card is the stage
- The hexagon is the atomic identity unit connecting badge to Bitcoin sphere
- Credibility must remain public when the badge is public
- No team gets to freestyle canon (Principle 15)

---

## Document Status

**Canonical system PRD (canon layer):**
- `02_canon/HODLNEER_PRD.md` — root document for the Hodlneer vertical. System boundaries, onboarding, badge lifecycle, HDL integration. All canon derives from this.

**Feature-level PRD (governance layer):**
- `01_governance/vision/HODLNEER_BADGE_PRD.md` — badge artifact definition: tiers, issuance, evolution, revocation. Scoped to the badge artifact, not the system.

---

## Related Sections

- [[HODLNEER_INDEX]] — full vertical index including COPY, EXPERIENCE, EXECUTION, INTEGRATION
- All COPY docs that translate canon into user-facing language
- [[EPICS]] — implementation lanes that execute against this canon
