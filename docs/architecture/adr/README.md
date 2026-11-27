# Architecture decision register

G0: no ADR accepted by this change alone. Owner authorization of documentation-only scope is recorded in the [foundation report](../../qualification/CP0-CP2.md); it is not acceptance of architectural proposals. Existing implemented behaviour is recorded in the [baseline](../FOUNDATION_BASELINE.md). Candidate IDs below are provisional and preserve the CP1/CP2 proposal sequence.

| Candidate | Proposed decision | Rationale / alternative | Qualification dependency |
|---|---|---|---|
| ADR-001 | Retain edge-first modular monolith | Lower Pi complexity than premature microservices | CP3 |
| ADR-002 | Exclusive edge runtime authority | One worker alone insufficient; qualify OS lock; distributed fencing later | EP-001 |
| ADR-003 | Separate construction and activation | Avoid side effects in web-only mode | EP-001/002 |
| ADR-004 | Canonical command boundary | Preserve existing actuator manager; reject raw bypass | EP-003A/B |
| ADR-005 | Device-specific fail-safe requirements | Application timeout alone insufficient | EP-003F |
| ADR-006 | SQLite default; explicit transaction/recovery contracts | Avoid premature database migration | EP-004 |
| ADR-007 | Canonical dependencies and platform profiles | Qualify reproducible installs before declaring support | EP-005 |
| ADR-008 | Unified model eligibility/promotion and artifact trust | Preserve existing model-specific gates | CP4 |
| ADR-009 | Separate measured calibration and agronomic learning | Avoid confusing physical flow with user preference | EP-003E/CP4 |
| ADR-010 | Optional capability-scoped K.I.T.T. integration | No mandatory external AI | CP6 |
| ADR-011 | Separate knowledge plane from control plane | External information grants no physical authority | CP6 |
| ADR-012 | Shared knowledge consent and provenance | Prevent unconsented disclosure and unreliable recommendations | CP6 |

Before acceptance, create a dated individual ADR with context, alternatives, decision, consequences, dependencies, owner approval and evidence. Supersession must link the prior decision; do not silently edit history. No candidate currently has an accepted status.
