# SYSGrow — Agricultural AI Ecosystem roadmap

Status: proposal for owner review; no implementation authority beyond G0 documentation. Maintain the existing Raspberry Pi-first modular Flask/SQLite/MQTT platform. Vision: observe reliably, reason intelligently, authorize explicitly, validate deterministically, execute exclusively, verify physically, learn from evidence and share responsibly.

## Programme sequence

| Phase | Objective | Gate |
|---|---|---|
| CP0–CP2 | Baseline, architecture, security and physical safety | Reports delivered; acceptance pending; safety NOT QUALIFIED |
| G0/G0.1/G0.2/G0.3 | Canonical engineering governance | Documentation-only candidate; mandatory provenance, source semantics, exact-HEAD CI/enforcement, independent review and owner integration approval |
| D0 | Foundational design contracts | Separate owner acceptance after qualified G0 integration; no implementation authority |
| R1a/R1b | Critical containment and exclusive edge runtime | Deny unauthorized consequential physical-interface effects, including lifecycle paths; default strict irrigation inhibition; alternative atomic admission requires implementation and qualification within R1b; no full closure |
| R2a/R2b | Canonical command, recovery and bounded ownership | Minimum durable recovery and command admission in R2a; bounded process/dispatch ownership in R2b; F-001 remains OPEN |
| R3a/R3b | Irrigation, lifecycle, persistence and deployment | EP-002, EP-003C–F, remaining EP-004/005/007; full recovery and rearm contracts |
| Q | Cross-package qualification | Profile-specific evidence; only here consider full F-001/EP-001 and EP-003C closure; no activation authority |
| CP3 | Performance/deployment benchmarks | Reproducible workload and measured budgets |
| CP4 | Agricultural intelligence qualification | Data provenance, temporal validation, ML promotion and fallback |
| CP5 | Simulation/testing closeout | Risk-based coverage, contract/fault tests and CI matrix |
| CP6 | Ecosystem integration | Optional K.I.T.T., knowledge exchange, consent and isolation |
| CP7 | Strategic closeout | Reconciled findings, approved roadmap and bounded future plans |

Simulation and regression tests accompany remediation from R1, not only CP5. Non-conflicting qualification can run in parallel with separate authorization. Integration and activation gates remain distinct. See [foundation plan](docs/plans/SYSGROW-FOUNDATION-001.md), [remediation plans](docs/plans/REMEDIATION.md), [findings](docs/qualification/FINDINGS.md).

## Product direction (proposed)

- Edge: local safety, reliable telemetry, hardware interoperability and per-plant irrigation (dedicated pump, shared pump/valves, manual logging). Retain existing irrigation decomposition.
- Labs: simulation, reproducible benchmarks, fault injection, qualified Pi deployment profiles; performance budgets based on measurements, not assumptions.
- Intelligence: valid temporal forecasting, Bayesian personalization, plant digital passports, predictive irrigation and eventually computer vision/digital twins; experimental control only in simulation until qualified.
- K.I.T.T.: optional capability-scoped integration; local policy owns execution; evaluate standards-based MCP/A2A during CP6, without assuming existing compatibility.
- Knowledge Hub: build on existing condition-profile sharing (CAP-001), not a duplicate subsystem. Evidence, provenance, consent, revisions, moderation and multilingual content; public publishing isolated from local control. Blog remains a static JSON-backed capability at baseline, not a federated network.
- Fleet: opt-in aggregation first; distributed/federated learning only after privacy, poisoning and heterogeneous-data qualification. No mandatory cloud dependency.

Measure water and energy per yield, climate-range time, prediction errors, verified operation and intervention rate before competitive claims. Existing v3.1/v3.2/v3.x backlog features are retained as historical candidates, not committed release dates. No version allocation or delivery date is approved here.

The R1–R3 sequence is a proposed checkpoint-level ordering, not permission to implement or a promise that entire packages are independent. Use the staged dependency graph in [REMEDIATION.md](docs/plans/REMEDIATION.md); full finding closure waits for all relevant enforcement, transaction, recovery and device-specific evidence.

## G0.2 sequencing authority

The [staged dependency matrix](docs/plans/REMEDIATION.md) is canonical over this roadmap summary. R1a denies unsupported/unqualified ordinary dispatch; R1b defaults to strict irrigation inhibition (alternative minimum atomic admission requires implementation and synthetic qualification within R1b, never lifting other gates). R2a delivers minimum durable recovery before consequential dispatch; R2b qualifies process/dispatch ownership only. F-001 and full EP-001/EP-003C closure reserved for Q after R3a/R3b and applicable evidence. D0 contract ownership is in [D0-CONTRACTS.md](docs/plans/D0-CONTRACTS.md); [qualification profiles](docs/qualification/QUALIFICATION-PROFILES.md) distinguish software integration, deployment, physical safety and activation. G0.3 documentation-only candidate; future checkpoints separately authorized. Q reports scoped dispositions; CP3–CP7 advance under the applicable prerequisites in [qualification profiles](docs/qualification/QUALIFICATION-PROFILES.md), not an undifferentiated global PASS. Isolated qualification may collect its own missing evidence; no deployment or activation without complete applicable qualification.
