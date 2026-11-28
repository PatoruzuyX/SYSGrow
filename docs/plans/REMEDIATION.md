# Foundation bounded remediation ExecPlans

Status: proposed, CP1 plans revised by CP2. No implementation authorized except G0 documentation. Baseline `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`. Each package must pin its actual starting HEAD, record dependencies and acceptance, use synthetic tests and stop at independent review/owner integration approval. See [findings](../qualification/FINDINGS.md), [invariants](../architecture/FOUNDATION_BASELINE.md), [guidelines](../guidelines.md). Revert unmerged changes or use a reviewed rollback of only the package; persistence/physical recovery requires separate safe procedures. No package grants deployment or hardware operation.

## EP-001 — SYSGROW-RUNTIME-OWNERSHIP-001 (rev 0.2)

F-001 Critical. R1a containment; R2b bounded ownership; full EP-001/F-001 closure only at Q. Candidate paths: smart_agriculture_app.py, app/__init__.py, app/services/container.py and container_builder.py, scheduler CLI, deployment and targeted tests. M0 baseline; M1 lifecycle/authority contract; M2 exclusive ownership; M3 construction-only mode; M4 reconcile entry points; M5 deny non-owner at all physical boundaries; M6 concurrency/crash/restart tests; M7 review. Initially single control process plus shared OS lock; verify lock boundary and failure semantics. No distributed orchestration, frontend/ML redesign, topic migration or production activation. Acceptance: simultaneous startup one owner; non-owner cannot register/control; CLI cannot bypass; passive construction no control workloads or unauthorized consequential interface effects (including initialization and cleanup); ownership held through shutdown; restart reconciliation; simulated termination cannot create competing command authority. Depends on CP2 safety requirements and accepted ownership ADR; coordinate EP-003A non-owner enforcement. FT-001/015/016.

## EP-002 — SYSGROW-RUNTIME-LIFECYCLE-001 (rev 0.2)

F-023/024/025/028. M1 installation vs unit ownership; M2 unit-specific poll registrations; M3 disposable subscriptions; M4 invalidate queued work; M5 ordered quiescence and recovery; M6 regression; M7 review. Preserve EventBus and shared poller. Unit A stop cannot interrupt B; repeated start/stop idempotent; disposed controllers cannot command or produce unauthorized consequential interface effects; partial start rolls back; device-appropriate shutdown reconciled or unknown; no resource growth under repetitions. Depends on bounded R2b ownership evidence and applicable R3a/EP-003 device contracts; not full EP-001 closure (reserved for Q). Exclude wholesale event platform replacement. FT-013/016/023.

## EP-003 — SYSGROW-ACTUATOR-SAFETY-001 (rev 0.2)

Critical F-033/034/035 plus F-002/003/004/016/025/026/027/039/040/041/042/044. Preserve actuator manager, irrigation façade and existing safeguards. Each subplan requires independent authorization and review.

| Subplan | Bounded scope | Acceptance / tests |
|---|---|---|
| EP-003A | F-026/034; classify all command paths, mandatory authorization/safety/ownership; reject unknown protocol operations | all ON/toggle/level/pulse/adapter and consequential lifecycle paths deny unauthorized effects; scoped service principals; no bypass; FT-005/007/019/043/045 |
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

F-012/014/020/021. G0 documentation only; proposed branch docs/sysgrow-governance-001. Preserve all historical records and refs, add canonical guidance, evidence, candidate ADRs, roadmap and plan links. G0/G0.1/G0.2/G0.3 acceptance: all 44 OPEN, all four Critical mapped to gates; documentation-only diff, traceable original reports, verified links and evidence anchors, three independently generated exact-HEAD reviews, successful applicable exact-HEAD CI, effective check-enforcement evidence and separate owner integration approval. See [G0 review record](../qualification/G0-REVIEW.md). Branch enforcement and individual historical recovery remain open; settings changes and branch deletion excluded. No finding automatically closed.

