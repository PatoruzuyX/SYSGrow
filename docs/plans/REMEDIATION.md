# Foundation bounded remediation ExecPlans

Status: proposed, CP1 plans revised by CP2. No implementation authorized except G0 documentation. Baseline `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`. Each package must pin its actual starting HEAD, record dependencies and acceptance, use synthetic tests and stop at independent review/owner integration approval. See [findings](../qualification/FINDINGS.md), [invariants](../architecture/FOUNDATION_BASELINE.md), [guidelines](../guidelines.md). Revert unmerged changes or use a reviewed rollback of only the package; persistence/physical recovery requires separate safe procedures. No package grants deployment or hardware operation.

## EP-001 — SYSGROW-RUNTIME-OWNERSHIP-001 (rev 0.2)

F-001 Critical. R1. Candidate paths: smart_agriculture_app.py, app/__init__.py, app/services/container.py and container_builder.py, scheduler CLI, deployment and targeted tests. M0 baseline; M1 lifecycle/authority contract; M2 exclusive ownership; M3 construction-only mode; M4 reconcile entry points; M5 deny non-owner at all physical boundaries; M6 concurrency/crash/restart tests; M7 review. Initially single control process plus shared OS lock; verify lock boundary and failure semantics. No distributed orchestration, frontend/ML redesign, topic migration or production activation. Acceptance: simultaneous startup one owner; non-owner cannot register/control; CLI cannot bypass; construction no control workloads; ownership held through shutdown; restart reconciliation; simulated termination cannot create competing command authority. Depends on CP2 safety requirements and accepted ownership ADR; coordinate EP-003A non-owner enforcement. FT-001/015/016.

## EP-002 — SYSGROW-RUNTIME-LIFECYCLE-001 (rev 0.2)

F-023/024/025/028. M1 installation vs unit ownership; M2 unit-specific poll registrations; M3 disposable subscriptions; M4 invalidate queued work; M5 ordered quiescence and recovery; M6 regression; M7 review. Preserve EventBus and shared poller. Unit A stop cannot interrupt B; repeated start/stop idempotent; disposed controllers cannot command; partial start rolls back; device-appropriate shutdown reconciled or unknown; no resource growth under repetitions. Depends on EP-001 and EP-003 device contracts. Exclude wholesale event platform replacement. FT-013/016/023.

## EP-003 — SYSGROW-ACTUATOR-SAFETY-001 (rev 0.2)

Critical F-033/034/035 plus F-002/003/004/016/025/026/027/039/040/041/042/044. Preserve actuator manager, irrigation façade and existing safeguards. Each subplan requires independent authorization and review.

| Subplan | Bounded scope | Acceptance / tests |
|---|---|---|
| EP-003A | F-026/034; classify all command paths, mandatory authorization/safety/ownership; reject unknown protocol operations | all ON/toggle/level/pulse/adapter paths deny prohibited commands; no bypass; FT-005/007/019 |
| EP-003B | F-004/035/042/044; adapter result contracts, caller interpretation, acknowledgement and state evidence; reconcile actual MQTT wiring | transport/GPIO/Modbus failures explicit; no false success; unverified outcome visible; scheduling/bulk respect rejection; FT-008–011/021/022 |
| EP-003C | F-033/041; approval and current policy at execution, atomic validated state transitions; early containment separately authorized | required approval, disabled automation, cancellation, expiry and delayed timing enforced; conflict cannot mutate claimed request silently; durable failure visible; FT-002–004/020 |
| EP-003D | F-016/027/040; physical resource identity, owner-bound locks, explicit dedicated/shared/manual topology | stale release cannot delete reservation; valve uncertainty blocks shared pump; failed shutdown quarantines resource; FT-012–014 |
| EP-003E | F-003/039; execution-time eligibility and bounded calibration; preserve separate measured flow and preferences | stale/missing data blocks autonomous action; compatible real service composition; measured duration/volume traceable; FT-005/006 |
| EP-003F | F-002/025/040; independent operating bounds, device-specific shutdown and restart reconciliation | process/network failure cannot exceed qualified limits; unknown shutdown blocks ordinary operation; simulation plus separately approved device-specific HIL; FT-013/015/022 |

Dependencies: EP-001 ownership; EP-007 owns resource authorization and broker/maintenance trust; EP-004 owns transaction semantics; EP-002 coordinates shutdown. Suggested integration A -> B -> C -> D -> E -> F, early C containment may precede adapter redesign. No raw protocol bypass, new cloud/AI, universal safe limits or hardware activation. Full qualification requires all applicable Critical findings and device safety evidence, not just software tests.

