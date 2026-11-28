# Foundation architecture baseline and proposed target

Baseline: `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`; source review CP0–CP2, 27 November 2026. Current behaviour and target requirements are separate. See [qualification evidence](../qualification/CP0-CP2.md), [findings](../qualification/FINDINGS.md), [decision register](adr/README.md). Target proposals are pending owner acceptance; no implementation is implied.

## Current principal boundaries

| Responsibility | Current implementation | Target ownership |
|---|---|---|
| Presentation | Flask blueprints, Jinja2, Socket.IO | API/UI only; resource authorization |
| Composition | app/__init__.py, ServiceContainer, ContainerBuilder | construct without physical authority |
| Runtime | GrowthService, DeviceCoordinator | explicit exclusive installation lifecycle |
| Events/jobs | EventBus, UnifiedScheduler, SchedulingService | process-local events; scheduler owned by runtime |
| Sensor pipeline | SensorManagementService, SensorPollingService, MQTTSensorService | shared polling with per-unit registrations |
| Climate/plant decisions | ClimateController, ControlLogic, PlantSensorController, ThresholdService | bounded intent, not direct hardware authority |
| Irrigation | IrrigationWorkflowService, detection/execution/feedback services | preserve façade; enforce authorization, resource ownership and reconciliation |
| Execution | ActuatorManagementService, ActuatorEntity, hardware adapters | one mandatory command boundary; typed outcomes |
| Safety | SafetyService and device protections | mandatory deterministic policy; hardware-independent protection separately qualified |
| Storage | repositories, SQLite operations, JSON stores | transactional relational authority; controlled snapshot writers |
| Intelligence | model registry, prediction, training, monitoring, personalized learning | advisory/validated inference; no implicit authority |
| Sharing | local condition profiles/snapshots | CAP-001; future separate knowledge plane |

Current production entry point bootstraps runtime; container construction can start scheduler/MQTT even with hardware bootstrap disabled. Two configured web workers can construct multiple runtimes; actual competing physical execution not reproduced (F-001). Process-local singletons are not cross-process locks. Existing atomic irrigation claims/unit locks do not establish installation-wide authority. Legacy architecture document references a superseded runtime wrapper; preserve it as historical design material.

SQLite WAL, repository protocols and hardware-aware memory settings exist. JSON store under var/ has advisory lock and atomic replace but no whole read-modify-write guarantee; model registry and personalized profiles use other file stores. Transactions, recovery and concurrent writers require EP-004/CP4. Do not infer PostgreSQL portability from marker protocols.

## Proposed lifecycle and trust boundaries

Passive construct -> acquire exclusive authority (reconciliation only) -> establish recovery evidence and qualified initialization prerequisites without ordinary effects -> reconcile outstanding work/device state (qualified bounded recovery effects only) -> qualified ordinary admission/run -> quiesce -> safely reconcile -> qualified disposal -> release authority. Failed/unknown ownership or unreconciled equipment blocks ordinary energization. Start with single control-capable process plus qualified shared OS locking boundary; multi-host fencing or dedicated runtime process is a later decision. A single worker alone is insufficient. Read-only web mode cannot auto-register equipment or start control jobs. Never prevent appropriate independent emergency protection. Shutdown must retain authority until appropriate reconciliation; safe states depend on device and installation.

Human/API/scheduler/controller/AI intent -> verified identity and resource authorization -> exclusive runtime -> deterministic safety -> adapter -> device outcome -> evidence. Unknown state is not success. Best-effort EventBus is not a durable safety command queue. Physical resource identity is independent of unit IDs; shared pump requires qualified water path. Manual watering does not issue pump commands. Preserve device-specific independent protection; no universal operating limits approved.

## Required target invariants (not implemented claims)

| ID | Requirement |
|---|---|
| INV-001 | One authorized physical runtime per installation |
| INV-002 | Passive construction and non-owner paths cannot grant physical authority or produce unauthorized consequential interface effects |
| INV-003 | All energizing paths pass mandatory safety |
| INV-004 | Ownership enforced before operations |
| INV-005 | Unit stop cannot interrupt other units |
| INV-006 | Disposed controllers cannot process control work |
| INV-007 | Lock release is owner-bound |
| INV-008 | Failed transactions cannot commit partial work |
| INV-009 | Unknown device state is not verified success |
| INV-010 | Unvalidated models have no production authority |
| INV-011 | External AI cannot bypass policy |
| INV-012 | Optional services cannot break local independence |

| ID | Safety acceptance invariant |
|---|---|
| SAFE-001 | Exclusive runtime owns ordinary consequential interface effects including lifecycle paths; independent protective mechanisms and narrowly qualified emergency recovery remain distinct |
| SAFE-002 | Authorized human or explicitly scoped service principal, resource and action for every ordinary consequential effect |
| SAFE-003 | Deterministic device-specific safety on all consequential effects including initialization and cleanup |
| SAFE-004 | Required irrigation approval revalidated at execution |
| SAFE-005 | Missing/stale required observations block ordinary autonomous execution |
| SAFE-006 | Dispatch distinct from physical verification |
| SAFE-007 | Uncertain OFF never reported verified |
| SAFE-008 | Exclusive physical-resource reservation |
| SAFE-009 | Stale owners cannot release current reservations |
| SAFE-010 | Restart reconciles outstanding operations |
| SAFE-011 | Critical operating bounds independent of application process |
| SAFE-012 | Unknown/unsupported physical commands rejected |
| SAFE-013 | External agents cannot override local safety |
| SAFE-014 | Rejection distinct from transport failure |
| SAFE-015 | Consequential operations have traceable outcomes |

