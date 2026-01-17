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
| **6** | Inspectable **reference artifacts** (schemas, registries, Python logic) | “Reference implementation exists; not production.” |
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

## 3. Reference Artifacts — **TRL 6**

> **Definition:** Inspectable, machine-readable artifacts intended for
analysis, tooling, and reproducibility.
> **Constraint:** Reference-only. No production assurances.

### 3.1 Core Reference Data & Logic

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `implementation/Quantum_Action_Catalog_v1.1.json` | 6 | JSON action registry | Canonical structured catalog |
| `implementation/Quantum-Action-Catalog.md` | 6 | Human-readable mirror | Interprets JSON, not enforcement |
| `implementation/Quantum-Classical-Control-Plane.md` | 6 | Control-plane reference | Logical interface description |
| `implementation/INTEGRITY-STACK-v2.2.md` | 6 | Integrity Stack reference | Tied to probe logic |
| `implementation/Integrity-Stack-v2.2.md` | 6 | Same as above | Canonical reference |
| `implementation/README.md` | 4 | Boundary notice | Interpretation rules |

### 3.2 Patch-Level Reference Modules

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `implementation/modules/patches-v1.1/Blacksite-Mode-v1.1.md` | 6 | Mode logic | Reference containment semantics |
| `implementation/modules/patches-v1.1/CLF-v1.1.md` | 6 | CLF logic | Reference logic only |
| `implementation/modules/patches-v1.1/Stress-Map-v1.1.md` | 6 | Stress model | Inspectable mapping |
| `implementation/modules/patches-v1.1/Vesta-Protocol-v1.1.md` | 6 | Protocol patch | Reference delta |

---

## 4. Methodology & Consulting Assets — **TRL 4**

> **Definition:** Repeatable governance, audit, and red-team processes.
> **Constraint:** Process ≠ effectiveness.

### 4.1 Consulting Suite

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `consulting/` | 4 | Engagement assets | Commercial workflow |
| `Consulting-Suite-Index.md` | 4 | Index | Navigation only |
| `business/` | 4 | Commercial context | Non-technical |
| `market/` | 4 | Market analysis | Non-technical |

### 4.2 Methodology

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `Methodology-Appendix.md` | 4 | Methodology | Process definition |
| `docs/methodology/Appendix-M-Poly-Model-Methodology.md` | 4 | Poly-model method | Explicitly non-empirical |
| `docs/methodology/Latent-Paradigm-to-Kernel-Mapping.md` | 4 | Mapping method | Analytical only |
| `docs/methodology/README.md` | 4 | Scope | Interpretation rules |

---

## 5. Core Protocol & Stack Specifications — **TRL 2–3**

> **Rule:** Narrative or architectural specs without executable artifacts
remain conceptual.

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `core/Blacksite-Mode-v1.0.md` | 2–3 | Spec | Conceptual |
| `core/CLF-v1.0.md` | 2–3 | Spec | Conceptual |
| `core/MACH-v1.0-Spec.md` | 2–3 | Spec | Conceptual |
| `core/PGS-v1.0-Overview.md` | 2–3 | Spec | Conceptual |
| `core/PGS-v1.1-Upgrade-Spec.md` | 2–3 | Spec | Conceptual |
| `core/Sovereign-Kernel-v0.1.md` | 2–3 | Spec | No runtime |
| `core/Sovereign-Kernel-v0.2.md` | 2–3 | Spec | No runtime |
| `core/Sovereign-Kernel-v0.3.md` | 2–3 | Spec | No runtime |
| `core/Sovereign-Kernel-v0.4.md` | 2–3 | Spec | No runtime |
| `core/Sovereign-Protocol-v3.0.md` | 2–3 | Spec | Conceptual |
| `core/Sovereign-Protocol-v3.1-Patch.md` | 2–3 | Patch spec | Conceptual |
| `core/Sovereign-Stack-v2.4.3.md` | 2–3 | Stack spec | Snapshot |
| `core/Stress-Map-v1.0.md` | 2–3 | Model | Conceptual |
| `core/Thermodynamic-Foundations.md` | 1–2 | Theory | Non-validated |
| `core/Vesta-Protocol-v1.0.md` | 2–3 | Spec | Conceptual |
| `core/Vesta-Protocol-v2.0.md` | 2–3 | Spec | Conceptual |

---

## 6. Analysis, Theory, and Architecture — **TRL 0–2**

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/analysis/` | 1–2 | Analysis | Exploratory |
| `docs/analysis/LLM-Politeness-Mechanics-v1.0.md` | 1–2 | Analysis | Hypothesis |
| `docs/analysis/Tendril-Theory-and-MultiAgent-Coherence.md` | 1–2 | Theory | Unvalidated |
| `docs/analysis/thermodynamic_alignment_theory.md` | 1–2 | Theory | Unvalidated |
| `docs/architecture/` | 2 | Diagrams | Conceptual |
| `docs/architecture/Jailbreak-Lifecycle-Diagram-v1.0.md` | 2 | Diagram | Non-executable |
| `docs/architecture/System-View-Heatmap-v1.0.md` | 2 | Diagram | Non-executable |
| `docs/diagrams/Vesta-Governance-Framework-Data-Flow-Diagram.md` | 2 | Diagram | Flow view |

---

## 7. Evidence & Simulations — **TRL 3–4 (Context-Bound)**

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `docs/evidence/` | 3–4 | Evidence | Case-specific |
| `docs/evidence/EVIDENCE-003_Thermodynamic_Quench_DeepSeek/` | 3–4 | Evidence set | Not generalizable |
| `docs/simulations/` | 3 | Simulations | Scenario-specific |
| `docs/simulations/SIM-001_Self_Jailbreak_Containment.md` | 3 | Simulation | Non-predictive |

---

## 8. Publications, Summaries, Archives — **TRL 0–1**

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `publications/` | 1 | Publication drafts | Narrative |
| `summaries/` | 1 | Summaries | Non-technical |
| `docs/theory/` | 1 | Theory | Research only |
| `docs/threat-models/` | 2 | Threat narratives | Conceptual |
| `archive/` | 0–1 | Historical | Frozen |
| `graveyard/` | 0 | Deprecated | Do not cite |
| `salvage/` | 0–1 | Recovered ideas | Non-authoritative |

---

## 9. Federal & Compliance Crosswalks — **TRL 4**

| Path | TRL | Artifact | Notes |
|---|---:|---|---|
| `Genesis_Mission_Compliance_Brief.md` | 4 | Mapping | Interpretive |
| `Vesta_Governance_Framework_Federal_Crosswalk.md` | 4 | Crosswalk | Alignment only |
| `Vesta-Governance-Framework-ZK-Governance-Pipeline.md` | 4 | Pipeline concept | Non-operational |

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
| 2026-01-15 | Initial full artifact inventory | Stephen S. Brouhard |