## EP-007 — SYSGROW-SECURITY-BOUNDARIES-001

F-004/005/018/036/037/038/043. M1 verified identity (no implicit fallback); M2 resource permissions; M3 HTTP/public allowlists/CSRF; M4 Socket.IO authenticated memberships/revocation; M5 broker identity/ACL/transport; M6 privileged firmware maintenance/provenance; M7 security regression/review. Acceptance: deny anonymous/prohibited direct and child resource access and missing/disabled/revoked or insufficiently scoped internal service principals; no privileged fallback; no cross-unit subscriptions, public health minimal, invalid firmware trust rejected, no leaked raw internal exceptions; comprehensive SQL review with allowlists/parameter binding. EP-003 owns command and physical outcome, EP-007 owns principal and transport authorization. No live penetration test or external agent authority. FT-017/018/024.

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

## Proposed checkpoint dependency graph (G0.3)

This is a planning correction, not authorization or accepted architecture. Dependencies below are checkpoint-level; cross-package cooperation is not a declaration that a complete dependent package is already qualified. Each implementation checkpoint requires its own owner authorization, exact baseline, exclusions, test matrix, rollback/recovery procedure and review.

| Checkpoint | Prerequisites | Bounded exit |
|---|---|---|
| D0 | Qualified G0 integration | Accept individual ADRs and all mandatory interfaces in [D0 contract matrix](D0-CONTRACTS.md); no implementation or activation |
| R1a | D0 | EP-001 containment: exclusive authority before control workloads; construction-only non-owner path; install deny-by-default guard and block any unclassified, unqualified or recovery-dependent ordinary dispatch. Prove zero unauthorized consequential physical-interface effects at the lowest relevant synthetic boundary from denied paths, including constructor, registration, initialization, discovery/CLI, reconnect/replay, disposal and cleanup; no adapter-command-only oracle. Unknown or unqualified effects denied. No ordinary energization until minimum recovery and applicable command contracts qualified; no F-001 closure |
| R1b | D0, R1a | EP-003C containment: default strict inhibition of automatic/scheduled irrigation, pending/legacy/unclassified execution and unauthorized direct irrigation paths; retain manual observation logging without actuation or any consequential interface effect; prove zero unauthorized effects at the lowest relevant boundary under strict inhibition and the alternative. A separately authorized alternative may implement and synthetically qualify EP-004 minimum atomic admission/claim and EP-007 identity checks within R1b, but cannot lift R1a inhibition or any other prerequisite. No mock-only contract or non-atomic precheck substitutes for enforcement; no full EP-003C closure |
| R2a | R1a, R1b | EP-003A/B and EP-007 applicable enforcement: complete consequential effect and command-origin inventory, scoped internal identities and final admission classification, authorization, typed outcomes and real synthetic composition; implement and qualify minimum durable operation/resource identity, owner epoch, pre-dispatch record, atomic claim/revocation ordering, restart inhibition, quarantine surviving lease release and corrupt/missing/stale recovery evidence (EP-004/003D). No consequential ordinary dispatch without all relevant minimum contracts; synthetic only |
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

## Fault-design acceptance oracles (G0.3)

All FT-001–045 are designs, not executed tests. Each authorized implementation plan must define fixture topology, actual composed services, synthetic adapters, isolated persistence, controlled clocks, deterministic barriers, injection point, expected durable state and captured adapter calls. No real broker/device/provider. Assert denial means zero unauthorized consequential physical-interface effects, not merely zero command submissions or an error status. Instrument the lowest relevant synthetic interface, including configuration/setup, cleanup, discovery/reconnect/replay and transport effects, with a positive control proving instrumentation detects the effect. Unknown classification or incomplete coverage is HOLD. Assert unknown physical outcome, quarantine and ownership survive restart and reservation expiry. Device-specific deadline/limit values must be separately qualified; unavailable evidence is not N/A.

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

