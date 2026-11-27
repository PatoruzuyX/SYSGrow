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

## Acceptance versus qualification

The qualification dependency column identifies downstream evidence needed for implementation/activation, not automatically a prerequisite to accept a design. An individual ADR may be accepted before implementation only with a bounded contract, alternatives, known risks, unresolved questions, a validation plan and explicit owner approval. Mark proposed, accepted, superseded or rejected independently of implementation status. Record implementation authorization, verification and integration separately; physical qualification and activation require their own evidence and owner approval. No G0/G0.1 ADR is accepted by the documentation change.

## G0.2 D0 contract ownership

All 12 candidate ADRs remain proposed. [D0 contract matrix](../../plans/D0-CONTRACTS.md) assigns required interfaces, accountable owners, consumers and validation prerequisites; ADR-004 candidate scope is extended to explicitly include principal/resource authorization (EP-007) and its interface with command admission (EP-003A), without accepting the decision. ADR-005/006 coordinate durable quarantine and recovery. Design acceptance requires resolving the listed questions and validation plans, not downstream implementation success. No design acceptance by G0.2.
