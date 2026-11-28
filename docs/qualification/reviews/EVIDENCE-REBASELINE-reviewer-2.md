# **SYSGROW-EVIDENCE-REBASELINE-001**

## **Independent qualification — Reviewer 2: Security and Physical Safety**

**Review date:** 28 November 2026\
**Repository:** [PatoruzuyX/SYSGrow](https://github.com/PatoruzuyX/SYSGrow?utm_source=chatgpt.com)\
**Pull request:** [#3](https://github.com/PatoruzuyX/SYSGrow/pull/3?utm_source=chatgpt.com)\
**Review method:** Independent, revision-pinned, read-only source and documentary qualification.

This review distinguishes four separate questions:

- Whether the replacement technical evidence accurately represents the application baseline.
- Whether the finding definitions, classifications and severity ratings are defensible.
- Whether remediation acceptance criteria and fault-test oracles are sufficient.
- Whether the proposed governance amendment preserves mandatory security and physical-safety gates.

Acceptance of replacement evidence must not be interpreted as remediation completion, runtime qualification or permission to operate physical equipment.

## **1. Repository and candidate identity**

**Candidate identity and documentary scope**

PASS

Candidate HEAD — independently confirmed

a10107a4f78eea8c37a0b1a6ab7d616a61b4df87

Candidate tree — independently confirmed

6afe5fa9a1838137e80a290ccbb35eab6ea70172

Direct parent — independently confirmed

5d646ba58cb071b392cea94287371925ba82e626

Application baseline — confirmed ancestor

2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21

Delta from governance parent

# **1 commit**

5 documentation paths

Delta from application baseline

# **5 commits**

35 documentation paths

Commits behind baseline

# **0**

PR state

# **Open / Draft**

The direct-parent comparison confirms four newly added qualification documents and one modification to `docs/INDEX.md`. No application or firmware source changes appear in that comparison or the cumulative comparison against the application baseline.

Primary identity evidence: [Git commit object](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/commits/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87?utm_source=chatgpt.com), [parent comparison](https://github.com/PatoruzuyX/SYSGrow/compare/5d646ba58cb071b392cea94287371925ba82e626...a10107a4f78eea8c37a0b1a6ab7d616a61b4df87?utm_source=chatgpt.com), [application baseline comparison](https://github.com/PatoruzuyX/SYSGrow/compare/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21...a10107a4f78eea8c37a0b1a6ab7d616a61b4df87?utm_source=chatgpt.com).

The commit is reported as unsigned. This does not invalidate its Git object identity, but cryptographic author authentication has not been established.

**Scope conclusion:** the candidate proposes changes to the evidence basis and governance documentation, not corrections to the underlying security or physical-control implementation.

The subsequent recursive Git tree comparison independently confirmed:

- Both trees were returned without truncation.
- Exactly 35 non-directory paths differ from the application baseline, all Markdown.
- No baseline paths have been removed.
- PR #3 identifies the supplied candidate SHA as its current HEAD and the authorized application baseline as its base.

The application baseline contains 780 blobs. No firmware source files, conventional embedded firmware build configurations or Git submodules were identified in that tree.

## **2. Independent qualification verdict**

# **Reviewer 2 — HOLD**

Blocking corrections

Critical

# **0**

High

# **3**

Medium

# **3**

Low

# **0**

Counts refer to new candidate review defects, not the existing application findings.

| Repository identity and documentation scope    | PASS          |
| ---------------------------------------------- | ------------- |
| Four existing Critical severity ratings        | PASS          |
| Replacement technical evidence sufficiency     | HOLD          |
| Security and command-path composition accuracy | HOLD          |
| ER-04 downstream firmware trust                | HOLD          |
| Remediation acceptance and fault-test design   | HOLD          |
| EGA-001 preservation of existing safety gates  | PASS          |
| EGA-001 acceptance readiness                   | HOLD          |
| G0 integration                                 | HOLD          |
| Production physical safety                     | NOT QUALIFIED |

The candidate is substantially stronger than a simple reconstruction of the missing CP0–CP2 reports. Its separation of historical provenance, directly observed defects, conditional consequences and future qualification is appropriate.

However, independent source inspection identified several important discrepancies that prevent accepting it as the authoritative replacement technical evidence basis.

The most significant is **F-034: the registered Zigbee command path contains an additional interface mismatch that contradicts the implied successful delegation described in the candidate.** Other findings, particularly F-003, F-043 and F-044, can now be supported with stronger composition evidence than the candidate provides.

## **3. New candidate correction register**

| Correction ID | Severity | Affected evidence                 | Disposition                                                                                                    |
| ------------- | -------- | --------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| ERB-SS-01     | High     | F-034                             | Registered actuator command-path composition is inaccurately characterized                                     |
| ERB-SS-02     | High     | F-043, ER-04                      | Firmware maintenance admission, false status and queued destination defects are incompletely characterized     |
| ERB-SS-03     | High     | F-003, F-044                      | Known dependency composition is treated as an unresolved wiring question                                       |
| ERB-SS-04     | Medium   | F-016                             | Evidence classification conflates an observed lock limitation with missing topology evidence                   |
| ERB-SS-05     | Medium   | F-033, F-036, F-039, F-040, F-041 | Additional directly observable admission, authorization and recovery defects require stronger evidence mapping |
| ERB-SS-06     | Medium   | Acceptance criteria, ER-04        | Firmware maintenance and calibration fault-test oracles require explicit extensions                            |

These are reviewer-assigned correction identifiers and severities. They are proposed review dispositions, not modifications to the existing 44-finding register.

# **4. Independent challenge of the four Critical findings**

Existing application baseline — Critical findings

**F-001**

Competing runtime ownership

Critical / OPEN

**F-033**

Required irrigation approval not enforced

Critical / OPEN

**F-034**

Protocol-specific command safety bypass

Critical / OPEN

**F-035**

False physical-operation success

Critical / OPEN

All four severity ratings remain defensible. None is closed or physically qualified.

## **4.1 F-001 — Competing runtime ownership**

**Disposition: PASS — Critical, Verified, OPEN.**

### **Independently reproduced composition**

Static composition and potential effects, not an observed deployment or physical incident.

| Pinned source                                                                                                                                                                           | Direct observation                                              |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| [Dockerfile:77–83](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/Dockerfile?utm_source=chatgpt.com#L77-L83)                                       | Gunicorn configured with two workers                            |
| [smart_agriculture_app.py:16–36](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/smart_agriculture_app.py?utm_source=chatgpt.com#L16-L36)           | Module-level application construction enables runtime bootstrap |
| [app/**init**.py:106–112](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/__init__.py?utm_source=chatgpt.com#L106-L112)                         | Application construction builds the container                   |
| [container.py:137–159](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container.py?utm_source=chatgpt.com#L137-L159)                  | Scheduler configuration is not gated by `start_coordinator`     |
| [scheduled_tasks.py:1525–1540](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/workers/scheduled_tasks.py?utm_source=chatgpt.com#L1525-L1540)   | Scheduler defaults to starting                                  |
| [gpio_relay.py:27–42](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/actuators/relays/gpio_relay.py?utm_source=chatgpt.com#L27-L42)   | Construction can configure GPIO output                          |
| [gpio_relay.py:85–104](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/actuators/relays/gpio_relay.py?utm_source=chatgpt.com#L85-L104) | Cleanup and destructor can release GPIO configuration           |

An additional lifecycle concern is established by [actuator_management_service.py:181–187](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L181-L187): construction registers discovery callbacks and requests a device list when the Zigbee service is supplied.

### **Counterexamples and limitations**

Disabling MQTT can prevent its connection path. An environment without available GPIO support avoids GPIO configuration. A deployment using different worker settings may avoid the illustrated two-worker topology.

None of those counterexamples removes the underlying ownership and passive-construction defect.

**Required closure:** retain EP-001 ownership, R1a containment, R2b bounded qualification and full closure at Q. Include initialization, destructor and cleanup effects in the composed fault tests.

Critical severity remains justified by the potential consequences of competing authority over shared physical resources.

## **4.2 F-033 — Required irrigation approval not enforced**

**Disposition: PASS for the principal defect — Critical, Verified, OPEN. Supplementary corrections required under ERB-SS-05.**

The actual application composition strengthens this finding beyond the replacement register's immediate SQL and execution anchors.

### **Pinned evidence**

| Source                                                                                                                                                                                                                   | Observation                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- |
| [container_builder.py:1087–1099](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container_builder.py?utm_source=chatgpt.com#L1087-L1099)                               | Wires execution dependencies and registers tasks                                        |
| [irrigation_workflow_service.py:615–680](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_workflow_service.py?utm_source=chatgpt.com#L615-L680)   | Schedules due-request execution                                                         |
| [irrigation_workflow.py:204–256](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/ops/irrigation_workflow.py?utm_source=chatgpt.com#L204-L256)                | Claim selection admits pending, approved and delayed records                            |
| [irrigation_execution_service.py:244–292](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L244-L292) | Missing response can be recorded as AUTO learning; no required-approval admission check |
| [irrigation_execution_service.py:309–361](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L309-L361) | Claimed request proceeds toward valve and pump activation                               |

### **Additional directly observed defect**

The claim query uses an OR relationship between the original scheduled time and the delayed-until time.

A delayed request can therefore satisfy the due-selection predicate through its original scheduled time even when its replacement delay has not expired.

This is stronger than a hypothetical timing risk: the problematic selection predicate is directly observable.

The register should explicitly identify this under F-033/F-041 and FT-030.

### **Counterexample**

An expired request is excluded by the existing expiry predicate. A missing actuator or a failed lock acquisition also prevents the normal pump operation.

Those safeguards must be preserved. They do not enforce required approval, current configuration or authorized delayed timing.

### **Required qualification**

The final admission contract must independently establish current approval policy, explicit authorization, resource identity, current operating mode, timing, expiry and revocation ordering.

The fact that a scheduler claimed a database row must never constitute command authority.

## **4.3 F-034 — Protocol-specific command safety bypass**

**Disposition: HOLD — Critical severity retained; source definition requires correction.**

**ERB-SS-01 — High.**

This is a material evidence discrepancy identified during independent composition tracing.

The candidate states that `send_command()` calls an actuator adapter without the ordinary `turn_on()` safety check. The method expresses that intention, but the actual factory-created entity uses a different attribute.

### **Actual registered-actuator composition**

| Component                                                                                                                                                                                                        | Observed interface                                |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| [ActuatorFactory:77](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/actuators/factory.py?utm_source=chatgpt.com#L77)                                           | Constructs `ActuatorEntity(..., adapter=adapter)` |
| [ActuatorEntity:159–194](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/domain/actuators/actuator_entity.py?utm_source=chatgpt.com#L159-L194)                           | Declares `adapter`, not `_adapter`                |
| [ActuatorManagementService:975–1009](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L975-L1009) | Reads `actuator._adapter` before delegating       |

No `_adapter` alias was identified in the inspected `ActuatorEntity` implementation.

Consequently, for an ordinary factory-created actuator, the inspected registered command path is expected to encounter an attribute mismatch before adapter delegation. That is a distinct source-level defect, not evidence of successfully reaching the physical interface through that branch.

### **Why Critical severity must nevertheless remain**

The unregistered-device fallback is separately supported by source:

- [actuator_management_service.py:945–973](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L945-L973) delegates to the discovery service.
- [zigbee_management_service.py:130](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/zigbee_management_service.py?utm_source=chatgpt.com#L130) unwraps `MQTTClientWrapper` to its underlying client.
- [zigbee_management_service.py:665–695](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/zigbee_management_service.py?utm_source=chatgpt.com#L665-L695) performs direct command publication without the inspected ordinary actuator safety-service admission.

This alternative path remains configuration-dependent, but is sufficient to support the architectural concern.

### **Mandatory correction**

Reframe F-034 as:

> Protocol-specific command paths lack consistent mandatory admission. The registered path additionally contains an adapter attribute incompatibility; the unregistered discovery fallback provides a distinct direct transport path. Actual command delivery and physical effects remain unverified.

Do not treat the attribute incompatibility as a safety mechanism.

Fixing only `_adapter` to `adapter` in a future implementation could expose a previously broken delegation path without adding mandatory safety admission. That is precisely why composition and negative testing must precede any remediation acceptance.

## **4.4 F-035 — False physical-operation success**

**Disposition: PASS — Critical, Verified, OPEN.**

The GPIO example is sufficient to establish the defect without assuming MQTT, firmware or physical deployment behaviour.

### **Confirmed composition**

| Layer                                                                                                                                                                                                               | Source behaviour                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| [GPIORelay:55–83](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/actuators/relays/gpio_relay.py?utm_source=chatgpt.com#L55-L83)                                   | Logs GPIO failure or unavailability; returns no explicit failure value |
| [ActuatorFactory:62–103](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/actuators/factory.py?utm_source=chatgpt.com#L62-L103)                                     | Supplies the relay to the actuator entity                              |
| [ActuatorEntity:204–282](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/domain/actuators/actuator_entity.py?utm_source=chatgpt.com#L204-L282)                              | Interprets `None` as successful ON or OFF                              |
| [IrrigationExecutionService:142–170](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L142-L170) | Can record successful completion based on the returned state           |

**GPIO operation fails or is unavailable**

Failure logged inside adapter

`return None`

`success = True if result is None else bool(result)`

**False logical success**

Actual physical state remains unknown

Further supporting evidence is present in [zigbee_adapter.py:61–106](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/actuators/zigbee_adapter.py?utm_source=chatgpt.com#L61-L106), where publication is followed by logging or a successful return without independently establishing device state.

### **Counterexample**

Some adapter failures can raise exceptions, and the entity handles certain exceptions by returning `ERROR`. Therefore, not every unsuccessful physical-operation attempt becomes reported success.

The verified defect is that **particular failure modes can be converted into successful logical outcomes**, not that all outcomes are false.

Critical severity is justified because incorrect shutdown evidence can undermine subsequent admission, recovery and resource protection decisions.

# **5. Qualification of all assigned findings**

The following dispositions concern the accuracy and sufficiency of the replacement evidence, not runtime remediation closure.

| Finding | Baseline severity | Classification assessment                           | Review |
| ------- | ----------------- | --------------------------------------------------- | ------ |
| F-001   | Critical          | Verified supported                                  | PASS   |
| F-002   | High              | Risk supported                                      | PASS   |
| F-003   | High              | Verified; stronger composition evidence required    | HOLD   |
| F-004   | High              | Risk supported                                      | PASS   |
| F-005   | High              | Risk supported at umbrella scope                    | PASS   |
| F-016   | Medium            | Unverified requires clarification                   | HOLD   |
| F-026   | High              | Verified supported                                  | PASS   |
| F-027   | High              | Verified supported                                  | PASS   |
| F-033   | Critical          | Verified supported                                  | PASS   |
| F-034   | Critical          | Verified, but composition description inaccurate    | HOLD   |
| F-035   | Critical          | Verified supported                                  | PASS   |
| F-036   | High              | Verified; strengthen route evidence                 | HOLD   |
| F-037   | High              | Verified supported                                  | PASS   |
| F-038   | Medium            | Verified supported                                  | PASS   |
| F-039   | High              | Verified; additional eligibility cases required     | HOLD   |
| F-040   | High              | Verified; recovery consequence understated          | HOLD   |
| F-041   | High              | Verified; caller and timing behaviour incomplete    | HOLD   |
| F-042   | High              | Verified supported                                  | PASS   |
| F-043   | High              | Verified local defects; downstream trust unresolved | HOLD   |
| F-044   | High              | Verified; composition stronger than reported        | HOLD   |

### **Assigned evidence dispositions**

# **11**

PASS

# **9**

HOLD

20 assigned findings reviewed. All remain OPEN at application level.

## **5.1 F-002 — Independent actuator shutdown**

**PASS — High, Risk.**

[irrigation_execution_service.py:110–184](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L110-L184) establishes an application-managed completion mechanism.

It does not establish independent operating bounds or shutdown protection when the application, broker or host becomes unavailable.

The candidate correctly avoids asserting that independent hardware protection is absent.

Required evidence remains device-specific, including protection independence, relevant common-cause failures, shutdown certainty and qualified operating limits.

## **5.2 F-003 — Pump calibration interface**

**HOLD — High, Verified. ERB-SS-03.**

The candidate correctly identifies the signature mismatch, but leaves actual service wiring as an outstanding qualification question that can already be resolved statically.

| Pinned evidence                                                                                                                                                                                                     | Observation                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [container_builder.py:1113–1118](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container_builder.py?utm_source=chatgpt.com#L1113-L1118)                          | `PumpCalibrationService` receives `hardware.actuator_management_service` |
| [pump_calibration.py:284–301](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/pump_calibration.py?utm_source=chatgpt.com#L284-L301)                       | Passes `duration_seconds` to `turn_on()`                                 |
| [actuator_management_service.py:590–615](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L590-L615) | `turn_on()` accepts only `actuator_id`                                   |

The dependency composition is therefore established for the standard container path. Successful application startup, API invocation and actual hardware operation remain conditional.

Additional defects requiring evidence mapping:

- The caller evaluates the returned object through truthiness rather than its state.
- Calibration completion calculates flow from requested duration, not independently established actual runtime.
- Cancellation removes the session before requesting OFF and does not validate the returned shutdown state.

Evidence: [pump_calibration.py:336–392](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/pump_calibration.py?utm_source=chatgpt.com#L336-L392), [pump_calibration.py:405–413](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/pump_calibration.py?utm_source=chatgpt.com#L405-L413).

**Required correction:** explicitly distinguish the current invocation incompatibility from latent outcome and shutdown defects that could become reachable after a signature-only repair.

## **5.3 F-004 — MQTT security and acknowledgement**

**PASS — High, Risk.**

[deployment/mosquitto.conf:1–24](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/deployment/mosquitto.conf?utm_source=chatgpt.com#L1-L24) confirms a listener and commented authentication examples.

[mqtt_broker_wrapper.py:201–223](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/mqtt/mqtt_broker_wrapper.py?utm_source=chatgpt.com#L201-L223) confirms that publication results are internally recorded but not returned as a meaningful delivery outcome.

The source does not establish effective broker authentication, anonymous access, external exposure or deployed topic permissions. Broker defaults and runtime overrides must not be guessed.

Retain both EP-003B and EP-007 dependencies.

## **5.4 F-005 — Resource authorization and isolation**

**PASS — High, Risk.**

The inspected [api_auth.py:30–95](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/middleware/api_auth.py?utm_source=chatgpt.com#L30-L95) establishes write authentication middleware, not comprehensive authorization.

One terminology correction is advisable: the middleware specifically checks the presence of the `user` session key, whereas `_common.get_user_id()` accesses `user_id`.

These are not identical identity assertions.

The broad finding can remain Risk, with F-036–038 retaining the narrower Verified observations.

## **5.5 F-016 — Cross-unit physical-resource coordination**

**HOLD — Medium. ERB-SS-04.**

[infrastructure/database/ops/irrigation_workflow.py:823–890](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/ops/irrigation_workflow.py?utm_source=chatgpt.com#L823-L890) directly establishes that the inspected irrigation reservation is keyed by logical unit ID and expiry.

Two separate propositions must be recorded:

| Proposition                                                                         | Evidence status |
| ----------------------------------------------------------------------------------- | --------------- |
| Inspected reservation does not use physical-resource identity                       | Verified        |
| Actual installation contains conflicting shared physical resources                  | Unverified      |
| Conflicting reservations could produce competing operations if resources are shared | Risk            |

The inherited Unverified classification is defensible only if the finding remains explicitly defined as missing qualification of cross-unit coordination.

It is insufficient if intended to classify the observed lock mechanism itself.

**Recommendation:** retain the existing Medium rating for the unresolved topology question, but document escalation to High where supported shared-resource operation lacks enforced exclusion. Do not silently reclassify the historical row.

## **5.6 F-026 — Inconsistent actuator safety checks**

**PASS — High, Verified.**

[actuator_management_service.py:591–673](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L591-L673) confirms that ordinary ON invokes `SafetyService.can_turn_on()`, while alternative operations delegate differently.

[actuator_entity.py:329–373](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/domain/actuators/actuator_entity.py?utm_source=chatgpt.com#L329-L373) establishes that:

- Toggle can invoke entity-level ON.
- Level changes can fall back to entity-level ON.
- Pulse directly invokes entity-level ON, sleeps and then requests OFF.

The existence of an entity lock is not proof of equivalence with the complete service-level safety policy.

Preserve the finding separately from F-034 because it concerns ordinary alternate operation methods, not only protocol-specific dispatch.

## **5.7 F-027 — Ownerless reservation release**

**PASS — High, Verified.**

[irrigation_workflow.py:823–890](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/ops/irrigation_workflow.py?utm_source=chatgpt.com#L823-L890) confirms transactional acquisition and release by `unit_id` alone.

The synthetic counterexample is straightforward: an expired owner and a replacement owner refer to the same logical reservation, and release does not distinguish their respective ownership epochs.

The acceptance criterion correctly requires ownership-bound release. Physical quarantine must remain independent of reservation lifetime.

## **5.8 F-036 — Resource authorization gaps**

**HOLD — High, Verified. ERB-SS-05.**

The candidate correctly identifies the service-layer gap. Independent inspection establishes a stronger route-to-service chain.

| Pinned evidence                                                                                                                                                                                                        | Observation                                                       |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| [irrigation API:120–139](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/irrigation/__init__.py?utm_source=chatgpt.com#L120-L139)                               | Approval endpoint forwards request ID and session-derived user ID |
| [irrigation_workflow_service.py:391–398](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_workflow_service.py?utm_source=chatgpt.com#L391-L398) | Facade delegates to feedback service                              |
| [irrigation_feedback_service.py:82–123](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_feedback_service.py?utm_source=chatgpt.com#L82-L123)   | Checks status but not requesting user's ownership before approval |
| [\_common.py:40–54](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/_common.py?utm_source=chatgpt.com#L40-L54)                                                  | Defaults missing user ID to `1`                                   |

The reviewed endpoint also has a preceding request retrieval path that returns the identified record without a visible resource-ownership comparison in that method.

This does not establish successful cross-user access against a running application. Global protections, actual session state and complete authorization composition still require qualification.

**Required correction:** add the route and facade anchors, and distinguish authentication, user identity consistency and resource-level authorization.

## **5.9 F-037 — Socket.IO membership authorization**

**PASS — High, Verified.**

[sensor_handlers.py:35–96](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/socketio/sensor_handlers.py?utm_source=chatgpt.com#L35-L96) confirms the permissive room-join behaviour.

[sensor_handlers.py:119–156](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/socketio/sensor_handlers.py?utm_source=chatgpt.com#L119-L156) further establishes that dashboard and device namespace handlers call those helpers.

Session selection is not proof of authorized unit membership.

Required acceptance must test:

- Namespace authentication.
- Initial and subsequent room membership.
- Permission changes and session revocation.
- Actual event delivery and absence of protected information leakage.

A rejection response alone is not a sufficient confidentiality oracle.

## **5.10 F-038 — Excessive public health exemptions**

**PASS — Medium, Verified.**

[api_auth.py:30–81](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/middleware/api_auth.py?utm_source=chatgpt.com#L30-L81) exempts the health blueprint from write authentication.

[health/system.py:380–395](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/health/system.py?utm_source=chatgpt.com#L380-L395) contains a POST endpoint that invokes health alert creation.

The exemption is directly observable. Successful anonymous mutation is not established because the complete deployed middleware and access path have not been exercised.

The proposed explicit public read-only allowlist is appropriate.

## **5.11 F-039 — Execution-time eligibility and freshness**

**HOLD — High, Verified. ERB-SS-05.**

The candidate identifies the missing execution-time revalidation correctly, but additional cases deserve explicit treatment.

[irrigation_detection_service.py:93–120](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_detection_service.py?utm_source=chatgpt.com#L93-L120) checks workflow-disabled and manual-mode conditions during detection.

[irrigation_detection_service.py:144–187](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_detection_service.py?utm_source=chatgpt.com#L144-L187) checks observation age conditionally.

The inspected timestamp logic establishes an upper age test but no corresponding future-timestamp rejection in that block.

[irrigation_execution_service.py:244–292](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L244-L292) establishes that execution consumes the previously created request and applies a configured upper duration bound, but does not re-run all detection eligibility checks.

**Required correction:** explicitly cover policy changes after request creation, manual-mode transitions, future/missing timestamps, non-finite measurements, reassigned resources and changed calibration or operating limits.

Preserve the existing duration bound as an implemented safeguard. It is not an independently qualified physical limit.

## **5.12 F-040 — Valve topology and uncertain shutdown**

**HOLD — High, Verified. ERB-SS-05.**

The current description correctly identifies valve activation before detailed execution logging and uncertain cleanup. It should be more precise about operation ordering.

[irrigation_execution_service.py:309–352](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L309-L352) establishes that:

1. Valve activation is attempted.
2. Execution-start state is recorded.
3. Detailed execution logging occurs.
4. Pump activation follows.

A reported valve error also takes a branch that records failure and releases the unit reservation.

During completion, the service records successful pump execution before the final valve-close attempt. The valve's returned state is not inspected.

Evidence: [irrigation_execution_service.py:142–182](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_execution_service.py?utm_source=chatgpt.com#L142-L182).

This supports a specific concern: **a completed workflow record and released reservation are not sufficient evidence that the entire physical topology has been reconciled.**

The physical valve position is unknown in these counterexamples, not proven open or closed.

Required remediation must preserve a durable record of each consequential operation and unresolved topology state independently of reservation release.

## **5.13 F-041 — Irrigation state transition concurrency**

**HOLD — High, Verified. ERB-SS-05.**

The owner-independent status mutation is directly supported by [irrigation_workflow.py:912–947](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/ops/irrigation_workflow.py?utm_source=chatgpt.com#L912-L947).

The finding should additionally identify that the feedback handlers can report successful approval, delay or cancellation without checking the boolean result of `update_status()`.

Evidence: [irrigation_feedback_service.py:110–154](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/irrigation_feedback_service.py?utm_source=chatgpt.com#L110-L154).

This is both a concurrency and a durable outcome-integrity issue.

A request handler must not report that authorization or cancellation succeeded when the corresponding persistence operation failed.

## **5.14 F-042 — Schedule and bulk result handling**

**PASS — High, Verified.**

[scheduling_service.py:1677–1704](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/scheduling_service.py?utm_source=chatgpt.com#L1677-L1704) confirms that actuator method results are ignored before successful schedule execution is recorded.

The bulk-control path is also directly supported:

- [actuator_management_service.py:285–323](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L285-L323) returns a boolean reflecting the interpreted state.
- [actuators/control.py:92–102](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/devices/actuators/control.py?utm_source=chatgpt.com#L92-L102) ignores that boolean and records success when no exception is raised.

The proposed typed-outcome remediation is necessary and correctly assigned to EP-003B.

# **6. F-043 and ER-04 — Firmware maintenance trust**

**Disposition: HOLD — High, Verified local defects; downstream qualification unresolved.**

**ERB-SS-02 — High.**

This is the most important unresolved external trust boundary in the assigned evidence scope.

## **6.1 Actual source composition**

Upper layers inspected in the application repository. Downstream implementation and deployed trust remain unresolved.

## **6.2 Defect A — Maintenance admission**

[esp32.py:202–242](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/devices/esp32.py?utm_source=chatgpt.com#L202-L242) checks for device identity and firmware URL, retrieves an adapter and invokes firmware maintenance.

The endpoint body does not establish:

- Privileged firmware-maintenance authority.
- Per-device maintenance authorization.
- Artifact authenticity or approved provenance.
- An approved maintenance state or affected-resource inhibition.

Global authentication and possible external restrictions remain distinct questions.

The source-confirmed finding is insufficient local maintenance admission evidence, not confirmed unauthorized remote firmware installation.

## **6.3 Defect B — Unconditional successful status**

The same endpoint returns a `sent` status irrespective of whether the adapter returns a transaction ID.

[sysgrow_adapter.py:517–585](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L517-L585) establishes three materially different possibilities:

| Adapter outcome                 | Meaning                                       | Current API status |
| ------------------------------- | --------------------------------------------- | ------------------ |
| Transaction ID after submission | Submission attempted through adapter contract | `sent`             |
| Transaction ID while offline    | Command queued                                | `sent`             |
| `None`                          | Submission failed or command not sent         | `sent`             |

Neither the transaction ID nor the API status establishes trusted firmware delivery, installation or activation.

This is a directly observed API outcome defect and should be cross-referenced to F-035/F-042.

## **6.4 Defect C — Queued destination is not preserved**

This is an additional source-confirmed issue missing from the replacement evidence.

[sysgrow_adapter.py:826–842](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L826-L842) supplies a custom bridge-level destination for firmware updates.

However:

- The offline queue construction at lines 543–556 does not preserve that destination in the constructed pending command.
- Queue processing at [587–609](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L587-L609) recomputes the ordinary device set topic instead.

The intended destination and replay destination therefore differ in the inspected control flow.

Actual replay and downstream interpretation remain conditional on reconnection, availability and successful publication.

This defect is relevant not only to firmware availability but also to command identity, authorization scope, routing integrity and recovery.

## **6.5 Downstream source availability**

I independently queried the recursive Git tree at the exact application baseline:

[Application baseline Git tree](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21?recursive=1\&utm_source=chatgpt.com)

The complete returned inventory contains ESP32-related documentation and Python adapters, but no identified conventional C/C++/Arduino firmware source, firmware build configuration or Git submodule.

This establishes a bounded repository-inventory result. It does not establish that the firmware source does not exist elsewhere.

ER-04 cannot currently establish downstream trust.

### **Evidence required to resolve ER-04**

| Boundary              | Minimum qualification evidence                                                 |
| --------------------- | ------------------------------------------------------------------------------ |
| Bridge                | Exact source repository, revision, build and command admission                 |
| Artifact retrieval    | Approved artifact origin, destination restrictions and authenticated transport |
| Artifact authenticity | Cryptographic verification against an approved trust root                      |
| Target compatibility  | Hardware identity, firmware compatibility and installation policy              |
| Update lifecycle      | Privileged maintenance authority, bounded lifetime, quiescence and recovery    |
| Boot chain            | Applicable boot verification and authorized rollback policy                    |
| Failure recovery      | Power-loss, interrupted update and failed verification behaviour               |
| Post-update           | Firmware identity, reconciliation, independent protection and qualified rearm  |

These are proposed qualification requirements, not assertions that particular firmware mechanisms are implemented.

No source-level evidence in the inspected application repository permits accepting the downstream device security boundary.

# **7. F-044 — ESP32 MQTT interface incompatibility**

**Disposition: HOLD — High, Verified. ERB-SS-03.**

The replacement row describes wrapper wiring as conditional and not established. The configuration dependency is conditional, but the standard dependency composition can be established directly.

## **7.1 Dependency chain**

1

**ContainerBuilder**

Constructs MQTTClientWrapper when MQTT is enabled

2

**SensorManagementService**

Receives the configured MQTT client

3

**SensorFactory**

Supplies the client to adapter construction

4

**SensorRegistry**

Maps MQTT / WIRELESS to SYSGrowAdapter

5

**SYSGrowAdapter**

Uses the supplied client for publication

Adapter expects

`publish(topic, payload, retain=...)`

Wrapper provides

`publish(topic, payload)`

Incompatible method contracts in the standard MQTT-enabled composition.

### **Pinned evidence**

| Source                                                                                                                                                                                                          | Composition role                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| [container_builder.py:327–357](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container_builder.py?utm_source=chatgpt.com#L327-L357)                          | Creates the wrapper                                  |
| [container_builder.py:740–759](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/container_builder.py?utm_source=chatgpt.com#L740-L759)                          | Passes configured MQTT client into hardware services |
| [sensor_management_service.py:127–143](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/sensor_management_service.py?utm_source=chatgpt.com#L127-L143) | Constructs sensor factory with client                |
| [sensors/factory.py:96–113](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/sensors/factory.py?utm_source=chatgpt.com#L96-L113)                                | Injects client when not overridden                   |
| [sensors/registry.py:289–293](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/sensors/registry.py?utm_source=chatgpt.com#L289-L293)                            | Registers SYSGrow adapter for supported protocols    |
| [sysgrow_adapter.py:489–515](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L489-L515)             | Passes unsupported keyword argument                  |
| [mqtt_broker_wrapper.py:201–223](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/mqtt/mqtt_broker_wrapper.py?utm_source=chatgpt.com#L201-L223)                 | Provides incompatible signature                      |

The bridge-command fallback in [esp32.py:89–102](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/devices/esp32.py?utm_source=chatgpt.com#L89-L102) additionally constructs an adapter directly using the container MQTT client.

### **Counterexample**

An adapter instantiated with a different compatible MQTT client may not exhibit this signature error. The sensor factory also permits explicitly supplied client parameters.

Therefore, a universal claim that every ESP32 command fails would be inaccurate.

### **Mandatory correction**

Replace the unresolved composition wording with:

> The standard MQTT-enabled container and sensor-factory composition supplies MQTTClientWrapper to SYSGrowAdapter unless overridden. Their publish signatures are incompatible. Actual invocation, runtime configuration and physical effects remain untested.

The remediation must address both signature compatibility and meaningful publication outcomes.

Merely adding a `retain` parameter would not resolve the underlying delivery-certainty problem.

# **8. Command authority and physical-safety contract qualification**

The following target architecture is documented in the candidate's inherited governance and remains appropriate.

Primary governance sources:

[FOUNDATION_BASELINE.md:49–100](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/architecture/FOUNDATION_BASELINE.md?utm_source=chatgpt.com#L49-L100), [D0-CONTRACTS.md](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/plans/D0-CONTRACTS.md?utm_source=chatgpt.com), [SECURITY.md](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/SECURITY.md?utm_source=chatgpt.com).

| Safety contract                                    | Documentary assessment |
| -------------------------------------------------- | ---------------------- |
| Exclusive physical runtime                         | PASS                   |
| Explicit human/service principal                   | PASS                   |
| Action/resource-level authorization                | PASS                   |
| Current approval and policy revalidation           | PASS                   |
| Durable admission and revocation ordering          | PASS                   |
| Typed processing and physical outcomes             | PASS                   |
| Consequential lifecycle effects                    | PASS                   |
| Owner-bound physical reservations                  | PASS                   |
| Durable quarantine                                 | PASS                   |
| Restart and stale persistence recovery             | PASS                   |
| Independent protection                             | PASS                   |
| Restricted emergency authority                     | PASS                   |
| Qualified rearm                                    | PASS                   |
| Firmware-specific trust and maintenance acceptance | HOLD                   |

These are documentary contract dispositions. They provide no evidence of implemented enforcement.

## **8.1 Typed outcomes**

The candidate correctly retains distinct requested, authorized, dispatched, acknowledged, verified, rejected, failed and unknown states.

1

**Requested**

Intent received

2

**Authorized**

Admission requirements satisfied

3

**Dispatched**

Submission established

4

**Acknowledged**

Correlated acknowledgement received

5

**Verified**

Fresh, appropriate physical-state evidence

Rejected

Admission denied

Failed

Known processing failure

Unknown

Physical certainty absent

A failed processing result and unknown physical state can coexist. They should not be modeled as mutually exclusive terminal outcomes.

That distinction is already supported by [FOUNDATION_BASELINE.md:77–88](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/architecture/FOUNDATION_BASELINE.md?utm_source=chatgpt.com#L77-L88).

No further general correction is required to the documentary outcome contract.

# **9. Remediation acceptance and fault-test sufficiency**

**Overall disposition: HOLD — ERB-SS-06, Medium.**

The inherited G0.3 common fault-test requirements are substantially improved.

[REMEDIATION.md:124–148](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/plans/REMEDIATION.md?utm_source=chatgpt.com#L124-L148) requires actual composed services, isolated persistence, controlled clocks, deterministic barriers, captured adapter calls and positive controls for lowest-interface instrumentation.

These address significant weaknesses identified by the archived security reviews.

## **9.1 Reassessment of archived security concerns**

| Historical concern                                      | Current documentary disposition |
| ------------------------------------------------------- | ------------------------------- |
| Persistent quarantine and restart recovery              | PASS                            |
| Scoped authority and dispatch ordering                  | PASS                            |
| Physical-state uncertainty                              | PASS                            |
| Independent protection and emergency authority          | PASS                            |
| Existing-installation restrictions                      | PASS                            |
| G0.2-SS-01: lifecycle effects outside command admission | PASS                            |
| G0.2-SS-02: combined recovery and transport faults      | PASS                            |
| G0.2-SS-03: service-principal authorization             | PASS                            |

Applicable historical evidence: [G0.1 Reviewer 2](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/reviews/G0.1-reviewer-2.md?utm_source=chatgpt.com), [G0.2 Reviewer 2](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/reviews/G0.2-reviewer-2.md?utm_source=chatgpt.com), [G0.3 correction record](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/G0.3-REVIEW.md?utm_source=chatgpt.com).

The current contracts address these concerns at design level. Their historical HOLD verdicts remain unchanged.

## **9.2 Required fault-test oracle extensions**

The existing FT identifiers should preferably be extended instead of creating duplicate tests.

| Existing tests         | Required explicit extension                                                                                                  |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| FT-005/007/019/043     | Exercise factory-created entities through actual service interfaces, including registration and protocol-specific delegation |
| FT-005/006/022         | Calibration signature, typed failure, non-finite input, actual runtime, uncertain cancellation and durable reconciliation    |
| FT-002/003/004/020/030 | Pending approval, operating-mode changes, original versus replacement due time, failed status persistence                    |
| FT-008/011/029/032     | Verify real wrapper/adapter compatibility, queue admission, known failure and ambiguous delivery                             |
| FT-013/025/037/040/044 | Valve uncertainty before logging and successful pump completion followed by uncertain valve shutdown                         |
| FT-017/018/045         | Authentication, identity mismatch, direct/child resource permission and revoked socket membership                            |
| FT-021/042             | Returned rejection without exception must never produce a successful execution record                                        |
| FT-024/027/036         | Explicit firmware-maintenance authority, artifact trust, queued destination preservation, expiry and revocation              |

## **9.3 Required firmware test design**

FT-024 currently states the essential expectation: firmware trust absent means block the update.

That is directionally correct but insufficient as the sole explicit firmware oracle.

The future authorized maintenance qualification needs distinguishable cases for:

| Fault condition                           | Required result                                      |
| ----------------------------------------- | ---------------------------------------------------- |
| Unauthorized maintenance principal        | No consequential submission                          |
| Authorized principal, unauthorized target | Rejected                                             |
| Invalid or untrusted artifact             | Rejected before installation                         |
| Unavailable transport                     | Known failure or queued state, never false `sent`    |
| Revoked queued request                    | No new dispatch; reconcile any prior submission      |
| Replayed command with altered destination | Rejected or safely inhibited                         |
| Missing acknowledgement                   | Unverified outcome                                   |
| Interrupted update                        | Qualified recovery or durable maintenance inhibition |
| Unexpected firmware identity              | No ordinary activation                               |
| Failed rearm prerequisites                | Resource remains inhibited                           |

Actual firmware testing requires the missing downstream implementation evidence and separate authorization.

I am not proposing that these tests be executed under the current documentation-only assignment.

# **10. D0–R–Q sequencing**

**Disposition: PASS — documentary dependency preservation.**

The replacement evidence does not alter the previously established staged remediation ordering.

D0

**Design contracts**

Resolve mandatory architecture and validation questions

R1a

**Runtime containment**

Deny unqualified consequential effects

R1b

**Irrigation containment**

Strict inhibition or qualified bounded alternative

R2a

**Minimum enforcement and recovery**

Admission, outcomes, persistence, authorization

R2b

**Bounded runtime ownership**

Separate-process and dispatch qualification

R3a

**Full irrigation and persistence contracts**

Topology, reservation, freshness and recovery

R3b

**Lifecycle, protection and platform**

Quiescence, independent protection and rearm

Q

**Independent scoped qualification**

Applicable evidence and closure disposition

**Production activation**

Separate qualification, site disposition and explicit authorization

Evidence: [REMEDIATION.md:86–103](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/plans/REMEDIATION.md?utm_source=chatgpt.com#L86-L103).

The important distinction is preserved: R2b establishes bounded ownership, not full F-001 closure. Full EP-001 and EP-003C closure remains reserved for Q with all applicable evidence.

No circular dependency or premature physical activation authorization was identified in the reviewed sequencing.

# **11. EGA-001 — Proposed evidence governance amendment**

## **11.1 Scope and gate substitution**

**Disposition: PASS for security and safety gate preservation. HOLD for acceptance.**

Primary evidence: [EVIDENCE-GOVERNANCE-AMENDMENT.md:3–11](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md?utm_source=chatgpt.com#L3-L11).

EGA-001 correctly limits the proposed substitution to the original CP0–CP2 technical-report provenance and semantic-reconciliation prerequisite.

It does not claim to recreate missing reports, establish historical phase attribution or invalidate adverse reviewer verdicts.

| Mandatory gate                                 | Preserved? |
| ---------------------------------------------- | ---------- |
| Permanent original-provenance limitation       | Yes        |
| Independent replacement evidence qualification | Yes        |
| Resolution of material finding disagreements   | Yes        |
| All existing runtime findings remain open      | Yes        |
| Independent final-candidate review             | Yes        |
| Applicable successful exact-HEAD CI            | Yes        |
| Effective integration enforcement              | Yes        |
| Separate owner integration approval            | Yes        |
| Separate ADR acceptance                        | Yes        |
| D0/R/Q implementation ordering                 | Yes        |
| Device-specific qualification                  | Yes        |
| Independent protection requirements            | Yes        |
| Separate production activation approval        | Yes        |

I find no explicit safety-gate waiver in EGA-001.

## **11.2 Material qualification counterexample**

Suppose the owner accepts EGA-001 while the replacement register still incorrectly characterizes registered protocol delegation or treats missing downstream firmware evidence as a resolved matter.

That would violate the amendment's own eligibility requirements.

Its acceptance condition therefore cannot presently be satisfied.

The correct remedy is not to reject the concept of evidence replacement. It is to correct and independently qualify the replacement evidence before accepting the substitution.

## **11.3 Durable evidence preservation**

The six proposed rules in [EGA-001:15–20](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md?utm_source=chatgpt.com#L15-L20) are appropriate.

| Clause             | Assessment                                                         |
| ------------------ | ------------------------------------------------------------------ |
| Before work        | PASS — authorization, revision and provenance                      |
| During work        | PASS — original evidence, limitations and protected data handling  |
| At checkpoint      | PASS — integrity, retention and retrieval                          |
| Before integration | PASS — independent verification and actual CI checkout correlation |
| After integration  | PASS — resulting revision and preservation of adverse results      |
| Evidence retention | PASS — durable storage and no retrospective fabrication            |

One implementation consideration should be recorded for subsequent security planning: access-controlled evidence storage must itself have appropriately scoped permissions, retention controls and a tested recovery mechanism.

Cryptographic integrity alone does not establish the accuracy or authorization of an evidence artifact.

# **12. Mandatory corrections for the next candidate**

### **Reviewer 2 correction checklist**

0/8

**ERB-SS-01**

Correct F-034 registered adapter composition; retain the independent unregistered-device path.

**ERB-SS-02**

Expand F-043 and ER-04 to distinguish maintenance admission, unconditional sent status, queue destination integrity and unresolved downstream trust.

**ERB-SS-03**

Add confirmed container composition anchors for F-003 and F-044; preserve conditional runtime reachability.

**ERB-SS-04**

Separate the Verified lock-key observation from the Unverified shared-topology qualification in F-016.

**ERB-SS-05**

Strengthen F-033/036/039/040/041 evidence with timing, route composition, current policy, persistence outcomes and partial recovery.

**ERB-SS-06**

Extend applicable FT designs and remediation acceptance criteria for calibration, firmware maintenance, real interface composition and typed outcomes.

**Evidence gate**

Obtain pinned downstream firmware evidence or resolve its exact mandatory qualification applicability without misrepresenting trust.

**Requalification**

Obtain fresh independent reviews of the corrected exact candidate HEAD.

Manual tracking only. Checking an item does not establish repository changes or independent qualification. Copy correction register

No new foundation finding identifiers are necessary at this stage. The newly identified observations can be incorporated into existing finding definitions, with traceable revision history and explicit reviewer reconciliation.

That is my proposed approach, not an owner-approved register change.

# **13. Remaining integration gates**

Fresh read-only GitHub queries returned the following for the exact candidate:

| Evidence                           | Observed result                              |
| ---------------------------------- | -------------------------------------------- |
| PR HEAD                            | Matches authorized candidate                 |
| PR base                            | Matches application baseline                 |
| PR state                           | Open, draft                                  |
| Combined status                    | Pending                                      |
| Returned commit status entries     | 0                                            |
| Returned check runs                | 0                                            |
| Effective repository enforcement   | Not independently established in this review |
| Original CP0–CP2 reports           | Not recovered                                |
| Replacement evidence qualification | HOLD                                         |
| EGA-001 acceptance                 | Not granted                                  |

Primary metadata: [candidate combined status](https://api.github.com/repos/PatoruzuyX/SYSGrow/commits/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/status?utm_source=chatgpt.com), [candidate check runs](https://api.github.com/repos/PatoruzuyX/SYSGrow/commits/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/check-runs?utm_source=chatgpt.com).

Zero returned checks on the candidate commit does not establish the cause of missing CI or exhaustively determine every possible merge-ref workflow state.

The separate integration-enforcement workstream remains necessary.

# **14. Limitations and scope compliance**

This review independently inspected pinned application source, candidate documentation, relevant archived security-review sections, actual service construction paths and recursive Git tree metadata.

The review has the following limitations:

- The complete original CP0–CP2 reports and original recovery export were not available for inspection.
- Relevant sections of archived security reviews were inspected, but I did not independently reproduce every archived review anchor or read every archived line.
- The review covered the 20 assigned findings, not exhaustive qualification of all 44 findings and every secondary anchor.
- No exhaustive command-origin inventory, penetration test or composed application execution was performed.
- Downstream ESP32 bridge and firmware implementation could not be located in the baseline tree. Its security and safety properties remain unqualified.
- No local checkout, effective inherited repository-policy audit, installed hardware, broker deployment, wiring, physical topology or independent protective mechanism was inspected.
- No tests were executed. All counterexamples are static reasoning or proposed synthetic fault scenarios.
- Severity assignments for the six reviewer corrections and the proposed mapping of additional source observations into existing findings are independent reviewer decisions, not accepted owner decisions.

No repository modifications, Git mutations, submitted reviews, CI dispatch, settings changes, deployment, physical operations or merge were performed.

# **15. Final acceptance record**

# **HOLD**

Reviewer 2

SYSGROW-EVIDENCE-REBASELINE-001

Reviewed candidate

a10107a4f78eea8c37a0b1a6ab7d616a61b4df87

Reviewed tree

6afe5fa9a1838137e80a290ccbb35eab6ea70172

Candidate corrections

**3 High / 3 Medium**

Existing Critical findings

**4 OPEN**

Total foundation findings

**44 OPEN**

Fault-test designs

**45**

Tests executed in review

**0**

Replacement evidence acceptance

HOLD

EGA-001 acceptance

HOLD

G0 integration

HOLD

Production safety

NOT QUALIFIED

**Final recommendation:** retain the evidence-rebaseline approach and the narrowly scoped EGA-001 amendment. Both provide a defensible route forward despite the missing historical reports.

However, do not accept the current candidate as the authoritative replacement evidence basis. Correct ERB-SS-01–06, resolve the applicable mandatory evidence gaps, and independently requalify the resulting exact revision.

The primary objective of this exercise is not merely to reconstruct 44 plausible findings. It is to establish a replacement evidence basis that accurately represents how SYSGrow is actually composed, where authority is enforced, where it is absent, and which security and physical consequences remain unknown.