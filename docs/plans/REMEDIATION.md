# Foundation bounded remediation ExecPlans

Status: proposed, CP1 plans revised by CP2. No implementation authorized except G0 documentation. Baseline `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`. Each package must pin its actual starting HEAD, record dependencies and acceptance, use synthetic tests and stop at independent review/owner integration approval. See [findings](../qualification/FINDINGS.md), [invariants](../architecture/FOUNDATION_BASELINE.md), [guidelines](../guidelines.md). Revert unmerged changes or use a reviewed rollback of only the package; persistence/physical recovery requires separate safe procedures. No package grants deployment or hardware operation.

## EP-001 — SYSGROW-RUNTIME-OWNERSHIP-001 (rev 0.2)

F-001 Critical. R1a containment; R2b bounded ownership; full EP-001/F-001 closure only at Q. Candidate paths: smart_agriculture_app.py, app/__init__.py, app/services/container.py and container_builder.py, scheduler CLI, deployment and targeted tests. M0 baseline; M1 lifecycle/authority contract; M2 exclusive ownership; M3 construction-only mode; M4 reconcile entry points; M5 deny non-owner at all physical boundaries; M6 concurrency/crash/restart tests; M7 review. Initially single control process plus shared OS lock; verify lock boundary and failure semantics. No distributed orchestration, frontend/ML redesign, topic migration or production activation. Acceptance: simultaneous startup one owner; non-owner cannot register/control; CLI cannot bypass; construction no control workloads; ownership held through shutdown; restart reconciliation; simulated termination cannot create competing command authority. Depends on CP2 safety requirements and accepted ownership ADR; coordinate EP-003A non-owner enforcement. FT-001/015/016.

## EP-002 — SYSGROW-RUNTIME-LIFECYCLE-001 (rev 0.2)

F-023/024/025/028. M1 installation vs unit ownership; M2 unit-specific poll registrations; M3 disposable subscriptions; M4 invalidate queued work; M5 ordered quiescence and recovery; M6 regression; M7 review. Preserve EventBus and shared poller. Unit A stop cannot interrupt B; repeated start/stop idempotent; disposed controllers cannot command; partial start rolls back; device-appropriate shutdown reconciled or unknown; no resource growth under repetitions. Depends on bounded R2b ownership evidence and applicable R3a/EP-003 device contracts; not full EP-001 closure (reserved for Q). Exclude wholesale event platform replacement. FT-013/016/023.

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

Dependencies: staged EP-001 containment and bounded ownership contracts (not full Q closure); EP-007 owns resource authorization and broker/maintenance trust; EP-004 owns transaction semantics; EP-002 coordinates shutdown. Use the staged dependency graph below, not a circular whole-package dependency. Early C containment defaults to strict inhibition; alternative minimum atomic admission must be implemented and qualified within R1b before claiming that mechanism, without lifting R1a inhibition. No full closure before Q. No raw protocol bypass, new cloud/AI, universal safe limits or hardware activation. Full qualification requires all applicable Critical findings and device safety evidence, not just software tests.

## EP-004 — SYSGROW-PERSISTENCE-INTEGRITY-001

F-029/030/031; F-009 calibration persistence and F-041 transaction dependency. Audit transaction callers/nesting before changing context manager. Establish rollback semantics, exclusive migration/recovery, explicit errors and critical snapshot concurrency. Preserve SQLite/repositories. Inject failures, prove no partial writes, no competing maintenance or silent healthy empty installation; qualify backup/restore and calibration persistence with CP4. No wholesale ORM/PostgreSQL migration. FT-020. Can design early; integrate with ownership.

## EP-005 — SYSGROW-DEPLOYMENT-001

F-010/011/013/015. Reconcile pyproject and requirements; qualify generated core/optional ML/vision/dev profiles and Python/OS/ARM targets, clean-checkout Docker, durable directories and CI install/startup paths. Native Pi/systemd primary, Docker alternative pending qualification; Windows dev retained. Python 3.11/3.13 candidates, 3.12 compatibility to be tested. No platform support claims before evidence. Requires D0 deployment-related decisions and R2b bounded ownership evidence; full EP-001 closure is not a prerequisite to R3b deployment-profile qualification. No unrelated app refactor or deployment.

## EP-006 — SYSGROW-GOVERNANCE-001

F-012/014/020/021. G0 documentation only; proposed branch docs/sysgrow-governance-001. Preserve all historical records and refs, add canonical guidance, evidence, candidate ADRs, roadmap and plan links. G0/G0.1/G0.2 acceptance: all 44 OPEN, all four Critical mapped to gates; documentation-only diff, traceable original reports, verified links and evidence anchors, three independently generated exact-HEAD reviews, successful applicable exact-HEAD CI and separate owner integration approval. See [G0 review record](../qualification/G0-REVIEW.md). Branch enforcement and individual historical recovery remain open; settings changes and branch deletion excluded. No finding automatically closed.

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

## G0.2 proposed checkpoint dependency graph

