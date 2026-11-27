# SYSGROW-FOUNDATION-001 — CP0–CP7 ExecPlan

Status: proposed plan, G0 documentation-only candidate. Baseline `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`. CP0–CP2 reports delivered, technical owner acceptance pending. See [evidence](../qualification/CP0-CP2.md), [register](../qualification/FINDINGS.md), [roadmap](../../ROADMAP.md). No phase or remediation is authorized by this document alone.

| Checkpoint | Scope/deliverables | Exit criteria |
|---|---|---|
| CP0 | baseline/history/CI/test/dependency inventory, initial risk register | pinned baseline, limitations, owner acceptance |
| CP1 | service ownership, lifecycle, persistence, branches, deployment, ADR candidates | critical owner contracts mapped; contradictions bounded; exhaustive graph remains outstanding |
| CP2 | command paths, authorization, threat model, fail-safe policy and EP-001–003 refinement | source evidence and disposition; production safety NOT QUALIFIED; hardware and exhaustive paths outstanding |
| G0/G0.1/G0.2 | governance docs, findings, plans and roadmap; review-driven documentation corrections | documentation-only diff, all findings open, original-report provenance and link/anchor qualification, three independent exact-HEAD reviews, successful applicable exact-HEAD CI and separate owner integration approval |
| Remediation gate D0/R1–R3/Q | critical containment, runtime/command/result/irrigation/lifecycle/security/persistence and deployment | separately authorized plans, applicable critical closure evidence; no activation by integration |
| CP3 | reference workloads, CPU/RSS/disk/thermal, SQLite/WAL, MQTT/Socket.IO, frontend, ML interference, recovery/soak | measured reproducible budgets and platform results |
| CP4 | dataset provenance, features/labels, chronological/grouped validation, Bayesian, drift, registry/promotion, artifact trust, agricultural outcomes | each model has objective, evaluation, eligibility and abstention/fallback |
| CP5 | coverage, real composition, simulation, network/process faults, CI matrix, release suite | repeatable risk-based tests; platform/dependency qualification |
| CP6 | K.I.T.T. capability contract, identity, revocation, governance, shared knowledge, privacy, blog, MCP/A2A and fleet feasibility | no direct external physical authority, consent, local independence |
| CP7 | closeout, reconciled backlog, accepted ADRs, roadmap and implementation plans | independent review, owner approval, unresolved risks traceable |

CP3 initial benchmark proposals (not measured or approved): Pi 4 4 GB, 5 units/50 sensors/5 dashboard clients, core RSS below 500 MB, cached API p95 below 250 ms, sensor-to-dashboard p95 below 1 s, zero duplicate physical actions and zero critical deadline violations in qualification, 30-day soak. CP3 must benchmark qualified runtime, not prematurely optimize unqualified topology. Simulation accompanies each remediation. CP4/CP6 do not assume K.I.T.T. compatibility or authorize external provider calls. CP5 no fabricated coverage. CP7 closeout cannot silently accept risks.

Use [REMEDIATION.md](REMEDIATION.md) for bounded work packages. Reverify baseline before each authorization; preserve existing completed work and historical branches. Stop before merge/deployment/activation without separate approval.

The proposed R1–R3 ordering is refined into design, minimum containment, enforcement and final qualification checkpoints in [REMEDIATION.md](REMEDIATION.md). G0.1 records documentation corrections and remaining evidence gates in [G0-REVIEW.md](../qualification/G0-REVIEW.md); it does not close runtime findings or accept ADRs.

## G0.2 clarification

G0.2 supersedes G0.1 planning sequence only as a proposed documentation correction. Use [staged dependencies](REMEDIATION.md) and [D0 contracts](D0-CONTRACTS.md). R1a/R1b containment does not permit ordinary energization where required contracts are missing. R2b is bounded process/dispatch ownership; full F-001/EP-001 and EP-003C closure at Q, after R3a/R3b and applicable [qualification profiles](../qualification/QUALIFICATION-PROFILES.md). FT-001–042 are test designs only. Original reports and exact-HEAD CI/enforcement remain mandatory evidence gates.
