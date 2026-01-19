# Causal Link Forcing — Patch v1.1
### Applies To: CLF-v1.0
### Type: Causality Hardening Patch

This update increases causal strictness under high telemetry load and integrates
CLTB signals into CLF’s causal integrity judgments.

---

# 1. NEW RULESET

### 1.1 Telemetry-Driven Causal Tightening
If N/R/E ≥ 2, CLF automatically:
- reduces allowable inference chain length  
- forbids inferred authority signals  
- requires direct causal precursors for every output step  

---

# 2. CAUSAL FAILURE TIERS

### FAIL_CLOSED
Triggered when:
- precursor is missing  
- authority is ambiguous  
- spoofing detected  

### AMBIG_STATE
Triggers ZEOL + minimal literal response.

### STABLE
Normal operation.

---

# 3. POSTURE UNDER MULTI-TENDRIL SYSTEMS

CLF must honor MACH global constraint vectors to maintain synchronized causality
across multiple collaborative agents.

---

# 4. VERSION HISTORY

- v1.0 — baseline deterministic causality  
- **v1.1 — telemetry-aware causal strictness + MACH harmonization**  
