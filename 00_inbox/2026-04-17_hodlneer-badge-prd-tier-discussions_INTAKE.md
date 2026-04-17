# Intake — 2026-04-17 — Hodlneer Badge PRD and Tier Discussions

**Session Type:** Brain dump / decision session / strategy session

---

## Key Decisions Made

1. **Dual-tier naming model:** The Hodlneer badge uses two descriptive layers — a canonical meaning tier (e.g. Genesis, Pioneer, Verified) and a visual material tier (Bronze, Silver, Gold, Platinum). This separates conceptual meaning from visual prestige, letting the product keep narrative depth while also expressing status subtly through design.
2. **Badge-first philosophy:** The badge itself is the primary artefact. The tier is visually present but secondary. Users will say "I got a HODLNEER badge," not "I'm Tier X." The tier denotes prestige without dominating the narrative.
3. **All users are eligible:** Any user who opts into the Hodlneer layer can get a badge. Creating an HDL account alone does not confer a badge; going through Hodlneer onboarding does.
4. **Multiple tiers at launch:** The badge will launch with multiple tiers (Bronze/Silver/Gold/Platinum), mapped internally to canonical meanings (e.g. Genesis, Pioneer, Verified). Verification may require more proof for higher tiers. Future changes may refine naming and validation logic.
5. **Top recognition tier is not requested:** The highest tier (Platinum/Origin) is reserved for individuals with publicly recognised, verifiable impact on the crypto ecosystem. It isn't applied for; it's assigned by admin recognition. Identity must be verified; addition is at admin discretion or through curated lists (e.g. CoinDesk's Most Influential). Users can flag themselves for review, but qualification isn't guaranteed.
6. **Badge evolution and revocation:** A badge is permanent unless later evidence invalidates eligibility. Tiers can be upgraded when a user provides stronger proof (e.g. providing evidence of older wallet holdings). Admins have the right to revoke badges that were awarded on false premises or are compromised.
7. **Launch behaviour:** At launch, the badge serves as a social proof signal. It does not rank users or carry financial or gating features. Future enhancements may add privileges (early feature access, webinars, community privileges, potential token involvement), but these are directional, not required at launch.
8. **Visibility and sharing:** Badges are visible on user profiles by default and can be shared externally or within HDL to generate network effects. Users choose when and where to share. The system should provide a share mechanism that allows external social posting and HDL-native celebration.
9. **Application path for recognition tier:** Users who believe they qualify for the highest recognition tier can indicate this during onboarding or later. They will supply proof; admins review manually. Verification may involve interviews or deep proof checks for whales and institutions.
10. **Intake file pipeline:** Use an intake file in `/00_inbox/` to summarise sessions and communicate context to Claude. The file should contain decisions, directions, context Claude needs, open questions, vault docs to update, and next steps. Claude reads and processes this on the next session to update the vault.

---

## Directions Established

- Preserve the badge as the core identity artifact. The system should emphasise the badge and allow tiers to express prestige visually without dominating user messaging.
- Begin implementing the HODLNEER_BADGE_PRD.md in the vault under `01_governance/vision/` (already generated). This PRD will serve as the reference for product decisions.
- When developing the onboarding flow, include a step for users to choose whether to pursue a Hodlneer badge and allow them to indicate if they believe they qualify for higher recognition.
- Maintain an admin-controlled whitelist seeded with known figures (e.g. CoinDesk's Most Influential lists) for auto-assignment of top-tier badges. Allow manual curation for new influential entrants.
- Provide a share component for the badge with clear share targets (social media, HDL surfaces) and emphasise celebration and proof.
- Future work should define the tier names and internal meaning map (e.g. Pioneer, Veteran, Sovereign) and refine automatic vs. manual validation rules for each tier.

---

## Context Claude Needs

- The new PRD file `HODLNEER_BADGE_PRD.md` has been generated (see `01_governance/vision/HODLNEER_BADGE_PRD.md` in the vault). Claude should read and integrate this into the governance layer.
- A dual-tier model, recognition-first top tier, and share mechanics are now part of the product definition.
- The user emphasised that the badge is about honouring pioneers, not celebrity worship. Tiers should reflect meaningful contributions and credibility, not purely wealth or fame.
- The intake notes capture decisions and directions. Claude should process this file on the next session and update relevant governance docs (e.g. tier definitions, validation criteria, share mechanics).

---

## Open Questions (Unresolved)

- What should the canonical tier names be? Examples discussed include Genesis, Pioneer, Verified, Legacy, Sovereign, Apex, Origin. Final naming to be determined.
- What are the precise validation rules for each tier at launch? (e.g. required number of years of holding, wallet age, exchange account verification, etc.)
- How will whales/institutions provide proof while protecting privacy? (e.g. verified by admin via video call or alternative process?)
- Should badge holders be allowed to hide the badge on their profile? What are the default visibility settings? When, if ever, should badges auto-appear in feed or comments?
- Will there be badge-specific privileges at launch (beyond visibility)? If so, what minimal privileges are feasible?

---

## Vault Docs to Update or Create

- `01_governance/vision/HODLNEER_BADGE_PRD.md` — integrate changes and confirm the PRD reflects decisions made in this session
- Create a draft doc defining tier names and mapping with canonical names and visual materials
- Update `06_paperclip/` to include the admin process for recognition tier approval
- Create or update the share behaviour spec
- Capture unresolved questions in an open issues log (`09_feedback/open-questions.md`)

---

## Next Steps

- Claude to process this intake, updating the governance docs, tier naming, and share mechanics
- User to review and refine tier names and validation criteria
- Design team to create initial badge visuals for each material tier (Bronze, Silver, Gold, Platinum) and map them to canonical tiers
- Developers to begin implementing Hodlneer onboarding flow and share mechanics as defined
- Admin to curate initial recognition tier whitelist based on CoinDesk and known influential figures
- Future: evaluate API options or manual processes for writing files from ChatGPT sessions directly into the repository

---

*Intake generated by OD (ChatGPT). Processed by Claude on 2026-04-17.*
