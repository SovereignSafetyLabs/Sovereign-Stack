# TECHNICAL REFERENCE INDEX
# CLASSIFICATION: UNCLASSIFIED // TLP:WHITE
# SYSTEM: VESTA GOVERNANCE FRAMEWORK

> **⚠️ NOTICE: REFACTOR IN PROGRESS**
> The system is migrating from "Sovereign Stack" to "Vesta Governance Framework."
> While filenames have been updated, internal content references may still be undergoing alignment.

## 1. SCOPE & PURPOSE
This directory indexes the technical specifications, architectural diagrams, and engineering constraints of the Vesta Governance Framework.

**WARNING:** This index distinguishes between **Reference Artifacts (TRL 5)** and **Design Specifications (TRL 2-3)**. Auditors must verify the TRL status of each referenced component in `VALIDATION_STATUS.md`.

## 2. ARCHITECTURAL BASELINE
Primary engineering documents defining the system boundaries and logic flow.

| Component | File Path | Status |
| :--- | :--- | :--- |
| **System Architecture** | [`../architecture/Vesta-Governance-Framework-Architecture-v1.0.md`](../architecture/Vesta-Governance-Framework-Architecture-v1.0.md) | **Design Spec** |
| **Data Flow** | [`../diagrams/Vesta-Governance-Framework-Data-Flow-Diagram.md`](../diagrams/Vesta-Governance-Framework-Data-Flow-Diagram.md) | **Logic Model** |
| **Heatmap Analysis** | [`../architecture/System-View-Heatmap-v1.0.md`](../architecture/System-View-Heatmap-v1.0.md) | **Analytical** |

## 3. THREAT MODELING & CONTAINMENT
Technical analysis of adversarial vectors and containment logic.

| Vector | File Path | Description |
| :--- | :--- | :--- |
| **Representation Drift** | [`../threat-models/Representation-Drift-Crosswalk.md`](../threat-models/Representation-Drift-Crosswalk.md) | Fine-tuning induced misalignment (*Nature*, 2026). |
| **Self-Jailbreaking** | [`../threat-models/Self-Jailbreaking-Crosswalk.md`](../threat-models/Self-Jailbreaking-Crosswalk.md) | Recursive failure modes (Reasoning Models). |
| **Interception** | [`../threat-models/Jailbreak-Interception-Pipeline.md`](../threat-models/Jailbreak-Interception-Pipeline.md) | Detection logic flow. |
| **Lifecycle** | [`../architecture/Jailbreak-Lifecycle-Diagram-v1.0.md`](../architecture/Jailbreak-Lifecycle-Diagram-v1.0.md) | Attack path visualization. |

## 4. INTEGRATION & SIMULATION
Evidence of testing and external integration standards.

- **Simulations:** See [`../simulations/`](../simulations/) for synthetic stress test records (SIM-001).
- **Federal Crosswalk:** See [`../../business/Vesta_Governance_Framework_Federal_Crosswalk.md`](../../business/Vesta_Governance_Framework_Federal_Crosswalk.md) for NIST 800-53 mapping.

## 5. REFERENCE IMPLEMENTATION (TRL 5)
For executable reference code and configuration schemas, refer strictly to the Implementation directory.

- **Action Catalog (JSON):** [`../../reference-implementation/Quantum_Action_Catalog_v1.1.json`](../../reference-implementation/Quantum_Action_Catalog_v1.1.json)
- **Control Plane API:** [`../../reference-implementation/Quantum-Classical-Control-Plane.md`](../../reference-implementation/Quantum-Classical-Control-Plane.md)

---
*End of Technical Index*