R1a/R1b negative containment oracles must prove unsupported or inhibited ordinary paths cannot produce unauthorized consequential interface effects, even if complete inventory is deferred; if that cannot be proved, containment does not pass. Independent protection and separately qualified bounded emergency/reconciliation authority are not ordinary effects or a bypass. No consequential initialization without qualified ownership, recovery and device-specific limits. R2a minimum recovery is required before any simulated ordinary dispatch under the new boundary; synthetic tests may exercise fault paths using isolated devices only. R2b cannot close F-001. Q closure is profile-specific and must not erase unresolved safety findings.

## G0.3 mandatory fault-design extensions

These extend, not replace, FT-001–042. Apply the common oracles above. The detailed review matrix marks ten distinct existing IDs for extension; FT-025 receives both lifecycle and combined-recovery extensions. Apply all eleven extension assignments.

| ID | Additional mandatory oracle |
|---|---|
| FT-001 | Separate processes; instrument construction, registration and initialization at lowest relevant interface; non-owner produces zero unauthorized effects |
| FT-016 | Repeated start/stop, discovery/reconnect, disposal and cleanup including stale callbacks; zero unauthorized interface effects; independent protection preserved |
| FT-018 | Human and service identities missing, disabled, revoked or authenticated but out of resource/action scope; shared-resource conflicting permissions deny before consequential effects |
| FT-025 | Owner crash at lifecycle initialization and partial operation boundaries; combined FT-044 scenario; no unauthorized recovery-side effect |
| FT-027 | Per-origin service authorization, stale policy/config revision and revocation on both sides of admission; deny before admission or reconcile possible effects thereafter |
| FT-033 | Protective intervention combined with process loss, stale restoration and unresolved transport; independent inhibition survives or fails closed |
| FT-034 | Restored snapshot predating protective intervention cannot erase invalidation/quarantine or authorize rearm |
| FT-036 | Delayed transport delivery remains possible after protection/replacement; a safe instantaneous observation cannot clear quarantine |
| FT-039 | Reset with queued or in-flight stale work plus owner replacement; no ordinary rearm until reliable exclusion/reconciliation and fresh authority |
| FT-041 | Obsolete persistence restoration jointly with protective intervention and unresolved transport; fail closed if trustworthy evidence absent |

FT-025 is shared between lifecycle and combined recovery. The report summary says eleven existing designs, but its detailed matrix identifies ten distinct IDs; preserve the original report and address every marked ID plus FT-025's two overlapping extensions. Do not count refinements as new tests.

| ID | Synthetic condition | Mandatory outcome | Accountable owner / dependencies |
|---|---|---|---|
| FT-043 | Non-owner or inhibited constructor, registration, initialization, discovery, reconnect, disposal or cleanup capable of consequential effects | Lowest-interface instrumentation detects effects in positive control; denied path produces zero unauthorized effects; no ordinary initialization before qualified ownership/recovery/device contract | EP-001 / EP-002, EP-003A |
| FT-044 | Outstanding admitted transport effect; protection intervenes; crash before reconciliation; restore obsolete record; replacement obtains lock and observes apparently safe state | Jointly assert durable/independently reliable invalidation, owner epoch, inhibition, quarantine and unresolved delivery; no ordinary effects or rearm while stale effect possible; missing evidence fails closed; only qualified reconciliation and fresh admission after exclusion | EP-003F / EP-001, EP-003B/D, EP-004 |
| FT-045 | Each internal origin (scheduler, climate/plant controllers, calibration, ML, background workers and future integration) requests out-of-scope effect with missing/disabled/revoked or insufficient identity, stale policy/config, conflicting resource scopes | Zero unauthorized consequential effects before admission; no implicit privileged fallback; a valid identity or runtime lock does not substitute for action/resource permission; after admission reconcile possible effects | EP-007 / EP-003A |

These are synthetic designs only. Q combines recovery, transport and emergency faults, not merely independently passing individual tests. HIL is governed separately by [qualification profiles](../qualification/QUALIFICATION-PROFILES.md); no real equipment in G0.3.