Device-specific qualification: GPIO safe boot/failure, MQTT/Zigbee delivery and state, Wi-Fi trusted destination/response, Modbus response validation, ESP32 firmware/transaction safety. Pumps/valves, heaters, humidifiers, lights, ventilation and any CO2 equipment require device-appropriate safeguards and safe states. No hardware certification is established.

## G0.1 target contract refinements (proposed; not implementation evidence)

Ownership acquisition grants reconciliation authority only, not energization permission. The runtime starts inhibited; durable outstanding operations and resource quarantine must be recovered before normal command admission. An OS lock may disappear after process death; lock acquisition is not proof of physical state. Unresolved or unavailable recovery evidence remains fail-closed, including loss/corruption of the persistence store. Persist or otherwise establish an independently reliable record of operation identity, resource identity, owner/fence, outcome and unresolved quarantine before consequential dispatch; do not lose the quarantine when reservations expire. Recovery must account for commands in flight, delayed delivery and stale owners. If an old owner or command cannot be reliably excluded, do not resume ordinary operation.

Normal software actuation is exclusively owned; independent protective hardware and narrowly scoped, qualified emergency recovery are distinct from routine command authority. Never disable or obstruct independent protection. Define recovery access, authority, audit evidence and safe limits per device; emergency authority cannot be reused to authorize normal energization.

A command authorization is scoped to the operation, authenticated principal or explicitly authorized service identity, physical resource/topology, policy/configuration revision, runtime owner/fence and validity period. Revalidate these and required fresh observations at the final admission boundary. Cancellation, expiry, permission revocation, policy changes, resource reassignment or owner replacement invalidate stale admission. Define the dispatch linearization point: before it a cancellation that wins prevents dispatch; after it reconcile an outstanding physical operation instead of claiming it never ran. Use durable identifiers, bounded retries and correlation; do not replay uncertain consequential actions blindly.

| Outcome | Evidence required |
|---|---|
| Requested | Identifiable intent received; no physical claim |
| Authorized | Current principal, resource, policy, owner and safety admission checks passed; no dispatch claim |
| Dispatched | Transport/adapter submission established; no physical claim |
| Acknowledged | Correlated, defined acknowledgement of the expected operation; acknowledgement alone is not physical verification |
| Verified | Fresh, device-appropriate evidence of expected physical state; distinguish reported/logical state from physical verification |
| Rejected | Policy denied admission before consequential dispatch |
| Failed | A known processing/transport/device failure; does not establish physical OFF |
| Unknown | Physical outcome cannot be established, including ambiguous delivery, missing/stale evidence or failed reconciliation |

Failure of a stage does not erase possible device effects. Track operation processing and physical-state certainty separately. For uncertain shutdown, retain durable quarantine until qualified reconciliation; never promote a stale acknowledgement or a successful publish into physical verification. See [remediation plans](../plans/REMEDIATION.md).

## G0.2 dispatch and rearm refinements

D0 must define the authoritative atomic durable admission event, revocation ordering, transport submission, delivery, expiry and fencing capability per transport. A committed admission is not delivery. Cancellation after admission attempts qualified cancellation if supported and reconciles effects; revocation after admission cannot be assumed to prevent delivery. If stale or delayed effects cannot be reliably excluded, preserve durable uncertainty and inhibit affected resources. Record operation identity, resource, owner epoch, policy revision, validity and recovery evidence before any consequential submission; missing/corrupt/stale recovery data fails closed. Never blindly replay.

Independent intervention invalidates pre-intervention ordinary authority. Emergency permission is restricted to qualified recovery, not ordinary energization. Rearm requires device-specific qualified conditions, reconciliation, invalidation of stale work, and fresh ordinary admission. Protection reset alone grants no authority. Minimum durable recovery precedes any consequential dispatch; R2b qualifies bounded process/dispatch ownership only; full F-001 closure at Q after R3a/R3b. See [D0 contracts](../plans/D0-CONTRACTS.md) and [qualification profiles](../qualification/QUALIFICATION-PROFILES.md). These are proposed requirements, not accepted design or implemented safeguards.

## G0.3 physical-interface containment and combined recovery

A consequential physical-interface effect includes any operation capable of altering device state, output configuration, transport/device command queues or protective behavior. Cover construction, registration, initialization, discovery, reconnect/replay, normal dispatch, disposal and cleanup. Non-owner or inhibited ordinary paths must produce zero unauthorized consequential interface effects, not merely zero command method calls. Qualify instrumentation at the lowest relevant synthetic GPIO/transport/device boundary using actual composed services; include pin mode/setup, cleanup, publication/replay and state-restoring initialization as applicable. Passive observation is not authority for consequential initialization. Unknown effect classification is denied. Consequential initialization or cleanup requires qualified ownership, resource/action permission, recovery evidence and device-specific safety; no ordinary effects until R2a minimum recovery and applicable command contracts exist. Separately bounded and qualified emergency/reconciliation mechanisms are not ordinary authority; do not obstruct independent protection.

Protective intervention, invalidated authority, durable emergency inhibition, unresolved transport effects and physical quarantine must be reconciled jointly after process loss or stale restoration. A safe observation cannot clear earlier unresolved effects; absent reliable evidence fail closed. Qualified rearm requires applicable recovery/protective conditions, exclusion of stale effects and fresh authorization. EP-007 determines scoped human/service permissions (scheduler, controllers, calibration, ML, workers and future integrations); EP-003A enforces them before consequential effects with no privileged fallback. EP-001/002 own passive lifecycle; EP-003D quarantine policy; EP-004 reliable persistence. See [D0 contracts](../plans/D0-CONTRACTS.md) and [remediation](../plans/REMEDIATION.md). Requirements only.
