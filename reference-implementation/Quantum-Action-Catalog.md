# Quantum Action Catalog
**Framework:** Vesta Governance Framework
**Version:** 1.1 (Quantum-Classical Hybrid)
**Status:** REFERENCE ARTIFACT (TRL 5)
**Governance Mapping:** NIST AI RMF 1.0, ITAR/EAR Compliance (ECCN 3A901)

> ⚠️ **TRL NOTICE**
> This document is a **human-readable mirror** of the machine-readable JSON schema.
> It defines permissible action categories for analytical verification, not operational enforcement.

**Linkages**:
* **Machine-Readable Spec**: [`Quantum_Action_Catalog_v1.1.json`](Quantum_Action_Catalog_v1.1.json)
* **Hardware Enforcement**: [`Quantum-Classical-Control-Plane.md`](Quantum-Classical-Control-Plane.md)

## 1. Action Tiers & Risks
| Tier | Category | Risk Level | CLF Required | Implementation Reference |
| :--- | :--- | :--- | :--- | :--- |
| **0** | **SAFE** | LOW | No | Semantic reasoning, summaries, `read_telemetry` |
| **1** | **CONFIG** | LOW | No | Internal output styling, `execute_simulation` |
| **2** | **QUANTUM_FASTPATH** | MEDIUM | **Conditional** | High-throughput `entangle_nodes` (≤1M pairs) |
| **3** | **CRITICAL_HARDWARE** | HIGH | **YES** | `calibrate_repeater`, `route_entanglement`, `modify_key_material` |
| **4** | **PROHIBITED** | CRITICAL | **DENY** | External code execution, unauthorized firmware updates |

## 2. Quantum Substrate Actions (v0.3.4 Definition)
The following hardware-specific actions are governed by the **Vesta Protocol** and the **Integrity Stack**:

* **`read_telemetry`**: Low-risk status monitoring (QBER rates, photon counts). Classified as **Tier 0**.
* **`entangle_nodes`**: Medium-risk fast-path pairs. Auto-allow ≤1M pairs if Percentile Vise bounds are nominal. Classified as **Tier 2**.
* **`route_entanglement`**: High-risk switch configuration requiring human signature. Classified as **Tier 3**.
* **`calibrate_repeater`**: Critical-risk laser adjustment requiring Multi-Sig (human-in-the-loop). Classified as **Tier 3**.
* **`modify_key_material`**: Critical-risk PUF extraction for DTK shard rotation. Classified as **Tier 3**.

---

### **3. Version Lineage**
* **v1.1 (Current)**: Relocated to `/reference-implementation/`. Integrated v0.3.4 hardware action IDs and Fast-Path heralding logic.
* **v1.0 (Archived)**: Initial semantic governance payload focused on non-quantum workloads. Located in `/archive/2025-11-payloads/`.

---
**Maintained by**: Sovereign Safety Labs | Principal Architect: Stephen S. Brouhard