This is a planning correction, not authorization or accepted architecture. Dependencies below are checkpoint-level; cross-package cooperation is not a declaration that a complete dependent package is already qualified. Each implementation checkpoint requires its own owner authorization, exact baseline, exclusions, test matrix, rollback/recovery procedure and review.

| Checkpoint | Prerequisites | Bounded exit |
|---|---|---|
| D0 | Qualified G0 integration | Accept individual ADRs and all mandatory interfaces in [D0 contract matrix](D0-CONTRACTS.md); no implementation or activation |
| R1a | D0 | EP-001 containment: exclusive authority before control workloads; construction-only non-owner path; install deny-by-default guard and block any unclassified, unqualified or recovery-dependent ordinary dispatch. Prove no adapter submissions from denied paths, including unsupported discovery/CLI paths. No ordinary energization until minimum recovery and applicable command contracts qualified; no F-001 closure |
| R1b | D0, R1a | EP-003C containment: default strict inhibition of automatic/scheduled irrigation, pending/legacy/unclassified execution and unauthorized direct irrigation paths; retain manual observation logging without actuation. A separately authorized alternative may implement and synthetically qualify EP-004 minimum atomic admission/claim and EP-007 identity checks within R1b, but cannot lift R1a inhibition or any other prerequisite. No mock-only contract or non-atomic precheck substitutes for enforcement; no full EP-003C closure |
| R2a | R1a, R1b | EP-003A/B and EP-007 applicable enforcement: complete command-origin inventory, final dispatch classification, authorization, typed outcomes and real synthetic composition; implement and qualify minimum durable operation/resource identity, owner epoch, pre-dispatch record, atomic claim/revocation ordering, restart inhibition, quarantine surviving lease release and corrupt/missing/stale recovery evidence (EP-004/003D). No consequential ordinary dispatch without all relevant minimum contracts; synthetic only |
| R2b | R2a | Bounded EP-001 process and dispatch ownership qualification across startup/CLI/workers, adapters, stale-owner exclusion and minimum recovery; separate-process tests with actual shared lock boundary. F-001 and full EP-001 closure deferred to Q after R3a/R3b; unresolved resources remain inhibited |
| R3a | R2a, R2b | EP-003C/D/E and remaining EP-004: full transactional authorization, physical reservations, topology, observation freshness, calibration and durable recovery/quarantine; expand minimum R2a contracts, not duplicate owners |
| R3b | R3a | EP-002 and EP-003F: quiescence, invalidated queued/in-flight work, shutdown, independent protection and device-specific rearm; EP-005/remaining EP-007 deployment-profile evidence; no deployment or activation authority |
| Q | R3a, R3b | Cross-package negative/concurrency/fault qualification using [qualification profiles](../qualification/QUALIFICATION-PROFILES.md); F-001/full EP-001 and EP-003C closure only with all applicable evidence and independent review/owner disposition. Synthetic integration may pass separately; device safety and production activation remain HOLD without required evidence. No deployment or activation by Q alone |

Design work for later checkpoints may proceed in parallel if separately authorized; final closure cannot bypass prerequisites. Early containment is explicitly not final remediation and cannot expand autonomous operation.

### Required acceptance refinements

- EP-001: new ownership starts inhibited; durable outstanding operations and quarantine survive crash, lock release, lease expiry and restart. Unavailable/corrupt recovery evidence fails closed; stale owner/delayed command cannot gain authority. Test process separation and actual shared lock boundary, not just threads. Qualify non-owner denial across CLI, web, scheduled, discovery, calibration and adapter paths.
- EP-002: stop admission, invalidate queued work, account for in-flight effects, reconcile device-specific state, then dispose/release; process termination is a separate failure path. Preserve independent protection and do not mark shutdown verified from successful thread exit.
- EP-003A/B: inventory every command origin and adapter path including non-ON state-changing commands; classify physical effect, reject unsupported commands, and apply resource/principal/owner/policy/freshness checks at final dispatch. Define authoritative durable admission, transport submission and delivery as separate events; revocation before admission denies; after admission attempt safe cancellation when supported and reconcile possible effects. No claim of remote fencing or expiry without transport-specific evidence. Uncertain delivery or stale owner effects inhibit affected resources. Use the [outcome contract](../architecture/FOUNDATION_BASELINE.md); failure is not proof of OFF and stale/duplicate acknowledgement cannot promote state.
- EP-003C: define approval, cancellation, delayed timing, expiry, configuration and permission changes relative to the atomic dispatch admission point. Delay cannot be bypassed by a prior scheduled time. After dispatch, cancellation enters reconciliation, not false non-execution. Record durable decision/failure.
- EP-003D/E: bind authorizations and reservations to actual physical resource/topology, identity and owner; revalidate changed associations and fresh observations; preserve durable quarantine independently of lock lifetime. Reject invalid calibration/measurement and unqualified device limits.
- EP-003F: independent protection and emergency authority are distinct from normal software command authority; protective intervention inhibits ordinary commands, invalidates pre-intervention queued authority, requires device-specific reconciliation and qualified rearm, then fresh admission. Emergency capability is restricted, auditable and cannot authorize ordinary energization; qualify device-specific state and bounds, including loss of process, broker and power as applicable. Hardware-in-loop and actual activation require separate approval.

