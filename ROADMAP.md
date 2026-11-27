# SYSGrow — Agricultural AI Ecosystem roadmap

Status: proposal for owner review; no implementation authority beyond G0 documentation. Maintain the existing Raspberry Pi-first modular Flask/SQLite/MQTT platform. Vision: observe reliably, reason intelligently, authorize explicitly, validate deterministically, execute exclusively, verify physically, learn from evidence and share responsibly.

## Programme sequence

| Phase | Objective | Gate |
|---|---|---|
| CP0–CP2 | Baseline, architecture, security and physical safety | Reports delivered; acceptance pending; safety NOT QUALIFIED |
| G0 | Canonical engineering governance | Documentation-only candidate; independent review and owner integration approval |
| R1 | Critical containment and exclusive edge runtime | Accepted foundational contracts; EP-001 containment and early EP-003C containment with EP-003A/EP-007/EP-004 minimum interfaces; no full closure or production activation |
| R2 | Canonical command and result contracts | EP-003A/B; EP-007 authorization boundaries; EP-004 transactional prerequisites; qualify EP-001 only after dependent enforcement |
| R3 | Irrigation, lifecycle, persistence and deployment | EP-002, EP-003C–F, remaining EP-004/005/007; final cross-package qualification and applicable safety gates |
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
