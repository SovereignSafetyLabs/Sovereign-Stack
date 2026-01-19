# ARTIFACTS
**UNCLASSIFIED // TLP:WHITE**

## 0. Purpose

This document enumerates **all major repository artifacts** and assigns a
**Technology Readiness Level (TRL)** to each class to prevent over-claim,
scope confusion, or audit ambiguity.

This is an **inventory**, not a validation claim.

---

## 1. TRL Interpretation Rules (Repo-Specific)

| TRL | Meaning in this repository | Allowed claim |
|---:|---|---|
| **6** | **System Prototype** (Physical) | *Unused in this release.* (Requires hardware in loop) |
| **5** | **Component Validation** (Simulated) | “Logic validated in simulation; hardware interfaces modeled.” |
| **4** | Defined **methodology / process artifacts** | “Repeatable process; results context-dependent.” |
| **2–3** | Conceptual or analytical specifications | “Design / hypothesis; incomplete.” |
| **0–1** | Research theory, narrative, or archival material | “Unvalidated or historical.” |

**Non-Operational Rule:**
Nothing in this repository constitutes a deployed system, certification,
or enforceable governance control.

---

## 2. Repository Root & Governance Files

| Path | TRL | Type | Notes |
|---|---:|---|---|
| `README.md` | 4 | Scope boundary | Authoritative interpretation rules |
| `ARTIFACTS.md` | 4 | Inventory | This document |
| `LICENSE` | 4 | Legal | CC-BY 4.0 |
| `CITATION.cff` | 4 | Metadata | Citation only |
| `CONTRIBUTING.md` | 4 | Process | Contribution rules |
| `SECURITY.md` | 4 | Disclosure | Vulnerability handling |
| `VALIDATION_STATUS.md` | 4 | Status register | Explicit non-guarantee |

---

## 3. Reference Artifacts — **TRL 5**

> **Definition:** Inspectable logic and schemas validated in a simulated environment.
> **Constraint:** Reference logic only. Hardware interfaces are modeled, not physical.

### 3.1 Core Reference Data & Logic (`reference-implementation/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `reference-implementation/Quantum_Action_Catalog_v1.1.json` | 5 | JSON action registry | Canonical structured catalog |
| `reference-implementation/Quantum-Action-Catalog.md` | 5 | Human-readable mirror | Interprets JSON; not enforcement |
| `reference-implementation/Quantum-Classical-Control-Plane.md` | 5 | Control-plane reference | Interface + governance reference logic |
| `reference-implementation/Integrity-Stack-v2.2.md` | 5 | Integrity Stack reference | Reference logic artifact |
| `reference-implementation/README.md` | 4 | Boundary notice | Interpretation rules |

### 3.2 Patch-Level Reference Modules (`patches/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `patches/Blacksite-Mode-v1.1.md` | 5 | Mode delta | Reference containment semantics |
| `patches/CLF-v1.1.md` | 5 | CLF delta | Reference logic only |
| `patches/Integrity-Stack-v2.2.md` | 5 | Stack delta | Reference logic only |
| `patches/PGS-v1.1-Upgrade-Spec.md` | 2–3 | Upgrade spec | Reference patch specification |
| `patches/README.md` | 4 | Taxonomy guide | Patch usage and categories |
| `patches/Sovereign-Protocol-v3.1-Patch.md` | 5 | Protocol delta | Reference delta |
| `patches/Stress-Map-v1.1.md` | 5 | Stress model delta | Inspectable mapping |
| `patches/Vesta-Protocol-v1.1.md` | 5 | Protocol delta | Reference delta |

---

## 4. Methodology — **TRL 4**