## R1 proposed evidence and fault-design refinements

EP-006 original-report prerequisite stays binding until valid limited candidate-scoped substitution under [EGA-001](../qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md); all remaining CI/enforcement/review/approval gates unchanged. [Replacement matrix](../qualification/EVIDENCE-REBASELINE-001.md) supplements closure criteria without changing finding owners, staged dependencies or proposed ADRs. EP-005 reproducible installation/OS/Python/ARM prerequisites complement CP3 measurement for F-015; CP4 registry durability depends on EP-004; EP-004/CP4 calibration through actual service composition coordinates EP-003E. EP-007 maintenance authority/artifact/destination trust consumes EP-003A/B admission/outcomes and EP-003F recovery. ER-04 downstream trust HOLD for applicable firmware/device maintenance and activation qualification; source absence does not establish a downstream defect or waive later evidence. No HIL or OTA under this checkpoint.

| Existing FT identifiers | Additional mandatory synthetic design oracle |
|---|---|
| FT-005/007/019/043 | Actual factory-created registered actuator vs unregistered discovery path; correct interface mismatch only with mandatory admission. Demonstrate positive instrumentation and zero unauthorized consequential effects including construction/cleanup. |
| FT-005/006/022 | Composed calibration signature, finite positive bounded inputs, typed failure, independently established elapsed runtime, uncertain OFF/cancel/restart durable reconciliation; no truthiness success. |
| FT-002/003/004/020/030 | Pending approval, manual/disabled changes, expired/replaced due timestamp, failed persisted approve/delay/cancel, expected-state/version CAS; no unauthorized effect or false success. |
| FT-008/011/029/032 | Real synthetic wrapper/adapter composition and conditional overrides; incompatible call/known failure/offline queue/ambiguous transport distinguished; correlated outcomes. |
| FT-013/015/016/025/037/040/044 | Valve uncertainty before detailed log, completion before uncertain valve close, reservation release independent of quarantine, premature shutdown completion/ignored stop False, failure at every step and restart; no false physical success. |
| FT-017/018/045 | Identity consistency (user vs user_id), no implicit privileged fallback, direct/child resource permission, service scopes, revoked session/room membership; verify actual absence of protected delivery, not merely rejection response. |
| FT-021/042 | Returned rejection or persistence failure without exception cannot produce successful execution or durable promotion; reconcile actual outcome. |
| FT-024/027/036 | Privileged maintenance principal/action/target, trusted artifact, exact destination identity preserved, offline queue known vs sent, expiration/revocation and stale effects, missing acknowledgement unknown, interrupted update durable inhibition, unexpected identity or failed rearm blocks ordinary activation. |
 
FT-024 downstream cases require separately authorized applicable bridge/device source and qualification plan; no firmware test here. All 45 unique FT designs retained, none executed. Existing acceptance oracles are cumulative, not replaced by this extension. CP4 additional synthetic ML validation must distinguish readiness, enablement, selection, eligibility, promotion, artifact trust and durable restart; no-evidence abstention, invalid auxiliary artifact rejection, failed persistence and concurrent writer tests. No model or runtime execution. No new fault ID or architecture required.

## R2 bounded additional fault-design oracles (not executed)

These requirements extend the existing FT designs, not replace their original oracles. Use actual isolated service composition, synthetic fixtures, controlled clocks, deterministic barriers, isolated persistence and lowest-interface positive controls. No runtime, ML or physical execution under this checkpoint.

