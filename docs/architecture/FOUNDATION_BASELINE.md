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

Construct -> acquire exclusive authority -> initialize -> reconcile outstanding work/device state -> run -> quiesce -> safely reconcile -> dispose -> release authority. Failed/unknown ownership or unreconciled equipment blocks ordinary energization. Start with single control-capable process plus qualified shared OS locking boundary; multi-host fencing or dedicated runtime process is a later decision. A single worker alone is insufficient. Read-only web mode cannot auto-register equipment or start control jobs. Never prevent appropriate independent emergency protection. Shutdown must retain authority until appropriate reconciliation; safe states depend on device and installation.

Human/API/scheduler/controller/AI intent -> verified identity and resource authorization -> exclusive runtime -> deterministic safety -> adapter -> device outcome -> evidence. Unknown state is not success. Best-effort EventBus is not a durable safety command queue. Physical resource identity is independent of unit IDs; shared pump requires qualified water path. Manual watering does not issue pump commands. Preserve device-specific independent protection; no universal operating limits approved.

## Required target invariants (not implemented claims)

| ID | Requirement |
|---|---|
| INV-001 | One authorized physical runtime per installation |
| INV-002 | Construction cannot grant physical authority |
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
| SAFE-001 | Exclusive runtime executes physical commands |
| SAFE-002 | Authorized principal and resource for every command |
| SAFE-003 | Deterministic safety on all energization |
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
