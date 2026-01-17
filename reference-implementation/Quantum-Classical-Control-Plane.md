# Vesta Governance Reference Architecture
**Framework:** Vesta Governance Framework
**Artifact Type:** Reference Logic & Interface Specification
**Maturity:** TRL 5 (Software) / TRL 2 (Hardware)
**Date:** January 16, 2026
**Status:** ACTIVE RESEARCH // REFERENCE ARTIFACT

---

## 0.0 Context: The Quantum-Classical Control Plane
This reference architecture defines the **Classical Control Plane** interface for orchestrating quantum network nodes. While the underlying hardware operates on quantum mechanics (entanglement distribution), the instruction layer—responsible for routing, key assignment, and telemetry validation—is classical software.

> ⚠️ **TRL NOTICE**
> This document is a **Reference Specification**. It defines the logic gates, schemas, and physics constraints for a theoretical high-assurance control plane. It is **not** an operational deployment manual.

---

## 1. CORE ARCHITECTURAL FOUNDATION: DEFAULT-DENY ZERO-TRUST
**Objective:** Enforce Axiom A (Physical Sovereignty) via cryptographic signature gates at the hardware boundary.

### The Control Loop (Logical Flow)
1. **Observe:** Agent identifies intent based on incoming telemetry or objective function.
2. **Classify:** Policy Engine maps intent to the **Action Catalog**.
3. **Gate:**
    * *Low Risk:* Auto-Execute.
    * *Medium/High Risk:* **BLOCK** → Generate Dry-Run → Request Human Signature.
4. **Verify:** Server-side cryptographic verification of `operator_pubkey` against `dry_run_hash`.
5. **Execute:** Instruction passed to FPGA/ASIC controller only upon valid ECDSA signature.
6. **Log:** Write to append-only, hash-chained audit ledger.

---

## 2. ACTION CATALOG (Risk Classification)
*Hardware-enforced permission levels for runtime tooling.*

| Action ID | Description | Risk Level | Signature Required | Fast-Path |
| :--- | :--- | :--- | :--- | :--- |
| `read_telemetry` | GET status, QBER rates, photon counts | **LOW** | NO | N/A |
| `execute_simulation` | Sandboxed Hamiltonian simulation/analysis | **MEDIUM** | **YES** (Session Key) | N/A |
| `entangle_nodes` | Create entangled pairs between quantum nodes | **MEDIUM** | **Conditional** | **YES** (See Sec 2.1) |
| `route_entanglement` | Direct entanglement pair allocation (switch config) | **HIGH** | **YES** (Human Key) | NO |
| `modify_key_material` | DTK shard rotation or PUF extraction | **HIGH** | **YES** (Human Key) | NO |
| `calibrate_repeater` | Pump laser power / phase adjustment | **CRITICAL** | **YES** (Multi-Sig) | NO |
| `update_firmware` | Flash new PDK / gate config to controller | **CRITICAL** | **YES** (Offline Key) | NO |

### 2.1 Fast-Path Traffic Governor (Anti-Flood Protocol)
**ECO-2026-01-15:** Replaces static thresholding with Token Bucket rate limiting to prevent "Flash Flood" DoS attacks.

To accommodate high-throughput quantum networking (200M pairs/sec) without strictly serialized signature verification, the system utilizes a **Token Bucket Governor**.

**Reference Implementation (Python 3.10):**

```python
from dataclasses import dataclass, field
from time import time
from typing import Optional

class RateLimitExceeded(Exception):
    """Raised when fast-path rate limit is exhausted."""
    pass

@dataclass
class TrafficGovernor:
    """
    TRL 5 Reference Logic: Token Bucket Rate Limiter
    Prevents 'Flash Flood' exhaustion of entropy reserves.
    
    Note: This reference implementation is not thread-safe.
    Production deployments should use thread-safe primitives (locks/atomics).
    """
    bucket_tokens: int = 10
    last_refill: float = field(default_factory=time)
    REFILL_RATE: int = 5  # Tokens per minute
    CAPACITY: int = 10    # Max burst capacity
    VOLUME_THRESHOLD: int = 1_000_000  # Pairs requiring slow-path

    def validate_request(self, entangled_pairs: int) -> bool:
        """
        Validate request against token bucket rate limiter.
        
        Args:
            entangled_pairs: Number of entangled pairs requested (must be >= 0)
            
        Returns:
            True if request allowed via fast-path, False if routed to slow-path
            
        Raises:
            ValueError: If entangled_pairs is negative
            RateLimitExceeded: If fast-path is exhausted (fail-closed)
        """
        # Input validation
        if entangled_pairs < 0:
            raise ValueError(f"entangled_pairs must be non-negative, got {entangled_pairs}")
        
        # 1. Volume Check (Static Gate)
        if entangled_pairs >= self.VOLUME_THRESHOLD:
            return False  # Route to Slow Path (Signature Required)

        # 2. Rate Limit Check (Dynamic Gate)
        self._refill()
        
        if self.bucket_tokens >= 1:
            self.bucket_tokens -= 1
            return True  # ALLOW Fast-Path
        else:
            # FAILURE MODE: FAIL-CLOSED
            # If bucket is empty, request is REJECTED, not queued.
            raise RateLimitExceeded("FAST_PATH_EXHAUSTED: Rate Limit Exceeded")

    def _refill(self) -> None:
        """
        Refill token bucket based on elapsed time since last refill.
        Updates bucket_tokens and last_refill timestamp.
        """
        now = time()
        delta_minutes = (now - self.last_refill) / 60.0
        new_tokens = int(delta_minutes * self.REFILL_RATE)
        if new_tokens > 0:
            self.bucket_tokens = min(self.CAPACITY, self.bucket_tokens + new_tokens)
            self.last_refill = now

```