| Existing FT identifiers | Required additional synthetic scenario and oracle |
|---|---|
| FT-008/024/027/029/032 | Queue at capacity (including zero/invalid capacity policy): explicit admission or rejection; every admitted ID accounted for including eviction/expiry, no silent disappearance. Preserve exact destination across queue/replay and current authority. Known replay publication failure or compatible-client non-success result never recorded as sent; explicit terminal failure or safely retained reconcilable operation. Ambiguous delivery preserves durable uncertainty/quarantine, no blind consequential retry. Mismatched, stale, duplicate or unrelated operation/target/transaction response cannot establish completion or physical verification; validate before status/callback. Positive control detects actual attempted publication; actual compatible and incompatible wrapper composition distinguished. |
| FT-005/006/020/022 | Failed/rejected start cannot create successful session; independently enforced device-specific authorized operating bound, synthetic clock reaches limit and qualified stop mechanism invoked; verify actual finite bounded measured volume and independently established elapsed runtime (not requested duration). On missing/failed/unknown shutdown, cancellation, restart or persistence False/exception/uncertain commit, retain operation identity and unresolved state, no durable calibration success or eligibility; successful control requires verified shutdown and exactly intended durable data. EP-003E, EP-003F and EP-004. |
| FT-004/020/030 | Missing row, wrong expected state/version, zero or unexpected affected rows, False, commit failure or ambiguity: reject/conflict or hold for reconciliation, no successful approval/delay/cancel, no associated preference-learning/ML-collected effects or unauthorized physical effect. Positive control exactly one intended committed transition; learning causally linked to committed operation and idempotent. Preserve prior timing, authorization and stale-work oracles. |

### CP4 negative lifecycle and bundle-coherence qualification design

The owner authorization referred to eleven cases; the R1 Reviewer 3 table actually contains twelve rows. All twelve are retained below; no new FT identifiers. These are design requirements, not results. CP4 owns lifecycle/statistical eligibility, EP-004 supplies durable registry/persistence, CP6 consumes qualified artifact trust where applicable, EP-003A and EP-007 enforce physical admission independently. Use synthetic inert artifacts and instrumentation; no untrusted artifact deserialization.

| Case | Mandatory measurable oracle |
|---|---|
| Training saves dictionary metadata without status | Candidate persisted non-production; no active entry/production selection or implicit promotion; exercise actual trainer callers and all supported registry representations |
| Registry contains only inactive versions | No eligible production version returned; no inference from inactive fallback; explicit abstention |
| Invalid or null error metric | Present malformed/null and absent required keys distinguished; eligibility denied for invalid required evidence, no default zero; alternate criteria use only valid explicitly permitted evidence |
| Non-finite or impossible metric | Reject NaN, +/-infinity and metric-specific out-of-domain values before favorable predicate; valid negative R² not mislabeled impossible |
| No prediction history or ground truth | Evidence unavailable, not perfect performance; no promotion/eligibility based on favorable defaults |
| Trainer returns unsuccessful result | No COMPLETED/job-success/training-complete broadcast for failure/cancellation; prior production version not new candidate identity |
| Registry persistence fails | No successful durable registration/promotion, no false successful retraining; retain/reconcile prior valid state and uncertainty after restart |
| Production version changes during loading | One immutable manifest-bound model/required auxiliaries/metadata/schema version or safe rejection; deterministic barrier during actual composed bundle load |
| Invalid scaler or encoder | Instrument deserializer; zero calls for invalid/substituted/missing required artifact, positive control proves instrumentation; verify integrity and containment before loading |
| Trust or eligibility revoked after caching | Recheck current scoped trust and eligibility on subsequent use, no unauthorized inference, invalidate stale cached bundle; qualified re-admission only |
| Different model and metadata versions | Reject mismatch before use, no borrowed metrics; bind every required component and verification to the immutable version |
| Eligibility passes but control policy denies action | Actual composed lowest-interface instrumentation shows zero unauthorized consequential physical effects; advisory inference cannot grant physical authority |

Required positive controls must establish valid trusted coherent eligible candidate handling and separately authorized deterministic admission in synthetic composition, not production operation. Preserve existing metric thresholds/no-fallback safeguards pending qualified change. All 45 FT designs retained, zero executed; CP4/CP6 downstream evidence and ER-04 remain separate.
