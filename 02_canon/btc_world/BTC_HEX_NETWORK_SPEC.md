# BTC World — Hex Network Specification (Consolidated)

This document unifies the narrative and technical specifications for the BTC Hex Network in the HDL universe.

It replaces:
- BTC_HEX_NETWORK_CANON.md
- BTC_HEX_NETWORK_CANON_FULL_SPEC.md

This is now the single source of truth.

---

## Purpose

The BTC Hex Network is the canonical visualization of Bitcoin participation.

It bridges:
- Bitcoin protocol data
- Visual representation
- Interaction systems
- Rendering architecture

It is NOT a literal blockchain.

It is a symbolic dome of participation.

Each hex = a wallet node (or clustered identity)

---

## Core Principle

Hex = Participation  
Not supply  
Not balance  

---

## Data Model

type HexData = {
  id: string
  activityScore: number
  txCount: number
  lastActive: timestamp
  valueFlow: number
  clusterSize: number
}

---

## Rendering Requirements

- InstancedMesh (mandatory)
- GPU-driven rendering
- LOD system
- Shader-based visuals

---

## Particle Systems

1. Transaction Flow
2. Mempool Turbulence
3. Block Formation
4. Energy Halos
5. Ambient Field

All must be data-driven.

---

## Performance Rules

MUST:
- GPU particles
- instancing
- 60 FPS

MUST NOT:
- CPU particle loops
- unbounded emitters

---

## Final Canonical Statement

The BTC Hex Network reveals Bitcoin as a living system.

It does NOT simulate Bitcoin.

It reveals it.