> **Definition:** Repeatable governance, audit, and red-team processes.
> **Constraint:** Process ≠ effectiveness.

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/methodology/Appendix-M-Poly-Model-Methodology.md` | 4 | Method | Poly-model design methodology (non-empirical) |
| `docs/methodology/Latent-Paradigm-to-Kernel-Mapping.md` | 4 | Mapping note | Ontology-to-mechanism traceability (analytical) |
| `docs/methodology/README.md` | 4 | Scope | Interpretation rules |

---

## 5. Core Protocol & Stack Specifications — **TRL 2–3**

> **Rule:** Narrative or architectural specs without executable artifacts remain conceptual.

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `core/Blacksite-Mode-v1.0.md` | 2–3 | Spec | Conceptual |
| `core/CLF-v1.0.md` | 2–3 | Spec | Conceptual |
| `core/MACH-v1.0-Spec.md` | 2–3 | Spec | Conceptual |
| `core/PGS-v1.0-Overview.md` | 2–3 | Spec | Conceptual |
| `core/README.md` | 4 | Boundary notice | Interpretation rules |
| `core/Sovereign-Kernel-v0.1.md` | 2–3 | Spec | Conceptual |
| `core/Sovereign-Kernel-v0.1-Supplement.md` | 1–2 | Supplement | Context / lineage |
| `core/Sovereign-Kernel-Runtime-v0.2.md` | 2–3 | Spec | Conceptual runtime description |
| `core/Sovereign-Kernel-v0.3.md` | 2–3 | Spec | Conceptual |
| `core/Sovereign-Kernel-v0.4.md` | 2–3 | Spec | Conceptual |
| `core/Sovereign-Protocol-v3.0.md` | 2–3 | Spec | Conceptual |
| `core/Stress-Map-v1.0.md` | 2–3 | Model | Conceptual |
| `core/Vesta-Protocol-v1.0.md` | 2–3 | Spec | Conceptual |
| `core/Vesta-Protocol-v2.0.md` | 2–3 | Spec | Conceptual |

---

## 5.1 PGS Modular Documentation (`pgs-modules/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `pgs-modules/PGS Module 0 Sovereign Protocol.md` | 2–3 | Module spec | Sovereign Protocol v3.0 (modular format) |
| `pgs-modules/PGS Module 1 Integrity Stack.md` | 2–3 | Module spec | Integrity Stack v2.1 (modular format) |
| `pgs-modules/PGS Module 2 CLF Architecture.md` | 2–3 | Module spec | CLF Architecture v1.0 (modular format) |
| `pgs-modules/PGS Module 3 Vesta Protocol.md` | 2–3 | Module spec | Vesta Protocol v1.0 (modular format) |
| `pgs-modules/PGS Module 4 Stress Map.md` | 2–3 | Module spec | Stress Map v1.0 (modular format) |
| `pgs-modules/PGS Module 5 Degradation Suite.md` | 2–3 | Module spec | Degradation Suite v2.1 (modular format) |
| `pgs-modules/PGS Module 6 Multi-Turn Attack Framework.md` | 2–3 | Module spec | Multi-Turn Attack Framework v1.0 (modular format) |
| `pgs-modules/PGS Module 7 Blacksite Mode.md` | 2–3 | Module spec | Blacksite Mode v1.0 (modular format) |
| `pgs-modules/README.md` | 4 | Module guide | PGS modular documentation overview |

---

## 6. Analysis, Theory, Architecture, Threat Models — **TRL 0–2**

### 6.1 Analysis (`docs/analysis/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/analysis/governance-behavior/Telemetry-Informed-Hardening-Patterns.md` | 1–2 | Governance analysis | Research analysis (moved from patches) |
| `docs/analysis/LLM-Politeness-Mechanics-v1.0.md` | 1–2 | Analysis | Hypothesis |
| `docs/analysis/PGS-Module-Rationale.md` | 1–2 | Rationale | Supplemental analysis (moved from core) |
| `docs/analysis/README.md` | 4 | Scope guide | Analysis documentation overview |
| `docs/analysis/Tendril-Theory-and-MultiAgent-Coherence.md` | 1–2 | Theory | Unvalidated |

### 6.2 Architecture & Diagrams (`docs/architecture/`, `docs/diagrams/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/architecture/Jailbreak-Lifecycle-Diagram-v1.0.md` | 2 | Diagram | Reference logic (non-executable) |
| `docs/architecture/PGS-Architecture-Overview.md` | 2 | Architecture | PGS system overview (conceptual) |
| `docs/architecture/PGS-Layer-Relationships.md` | 2 | Architecture | Layer interaction mapping |
| `docs/architecture/README.md` | 4 | Architecture guide | System-level documentation overview |
| `docs/architecture/Runtime-Governance-Decision-Flow.md` | 2 | Diagram + notes | Reference logic (non-executable) |
| `docs/architecture/System-View-Heatmap-v1.0.md` | 2 | Diagram | Non-executable |
| `docs/architecture/Vesta-Governance-Framework-Architecture-v1.0.md` | 2 | Diagram | Canonical system overview (conceptual) |
| `docs/diagrams/Vesta-Governance-Framework-Data-Flow-Diagram.md` | 2 | Diagram | Flow view |

