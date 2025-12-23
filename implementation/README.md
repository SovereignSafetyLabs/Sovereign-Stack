# Implementation Layer: Runtime Enforcement & Hardware Logic

This directory contains the operational artifacts required to transition Vesta Protocol theory into physical enforcement on quantum-classical substrates.

## 🛠️ Core Components

* **[Quantum-Classical Control Plane](Quantum-Classical-Control-Plane.md)**: The v0.3.4 specification governing the interaction between classical instruction layers and quantum photonic hardware.
* **[Quantum Action Catalog (Human-Readable)](Quantum-Action-Catalog.md)**: A risk-tiered index of permissible system actions, from telemetry monitoring to critical laser calibration.
* **[Quantum Action Catalog (Machine-Readable)](Quantum_Action_Catalog_v1.1.json)**: The v1.1 JSON payload used by the Sovereign Kernel for real-time instruction verification.
* **[Integrity Stack v2.1](INTEGRITY-STACK-v2.1.md)**: The runtime specification for the software-layer verification and boundary enforcement engine.



## ⚖️ Enforcement Logic

This layer operationalizes **Axiom A (Physical Sovereignty)** via two primary mechanisms:

1. **The Fast-Path**: Allows high-throughput operations (e.g., `entangle_nodes`) to bypass 1ms signature cycles, provided they remain within the **Percentile Vise** thermodynamic bounds.
2. **The Signature Gate**: Requires Multi-Sig human authorization for **CRITICAL** actions such as `calibrate_repeater` or `modify_key_material`.

## 📜 Standard Operating Procedures (SOPs)

* **SOP-1 (Approval)**: Defines the human-in-the-loop signature process for high-risk actions.
* **SOP-2 (Incident Response)**: Defines the automated revocation and "Deadman Switch" protocols triggered by policy violations.
