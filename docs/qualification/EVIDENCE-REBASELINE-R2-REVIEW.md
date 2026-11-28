# SYSGROW-EVIDENCE-REBASELINE-001-R2 — bounded correction record

Authorized existing PR #3 branch; starting HEAD `47794834e009334aa417b913fcc6818407ad234e`, tree `1f29e1d88a612712d957914d0f37c0e8af0b3e97`; application baseline `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`. Documentation only; all 44 findings OPEN, four Critical, 12 ADRs proposed. No runtime changes, tests, model operations, CI dispatch, settings, firmware, deployment, physical operations, EGA-001 acceptance or merge. D0–R1a/R1b–R2a/R2b–R3a/R3b–Q and CP3–CP7 preserved.

## Historical independent verdicts at R1

[Reviewer 1](reviews/EVIDENCE-REBASELINE-R1-reviewer-1.md) PASS assigned scope, one non-blocking Low; [Reviewer 2](reviews/EVIDENCE-REBASELINE-R1-reviewer-2.md) HOLD, two High/one Medium; [Reviewer 3](reviews/EVIDENCE-REBASELINE-R1-reviewer-3.md) HOLD, two High/one Medium. All integration HOLD. Six blocking and one non-blocking observations, separate from the runtime register. [Provenance](reviews/PROVENANCE.md) preserves three new complete reports and excludes duplicate initial rebaseline reviewer 3. Earlier ten archives unchanged.

| Correction | Severity | Original observation | Documentary response / affected findings |
|---|---|---|---|
| R2-01 | High | R1-SS-01 | F-043/044 queue capacity, eviction accounting, replay failure, compatible-client non-success, operation/target/response correlation; FT-008/024/027/029/032 |
| R2-02 | High | R1-SS-02 | F-003 durable calibration completion, independent bounds, actual elapsed runtime, shutdown reconciliation and failed persistence; FT-005/006/020/022 |
| R2-03 | Medium | R1-SS-03 | F-041 zero-row success and ignored Boolean; exact expected-state/version and one committed transition, no failed-transition learning; FT-004/020/030 |
| R2-04 | High | ER-R3-R1-001 | F-007 implicit active registration and trainer callers, inactive selection, malformed metrics/ground truth, unsuccessful retraining completion; F-032 durable outcome dependency |
| R2-05 | High | ER-R3-R1-002 | F-008 actual predictor composition, immutable bundle, pre-deserialization trust, cache invalidation |
| R2-06 | Medium | ER-R3-R1-003 | CP4 negative lifecycle, coherence, persistence, concurrency and independent control admission design; all twelve cases in report table (authorization described eleven) |
| R2-07 | Low, non-blocking | REB-R1-RQ-01 | EGA-001 historical method limitation date-scoped; R1 primary tree evidence acknowledged; no authority change |

All seven candidate corrections in [replacement matrix](EVIDENCE-REBASELINE-001.md), [remediation/CP4 oracles](../plans/REMEDIATION.md) and [EGA-001](EVIDENCE-GOVERNANCE-AMENDMENT.md) await independent qualification. Existing observations and closure criteria retained and extended, not a new runtime architecture. Source-confirmed facts separated from conditional impacts. Actual queue/transport, calibration, database, model and hardware outcomes untested. No severity/owner change. Existing FT-001–045 retained, no new physical test IDs, none executed. Twelve CP4 design rows retained because Reviewer 3 lists twelve, not eleven; this is not new execution authority.

## Mandatory gates and delivery

EGA-001 remains PROPOSED; historical CP0–CP2 originals/raw recovery export remain unrecovered; original prerequisite remains binding until valid limited owner acceptance after independent replacement qualification. ER-04 bounded application source evidence distinct from downstream firmware/bridge/bootloader trust HOLD for applicable maintenance/device qualification. ER-05/F-012 effective required-check enforcement and successful applicable final-candidate CI remain mandatory pre-G0 integration. Three fresh exact-HEAD independent reviews, explicit EGA-001 limited acceptance and separate owner integration approval required. Production safety NOT QUALIFIED. No local worktree or deployed hardware inspected. Final commit/tree, archive readback and structural verification in PR evidence outside candidate tree. [R2 independent assignments](EVIDENCE-REBASELINE-REVIEW.md).
