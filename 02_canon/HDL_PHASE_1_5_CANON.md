# HDL Phase 1.5 Canon — Fiat Rails & Treasury Integration

## PURPOSE

This document formalizes HDL Phase 1.5 and integrates it into the existing canonical system.

It defines:
- HDL's relationship to fiat (USD) systems
- Stripe integration strategy
- Business treasury requirements
- Developer implementation expectations (Claude / Codex)
- Required updates to existing canonical documents

This document MUST be treated as a first-class canonical dependency — not a standalone addition.

---

## CORE PRINCIPLE (REINFORCED)

HDL is NOT a financial institution.

HDL is:
→ Identity Layer  
→ Social Layer  
→ Routing Layer  

Phase 1.5 adds:

→ Fiat On-Ramp EXPERIENCE (via partners)

WITHOUT:

- custody of funds
- internal liquidity
- market making
- financial execution ownership

---

## SYSTEM EXTENSION (UPDATED MODEL)

Existing model (from WALLET_MODEL.md):

User → Handle → Wallet Graph → Blockchain

Phase 1.5 extends this to:

User → HDL → Wallet → Fiat Rail (Stripe) → Blockchain

---

## NEW LAYER: HDL TREASURY (FIAT)

HDL operates as a company and requires fiat infrastructure.

### Definition

HDL Treasury is:
- Business bank account
- Stripe account
- Payment collection layer

### Responsibilities

- Receive subscriptions
- Receive donations
- Receive merch payments
- Handle operational funds

### Non-Responsibilities

- Holding user crypto funds
- Acting as a wallet
- Acting as an exchange

---

## REQUIRED INFRASTRUCTURE (BLOCKERS)

### 1. BUSINESS ENTITY

- LLC / S-Corp / Corp
- EIN

Status: REQUIRED

---

### 2. BUSINESS BANK ACCOUNT

Examples:
- Mercury
- Chase

Status: REQUIRED

---

### 3. STRIPE ACCOUNT

Used for:
- subscriptions
- one-time payments
- donations
- future crypto on-ramps

Status: REQUIRED

---

## STRIPE INTEGRATION MODEL

Stripe is used as:

→ Fiat processing layer  
→ Optional crypto on-ramp provider  

HDL NEVER:

- touches funds directly
- stores card data
- executes financial settlement logic

---

## CLAUDE / CODEX IMPLEMENTATION DIRECTIVES

Until Stripe is configured:

### ENV PLACEHOLDERS

STRIPE_API_KEY=__PLACEHOLDER__  
STRIPE_WEBHOOK_SECRET=__PLACEHOLDER__  

---

### REQUIRED BEHAVIOR

Claude MUST:

1. Stub payment services
2. Mock successful responses
3. Create TODO blocks for:
   - Stripe account setup
   - API key insertion
   - webhook configuration

---

### PROHIBITED BEHAVIOR

Claude must NEVER:

- block implementation due to missing Stripe
- hardcode secrets
- simulate custody of funds

---

## UX REQUIREMENTS

### FEATURE: “ADD FUNDS”

User flow:

1. User connects wallet
2. User clicks “Add Funds”
3. Stripe handles payment
4. Crypto arrives in wallet

---

### FEATURE: “SUPPORT HDL”

- donations via Stripe
- no crypto dependency required

---

### FEATURE: SUBSCRIPTIONS

- HDL Pro / Premium tiers
- handled entirely by Stripe

---

## RELATIONSHIP TO EXISTING CANON

### WALLET_MODEL.md

ADD:

- Fiat exists OUTSIDE wallet model
- HDL does not custody funds
- Stripe is external rail

---

### ROUTING_ENGINE.md

ADD:

- Routing Engine NEVER touches fiat
- Fiat must be converted BEFORE routing layer

---

### IDENTITY MODEL

NO CHANGE

Identity remains:
User → Handle → Wallet → Network

---

## NEW CANON FILE PLACEMENT

This file MUST be placed at:

canon/shared/FIAT_RAILS_AND_TREASURY.md

---

## REQUIRED CANON INDEX UPDATE

Update:

canon/CANON_INDEX.md

Add:

- FIAT_RAILS_AND_TREASURY.md

Under:
→ Shared Architecture

---

## REQUIRED CROSS REFERENCES

Add references FROM:

- WALLET_MODEL.md
- ROUTING_ENGINE.md

Pointing TO:

FIAT_RAILS_AND_TREASURY.md

---

## IMPLEMENTATION STATUS MODEL

Add environment awareness:

LEVEL 0 → No bank / no Stripe  
LEVEL 1 → Stripe test mode  
LEVEL 2 → Live payments  

Claude should adapt behavior based on level.

---

## FINAL POSITIONING

HDL =

“The easiest place to start your crypto journey.”

Supported by:

- identity
- social
- routing
- fiat rails (externally powered)

---

END OF DOCUMENT