---

## 3. DATA STRUCTURES & ENFORCEMENT

### A. Approval Request Schema (The "Ticket")

```json
{
  "action_id": "calibrate_repeater",
  "resource_uri": "qnode:us-east-1:rack-4:laser-2",
  "parameters_digest": "sha256:e3b0c442...",
  "preview_plan": "Increase pump power to 1.2mW for QBER reduction.",
  "risk_level": "CRITICAL",
  "nonce": 847382,
  "expires_at": "2026-02-01T12:00:00Z",
  "operator_pubkey": "0x7F...",
  "signature": null
}

```

### B. Audit Log Entry Schema (Tamper-Evident)

```json
{
  "timestamp": "2026-02-01T09:00:00Z",
  "input_hash": "sha256:...",
  "policy_version": "v3.2.0",
  "decision": "VIOLATION_BLOCKED",
  "reason": "AXIOM_A_FAILURE",
  "blocked_capability": "route_entanglement",
  "chain_hash": "sha256:[Previous_Hash + Current_Entry]"
}

```

---

## 4. STANDARD OPERATING PROCEDURES (SOPs)

### SOP-1: OPERATOR APPROVAL

**Trigger:** Agent requests HIGH or CRITICAL action.

* **Verify:** Operator reviews `preview_plan` against external intent.
* **Sign:** Operator signs the hash using a hardware token (YubiKey/Ledger).
* **Execute:** Agent receives signature, validates against `operator_pubkey`, and proceeds.

### SOP-2: INCIDENT RESPONSE

**Trigger:** `policy_violation` event logged.

* **Triage:** Automated alert to SecOps.
* **Isolate:** Revoke Agent API Key immediately.
* **Audit:** Review hash-chain for divergence.
* **Patch:** Update Policy Bundle to close logic gap.

---

## APPENDIX A: QUANTUM PUF EXTRACTION (TRL 2)

> **Notice:** This section describes **conceptual hardware designs** for physical entropy extraction.

### A.1 Physical Unclonable Function (PUF) Overview

Vesta uses **entanglement-based PUFs** to generate hardware-rooted cryptographic material. Quantum PUFs exploit **waveguide fabrication defects** in Photonic Integrated Circuits (PICs) to produce unclonable entropy.

### A.3 Security Properties

| Property | Guarantee | Enforcement |
| --- | --- | --- |
| **Unclonability** | Waveguide defects cannot be replicated | Fabrication variance (~5nm) |
| **Tamper-Evidence** | Phase coherence breaks under probing | Quantum limit (No-Cloning) |
| **Entropy Rate** | ≥128 bits per cycle | von Neumann extractor |

---

## APPENDIX B: LATENCY ANALYSIS (TRL 2)

> **Notice:** Theoretical latency budgets for FPGA implementation.

### B.1 Quantum Heralding Latency Budget

| Operation | Latency | Bottleneck |
| --- | --- | --- |
| Entanglement generation (SPDC) | ~10µs | Downconversion rate |
| Heralding detection | ~10µs | Detector jitter |
| Classical routing decision | **<100µs** | **Control plane overhead** |
| Total end-to-end latency | ~100µs | Thermal time constant |

### B.2 Fast-Path Safety Argument

The fast-path does **not** bypass governance—it **defers signature verification** to audit review, governed by the `TokenBucket` (Sec 2.1) to prevent exhaustion.

---

## REVISION HISTORY

| Version | Date | Changes |
| --- | --- | --- |
| v3.2 | 2026-01-16 | **Major:** Integrated `TokenBucket` rate limiter; TRL Downgrade to TRL 5/2. |
| v0.3.4 | 2025-12-22 | **Legacy:** Initial Release Candidate (Deprecated). |

---

**Document Status:** ANALYTICAL REFERENCE (TRL 5)
**Classification:** UNCLASSIFIED // TLP:WHITE
**Contact:** Sovereign Safety Labs