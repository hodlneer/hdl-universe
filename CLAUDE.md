# HDL Universe — Agent Context

## Purpose
This is the **architecture and doctrine repository**. It defines canonical truth for the HDL system.
It is NOT product code. Do not add runnable code here.

## Structure
```
02_canon/              - Source of truth (rules, entities, world topology)
  hdl_world/           - HDL platform canon
  btc_world/           - Bitcoin world canon
  shared/              - Shared rules (wallet model, routing, rendering)
08_bridges/            - Translation from canon to implementation
  hdl-platform/        - Frontend + backend integration plans
01_governance/         - Principles, decisions, constraints, terminology
06_paperclip/          - Org structure, roles, workflows, operating model
07_agents/             - Agent definitions (executive, domain, patterns)
09_feedback/           - Execution feedback, blockers, lessons
```

## Canon Hierarchy
1. `02_canon/` — defines how the system MUST behave (never modified for product convenience)
2. `08_bridges/` — translates canon into product requirements (not code, not canon)
3. `01_governance/` — principles, decisions, and directional constraints
4. Product repos (`hdl_react/`, `hdl-node-backend-api/`) — execute the system

## Core Invariants
- **Handle = Identity**: `@handle` is the user-facing identifier everywhere
- **Wallet = Ownership**: wallets are abstracted behind handles
- **Proof = Status**: badges represent history and verified identity
- **HDL is NOT a financial institution**: no custody, no liquidity, no market making

## Phase 1.5 (Fiat Rails)
HDL routes fiat via partners (Stripe). See `02_canon/HDL_PHASE_1_5_CANON.md`.
Required before Phase 1.5 can go live:
- [ ] LLC / EIN
- [ ] Business bank account
- [ ] Stripe account

## When Modifying Canon
1. Update the relevant canon file
2. Update `02_canon/CANON_INDEX.md`
3. Update any bridge documents that reference the changed canon
4. Never change canon to match product limitations — product must adapt

## Key Canon Files
- `02_canon/shared/WALLET_MODEL.md` — wallet and routing doctrine
- `02_canon/hdl_world/ROUTING_ENGINE.md` — handle-based routing
- `02_canon/hdl_world/IDENTITY_ANCHOR.md` — identity doctrine
- `02_canon/hdl_world/PROOF_ENGINE.md` — badge and proof system
- `08_bridges/hdl-platform/HDL_PRODUCT_ALIGNMENT_GAPS.md` — current gap list
