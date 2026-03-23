# HDL Platform Bridge

## Purpose

This folder connects the HDL canon (truth defined in `canon/`) with the product implementation. It contains translation and integration documents that explain how canonical principles map onto the actual front-end and back-end systems.

## Structure

This directory contains the following documents:

- `HDL_FRONTEND_INTEGRATION_PLAN.md` - maps UI/UX requirements to canonical identity, wallet, proof and feed principles.
- `HDL_BACKEND_INTEGRATION_PLAN.md` - defines API and data-model changes needed to align the back-end with handle-based identity, wallet abstraction, routing and proof systems.
- `HDL_NODE_BACKEND_API_CATALOG.md` - snapshot of the current backend API surface and modules. Serves as a reference point for integration planning.
- `HDL_PRODUCT_ALIGNMENT_GAPS.md` - identifies gaps between the current product and the HDL canon, with priority ordering for remediation.

You can add additional documents here as new systems are defined (e.g. handle spec, proof engine spec, routing engine spec).

## Philosophy

The canon defines truth. This folder defines how truth becomes product.

It is not code or doctrine; it is a bridge. By separating these documents from the implementation repositories, we keep the canon pure and provide a clear map for product teams.

## Rules

- Do not put canonical doctrine here. Canon lives in `canon/`.
- Do not put raw code here. Code lives in the product repositories (`hdl`, `hdl-node-backend-api`).
- This folder is strictly for translation and integration guidance.

## Outcome

Maintaining this bridge ensures that:

- The product stays aligned with the evolving HDL canon.
- The canon remains pure and unpolluted by implementation details.
- Teams have a single source of truth for how to translate doctrine into code.

Use this folder to document any future integration plans, gap analyses or mapping documents between canon and product.