## EP-004 — SYSGROW-PERSISTENCE-INTEGRITY-001

F-029/030/031; F-009 calibration persistence and F-041 transaction dependency. Audit transaction callers/nesting before changing context manager. Establish rollback semantics, exclusive migration/recovery, explicit errors and critical snapshot concurrency. Preserve SQLite/repositories. Inject failures, prove no partial writes, no competing maintenance or silent healthy empty installation; qualify backup/restore and calibration persistence with CP4. No wholesale ORM/PostgreSQL migration. FT-020. Can design early; integrate with ownership.

## EP-005 — SYSGROW-DEPLOYMENT-001

F-010/011/013/015. Reconcile pyproject and requirements; qualify generated core/optional ML/vision/dev profiles and Python/OS/ARM targets, clean-checkout Docker, durable directories and CI install/startup paths. Native Pi/systemd primary, Docker alternative pending qualification; Windows dev retained. Python 3.11/3.13 candidates, 3.12 compatibility to be tested. No platform support claims before evidence. Requires EP-001 deployment decisions. No unrelated app refactor or deployment.

## EP-006 — SYSGROW-GOVERNANCE-001

F-012/014/020/021. G0 documentation only; proposed branch docs/sysgrow-governance-001. Preserve all historical records and refs, add canonical guidance, evidence, candidate ADRs, roadmap and plan links. G0 acceptance: all 44 OPEN, all four Critical mapped to gates; documentation-only diff, links, independent review, exact HEAD CI and owner approval. Branch enforcement and individual historical recovery remain open; settings changes and branch deletion excluded. No finding automatically closed.

## EP-007 — SYSGROW-SECURITY-BOUNDARIES-001

F-004/005/018/036/037/038/043. M1 verified identity (no implicit fallback); M2 resource permissions; M3 HTTP/public allowlists/CSRF; M4 Socket.IO authenticated memberships/revocation; M5 broker identity/ACL/transport; M6 privileged firmware maintenance/provenance; M7 security regression/review. Acceptance: deny anonymous/prohibited direct and child resource access, no cross-unit subscriptions, public health minimal, invalid firmware trust rejected, no leaked raw internal exceptions; comprehensive SQL review with allowlists/parameter binding. EP-003 owns command and physical outcome, EP-007 owns principal and transport authorization. No live penetration test or external agent authority. FT-017/018/024.

## CP4/CP3/CP5/CP6 follow-on ownership

CP4 F-006/007/008/009/017/032: data provenance, leakage-free temporal evaluation, registry integrity and explicit promotion/fallback; preserve existing irrigation metric gates. CP3 F-015/017/022/028: benchmark workloads, cache, queue and ML contention. CP5 F-013/019: coverage, actual composition, fault tests, CI profile qualification. CP6 F-008 and future knowledge/agent threats: optional integration and artifact trust. CP7 F-021 backlog reconciliation. Separate scoped plans required before changes.

## Fault qualification matrix (test designs only)

| ID | Synthetic condition | Required outcome |
|---|---|---|
| FT-001 | Concurrent startup | One owner |
| FT-002 | Pending request requires approval | No operation |
| FT-003 | Automation disabled after creation | Reject |
| FT-004 | Cancel races claim | No unauthorized operation |
| FT-005 | Invalid resource association | Reject |
| FT-006 | Missing/stale observation | Block |
| FT-007 | Active interlock | All energization rejected |
| FT-008 | MQTT disconnected | No false success |
| FT-009 | GPIO failure | Explicit failure |
| FT-010 | Modbus error response | Explicit failure |
| FT-011 | Missing acknowledgement | Unverified |
| FT-012 | Valve unavailable | Shared pump blocked |
| FT-013 | Shutdown fails | Quarantine resource |
| FT-014 | Expired owner releases | Current reservation intact |
| FT-015 | Runtime termination during irrigation | Independent bounds; HIL required for actual devices |
| FT-016 | Repeated unit restart | No duplicate authority |
| FT-017 | Anonymous socket subscription | Deny |
| FT-018 | Unauthorized unit request | Deny |
| FT-019 | Unknown protocol command | Reject |
| FT-020 | Transaction failure | No partial authorization |
| FT-021 | Schedule rejected | No success record |
| FT-022 | No physical verification | Unknown remains visible |
| FT-023 | Event queue saturation | Safety preserved |
| FT-024 | Firmware trust absent | Block update |

None executed by CP2 or G0. Test real composed services using synthetic hardware; do not confuse simulation with actual device certification. Report exact revision, commands, outcomes, failures and limitations. No merge without independent review and explicit owner approval; activation separate.
