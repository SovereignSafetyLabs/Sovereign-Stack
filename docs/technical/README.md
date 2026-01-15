# TECHNICAL REFERENCE INDEX
# CLASSIFICATION: UNCLASSIFIED // TLP:WHITE
# AUDIT CONTEXT: SYSTEM ARCHITECTURE & INTEGRATION

## 1. SCOPE & PURPOSE
This directory indexes the technical specifications, architectural diagrams, and engineering constraints of the Vesta Governance Framework. 

**WARNING:** This index distinguishes between **Runtime Artifacts (TRL 6)** and **Design Specifications (TRL 2-3)**. Auditors must verify the TRL status of each referenced component in `VALIDATION_STATUS.md`.

## 2. ARCHITECTURAL BASELINE
Primary engineering documents defining the system boundaries and logic flow.

| Component | File Path | Status |
| :--- | :--- | :--- |
| **System Architecture** | [`../architecture/Sovereign-Stack-Architecture-v1.0.md`](../architecture/Sovereign-Stack-Architecture-v1.0.md) | **Design Spec** |
| **Data Flow** | [`../diagrams/Sovereign-Stack-Data-Flow-Diagram.md`](../diagrams/Sovereign-Stack-Data-Flow-Diagram.md) | **Logic Model** |
| **Heatmap Analysis** | [`../architecture/System-View-Heatmap-v1.0.md`](../architecture/System-View-Heatmap-v1.0.md) | **Analytical** |

## 3. THREAT MODELING & CONTAINMENT
Technical analysis of adversarial vectors and containment logic.

| Vector | File Path | Description |
| :--- | :--- | :--- |
| **Self-Jailbreaking** | [`../threat-models/Self-Jailbreaking-Crosswalk.md`](../threat-models/Self-Jailbreaking-Crosswalk.md) | Recursive failure modes. |
| **Interception** | [`../threat-models/Jailbreak-Interception-Pipeline.md`](../threat-models/Jailbreak-Interception-Pipeline.md) | Detection logic flow. |
| **Lifecycle** | [`../architecture/Jailbreak-Lifecycle-Diagram-v1.0.md`](../architecture/Jailbreak-Lifecycle-Diagram-v1.0.md) | Attack path visualization. |

## 4. INTEGRATION & SIMULATION
Evidence of testing and external integration standards.

- **Simulations:** See [`../simulations/`](../simulations/) for synthetic stress test records (SIM-001).
- **Federal Crosswalk:** See [`../../business/Sovereign_Stack_Federal_Crosswalk.md`](../../business/Sovereign_Stack_Federal_Crosswalk.md) for NIST 800-53 mapping.

## 5. RUNTIME IMPLEMENTATION
For executable reference code and configuration schemas, refer strictly to the Implementation directory.

- **Action Catalog (JSON):** [`../../implementation/Quantum_Action_Catalog_v1.1.json`](../../implementation/Quantum_Action_Catalog_v1.1.json)
- **Control Plane API:** [`../../implementation/Quantum-Classical-Control-Plane.md`](../../implementation/Quantum-Classical-Control-Plane.md)

---
*End of Technical Index*
