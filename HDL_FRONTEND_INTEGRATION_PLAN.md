# HDL Frontend Integration Plan (React / Next.js)

## Purpose

This document defines how the HDL frontend (`hdl_react`) integrates with the HDL backend and evolves into a handle-first, wallet-native, proof-driven platform.

HDL.fun is the platform.  
Hodlneer is a badge identity (crypto pioneer), not the product.

## Core Frontend Principles

- Handle = Identity (`hdl.fun/username`)
- Wallet = Infrastructure (not UX friction)
- Proof = Status Layer (badges = social credibility)
- Feed = Entry Point (everything flows through it)

## 1. Handle-Based Identity

### Requirements

- Every user must have a unique handle
- Handles are:
  - human-readable
  - URL-based identity (`hdl.fun/username`)
  - wallet routing alias

### UI Components

- Handle Input (onboarding)
- Handle Availability Check (live)
- Handle Display (profile, posts, chat)

### API Integration

- `POST /users/check-username`
- `GET /wallets/:handle`

## 2. Wallet Layer (Thirdweb)

### Philosophy

Wallets should feel invisible but powerful.

Default:

- embedded wallet (HDL-managed)

Optional:

- external wallet (MetaMask, Phantom)

### UI Components

- Wallet Connect Modal
- Wallet Status Badge
- Send/Receive Modal

### API Integration

- `POST /auth/verify-wallet`
- `GET /wallets/:handle`
- `POST /wallets/send`

## 3. Proof / Badge System (Hodlneer Layer)

This is where Hodlneer lives now.

### Badge Types

- Claimed Identity
- Social Proof
- On-Chain Proof
- OG / Pioneer (Hodlneer)

### UI Components

- Badge Stack (Profile)
- Hover Tooltips (explain meaning)
- Feed Badge Indicators
- Proof Progress UI

### API Integration

- `GET /proof-badges`
- `GET /users/:handle/proofs`
- `POST /users/:handle/proofs`

## 4. Feed as Central Hub

The feed is Grand Central Station.

### Responsibilities

- content discovery
- identity reinforcement
- proof visibility
- interaction triggers

### UI Features

- Post cards
- Embedded badges
- Wallet actions (send tip, etc.)
- Reactions / comments

## 5. Messaging & Identity

### Requirements

- handle-based messaging
- wallet-aware interactions
- future: send assets inside chat

### UI Components

- Chat list
- Conversation view
- Inline send (future)

## 6. Routing System

### Canonical URLs

- `hdl.fun/username` -> wallet identity
- `/u/username` -> profile
- `/feed` -> main experience

### Rules

- Always resolve via handle
- Never expose raw wallet addresses to user

## 7. Migration Handling (Critical)

We are transitioning from Hodlneer to HDL.

### Rules

- Hodlneer = badge only
- HDL.fun = platform
- legacy references must fade out

### UX Strategy

- silent migration
- optional prompt: "claim your HDL handle"
- no confusion messaging

## 8. Future Layers

### Near-Term

- tipping via handle
- NFT display
- richer proof levels

### Mid-Term

- 3D identity cards
- world navigation (Three.js)
- presence-based UI

### Long-Term

- full HDL world engine integration
- VR / AR support
- identity as spatial experience

## Final Principle

If something needs:

- identity -> HANDLE
- ownership -> WALLET
- status -> PROOF
- interaction -> FEED

That's the system.

HDL is not a social app.

It's an identity layer disguised as one.
