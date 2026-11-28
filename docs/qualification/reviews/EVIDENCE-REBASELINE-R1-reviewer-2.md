# **SYSGROW-EVIDENCE-REBASELINE-001-R1**

## **Independent requalification — Reviewer 2: Security and Physical Safety**

**Review date:** 28 November 2026\
**Repository:** [PatoruzuyX/SYSGrow](https://github.com/PatoruzuyX/SYSGrow?utm_source=chatgpt.com)\
**Pull request:** [#3](https://github.com/PatoruzuyX/SYSGrow/pull/3?utm_source=chatgpt.com)\
**Review authority:** Independent, read-only qualification.

This review assesses whether the R1 corrections establish a defensible replacement technical evidence basis. It does not assess remediation completion or authorize physical operations.

## **1. Candidate identity and change containment**

| Identity                | Revision                                   |
| ----------------------- | ------------------------------------------ |
| Candidate HEAD          | `47794834e009334aa417b913fcc6818407ad234e` |
| Declared candidate tree | `1f29e1d88a612712d957914d0f37c0e8af0b3e97` |
| Superseded rebaseline   | `a10107a4f78eea8c37a0b1a6ab7d616a61b4df87` |
| Application baseline    | `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21` |

Fresh GitHub retrieval confirms that PR #3 points to the authorized candidate HEAD and application baseline.

Commits ahead of application baseline

# **6**

Commits behind baseline

# **0**

R1 changed paths

# **17**

All Markdown

Cumulative changed paths

# **39**

All Markdown

| Verification                                        | Result                               |
| --------------------------------------------------- | ------------------------------------ |
| PR HEAD matches assignment                          | PASS                                 |
| PR base matches authorized baseline                 | PASS                                 |
| Superseded candidate is ancestor, one commit behind | PASS                                 |
| Documentation-only comparison                       | PASS                                 |
| Deleted application paths                           | None                                 |
| PR state                                            | Open, draft, unmerged                |
| GitHub mergeability                                 | True — not integration authorization |

Primary evidence: [candidate commit](https://github.com/PatoruzuyX/SYSGrow/commit/47794834e009334aa417b913fcc6818407ad234e?utm_source=chatgpt.com), [R1 comparison](https://github.com/PatoruzuyX/SYSGrow/compare/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87...47794834e009334aa417b913fcc6818407ad234e?utm_source=chatgpt.com), [cumulative baseline comparison](https://github.com/PatoruzuyX/SYSGrow/compare/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21...47794834e009334aa417b913fcc6818407ad234e?utm_source=chatgpt.com).

The GitHub connector confirms the commit and comparison metadata. Its returned commit representation does not expose the raw Git tree identity; the declared tree matches the PR author's record, but is not independently certified through that representation.

**Change containment: PASS for the directly inspected GitHub comparisons.** Raw tree verification remains a separate evidence limitation.

## **2. Review continuity**

I retrieved the archived initial Reviewer 2 report from the exact R1 candidate. The returned Git blob is:

`d76d4e7279211cf8d2c79b3acf0dec710a4ce286`

The report contains 1,149 lines and retains its original HOLD verdict.

The historical correction mapping is preserved:

| Original review observation                       | R1 correction |
| ------------------------------------------------- | ------------- |
| ERB-SS-01 — Registered command composition        | REB-04        |
| ERB-SS-02 — Firmware maintenance and replay       | REB-05        |
| ERB-SS-03 — Actual dependency composition         | REB-06        |
| ERB-SS-04 — Physical-resource coordination        | REB-12        |
| ERB-SS-05 — Admission, authorization and recovery | REB-12        |
| ERB-SS-06 — Fault-test oracle completeness        | REB-13        |

Evidence: [archived Reviewer 2 report](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/reviews/EVIDENCE-REBASELINE-reviewer-2.md?utm_source=chatgpt.com), [R1 correction record, L7–24](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-REBASELINE-R1-REVIEW.md?utm_source=chatgpt.com#L7-L24).

A direct comparison of the canonical finding rows and replacement matrix returned 44 matching rows across the first seven fields, including severity, classification, owner and OPEN disposition.

This establishes structural continuity, not the technical sufficiency of each observation.

## **3. Independent requalification verdict**

# **HOLD**

Reviewer 2

The original security review observations have been substantially addressed. However, additional inspection of calibration persistence and firmware command tracking exposes consequential outcome-integrity gaps that require explicit evidence and fault-test coverage.

Critical

# **0**

High

# **2**

Medium

# **1**

Low

# **0**

New candidate review observations, separate from the 44 foundation findings.

| Qualification area                                | Disposition                                   |
| ------------------------------------------------- | --------------------------------------------- |
| Original REB-04 correction                        | PASS                                          |
| Original REB-05 correction                        | PASS — bounded source observations            |
| Original REB-06 correction                        | PASS — composition evidence                   |
| Original REB-12 correction                        | PASS — principal observations                 |
| REB-13 fault-test completeness                    | HOLD                                          |
| Four Critical finding definitions and severities  | PASS                                          |
| Replacement technical evidence sufficiency        | HOLD                                          |
| Downstream firmware trust                         | HOLD — separate applicable qualification gate |
| EGA-001 security and safety boundary preservation | PASS                                          |
| EGA-001 acceptance readiness                      | HOLD                                          |
| Historical provenance recovery                    | HOLD                                          |
| Integration qualification                         | HOLD                                          |
| Production safety                                 | NOT QUALIFIED                                 |

The HOLD is narrower than the initial Reviewer 2 verdict. The previous composition inaccuracies are corrected. The remaining technical concerns involve additional directly observable failure paths within the existing findings, rather than a need to redesign the foundation architecture.

## **4. Independent challenge of the four Critical findings**

**F-001 — Competing runtime ownership**

EP-001 · Critical · Verified

Replacement principal observation: PASS

OPEN

**F-033 — Required irrigation approval not enforced**

EP-003C · Critical · Verified

Replacement principal observation: PASS

OPEN

**F-034 — Protocol-specific command safety bypass**

EP-003A · Critical · Verified

Replacement principal observation: PASS

OPEN

**F-035 — False physical-operation success**

EP-003B · Critical · Verified

Replacement principal observation: PASS

OPEN

All four Critical severity ratings remain justified. No downgrade, closure or physical qualification is recommended.

### **4.1 F-001 — Competing runtime ownership**

**PASS — replacement technical observation.**

I independently reproduced the following composition chain.

**Gunicorn**

Two configured workers

Application construction

bootstrap_runtime=True

ServiceContainer.build()

**Scheduler**

Starts by default

**MQTT**

Conditional connection

**GPIO**

Conditional setup effects

Static composition and potential effects, not an observed runtime execution.

| Pinned application evidence                                                                                                                                                                               | Verified observation                                               |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| [Dockerfile L77–83](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/Dockerfile?utm_source=chatgpt.com#L77-L83)                                                        | Two workers configured                                             |
| [smart_agriculture_app.py L16–36](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/smart_agriculture_app.py?utm_source=chatgpt.com#L16-L36)                            | Runtime bootstrap enabled                                          |
| [app/**init**.py L106–144](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/__init__.py?utm_source=chatgpt.com#L106-L144)                                          | Constructs container and registers shutdown handlers               |
| [container.py L137–159](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container.py?utm_source=chatgpt.com#L137-L159)                                   | Scheduler configured independently of coordinator flag             |
| [scheduled_tasks.py L1525–1540](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/workers/scheduled_tasks.py?utm_source=chatgpt.com#L1525-L1540)                    | Scheduler starts by default                                        |
| [MQTT wrapper L121–153](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/mqtt/mqtt_broker_wrapper.py?utm_source=chatgpt.com#L121-L153)                    | Constructor attempts connection                                    |
| [GPIO relay L27–104](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/actuators/relays/gpio_relay.py?utm_source=chatgpt.com#L27-L104)                     | Conditional setup, output and cleanup effects                      |
| [Actuator management L181–187](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L181-L187) | Discovery registration and device-list request during construction |

**Counterexample:** Running a single web worker or disabling MQTT can eliminate particular competing-runtime scenarios, but neither establishes exclusive installation authority across entry points, replacement processes, recovery and GPIO lifecycle operations.

The inherited R1a containment, R2b bounded ownership and Q full-closure requirements remain appropriate.

**Disposition:** Critical / Verified / OPEN.

### **4.2 F-033 — Required irrigation approval not enforced**

**PASS — principal defect and R1 timing correction.**

The actual execution chain is now adequately represented.

| Pinned application evidence                                                                                                                                                                                 | Verified behaviour                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| [ContainerBuilder L1087–1099](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container_builder.py?utm_source=chatgpt.com#L1087-L1099)                     | Wires actuator and scheduling dependencies                                  |
| [Workflow service L615–680](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_workflow_service.py?utm_source=chatgpt.com#L615-L680)   | Registers execution and completion tasks                                    |
| [Detection service L240–312](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_detection_service.py?utm_source=chatgpt.com#L240-L312) | Creates request and conditionally sends approval notification               |
| [Database claim L204–262](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/ops/irrigation_workflow.py?utm_source=chatgpt.com#L204-L262)          | Claims pending, approved and delayed requests                               |
| [Execution service L88–102](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L88-L102)   | Executes claimed requests                                                   |
| [Execution service L244–361](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L244-L361) | No mandatory required-approval revalidation before consequential operations |

The detection source is particularly useful because `config.require_approval` governs notification creation in that inspected block. Notification policy is not final execution authority.

#### **Delayed-request counterexample**

Illustrative synthetic timestamps, not an observed irrigation incident.

The SQL uses an OR relationship between the original scheduled timestamp and the delayed timestamp. Therefore, the earlier timestamp can make the request eligible before its replacement delay expires.

The R1 correction correctly captures this defect without asserting that irrigation actually occurred.

Existing safeguards remain relevant: expiry filtering, transactional claim acquisition, missing-actuator checks and unit-lock acquisition. None establishes required approval.

**Disposition:** Critical / Verified / OPEN. Preserve strict R1b containment and full EP-003C qualification at Q.

### **4.3 F-034 — Protocol-specific command safety bypass**

**PASS — REB-04.**

The primary source discrepancy from the initial rebaseline has been corrected.

**Registered actuator**

ActuatorFactory

adapter=adapter

ActuatorEntity

Declares adapter

Service accesses \_adapter

Interface mismatch

**Discovery fallback**

No matching registered actuator

ZigbeeManagementService

Underlying MQTT client

Separate transport path

Pinned evidence:

| Source                                                                                                                                                                                                      | Observation                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| [ActuatorFactory L62–103](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/actuators/factory.py?utm_source=chatgpt.com#L62-L103)                            | Constructs entity with `adapter`                              |
| [ActuatorEntity L159–194](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/domain/actuators/actuator_entity.py?utm_source=chatgpt.com#L159-L194)                     | Declares `adapter`                                            |
| [Actuator management L945–1009](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L945-L1009) | Registered path reads `_adapter`; separate discovery fallback |
| [Zigbee management L127–132](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/zigbee_management_service.py?utm_source=chatgpt.com#L127-L132)    | Unwraps MQTT wrapper                                          |
| [Zigbee management L665–695](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/zigbee_management_service.py?utm_source=chatgpt.com#L665-L695)    | Direct command publication                                    |

I also inspected the complete actuator entity source for an `_adapter` compatibility alias or `__getattr__` implementation. Neither was found.

An ordinary factory-created actuator is therefore expected to encounter the attribute incompatibility before successful delegation.

The fallback is a different path. Its standard availability is conditional on MQTT being enabled and connected sufficiently for Zigbee service construction. It must not be represented as universally reachable.

**Counterexample to an unsafe remediation:** Correcting the registered attribute mismatch without adding mandatory final admission could expose a previously broken consequential command path.

The R1 wording explicitly rejects that interpretation.

**Disposition:** Critical / Verified / OPEN. Original ERB-SS-01 is satisfied within the documentary scope.

### **4.4 F-035 — False physical-operation success**

**PASS — replacement principal observation.**

The original defect remains directly reproducible through source inspection.

GPIO operation fails or GPIO is unavailable

Adapter logs failure

No explicit failure return

`result is None`

Logical ON/OFF success

Actual physical state remains unknown

Pinned evidence:

- [GPIO relay L55–83](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/actuators/relays/gpio_relay.py?utm_source=chatgpt.com#L55-L83).
- [ActuatorEntity L204–282](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/domain/actuators/actuator_entity.py?utm_source=chatgpt.com#L204-L282).
- [Irrigation execution L142–182](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L142-L182).
- [Irrigation execution L309–361](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L309-L361).

The executor also applies different failure predicates to valve and pump start outcomes. Merely excluding `ERROR` is insufficient to establish a successful operation.

An exception that propagates to the entity can correctly produce an error reading. Therefore, the defect is not that every physical failure produces logical success; particular failure modes do.

The general typed-outcome contract remains correct.

**Disposition:** Critical / Verified / OPEN.

## **5. REB-05 — Firmware maintenance and downstream trust**

**Original correction: PASS. Additional outcome-integrity evidence: HOLD.**

### **5.1 Maintenance authority and local API status**

The corrected F-043 row accurately describes the endpoint and adapter behaviour.

| Boundary                  | Independently verified                                                               |
| ------------------------- | ------------------------------------------------------------------------------------ |
| Required request fields   | Device identity and firmware URL                                                     |
| Device selection          | Registered SYSGrow adapter lookup                                                    |
| Maintenance authorization | No explicit per-target privileged maintenance check established within endpoint body |
| Artifact authorization    | No approved artifact provenance check established within endpoint body               |
| Offline submission        | Can return a queued transaction identifier                                           |
| Failed submission         | Can return `None`                                                                    |
| API result                | Labels all returned adapter outcomes `sent`                                          |

Primary evidence: [ESP32 endpoint L202–242](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/devices/esp32.py?utm_source=chatgpt.com#L202-L242), [SYSGrowAdapter L517–585](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L517-L585).

General write authentication does not establish privileged maintenance authority. However, the inspected endpoint body alone does not establish the absence of every possible deployment-level restriction.

No successful unauthorized firmware installation is demonstrated.

### **5.2 Queued destination preservation**

The previously identified destination discrepancy is independently confirmed.

Application-side control flow. Downstream interpretation remains unqualified.

The pending-command dataclass does not retain the custom destination. Queue processing reconstructs an ordinary device destination instead.

Evidence: [PendingCommand L56–69](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L56-L69), [queue submission and replay L517–610](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L517-L610), [maintenance submission L826–842](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L826-L842).

The existing expiration check is correctly preserved in R1.

### **5.3 New observation: R1-SS-01 — Firmware command tracking integrity**

High — blocking evidence correction

The R1 replacement now covers destination loss, but the same inspected queue implementation contains additional outcome-integrity defects.

| Source                                                                                                                                                                                           | Additional verified observation                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| [SYSGrowAdapter L134–149](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L134-L149) | Offline queue uses bounded `deque(maxlen=...)`                                                                             |
| [L543–564](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L543-L564)                | Appends commands and returns transaction identifiers without an explicit eviction outcome                                  |
| [L587–610](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L587-L610)                | Removes queued entry before attempting publication; unsuccessful publication has no corresponding failure-recording branch |
| [L489–515](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L489-L515)                | Compatible client's publication return value is not inspected                                                              |
| [L290–330](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L290-L330)                | Response matching relies on transaction ID without visibly comparing the extracted command against the pending operation   |

These are separate from the original destination mismatch.

The most consequential case is queue replay failure.

### **Queue outcome counterexample**

**Queued**

ID issued

**Removed**

Replay attempt

Publication fails

No explicit terminal failure record in inspected branch

Previously issued transaction ID does not establish delivery

This can be reasoned about directly from source. No message was published and no failure was experimentally injected.

A bounded queue also permits eviction when full. A capacity limit is desirable, but silently losing an already acknowledged queue admission is not an adequate consequential-operation outcome contract.

**Required correction:** supplement F-043/F-044 and the existing FT-008/024/027/029/032 designs with explicit queue-capacity admission, eviction accounting, replay publication failure, compatible-client non-success results and operation/target/response correlation.

A failed replay must not be represented as successful submission, and it must not cause blind retry of a potentially consequential operation.

Retain EP-003B outcome ownership and EP-007 maintenance authority. No additional canonical finding ID is necessary.

### **5.4 Legacy OTA utility**

The candidate now correctly includes [scripts/ota_updater.py L27–56](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/scripts/ota_updater.py?utm_source=chatgpt.com#L27-L56).

The utility describes HTTP-based firmware version and maintenance operations. Its existence is verified; its current deployment or operational authorization is not.

Its applicability must be included in the maintenance command-origin inventory before any corresponding security or activation qualification.

### **5.5 ER-04 applicability and downstream evidence**

| Evidence layer                                  | Disposition   |
| ----------------------------------------------- | ------------- |
| Local endpoint and adapter composition          | PASS          |
| Local maintenance admission observation         | PASS          |
| API false `sent` status                         | PASS          |
| Destination loss on queue replay                | PASS          |
| Complete local outcome integrity evidence       | HOLD          |
| Bridge authentication and authorization         | HOLD          |
| Artifact authenticity and trust roots           | HOLD          |
| Device firmware and boot verification           | HOLD          |
| Interrupted-update recovery and qualified rearm | HOLD          |
| Firmware maintenance activation                 | NOT QUALIFIED |

The R1 candidate correctly separates bounded application-source evidence from the external firmware trust boundary.

I support this separation.

**Missing downstream firmware source need not independently block documentary qualification of a bounded application-side defect.** It must block any dependent maintenance or device qualification that requires downstream trust evidence.

This is not an N/A determination, risk waiver or conclusion that the deployed firmware is insecure.

The downstream source inventory described in the R1 crosswalk is recorded author evidence. I did not independently reproduce the complete recursive tree inventory through the available connector in this review.

## **6. REB-06 — Calibration and MQTT composition**

### **6.1 F-003 — Actual pump calibration composition**

**Original composition correction: PASS. Additional persistence evidence: HOLD.**

The corrected R1 observation is supported.

**ContainerBuilder**

Injects ActuatorManagementService

**PumpCalibrationService**

Exposed through irrigation workflow facade

Caller supplies

`actuator_id`

`duration_seconds`

Service accepts

`actuator_id`

Incompatible invocation contract

| Pinned source                                                                                                                                                                                             | Verified observation                              |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| [ContainerBuilder L1113–1118](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container_builder.py?utm_source=chatgpt.com#L1113-L1118)                   | Actual dependency injection                       |
| [Workflow facade L272–274](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_workflow_service.py?utm_source=chatgpt.com#L272-L274)  | Stores calibration dependency                     |
| [API helper L540–552](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/_common.py?utm_source=chatgpt.com#L540-L552)                                 | Retrieves calibration through workflow            |
| [Calibration endpoint L514–569](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/irrigation/__init__.py?utm_source=chatgpt.com#L514-L569)           | Invokes calibration service                       |
| [Pump calibration L259–319](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/pump_calibration.py?utm_source=chatgpt.com#L259-L319)               | Supplies duration keyword, checks truthiness      |
| [Actuator management L590–615](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L590-L615) | Returns `ActuatorReading`; incompatible signature |

The principal defect is no longer an unresolved dependency-wiring question.

A different compatible implementation or test double could accept the duration argument. That would not qualify the standard composition.

The R1 replacement also correctly identifies latent defects involving truthiness, requested-versus-measured duration and unchecked cancellation shutdown.

### **6.2 New observation: R1-SS-02 — Calibration durable completion and bounded lifecycle**

High — blocking evidence correction

Additional inspection reveals a directly supportable calibration completion defect not explicitly captured by the corrected replacement matrix.

Pinned evidence:

| Source                                                                                                                                                                                                | Observation                                                                                                        |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| [pump_calibration.py L336–392](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/pump_calibration.py?utm_source=chatgpt.com#L336-L392)        | Stores calibration, deletes session and returns result without inspecting the persistence helper's Boolean outcome |
| [pump_calibration.py L568–599](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/pump_calibration.py?utm_source=chatgpt.com#L568-L599)        | Helper can return `False` and delegates configuration persistence                                                  |
| [Calibration completion API L574–611](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/irrigation/__init__.py?utm_source=chatgpt.com#L574-L611) | Returns successful response based on service result                                                                |
| [pump_calibration.py L405–413](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/pump_calibration.py?utm_source=chatgpt.com#L405-L413)        | Cancellation removes session before unchecked OFF                                                                  |

### **Calibration false-success path**

1. Calibration measurement submitted.
2. Flow rate calculated from requested duration.
3. Persistence helper returns `False`.
4. Session deleted despite failed persistence.
5. API may return successful calibration result.

Source-derived conditional counterexample. Not an executed calibration.

This is material because subsequent irrigation planning may depend on persisted calibration data. A result presented as newly calibrated while durable state remains unchanged can create inconsistent eligibility and dosing decisions.

There is a second lifecycle concern. In the inspected start method, duration enforcement is delegated to the incompatible actuator invocation. The completion method does not itself establish verified shutdown before calculating and accepting the measurement.

A signature-only repair must therefore not be accepted as qualification of bounded calibration.

The current positive-duration check in the API and active-session checks must be preserved. They do not establish independently enforced duration limits, durable completion or physical OFF certainty.

**Required correction:** extend F-003 and its FT-005/006/020/022 acceptance criteria to explicitly require:

- Rejected or failed actuator operation cannot establish a successful calibration session.
- Approved duration is enforced through a qualified operating-bound mechanism, not merely retained as session metadata.
- Actual measurement and independently established elapsed runtime are finite, bounded and traceable.
- Completion requires qualified shutdown reconciliation.
- Failed calibration persistence cannot produce successful durable calibration or discard unresolved operation state.

EP-003E remains the principal owner. EP-003F supplies independent operating bounds and recovery; EP-004 supplies durable persistence semantics.

This is distinct from F-009's sensor-calibration persistence placeholders.

### **6.3 F-044 — Actual MQTT composition and overrides**

**PASS — REB-06 composition correction.**

**ContainerBuilder**

MQTT enabled → MQTTClientWrapper

**SensorManagementService**

Receives configured client

**SensorFactory**

Injects client if not explicitly supplied

**SensorRegistry**

MQTT maps to SYSGrowAdapter

**SYSGrowAdapter**

Invokes publish with retain keyword

Incompatible publish signatures

The actual source confirms each stage.

| Pinned source                                                                                                                                                                                         | Role                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| [ContainerBuilder L327–357](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container_builder.py?utm_source=chatgpt.com#L327-L357)                   | Wrapper construction                       |
| [ContainerBuilder L740–759](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container_builder.py?utm_source=chatgpt.com#L740-L759)                   | Service injection                          |
| [Sensor management L127–143](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/sensor_management_service.py?utm_source=chatgpt.com#L127-L143) | Factory construction                       |
| [Sensor factory L80–135](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/sensors/factory.py?utm_source=chatgpt.com#L80-L135)                         | Conditional parameter injection            |
| [Sensor registry L289–293](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/sensors/registry.py?utm_source=chatgpt.com#L289-L293)                     | Protocol mapping                           |
| [SYSGrowAdapter L489–515](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L489-L515)      | Invocation contract                        |
| [MQTT wrapper L201–223](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/mqtt/mqtt_broker_wrapper.py?utm_source=chatgpt.com#L201-L223)                | Incompatible signature and untyped outcome |

#### **Protocol and override precision**

The R1 candidate adds an important correction beyond the initial review.

| Protocol             | Registry mapping                    | Factory automatically injects client                    |
| -------------------- | ----------------------------------- | ------------------------------------------------------- |
| MQTT                 | SYSGrowAdapter                      | Yes, if available and not overridden                    |
| WIRELESS             | SYSGrowAdapter                      | Not through the inspected automatic injection condition |
| Zigbee / Zigbee2MQTT | Separate applicable adapter mapping | Included in injection condition                         |

The `WIRELESS` registry entry is not evidence that it necessarily receives the same MQTT client through the same composition path.

The candidate correctly preserves this distinction.

The ESP32 bridge-level helper also supports a temporary adapter using the container client when no registered adapter is available. The device-specific maintenance endpoint follows registered-device lookup instead.

Evidence: [esp32.py L70–105](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/devices/esp32.py?utm_source=chatgpt.com#L70-L105).

**Counterexample:** An explicitly supplied compatible MQTT client can avoid the unsupported-keyword failure. That still does not establish publication success, device acknowledgement or physical verification.

The F-044 correction passes. Supplementary outcome-integrity requirements remain under R1-SS-01.

## **7. REB-12 — Authorization, topology and recovery**

The principal R1 corrections are supported. A supplementary persistence observation remains outstanding.

| Finding | R1 documentary correction                                          | Disposition                             |
| ------- | ------------------------------------------------------------------ | --------------------------------------- |
| F-016   | Separates local lock implementation from unknown physical topology | PASS                                    |
| F-033   | Current approval and replacement-delay semantics                   | PASS                                    |
| F-036   | Route-to-service identity and authorization chain                  | PASS                                    |
| F-039   | Execution-time policy, freshness and eligibility                   | PASS                                    |
| F-040   | Partial topology operation and uncertain recovery                  | PASS                                    |
| F-041   | Expected-state concurrency and ignored persistence result          | PASS, supplementary correction required |

### **7.1 F-016 — Evidence classification**

R1 now correctly distinguishes three separate propositions.

| Proposition                                                                  | Classification |
| ---------------------------------------------------------------------------- | -------------- |
| Inspected reservation is keyed by logical unit ID                            | Verified       |
| Actual installation contains shared physical resources                       | Unverified     |
| Shared topology without physical exclusion could permit competing operations | Risk           |

Pinned evidence: [irrigation_workflow.py L823–890](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/ops/irrigation_workflow.py?utm_source=chatgpt.com#L823-L890).

Retaining the historical Medium / Unverified classification is defensible because the principal finding concerns missing cross-unit qualification.

The R1 row explicitly records the verified local observation and conditional escalation when shared topology is established.

This resolves ERB-SS-04.

### **7.2 F-036 — Identity and resource authorization**

The corrected route-to-service chain is verified.

HTTP write middleware

Checks presence of session["user"]

API identity helper

Reads user_id, defaults to 1

Workflow and feedback service

Request ID and user ID passed through

Resource ownership comparison absent in inspected handler

Evidence: [api_auth.py L30–95](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/middleware/api_auth.py?utm_source=chatgpt.com#L30-L95), [\_common.py L40–54](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/_common.py?utm_source=chatgpt.com#L40-L54), [irrigation API L105–139](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/irrigation/__init__.py?utm_source=chatgpt.com#L105-L139), [feedback service L82–123](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_feedback_service.py?utm_source=chatgpt.com#L82-L123).

A session with one identity key present does not independently establish that the other key exists or represents the same authorized principal.

R1 correctly avoids claiming that a successful cross-user operation has been demonstrated.

Retain EP-007 ownership and FT-017/018/045.

### **7.3 F-039 — Execution-time eligibility**

The current detection path checks disabled and manual mode. It conditionally checks observation age.

The inspected timestamp block rejects an excessively old measurement but does not establish a corresponding future-timestamp check.

Pinned evidence: [detection service L93–187](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_detection_service.py?utm_source=chatgpt.com#L93-L187).

The execution path uses the earlier request and applies a configured maximum duration without repeating every detection prerequisite.

R1 now adequately covers changed operating mode, reassigned resources, calibration provenance, missing/future observations and non-finite values as required future acceptance cases.

**Counterexample:** A request is valid when created, but automation is disabled before execution. Detection-time validity cannot serve as continuing authorization.

The configured duration cap is an existing safeguard, not evidence of an independent physical limit.

### **7.4 F-040 — Partial topology recovery**

The corrected operation ordering is accurate.

Attempt valve activation

Record execution-start state

Create detailed execution log

Attempt pump activation

Record successful pump completion

Attempt valve shutdown

Returned state not inspected

Release unit reservation

Observed source ordering, not an actual physical execution trace.

Evidence: [execution service L309–392](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L309-L392), [completion L142–182](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L142-L182).

The candidate correctly identifies that successful pump completion and reservation release do not establish complete topology reconciliation.

The valve position remains unknown in the relevant failure scenarios.

The existing FT-037/040/044 combined recovery designs, together with the R1 extension, appropriately preserve durable quarantine independently of reservation lifetime.

### **7.5 New observation: R1-SS-03 — Zero-row persistence success**

Medium — documentary correction

R1 correctly identifies that feedback handlers ignore `update_status()` outcomes.

However, the underlying database method also contains a separate success-semantics gap.

[infrastructure/database/ops/irrigation_workflow.py L912–947](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/ops/irrigation_workflow.py?utm_source=chatgpt.com#L912-L947) performs an update, commits and returns `True` without checking how many rows were affected.

This means the Boolean result itself is not sufficient evidence that an intended transition occurred.

There are two distinct failure conditions:

| Condition                        | Existing defect                            |
| -------------------------------- | ------------------------------------------ |
| Persistence returns `False`      | Feedback caller ignores failure            |
| Update matches no applicable row | Persistence method may still return `True` |

**Counterexample:** The request observed by the handler no longer exists when its update occurs. A successful SQL transaction with zero matching rows is not a successful authorization or cancellation transition.

This is a conditional scenario, not a demonstrated production race.

The future compare-and-set contract must explicitly require the expected row/version, successful durable commit and exactly one intended transition.

**Required correction:** add the zero-row outcome to F-041 and FT-004/020/030. Verify that failure or conflict cannot be represented as successful approval, delay or cancellation, including associated preference-learning effects.

Retain the existing High foundation severity and EP-003C/EP-004 ownership.

## **8. REB-13 — Updated fault-test oracles**

**Disposition: HOLD — substantial improvement, three supplementary corrections required.**

I independently counted the distinct FT identifiers referenced in the current remediation document.

Unique FT identifiers

# **45**

Tests executed during review

# **0**

The current R1 extensions are cumulative rather than replacements for the inherited common fault oracles.

Evidence: [REMEDIATION.md L124–188](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/plans/REMEDIATION.md?utm_source=chatgpt.com#L124-L188), [R1 extensions L190–205](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/plans/REMEDIATION.md?utm_source=chatgpt.com#L190-L205).

### **8.1 Review of R1 extensions**

| Existing FT group              | Corrected oracle                                                                | Disposition                                             |
| ------------------------------ | ------------------------------------------------------------------------------- | ------------------------------------------------------- |
| FT-005/007/019/043             | Actual factory-created entities and discovery path; mandatory admission         | PASS                                                    |
| FT-005/006/022                 | Calibration composition, finite inputs, typed failure and cancellation recovery | HOLD — add durable completion and operating-bound cases |
| FT-002/003/004/020/030         | Approval, policy changes, delay and persistence failures                        | PASS in principle; explicit zero-row case required      |
| FT-008/011/029/032             | Wrapper compatibility, queue and ambiguous delivery                             | HOLD — add replay failure, eviction and correlation     |
| FT-013/015/016/025/037/040/044 | Combined lifecycle, topology and restart recovery                               | PASS                                                    |
| FT-017/018/045                 | Identity consistency, scoped principals and protected delivery                  | PASS                                                    |
| FT-021/042                     | Returned failure cannot become recorded success                                 | PASS                                                    |
| FT-024/027/036                 | Privileged maintenance, artifact trust, destination, expiry and rearm           | PASS in principle; queue accounting extension required  |

### **8.2 F-019 — Existing reliability tests**

The R1 description of existing tests is now sufficiently conservative.

I inspected [test_irrigation_reliability.py L91–179](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/tests/unit/irrigation/test_irrigation_reliability.py?utm_source=chatgpt.com#L91-L179).

| Test                          | Actual oracle                                        |
| ----------------------------- | ---------------------------------------------------- |
| Atomic request claim          | Sequential first and second claim                    |
| Parallel execution prevention | Sequential lock acquisition and rejection            |
| Valve failure                 | Stub actuator and assertion that pump was not called |
| No sleep calls                | Textual source inspection                            |
| Irrigation attribution        | Direct classification examples                       |

These tests are useful existing safeguards, but their inspected implementation does not establish simultaneous-worker qualification, complete adapter composition, restart recovery or physical safety.

R1 correctly avoids treating test names as comprehensive evidence.

### **8.3 Mandatory additional test cases**

The following are proposed extensions to the existing test designs, not new test IDs or authorization to execute them.

| Fault scenario                                  | Required synthetic oracle                                                           |
| ----------------------------------------------- | ----------------------------------------------------------------------------------- |
| Offline queue at capacity                       | Explicit rejection or accountable disposition; no silent loss of admitted operation |
| Known replay publication failure                | Explicit terminal processing outcome or safely retained reconciliable state         |
| Ambiguous replay delivery                       | Durable uncertainty; no blind consequential retry                                   |
| Compatible MQTT client returns failure          | No successful submission result                                                     |
| Mismatched command/target response              | Cannot promote unrelated operation to completed or physically verified              |
| Calibration reaches authorized operating bound  | Qualified stopping mechanism and outcome reconciliation                             |
| Calibration persistence returns `False`         | No durable calibration success                                                      |
| Calibration completion with unresolved shutdown | Result not eligible for consequential use                                           |
| State transition matches zero rows              | Explicit conflict/failure, no false authorization or cancellation                   |

The implementation plans must continue to supply actual fixture topology, isolated persistence, controlled clocks, deterministic barriers and lowest-interface positive controls.

## **9. Physical safety and staged architecture**

**PASS — preservation of documentary boundaries.**

The R1 corrections do not invalidate the established dependency graph.

**D0**

Resolve applicable mandatory design contracts

**R1a**

Runtime containment and denial of unauthorized effects

**R1b**

Strict irrigation containment or qualified bounded alternative

**R2a**

Minimum admission, durable evidence and recovery enforcement

**R2b**

Bounded process ownership qualification

**R3a**

Full irrigation, topology, calibration and persistence

**R3b**

Lifecycle, protection, recovery and platform

**Q**

Independent applicable profile qualification

**Production activation**

Separate device-specific evidence, site disposition and explicit authorization

Pinned governing records: [D0-CONTRACTS.md L3–24](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/plans/D0-CONTRACTS.md?utm_source=chatgpt.com#L3-L24), [REMEDIATION.md L85–103](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/plans/REMEDIATION.md?utm_source=chatgpt.com#L85-L103), [QUALIFICATION-PROFILES.md L3–42](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/QUALIFICATION-PROFILES.md?utm_source=chatgpt.com#L3-L42).

### **9.1 Ownership remains coherent**

| Contract                                         | Accountable package |
| ------------------------------------------------ | ------------------- |
| Installation authority                           | EP-001              |
| Unit lifecycle and disposal                      | EP-002              |
| Final consequential admission                    | EP-003A             |
| Typed transport and physical outcomes            | EP-003B             |
| Irrigation approval policy                       | EP-003C             |
| Physical reservation and quarantine              | EP-003D             |
| Observation and calibration eligibility          | EP-003E             |
| Independent protection and recovery              | EP-003F             |
| Atomic persistence                               | EP-004              |
| Deployment profiles                              | EP-005              |
| Identity, resource and maintenance authorization | EP-007              |

The new review observations do not require a new architectural owner or duplicate command framework.

### **9.2 Critical safety boundaries**

The following remain mandatory and are correctly preserved in the candidate:

| Invariant                                        | Documentary disposition |
| ------------------------------------------------ | ----------------------- |
| Exclusive runtime ownership                      | PASS                    |
| Passive non-owner construction                   | PASS                    |
| Consequential lifecycle-effect admission         | PASS                    |
| Explicit human and service principal             | PASS                    |
| Current required irrigation approval             | PASS                    |
| Separate processing and physical-state certainty | PASS                    |
| Reservation-independent quarantine               | PASS                    |
| Stale-owner and delayed-effect recovery          | PASS                    |
| Independent physical protection                  | PASS                    |
| Restricted emergency authority                   | PASS                    |
| Qualified rearm and fresh admission              | PASS                    |

Evidence: [FOUNDATION_BASELINE.md L49–100](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/architecture/FOUNDATION_BASELINE.md?utm_source=chatgpt.com#L49-L100).

These are proposed target invariants. None is credited as implemented or physically qualified by this review.

## **10. EGA-001 — Security and safety assessment**

**PASS for preservation of mandatory gates. HOLD for acceptance readiness.**

The revised amendment now establishes explicit lifecycle states.

1. **PROPOSED**

   Original-report prerequisite remains binding.

   Current state
2. **REPLACEMENT QUALIFIED**

   Independent technical evidence is sufficient.
3. **OWNER ACCEPTED — LIMITED SUBSTITUTION**

   Only the enumerated historical-report prerequisite is replaced.
4. **G0 INTEGRATION ELIGIBLE**

   Remaining applicable integration prerequisites satisfied.
5. **INTEGRATED / CANONICAL**

   Separately authorized integration and recorded canonical governance.

Pinned evidence: [EGA-001 L3–11](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md?utm_source=chatgpt.com#L3-L11), [explicit lifecycle and supersession L24–48](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md?utm_source=chatgpt.com#L24-L48).

The amendment preserves the distinction between accepting source evidence and qualifying the implementation.

| Gate                                           | Preserved |
| ---------------------------------------------- | --------- |
| Independent replacement qualification          | Yes       |
| Resolution of blocking technical disagreements | Yes       |
| All 44 findings remain OPEN                    | Yes       |
| Permanent historical provenance limitation     | Yes       |
| Applicable exact-HEAD CI                       | Yes       |
| Effective repository enforcement               | Yes       |
| Separate owner integration approval            | Yes       |
| Separate ADR acceptance                        | Yes       |
| Downstream maintenance/device trust            | Yes       |
| Independent physical protection                | Yes       |
| Separate production activation                 | Yes       |

No explicit safety-gate waiver was identified.

A bounded documentary PASS for F-043 does not require pretending that unavailable firmware implementation evidence is known. Conversely, EGA-001 acceptance cannot make that unavailable evidence sufficient for a later mandatory maintenance or device-specific qualification.

The remaining R1 review observations prevent unconditional acceptance readiness in my assigned scope.

## **11. Formal R1 review correction register**

The following identifiers are newly assigned independent reviewer observations.

| ID       | Severity | Affected evidence                   | Required correction                                                                   |
| -------- | -------- | ----------------------------------- | ------------------------------------------------------------------------------------- |
| R1-SS-01 | High     | F-043/F-044, FT-008/024/027/029/032 | Queue admission/eviction, replay failure, publication result and response correlation |
| R1-SS-02 | High     | F-003, FT-005/006/020/022           | Calibration persistence failure, bounded lifecycle and verified shutdown              |
| R1-SS-03 | Medium   | F-041, FT-004/020/030               | Zero-row persistence outcomes and exact transition success                            |

### **New reviewer severity distribution**

Critical

0

High

2

Medium

1

Low

0

The High severity assignments concern the completeness of the replacement technical evidence and mandatory future qualification oracles for consequential operations.

They do not establish new Critical runtime incidents, exploitation or observed physical failures.

I recommend incorporating them into the existing finding definitions and fault designs rather than expanding the canonical register.

## **12. Historical correction convergence**

The original six security observations should remain preserved at their historical candidate revision.

| Original observation | R1 response | Independent disposition                    |
| -------------------- | ----------- | ------------------------------------------ |
| ERB-SS-01            | REB-04      | PASS                                       |
| ERB-SS-02            | REB-05      | PASS for original requested correction     |
| ERB-SS-03            | REB-06      | PASS for original composition correction   |
| ERB-SS-04            | REB-12      | PASS                                       |
| ERB-SS-05            | REB-12      | PASS for original requested correction     |
| ERB-SS-06            | REB-13      | HOLD for supplementary oracle completeness |

The R1 author has substantively addressed the original review. The remaining HOLD does not result from repeating previously corrected objections.

The original reports should not be rewritten to incorporate these later observations.

## **13. Integration evidence and unresolved gates**

Fresh read-only GitHub queries against the exact candidate HEAD returned:

| Evidence                             | Directly observed             |
| ------------------------------------ | ----------------------------- |
| Candidate combined status entries    | 0                             |
| Returned PR-triggered workflow runs  | 0                             |
| PR open                              | Yes                           |
| Draft                                | Yes                           |
| Merged                               | No                            |
| Mergeable                            | Yes                           |
| Effective administrative enforcement | Not independently established |
| EGA-001 accepted                     | Not established or authorized |

Evidence: [candidate commit](https://github.com/PatoruzuyX/SYSGrow/commit/47794834e009334aa417b913fcc6818407ad234e?utm_source=chatgpt.com), [PR #3](https://github.com/PatoruzuyX/SYSGrow/pull/3?utm_source=chatgpt.com).

The workflow retrieval is limited to the connector's returned PR-triggered run scope. The empty responses do not constitute an exhaustive audit of all check-run or merge-ref evidence.

**Successful mandatory CI has not been established by this review.**

The enforcement workstream remains separately mandatory. The absence of effective administrative-policy evidence must not be represented as a qualified integration gate.

## **14. Required requalification checklist**

### **Requalification tracker**

0/11

Correct R1-SS-01 firmware queue and correlated outcome evidence.

Correct R1-SS-02 calibration persistence and bounded lifecycle evidence.

Correct R1-SS-03 zero-row transition outcome evidence.

Extend existing FT oracles without executing tests under documentary authority.

Preserve all historical reports and review identifiers.

Independently establish exact corrected candidate tree identity.

Obtain applicable independent final-candidate qualification.

Obtain separate explicit EGA-001 owner acceptance.

Establish successful applicable exact-HEAD CI.

Establish effective required-check enforcement.

Obtain separate explicit G0 integration authorization.

Manual tracking only. Selecting an item does not establish evidence, modify GitHub or grant approval. Copy checklist

Downstream firmware trust remains a separate mandatory qualification dependency before applicable maintenance and device activation. It must not be marked complete merely because documentary evidence qualification eventually passes.

## **15. Review limitations and scope compliance**

This review directly inspected candidate governance, replacement evidence rows, remediation plans, the archived initial Reviewer 2 report, GitHub comparison metadata and targeted application source at the authorized baseline.

The following limitations remain:

| Limitation                                                                | Consequence                                                                       |
| ------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Raw candidate Git tree object unavailable through the inspected connector | Exact tree identity not independently certified                                   |
| Complete recursive application inventory not reproduced here              | Downstream source-absence claim remains attributed to recorded inventory evidence |
| Original CP0–CP2 reports unavailable                                      | Historical provenance remains unresolved                                          |
| Original reviewer-session authenticity not independently established      | Archive retrieval is not session authentication                                   |
| No effective administrator-level enforcement audit                        | Integration enforcement remains HOLD                                              |
| No exhaustive repository-wide command-origin analysis                     | Runtime remediation still requires full origin inventory                          |
| No local checkout or deployed configuration inspection                    | Actual deployment reachability remains conditional                                |
| No synthetic, concurrency or physical testing                             | Counterexamples remain source-derived                                             |
| No downstream firmware or bootloader inspection                           | Maintenance trust remains unqualified                                             |

The three new reviewer identifiers, their severity assignments, the supplementary fault-test requirements and the proposed mapping into existing findings are independent reviewer judgments. They are not owner-approved governance or implementation changes.

No repository files, Git references, settings or submitted GitHub reviews were modified. No CI was dispatched. No firmware update, deployment, live data access, physical operation, EGA-001 acceptance or merge was performed.

## **16. Final acceptance record**

SYSGROW-EVIDENCE-REBASELINE-001-R1 / Reviewer 2

# **HOLD**

47794834e009334aa417b913fcc6818407ad234e

Documentary change containment

PASS

Original composition corrections

PASS

Four Critical finding justifications

PASS

Architecture preservation

PASS

Replacement evidence completeness

HOLD

Fault-test oracle completeness

HOLD

EGA-001 acceptance readiness

HOLD

Historical provenance recovery

HOLD

Integration eligibility

HOLD

Production safety

NOT QUALIFIED

Foundation findings OPEN

# **44 / 44**

Critical findings OPEN

# **4 / 4**

New blocking review observations

# **3**

Fault tests executed

# **0 / 45**

### **Reviewer recommendation**

Retain the R1 corrections and the EGA-001 strategy. The registered actuator composition, calibration injection, MQTT override distinction, approval timing, resource authorization and partial topology recovery are now substantially better documented.

The remaining work should be a narrowly scoped evidence and fault-oracle correction addressing R1-SS-01–03, followed by exact-candidate requalification.

There is no justification from this review for reopening the D0–R–Q architecture, introducing additional canonical runtime findings, reducing existing severities or requiring production hardware operation to qualify the bounded documentary evidence.

**Final verdict: HOLD — two High and one Medium candidate review observations. All 44 foundation findings remain OPEN. EGA-001 remains proposed. G0 integration is blocked, and production safety remains NOT QUALIFIED.**