# Stress Map — Patch v1.1
### Applies To: Stress-Map-v1.0
### Type: Pressure Modeling Upgrade

This update introduces hysteresis, telemetry broadcast, and predictable
posture transitions.

---

# 1. NEW FEATURES

### 1.1 Telemetry Broadcast
Stress Map now transmits:
N, R, E, posture_hint
directly into CLTB.

---

# 2. HYSTERESIS LOGIC

Once a posture increases:
- it cannot decrease until **two safe turns** occur  
- ambiguous turns do not count as safe  

---

# 3. POSTURE HINTS
LOW: N/R/E < 1
MED: any ≥ 1
HIGH: any ≥ 2
CRITICAL: any ≥ 3


These hints bias PGS posture selection across layers.

---

# 4. VERSION HISTORY
- v1.0 — initial  
- **v1.1 — hysteresis + broadcast + stability controls**  
