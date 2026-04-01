# HDL Universe

HDL Universe is the long-term governance, canon, and orchestration repository for the broader HDL ecosystem.

This repository is no longer just a canon dump. It is the persistent knowledge layer that captures HDL's evolving truth across time so that strategy, planning, implementation, and organizational design stay aligned as the ecosystem grows.

At a practical level, this repo is intended to serve as the root of the Obsidian vault for HDL. The vault preserves the original canon work while expanding to support governance, personas, Paperclip organizational design, agent definitions, bridge documents, and structured feedback loops from downstream execution.

---

## Why this repository exists

HDL is not a single app or a single repo. It is an evolving ecosystem with multiple layers, including product, lore, architecture, wallet experience, social identity, community systems, governance, and adjacent structures that may influence or support the larger vision over time.

Because this work unfolds gradually across months and years, we need a durable system that:

* preserves historical context
* holds the canon and core truth
* captures evolving decisions and rationale
* supports zooming in and out between macro and micro concerns
* prevents drift across strategy, architecture, and execution
* provides continuity across humans, AI systems, and time

This repository exists to fill that role.

---

## Core purpose

This repo acts as the HDL ecosystem's:

* **Canon layer**
  The doctrine, world logic, shared definitions, and conceptual system behind HDL

* **Governance layer**
  The principles, constraints, decisions, and directional truth that keep the system aligned

* **Obsidian layer**
  The local-first second brain used to hold context, connect ideas, and support long-horizon thinking

* **Orchestration support layer**
  The place where high-level organizational concepts are defined before they are routed into Paperclip or implementation workflows

* **Bridge layer**
  The translation surface between vision and execution, including links into implementation repos, specs, and downstream work

---

## What this repo is not

This repo is **not** the main HDL product codebase.
It is **not** the runtime orchestration engine.
It is **not** the task execution layer.

Instead:

* product repos build things
* Paperclip orchestrates work and organizational execution
* agents and implementation systems operate in scoped lanes
* this repo keeps the truth, structure, and long-term coherence intact

---

## Relationship to Obsidian

This repository is intended to be opened directly as an Obsidian vault.

That means:

* notes are plain Markdown
* links between concepts are first-class
* structure can evolve over time
* historical context remains portable and version-controlled
* no proprietary lock-in is introduced at the content layer

Obsidian is used here as a support system for deep thinking, governance, alignment, and long-term continuity. It is not expected to replace execution systems. It exists to keep the larger direction coherent while other tools and agents operate within their own lanes.

---

## Relationship to Paperclip

Paperclip is the execution and orchestration layer.

Paperclip is where organizational structure, task routing, and operational follow-through will eventually become active and hands-on. This repo supports that future by defining:

* high-level company structure
* roles and responsibilities
* operating patterns
* decision frameworks
* agent boundaries
* execution expectations

In that sense, this repo helps define **what must be true** and **how the system should think**, while Paperclip helps determine **how work gets routed and carried out**.

---

## Relationship to Claude and other AI systems

AI systems are part of the workflow, but they do not own the long-term truth.

This repo exists in part because no single model session can reliably hold the full historical and strategic context of HDL over time. AI agents are strongest when operating within scoped lanes. This repository helps provide that grounding.

### Expected AI role in this ecosystem

AI systems such as Claude are expected to:

* read relevant portions of the vault
* operate within a defined vertical or task lane
* break scoped goals into epics, tasks, and subtasks
* implement or support implementation inside the correct repos
* report back blockers, results, and assumptions

AI systems are **not** expected to originate or continuously maintain the entire macro architecture of HDL in one live session. That responsibility belongs to this governance layer.

---

## Current and evolving scope

The repo currently contains major canon and system-definition work, especially around:

* HDL world and shared doctrine
* BTC world and rendering/system concepts
* shared entities, routing, proof, particles, portals, and related concepts
* bridge documents to HDL platform work
* system overview and naming evolution

The scope is now expanding to also include:

* governance and principles
* explicit decisions and rationale
* personas and user lenses
* capabilities and use cases
* Paperclip organization design
* executive and agent role definitions
* feedback summaries from downstream implementation

---

## Repository structure

The structure will continue to evolve, but the intended model is roughly:

```text
hdl-universe/
├── README.md
├── SYSTEM_OVERVIEW.md
├── .obsidian/
├── 00_inbox/
├── 01_governance/
│   ├── vision/
│   ├── principles/
│   ├── constraints/
│   ├── decisions/
│   └── terminology/
├── 02_canon/
│   ├── hdl_world/
│   ├── btc_world/
│   └── shared/
├── 03_personas/
├── 04_capabilities/
├── 05_use_cases/
├── 06_paperclip/
│   ├── org_structure/
│   ├── roles/
│   ├── workflows/
│   └── operating_model/
├── 07_agents/
│   ├── executive/
│   ├── domain/
│   └── patterns/
├── 08_bridges/
│   ├── hdl-platform/
│   └── other-project-bridges/
├── 09_feedback/
│   ├── implementation-results/
│   ├── blockers/
│   └── lessons/
└── archive/
```

This is a target direction, not a rigid final schema. The structure should remain flexible enough to evolve as the real needs of the system become clearer.

---

## Design principles for this repo

The repo should follow these principles:

### 1. Preserve continuity

Past thinking matters. Historical context should be preserved, not discarded, unless there is a clear reason to archive or replace it.

### 2. Keep canon and governance connected

Canon should not drift away from strategy, and strategy should not drift away from the world it is meant to serve.

### 3. Support macro and micro thinking

The system should make it easy to zoom out to the ecosystem level and zoom in to a single persona, capability, role, or decision.

### 4. Prefer clarity over premature perfection

The structure should improve over time, but should not become so rigid that it blocks discovery and evolution.

### 5. Make downstream execution easier

The goal is not to create documentation for its own sake. The goal is to reduce ambiguity so that Paperclip, Claude, and other execution systems can operate more effectively.

### 6. Keep the truth portable

Content should remain in Markdown and version-controlled so the knowledge layer remains durable and tool-agnostic over time.

---

## Version control and evolution

Because this repo is the knowledge and governance layer for a long-term ecosystem, version control is essential.

Git is used not just to track file changes, but to preserve the evolution of:

* ideas
* structure
* doctrine
* decisions
* organizational models
* system direction

We do not expect to get the structure perfectly right on day one. This repository is expected to evolve and harden over time.

---

## Security posture

This vault is intended to live locally and be opened with Obsidian as a local-first tool.

That said:

* avoid storing raw secrets in notes
* be deliberate about plugin usage
* treat external AI integrations carefully
* use Git intentionally and review changes before committing

The aim is to preserve portability and long-term trust without introducing unnecessary operational risk.

---

## Near-term focus

The immediate next phase for this repo is to:

* preserve and reorganize the existing canon content
* establish the initial governance structure
* introduce personas as a first-class entry point
* begin defining the Paperclip organizational layer
* create clearer bridge surfaces into implementation repos
* formalize how downstream execution reports back into this vault

---

## Summary

HDL Universe is the long-term second brain for the HDL ecosystem.

It preserves the canon, anchors governance, supports Obsidian-based knowledge work, and provides the structure needed so strategy, organization, and downstream execution can stay aligned over time.

It is not the product itself.
It is not the final execution layer.
It is the continuity layer that helps everything else stay coherent.
