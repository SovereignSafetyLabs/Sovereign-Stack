# Architecture Documentation

## Scope

This directory contains **system-level architecture documentation** for the **Vesta Governance Framework** and its integrated suite, the **Platinum Governance Suite (PGS)**.

These documents describe:
- structural relationships between governance layers
- control-flow and decision-flow logic
- telemetry and constraint propagation
- module boundaries and interaction surfaces

They are intended to communicate **how the system is organized**, not how it is implemented or deployed.

---

## What These Documents Are

- **Architectural views** of the governance system
- **Relationship diagrams** between layers and modules
- **Reference logic flows** illustrating decision pathways
- **Analytical models** for reasoning about safety posture

They answer questions like:
- *Which layer governs what?*
- *How does telemetry flow upward?*
- *Where do containment decisions occur?*
- *How do PGS modules interlock?*

---

## What These Documents Are Not

This directory does **not** contain:

- source code
- implementation guides
- runtime configuration
- performance metrics
- operational guarantees
- claims of deployment readiness

All diagrams and flows are **conceptual reference representations**.

---

## Relationship to Other Directories

- **`/core/`**
  Canonical specifications and versioned primitives
  (e.g., Sovereign Protocol, Kernel, CLF, Vesta)

- **`/pgs-modules/`**
  Modular documentation describing the Platinum Governance Suite as a composable system

- **`/theory/`**
  Foundational models and theoretical justification

- **`/reference-implementation/`**
  Illustrative schemas, control-plane concepts, and inspectable logic

Architecture documents may reference concepts from these directories but do not supersede them.

---

## Document Index

Common document types found here include:

- **Framework Architecture Diagrams**
  High-level layered views of governance structure

- **Layer Relationship Maps**
  How Sovereign Protocol, PGS layers, Kernel, and operational modules interact

- **Decision & Control-Flow Diagrams**
  Reference logic for governance decisions and containment pathways

- **System Views & Heatmaps**
  Analytical perspectives on pressure, risk, and escalation behavior

Each document is scoped to a specific architectural question and should be read accordingly.

---

## Status & Posture

All architecture documents are provided as:

- **Research and reference material**
- **Non-operational**
- **Non-normative**
- **Non-assertive of safety guarantees**

They describe *intended structure and reasoning*, not verified system behavior.

---

## Authority

For authoritative specifications and versioned definitions, refer to:

- Repository root `README.md`
- `ARTIFACTS.md`
- `VALIDATION_STATUS.md`
- Canonical documents in `/core/`

---

**END OF DOCUMENT**