### Additional synthetic test designs (not executed)

| ID | Condition | Required outcome |
|---|---|---|
| FT-025 | Owner crashes with outstanding operation | Replacement owner starts inhibited |
| FT-026 | Restart with quarantined resource | Ordinary use remains blocked |
| FT-027 | Queued authorization revoked or stale | No dispatch |
| FT-028 | Resource association changes after approval | Reject stale authority |
| FT-029 | Transport fails after simulated delivery | Physical outcome remains unknown |
| FT-030 | Delayed request retains original due timestamp | No premature execution |
| FT-031 | Disposed controller retains queued work | No command authority |
| FT-032 | Duplicate/out-of-order acknowledgement | No incorrect state promotion |
| FT-033 | Runtime authority unavailable | Independent protection remains available in simulation; physical qualification separate |
| FT-034 | Persistence unavailable or corrupt during reconciliation | Fail closed |

Map FT-025/026/034 to EP-001/003D/004, FT-027/028/030 to EP-003A/C/E/007, FT-029/032 to EP-003B/F, FT-031 to EP-002, FT-033 to EP-003F. Report synthetic versus device-specific evidence separately.

## G0.2 fault-design acceptance oracles

All FT-001–042 are designs, not executed tests. Each authorized implementation plan must define fixture topology, actual composed services, synthetic adapters, isolated persistence, controlled clocks, deterministic barriers, injection point, expected durable state and captured adapter calls. No real broker/device/provider. Assert denial means zero consequential submissions, not merely an error status. Assert unknown physical outcome, quarantine and ownership survive restart and reservation expiry. Device-specific deadline/limit values must be separately qualified; unavailable evidence is not N/A.

| Existing test | Required extension |
|---|---|
| FT-001 | Separate OS processes, same shared lock boundary; second owner cannot submit; no thread-only substitution |
| FT-004 | Cancellation before admission prevents submission; after admission reconcile possible effects |
| FT-006 | Missing, invalid, future and stale timestamps; policy-specific freshness bounds |
| FT-007 | All consequential command paths including unknown/discovery/pulse/level |
| FT-008 | Distinguish known non-delivery from ambiguous delivery |
| FT-011 | Missing and late acknowledgement; no false verification |
| FT-012 | Partial valve operation and uncertain position; no pump submission |
| FT-013 | Quarantine survives reservation release and restart |
| FT-015 | Crash at each consequential operation transition; independent bounds separately qualified |
| FT-016 | Stale workers, callbacks and queued commands cannot submit |
| FT-018 | Direct/child resources and permission changes; no protected disclosure |
| FT-020 | Admission rollback, failed commit and transport boundaries; zero dispatch before durable record |
| FT-022 | Logical state and independent physical evidence distinguished |
| FT-023 | Bounded backpressure and qualified safety deadlines; no lost critical safety authority |
| FT-025 | Crash before/after each valve and pump operation, including partial operation |
| FT-027 | Revocation before/after admission/submission, delayed delivery and expiry |
| FT-032 | Correlate command identity, epoch, ordering and evidence freshness |
| FT-033 | Independent protection, emergency capability isolation and rearm |
| FT-034 | Missing, corrupt and stale restored recovery data fail closed |

The other 15 existing designs retain their original IDs and outcomes, with the common oracles above. FT-014 also asserts that reservation release never clears physical quarantine.

| ID | Synthetic condition | Mandatory outcome | Owner |
|---|---|---|---|
| FT-035 | Crash between durable admission and transport submission | Recover outstanding identity; no unsafe replay; inhibit if uncertain | EP-003A/B/004 |
| FT-036 | Previously admitted command remains in transport after revocation/owner replacement | Prove stale delivery excluded where supported; otherwise preserve uncertainty/quarantine | EP-001/003A/B/007 |
| FT-037 | Crash between valve activation and detailed execution log | Pre-dispatch evidence supports partial recovery; no ordinary energization until reconciled | EP-003C/D/004 |
| FT-038 | Emergency capability used for ordinary activation | Zero ordinary adapter submissions | EP-003A/F/007 |
| FT-039 | Protection reset with stale queued work | No ordinary operation before qualified rearm and fresh admission | EP-002/003F |
| FT-040 | Two logical units reference one physical resource | Exclusive resource reservation; conflicting dispatch denied | EP-003D |
| FT-041 | Recovery from obsolete DB snapshot | Unresolved operations cannot silently disappear; fail closed absent reliable recovery evidence | EP-004/003D |
| FT-042 | Logical state conflicts with independent physical evidence | Unknown physical certainty visible; inhibit affected resource | EP-003B/F |

R1a/R1b negative containment oracles must prove unsupported paths cannot submit commands even if complete inventory is deferred; if that cannot be proved, containment does not pass. R2a minimum recovery is required before any simulated ordinary dispatch under the new boundary; synthetic tests may exercise fault paths using isolated devices only. R2b cannot close F-001. Q closure is profile-specific and must not erase unresolved safety findings.