### 6.2.1 Specs Documentation (`docs/specs/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/specs/PGS_Layer_2.5_Vesta_Module.md` | 2–3 | Spec | PGS Layer 2.5 specification |
| `docs/specs/README.md` | 4 | Specs guide | Specification documentation overview |

### 6.2.2 Technical Documentation (`docs/technical/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/technical/README.md` | 4 | Technical guide | Technical documentation overview |

### 6.3 Theory (`docs/theory/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/theory/README.md` | 4 | Theory guide | Theoretical documentation overview |
| `docs/theory/The_Latent_Paradigm.md` | 1 | Doctrine | Research-only ontology |
| `docs/theory/Thermodynamic-Foundations.md` | 1–2 | Theory note | Non-validated; references archived PDF (moved from core) |

### 6.4 Threat Models (`docs/threat-models/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/threat-models/` | 2 | Threat narratives | Conceptual |
| `docs/threat-models/Jailbreak-Interception-Pipeline.md` | 2 | Threat model | Conceptual mapping |
| `docs/threat-models/Representation-Drift-Crosswalk.md` | 2 | Threat model | Conceptual mapping |
| `docs/threat-models/Self-Jailbreaking-Crosswalk.md` | 2 | Threat model | Conceptual mapping |

---

## 7. Evidence & Simulations — **TRL 3–4 (Context-Bound)**

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/evidence/` | 3–4 | Evidence | Case-specific |
| `docs/evidence/EVIDENCE-003_Thermodynamic_Quench_DeepSeek/` | 3–4 | Evidence set | Not generalizable |
| `docs/evidence/EVIDENCE-004_Emergent_Misalignment.md` | 3–4 | Evidence note | Context-bound |
| `docs/simulations/` | 3 | Simulations | Scenario-specific |
| `docs/simulations/SIM-001_Self_Jailbreak_Containment.md` | 3 | Simulation | Non-predictive |

---

## 7.1 Archive Publications (`archive/publications/`)

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `archive/publications/Sovereign_Stack_v2.4.3.pdf` | 5 | PDF reference | Original Sovereign Stack specification |
| `archive/publications/Thermodynamic_Foundations_of_Sovereign_Stack.pdf` | 5 | PDF reference | Thermodynamic foundations specification |

---

## 8. Summaries — **TRL 0–1**

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/summaries/README.md` | 4 | Summaries guide | Summary documentation overview |
| `docs/summaries/Sovereign-Stack-v2.4.3.md` | 1–2 | Stack summary | Legacy snapshot (moved from core) |
| `docs/summaries/Vesta-Governance-Framework-Narrative.md` | 1 | Narrative | High-level overview |
| `docs/summaries/Vesta-Governance-Framework-Quick-Reference.md` | 1 | Quick reference | One-page overview |

---

## 9. Federal & Compliance Crosswalks — **TRL 4**

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/market/` | 4 | Market / compliance | Interpretive, non-technical |
| `docs/market/Genesis_Mission_Compliance_Brief.md` | 4 | Mapping | Interpretive |
| `docs/market/Vesta_Governance_Framework_Federal_Crosswalk.md` | 4 | Crosswalk | Alignment only |
| `docs/market/Vesta-Governance-Framework-ZK-Governance-Pipeline.md` | 4 | Pipeline concept | Non-operational |

---

## 10. Maintenance Rules

1. **No silent TRL upgrades.**
2. **Specs do not become implementations by confidence.**
3. **Any new executable or machine-readable artifact must be added here.**
4. **If a file is archived or deprecated, its TRL freezes.**

---

## 11. Change Log

| Date | Change | Author |
|---|---|---|
| 2026-01-19 | TRL reassessment: downgraded all TRL 6 artifacts to TRL 5 as they rely on analytical models/simulated hardware rather than demonstrable physical hardware integration. (Added TRL 5 definition to Sec 1. Renamed INTEGRITY-STACK-v2.2.md → Integrity-Stack-v2.2.md). | Stephen S. Brouhard |
| 2026-01-19 | Major repository reorganization: moved patches/ to root level, created pgs-modules/ directory, redistributed core files, added archive/publications/ section, updated all paths. | Stephen S. Brouhard |
| 2026-01-19 | Corrected paths (reference-implementation/modules), removed stale business entries, reflected architecture rename, aligned theory/summaries/market locations. | Stephen S. Brouhard |
| 2026-01-15 | Initial full artifact inventory. | Stephen S. Brouhard |