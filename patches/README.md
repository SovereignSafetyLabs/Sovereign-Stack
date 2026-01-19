# Patch Taxonomy & Usage Guide

## Scope

This directory contains **patch documents** associated with the Vesta Governance Framework and its constituent components (e.g., Sovereign Protocol, PGS, Kernel).

Patches are **version-scoped amendments or clarifications** applied to existing specifications.
They do **not** represent standalone systems or deployment artifacts.

---

## What a Patch Is (and Is Not)

### A patch **is**:
- A bounded modification or extension to an existing document
- Version-referenced (e.g., applies to v3.0 → v3.1)
- Narrow in scope
- Traceable to a specific architectural or governance change
- Designed to preserve backward compatibility unless explicitly stated

### A patch **is not**:
- A full specification
- An implementation guide
- A deployment instruction
- A runtime guarantee
- A claim of operational enforcement

---

## Patch Categories

Patches in this repository generally fall into one of the following categories.

### 1. **Hardening Patches**
**Purpose:**
Clarify stricter interpretation, escalation posture, or constraint behavior under stress.

**Characteristics:**
- Refines existing rules
- Narrows ambiguity
- Adds conservative defaults
- Does not introduce new subsystems

**Example Topics:**
- Telemetry-aware escalation logic
- Identity claims under pressure
- Refusal behavior tightening

---

### 2. **Integration Patches**
**Purpose:**
Document how an existing component conceptually interfaces with newly introduced layers or signals.

**Characteristics:**
- Describes signal flow or dependency relationships
- Does not redefine authority boundaries
- Non-breaking by design

**Example Topics:**
- Integration with CLTB
- Interaction with ZEOL or Stress Map
- Alignment with Kernel telemetry

---

### 3. **Constitutional Amendments**
**Purpose:**
Refine or extend constitutional axioms or invariants.

**Characteristics:**
- Explicitly references prior versions
- Clearly identifies which axioms are affected
- Preserves unchanged axioms
- Treated as **non-breaking unless stated otherwise**

**Example Topics:**
- Expanded interpretation of an axiom
- Additional constraints under defined conditions

---

### 4. **Reference Addenda (Non-Operational)**
**Purpose:**
Preserve design reasoning or illustrative governance logic without asserting runtime behavior.

**Characteristics:**
- Clearly labeled as analytical or reference-only
- No thresholds, metrics, or guarantees
- Subordinate to canonical specifications

**Note:**
Some early patch drafts may be reclassified into addenda during hardening.

---

## Relationship to Canonical Documents

Patches are **subordinate** to canonical specifications located elsewhere in the repository, including:

- Core framework specifications
- Architecture documents
- Constitutional definitions
- Validation status statements

If a conflict exists, **canonical documents take precedence**.

---

## Versioning Expectations

- Patches explicitly state the version they apply to
- Patch version numbers do **not** imply release readiness
- Future versions may consolidate patches into updated canonical specs

---

## Non-Operational Disclaimer

All patch documents:

- Are research and reference materials only
- Do not assert deployment status
- Do not guarantee behavior or performance
- Do not imply enforcement completeness

They exist to support **traceability, design clarity, and governance reasoning**.

---

**END OF DOCUMENT**