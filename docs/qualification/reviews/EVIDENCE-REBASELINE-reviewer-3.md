# **SYSGROW-EVIDENCE-REBASELINE-001**

## **Independent qualification — Reviewer 3**

**Evidence, Integration and ML Qualification**

HOLD

**Mandatory evidence qualification and integration gates**

**Review date:** 28 November 2026\
**Repository:** [PatoruzuyX/SYSGrow](https://github.com/PatoruzuyX/SYSGrow?utm_source=chatgpt.com)\
**Pull request:** [PR #3](https://github.com/PatoruzuyX/SYSGrow/pull/3?utm_source=chatgpt.com)\
**Review authority:** Independent, read-only qualification.

The replacement-evidence exercise must be assessed independently of the historical CP0–CP2 conclusions. A source-supported finding can remain OPEN in a qualified documentary baseline, but an unverified mandatory evidence dependency cannot be treated as an accepted residual risk.

The integration HOLD is independently established by the current CI evidence. This does not, by itself, determine whether the replacement documentation is technically sufficient.

## **1. Candidate identity and ancestry**

Exact candidate HEAD — verified

a10107a4f78eea8c37a0b1a6ab7d616a61b4df87

Candidate tree — verified

6afe5fa9a1838137e80a290ccbb35eab6ea70172

Direct governance parent — verified

5d646ba58cb071b392cea94287371925ba82e626

Application baseline and current main — verified

2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21

Verified GitHub commit ancestry; not an authorization or integration sequence.

| Verification                               | Result                |
| ------------------------------------------ | --------------------- |
| PR HEAD matches assignment                 | PASS                  |
| Exact Git tree matches assignment          | PASS                  |
| Direct parent matches assignment           | PASS                  |
| Candidate relative to governance parent    | 1 ahead, 0 behind     |
| Candidate relative to application baseline | 5 ahead, 0 behind     |
| Current main matches application baseline  | PASS                  |
| PR status                                  | Open, draft, unmerged |
| GitHub mergeability                        | Clean, mergeable      |

Primary evidence: [Git commit object](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/commits/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87?utm_source=chatgpt.com), [parent comparison](https://github.com/PatoruzuyX/SYSGrow/compare/5d646ba58cb071b392cea94287371925ba82e626...a10107a4f78eea8c37a0b1a6ab7d616a61b4df87?utm_source=chatgpt.com), [baseline comparison](https://github.com/PatoruzuyX/SYSGrow/compare/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21...a10107a4f78eea8c37a0b1a6ab7d616a61b4df87?utm_source=chatgpt.com).

### **1.1 Documentation-only scope**

The direct candidate changes are:

| File                               | Additions | Deletions |
| ---------------------------------- | --------- | --------- |
| `docs/INDEX.md`                    | 5         | 0         |
| `EVIDENCE-GOVERNANCE-AMENDMENT.md` | 22        | 0         |
| `EVIDENCE-REBASELINE-001.md`       | 74        | 0         |
| `EVIDENCE-REBASELINE-REVIEW.md`    | 13        | 0         |
| `EVIDENCE-RECOVERY-CROSSWALK.md`   | 15        | 0         |
| **Total**                          | **129**   | **0**     |

The full comparison against the application baseline returns 35 changed files, all documentation or governance Markdown files. No application source, firmware, dependency, database migration or CI workflow modification appears in that comparison.

**Disposition: PASS — documentary diff scope.**

## **2. Current CI and integration enforcement**

The following evidence was retrieved directly from GitHub, rather than inherited from previous reviews.

| Evidence                                       | Current observation                |
| ---------------------------------------------- | ---------------------------------- |
| Exact-HEAD check runs                          | 0                                  |
| Exact-HEAD PR-triggered workflow runs returned | 0                                  |
| Main branch `protected`                        | `false`                            |
| Branch protection metadata                     | `enabled: false`                   |
| Required status-check enforcement              | `off`                              |
| Required check contexts                        | Empty                              |
| Required check definitions                     | Empty                              |
| Accessible rulesets, including parents         | Empty response                     |
| Detailed branch protection endpoint            | HTTP 403                           |
| Effective branch rules endpoint                | Unavailable through the connection |

Pinned/current evidence: [candidate check runs](https://api.github.com/repos/PatoruzuyX/SYSGrow/commits/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/check-runs?utm_source=chatgpt.com), [main branch metadata](https://api.github.com/repos/PatoruzuyX/SYSGrow/branches/main?utm_source=chatgpt.com), [repository rulesets](https://api.github.com/repos/PatoruzuyX/SYSGrow/rulesets?includes_parents=true\&utm_source=chatgpt.com).

The accessible evidence does not establish effective required-check enforcement. The inaccessible administrative endpoints prevent a complete effective-policy assessment.

**F-012 remains OPEN. ER-05 remains HOLD. Integration remains prohibited under the proposed G0 governance requirements.**

GitHub reporting a clean merge state is not equivalent to successful CI, effective branch protection, independent qualification or owner authorization.

## **3. Finding register integrity — all 44 findings**

I retrieved the replacement matrix and the existing canonical register from the exact candidate revision and compared their first seven fields row by row.

Finding identities reconciled

# **44/44**

Core field discrepancies

# **0**

Inherited source references retained

# **82/82**

Total replacement reference occurrences

# **91**

**Severity distribution**

Critical

**4**

High

**26**

Medium

**14**

**Evidence classification**

Verified: 29

Risk: 11

Unverified: 4

Verified denotes the register's evidence classification, not independent runtime or safety certification.

| Comparison field          | Matches | Disposition                |
| ------------------------- | ------- | -------------------------- |
| Finding ID                | 44/44   | PASS                       |
| Inherited discovery phase | 44/44   | PASS for preservation only |
| Severity                  | 44/44   | PASS for preservation      |
| Evidence classification   | 44/44   | PASS for preservation      |
| Finding definition/title  | 44/44   | PASS                       |
| Owner work package        | 44/44   | PASS for preservation      |
| OPEN disposition          | 44/44   | PASS                       |

Pinned evidence:

- [Original findings register, L5–50](https://github.com/PatoruzuyX/SYSGrow/blob/5d646ba58cb071b392cea94287371925ba82e626/docs/qualification/FINDINGS.md?utm_source=chatgpt.com#L5-L50)
- [Replacement matrix, L19–64](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/EVIDENCE-REBASELINE-001.md?utm_source=chatgpt.com#L19-L64)
- [Replacement classification and ownership rules, L15–17](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/EVIDENCE-REBASELINE-001.md?utm_source=chatgpt.com#L15-L17)

### **3.1 Source anchor inventory**

| Metric                               | Independently counted |
| ------------------------------------ | --------------------- |
| Original reference occurrences       | 82                    |
| Replacement reference occurrences    | 91                    |
| Additional occurrences               | 9                     |
| Distinct referenced source files     | 44                    |
| References with explicit line ranges | 76                    |
| Whole-file references                | 15                    |
| Inherited reference URLs missing     | 0                     |

These counts establish reference continuity. They do **not** establish that every reference is semantically sufficient.

The replacement preserves the four Critical findings without downgrading or closing them:

| Finding | Definition                                | Owner   |
| ------- | ----------------------------------------- | ------- |
| F-001   | Competing runtime ownership               | EP-001  |
| F-033   | Required irrigation approval not enforced | EP-003C |
| F-034   | Protocol-specific command safety bypass   | EP-003A |
| F-035   | False physical-operation success          | EP-003B |

The register's structural continuity passes. Independent technical justification of all classifications and severities remains a separate qualification obligation.

## **4. ER-01 — Test inventory and reproducibility**



PASS — tree inventory

HOLD — execution and coverage



Unlike the previous recovery crosswalk, I obtained the complete recursive Git tree directly from the pinned application commit. GitHub reported `truncated: false`.

**Application tree:** [6f59af9c2fdeff431bfb83411ee17bdf6619a016](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/6f59af9c2fdeff431bfb83411ee17bdf6619a016?recursive=1\&utm_source=chatgpt.com).

| Inventory                         | Original consolidation | Reproduced |
| --------------------------------- | ---------------------- | ---------- |
| Tracked files                     | 780                    | 780        |
| Python files                      | 487                    | 487        |
| Python files under `tests/`       | —                      | 67         |
| Test-named Python modules         | 65                     | **66**     |
| Other Python files under `tests/` | —                      | 1          |

The remaining Python file is `tests/conftest.py`.

The reproducible inventory rule is to enumerate non-directory Git tree entries under `tests/` ending in `.py`, and separately count files matching the test-module filename convention.

### **ER-01 conclusion**

The discrepancy between 65 and 66 test modules is independently resolved **for the pinned application tree**.

It remains impossible to determine why the original CP0 report recorded 65 without recovering its original enumeration procedure or output.

This does not establish:

- The number of collected pytest test cases.
- Successful test execution or absence of skipped tests.
- Statement, branch or service coverage.
- Hardware simulator completeness or production safety.

The historical 65 count should remain preserved, with the independently reproduced 66-module inventory recorded as new evidence.

## **5. ER-02 — Historical branch identity and tree reconciliation**

PASS — structural reproduction

I retrieved all four historical branch references, their pinned commit objects, complete recursive trees and ancestry comparisons.

All four current branch heads still match their historical recorded revisions.

| Branch                           | Current and historical HEAD | Match |
| -------------------------------- | --------------------------- | ----- |
| `codex/main-snapshot-20260314`   | `b1f17eb`                   | Yes   |
| `codex/pi-db-init-fix`           | `0e44e00`                   | Yes   |
| `codex/unit-create-fix-20260315` | `b9305e2`                   | Yes   |
| `codex/stash-backup-20260315`    | `9182885`                   | Yes   |

### **5.1 Independently reproduced tree comparisons**

The comparison uses file paths, object SHAs and Git file modes, rather than filenames or aggregate counts alone.

**Main snapshot**

156

372

1169

252

**Pi database initialization fix**

156

372

1169

252

**Unit creation fix**

156

372

1169

252

**Stash backup**

204

440

146

136

Identical

Changed

Branch-only

Main-only

| Branch            | Same | Changed | Branch-only | Main-only |
| ----------------- | ---- | ------- | ----------- | --------- |
| Main snapshot     | 156  | 372     | 1,169       | 252       |
| Pi DB fix         | 156  | 372     | 1,169       | 252       |
| Unit creation fix | 156  | 372     | 1,169       | 252       |
| Stash backup      | 204  | 440     | 146         | 136       |

All four comparisons reproduce the recorded CP1 figures exactly.

### **5.2 Pinned tree evidence**

| Historical branch | Direct Git tree                                                                                                                                                                    |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Main snapshot     | [cb85d04b5b5e5ec99bac9c366fac1732d5ce68e1](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/cb85d04b5b5e5ec99bac9c366fac1732d5ce68e1?recursive=1\&utm_source=chatgpt.com) |
| Pi DB fix         | [a146736a820afaf21be0a47061124f8c1a07b170](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/a146736a820afaf21be0a47061124f8c1a07b170?recursive=1\&utm_source=chatgpt.com) |
| Unit creation fix | [30235efb4ebf1657f9b1de5511bd9de06db6e246](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/30235efb4ebf1657f9b1de5511bd9de06db6e246?recursive=1\&utm_source=chatgpt.com) |
| Stash backup      | [bccd5eb1796116a9f27b613f8ba0c0a9184d0b12](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/bccd5eb1796116a9f27b613f8ba0c0a9184d0b12?recursive=1\&utm_source=chatgpt.com) |

None of these tree responses was truncated.

### **5.3 Ancestry**

GitHub explicitly returned “No common ancestor” for the first three branches when compared with the application baseline.

For the stash backup branch, GitHub returned:

- Status: diverged.
- Ahead: 1 commit.
- Behind: 4 commits.
- Common ancestor: `1f2cd5bfa6cbf0acced68762d72ed45d66b41527`.

These results match [CP0–CP2.md, L15–24](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/CP0-CP2.md?utm_source=chatgpt.com#L15-L24).

### **5.4 Counterexample to semantic equivalence**

The first three branches have identical aggregate comparison counts but **different Git tree identities**. Identical counts therefore cannot establish that their contents are interchangeable.

F-020's Verified classification and Medium severity are supported as a branch-reconciliation finding. The EP-006 ownership remains appropriate.

**F-020 remains OPEN.** Individual recovery decisions, semantic review and authorization are still required. No branch deletion, unrelated-history merge or bulk cherry-pick is justified.

The replacement crosswalk may now rely on this independently reproduced structural evidence instead of relying solely on historical conversation-summary counts.

## **6. ER-03 — Forecasting leakage and ML qualification**

### **F-006 — Climate training target leakage**

**Baseline severity:** High\
**Classification:** Verified\
**Replacement evidence:** PASS — source-confirmed defect\
**Runtime finding:** OPEN

Pinned application evidence:

- [ml_trainer.py, L112–125](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L112-L125)
- [ml_trainer.py, L137–196](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L137-L196)
- [ml_trainer.py, L267–318](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L267-L318)

Three distinct methodological defects are independently supported.

**Current training pipeline**

**Required forecasting evaluation pipeline**

| Defect                         | Direct source observation                                                             |
| ------------------------------ | ------------------------------------------------------------------------------------- |
| Target leakage                 | Environmental features contain the same variables selected as prediction targets.     |
| Preprocessing leakage          | Numeric imputation and IQR filtering occur before partitioning.                       |
| Temporal contamination         | Random train/test splitting does not establish future-period generalization.          |
| Cross-validation contamination | Scaling is fitted before cross-validation rather than independently within each fold. |

**Counterexample:** A temperature model can receive the current row's temperature as an input while predicting that same row's temperature. A high R² score would not demonstrate an ability to predict future temperature.

The replacement appropriately limits the finding to a forecasting objective. Same-row reconstruction or estimation could be a legitimate separate objective, provided its intended inference inputs are independently established.

**Required CP4 closure evidence:** explicit prediction horizon, feature availability timestamps, train-only preprocessing, leakage-resistant folds, independent temporal holdout, appropriate baseline comparisons and documented promotion criteria.

No model was trained or promoted during this review.

### **F-007 — Inconsistent model eligibility lifecycle**

**Baseline severity:** High\
**Classification:** Risk\
**Replacement evidence:** HOLD — material source evidence requires strengthening.

The replacement correctly identifies two gaps:

| Source                                                                                                                                                                                            | Verified behaviour                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| [ml_readiness_monitor.py, L368–399](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_readiness_monitor.py?utm_source=chatgpt.com#L368-L399) | Activation checks the model name and delegates enabling.                                            |
| [drift_detector.py, L157–212](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/drift_detector.py?utm_source=chatgpt.com#L157-L212)             | Missing prediction history returns perfect accuracy, perfect confidence and an `ok` recommendation. |

However, additional independently inspected sources strengthen the finding materially.

| Additional evidence                                                                                                                                                                                      | Observation                                                                                   |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| [irrigation_ml.py, L200–222](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/repositories/irrigation_ml.py?utm_source=chatgpt.com#L200-L222) | Repository enabling does not independently enforce sample readiness.                          |
| [model_registry.py, L529–549](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L529-L549)                    | Version selection prefers active entries but can fall back to a latest entry.                 |
| [model_registry.py, L551–610](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L551-L610)                    | Promotion changes registry status without independently evaluating model eligibility metrics. |

A registry containing only inactive model versions is a counterexample to treating a returned production-version identifier as proof of approved promotion.

Conversely, existing [ML Sprint 4 gating tests](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/tests/test_ml_sprint4_gating.py?utm_source=chatgpt.com) and [irrigation no-fallback tests](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/tests/unit/services/test_irrigation_ml_gating_no_fallback.py?utm_source=chatgpt.com) demonstrate that some eligibility controls already exist.

Therefore, a blanket assertion that SYSGrow has no ML eligibility enforcement would be incorrect.

**Required correction:** Add the registry-selection, promotion and repository-enabling anchors. Distinguish feature enablement, model availability, qualification, production selection, inference eligibility and physical-control authorization.

Retain High severity. Risk remains defensible for the system-wide consequence, while the local enforcement gaps are source-confirmed.

### **F-008 — Model artifact trust boundary**

**Baseline severity:** High\
**Classification:** Risk\
**Replacement evidence:** PASS for the bounded model-loading observation; HOLD for complete artifact trust coverage.

The registry loads serialized model objects through `joblib.load()` without an independently demonstrated authenticity check in the inspected loading path.

The replacement cites [model_registry.py, L387–404](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L387-L404).

An additional artifact-loading path exists at [L412–448](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L412-L448), including a separate `joblib.load()` call.

The threat is not limited to the primary model. Scalers, encoders and other serialized artifacts belong to the same trust boundary.

**Counterexample:** A trusted model file does not establish the integrity of a separately substituted preprocessing artifact.

Required qualification must cover artifact provenance, integrity, path containment, writer permissions, trusted deserialization, metadata binding and all loading entry points.

No malicious artifact was created or deserialized. Exploitability remains conditional on artifact and deployment control.

### **F-017 — ML workload contention**

**Baseline severity:** Medium\
**Classification:** Risk\
**Replacement evidence:** PASS.

The climate trainer configures `RandomForestRegressor` with `n_jobs=-1` at [ml_trainer.py, L302–305](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L302-L305).

This supports the concern that ML training may compete for available CPU resources with control, persistence, communications and scheduling workloads.

It does not establish:

- A missed physical safety deadline.
- A measured Raspberry Pi resource failure.
- That every deployment runs ML training concurrently with consequential control.

CP3 and CP4 joint ownership is appropriate. Closure requires resource-bounded training, cancellation behaviour, scheduling isolation and measured interference under the applicable qualified composition.

### **F-032 — Model registry concurrent writer integrity**

**Baseline severity:** High\
**Classification:** Risk\
**Replacement evidence:** PASS for the core concern; stronger closure evidence required.

[model_registry.py, L181–204](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L181-L204) confirms:

- Registry parsing failures fall back to an empty dictionary.
- Writers use a fixed `.json.tmp` path.
- Replacement is performed after writing JSON.
- Persistence failures are logged without an explicit failure result.

The promotion implementation subsequently calls `_save_registry()` and can return success, as shown in [L551–610](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L551-L610).

**Counterexample:** Two independently initialized registry writers can each derive changes from stale in-memory state. Even if each replacement is individually atomic, the later replacement can discard the other writer's update.

A second possible failure is an unsuccessful persistence operation followed by a successful promotion return.

Required closure includes cross-process coordination, unique artifact/version allocation, atomic lifecycle transitions, explicit persistence outcomes, restart reconciliation and promotion recovery.

Atomic file replacement alone is not transactional registry integrity.

## **7. ER-04 — Firmware maintenance and downstream trust**

### **F-043 — Firmware maintenance trust boundary**

**Baseline severity:** High\
**Classification:** Verified\
**Replacement evidence:** HOLD — downstream trust remains unqualified.

The following application-side chain was independently verified.

Solid boundaries represent inspected application code. Dashed boundaries represent unqualified downstream components, not confirmed defects in the firmware itself.

Pinned source evidence:

| Source                                                                                                                                                                                                | Observation                                                                    |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [esp32.py, L202–242](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/devices/esp32.py?utm_source=chatgpt.com#L202-L242)                        | URL accepted and response labelled `sent`.                                     |
| [sysgrow_adapter.py, L826–842](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L826-L842) | OTA operation delegated to command submission.                                 |
| [sysgrow_adapter.py, L517–585](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L517-L585) | Offline queue and tracked publishing.                                          |
| [sysgrow_adapter.py, L489–515](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L489-L515) | MQTT publishing interface, without independent firmware authenticity evidence. |

### **7.1 Additional queue-replay defect**

The replacement anchor ends at line 603, immediately before the queued command is published.

Extending the inspection to [sysgrow_adapter.py, L587–610](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L587-L610) reveals an additional transport consistency concern:

The initial OTA operation supplies a specific bridge maintenance topic. Offline queue replay reconstructs its destination using the ordinary device set-topic helper instead of preserving that original custom topic.

**Source-confirmed discrepancy:** Initial submission and queued replay do not necessarily preserve the same destination semantics.

The runtime consequences depend on actual bridge behaviour and device configuration, which remain unqualified.

The existing queue-expiration check must also be acknowledged; it would be incorrect to claim that queued commands have no expiration mechanism.

Required correction: extend the source anchor and include destination preservation, replay authorization and explicit submission outcomes within F-043/F-044's closure evidence. Reconcile implementation ownership between EP-007 and EP-003B without creating duplicate command contracts.

### **7.2 Additional historical OTA utility**

The application tree also contains [scripts/ota_updater.py, L27–56](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/scripts/ota_updater.py?utm_source=chatgpt.com#L27-L56), which describes firmware maintenance using plain HTTP endpoints.

This utility is additional evidence requiring an applicability assessment. Its existence does not prove it is deployed, authorized or connected to the current MQTT maintenance path.

No actual downstream firmware implementation was identified in the targeted application-tree inspection. The firmware documentation and maintenance scripts are not substitutes for the bridge, device firmware or bootloader source.

### **ER-04 conclusion**

The following remain unqualified: bridge-side authentication and authorization, signed artifact verification, trust anchors, transport security, replay prevention, anti-rollback behaviour, interrupted-update recovery and post-update physical safety.

The High severity remains appropriate. No evidence establishes that arbitrary or unsigned firmware is actually accepted by deployed hardware.

**ER-04 remains HOLD for downstream technical qualification.** The application-side observation can be independently accepted as a bounded OPEN finding after the evidence is strengthened.

## **8. Remaining primary evidence assignments**

### **F-012 — Mandatory integration checks unqualified**

**Medium / Risk — source and accessible metadata supported.**

The current CI absence and enforcement limitations were established directly in Section 2.

Additional direct observations:

| GitHub evidence                                | Result                                     |
| ---------------------------------------------- | ------------------------------------------ |
| Combined candidate status                      | Pending                                    |
| Combined status entries                        | 0                                          |
| All Actions runs associated with candidate SHA | 0                                          |
| Current synthetic merge commit                 | `8e45cea55bde1a5bf3bcd0aef8da75452d438c69` |
| Synthetic merge commit check runs              | 0                                          |

The integration gate is mandatory regardless of F-012's Medium baseline severity. A finding's severity does not determine whether a separately defined governance prerequisite may be bypassed.

### **F-013 — CI lock and coverage enforcement**

**Medium / Verified — PASS for replacement evidence.**

[ci.yml, L16–56](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/.github/workflows/ci.yml?utm_source=chatgpt.com#L16-L56) defines the following jobs:

| Job      | Declared verification                                         |
| -------- | ------------------------------------------------------------- |
| Lint     | Ruff lint and formatting                                      |
| Tests    | Python 3.13, essential/dev dependency installation and pytest |
| Security | Bandit                                                        |

The workflow installs `requirements-essential.txt` and `requirements-dev.txt`, not the lock file explicitly. Its pytest invocation contains no coverage option.

[pyproject.toml, L236–260](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/pyproject.toml?utm_source=chatgpt.com#L236-L260) contains pytest and coverage configuration, but pytest's configured `addopts` do not activate coverage.

Having coverage configuration and dependencies is not equivalent to enforcing coverage in CI.

The finding and EP-005/CP5 ownership are supported. No fresh test or dependency installation was performed.

### **F-018 — SQL and error-disclosure remediation completeness**

**Medium / Unverified — PASS for conservative classification.**

[http.py, L124–139](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/utils/http.py?utm_source=chatgpt.com#L124-L139) supports the distinction between sanitized server errors and lower-status `SysGrowError` messages.

Additional inspection of [irrigation_ml.py, L200–245](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/repositories/irrigation_ml.py?utm_source=chatgpt.com#L200-L245) identifies dynamic SQL construction requiring caller validation and allowlist assessment.

Dynamic SQL alone does not establish an exploitable injection vulnerability.

Retain the finding as Unverified until the complete repository/API remediation assessment is available.

### **F-019 — Hardware simulation and fault coverage**

**Medium / Unverified — PASS for classification; Medium evidence-description correction required.**

The replacement correctly identifies existing reliability tests in [test_irrigation_reliability.py, L91–179](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/tests/unit/irrigation/test_irrigation_reliability.py?utm_source=chatgpt.com#L91-L179).

However, the test names should not be treated as proof of their full intended properties.

| Existing test                 | Actual inspected evidence                                           |
| ----------------------------- | ------------------------------------------------------------------- |
| Atomic due-request claim      | Two sequential claim operations                                     |
| Parallel-execution prevention | Sequential acquire, reject, release and reacquire                   |
| Valve failure                 | Stub actuator manager and an assertion that the pump was not called |
| No sleep calls                | Textual source inspection                                           |
| Irrigation attribution        | Two direct classification examples                                  |

The atomic-claim and parallel-execution tests do not themselves orchestrate simultaneous workers.

**Counterexample:** A repository can pass sequential duplicate-claim tests while failing under overlapping transactions, process termination or stale-owner replacement.

Required correction: describe the tests according to their actual oracles, not merely their names. Distinguish sequential exclusion, concurrent execution qualification, process isolation, simulated interface effects and HIL evidence.

### **F-021 — Historical backlog drift**

**Medium / Verified — PASS.**

[BACKLOG.md, L23](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/BACKLOG.md?utm_source=chatgpt.com#L23) states that CI does not exist, while the pinned application tree contains the CI workflow.

This is a sufficient concrete example of historical backlog drift.

It does not mean the entire backlog is obsolete or that all historical tasks have been completed.

EP-006 and CP7 ownership remains appropriate.

## **9. All-anchor semantic qualification**

Following the initial reference inventory, I retrieved the 44 distinct referenced source files from the pinned application baseline in smaller batches and inspected the referenced excerpts.

All 91 reference occurrences are accounted for in the replacement matrix. No missing inherited reference URL or out-of-bounds range was identified during the inspection.

**Important limitation:** The consolidated automated range-verification attempt exceeded the connector's per-script call limit. Subsequent smaller batches successfully returned the source files and targeted excerpts, but I do not represent that as a separately preserved automated 91-anchor verification report.

The following row dispositions apply to **replacement evidence sufficiency**, not closure of application defects.

Bounded evidence PASS

# **38**

Evidence HOLD

# **6**

Runtime findings OPEN

# **44**

All 44HOLD (6)PASS (38)

**F-001**

Critical · Verified

PASS

Scheduler, worker topology, conditional MQTT and GPIO construction supported.

Owner: EP-001 · Runtime: OPEN

**F-002**

High · Risk

PASS

Application shutdown observed; independent hardware protection remains unknown.

Owner: EP-003F · Runtime: OPEN

**F-003**

High · Verified

PASS

Calibration call and service signature differ.

Owner: EP-003E · Runtime: OPEN

**F-004**

High · Risk

HOLD

Publish evidence needs its own direct row anchor; deployment trust unknown.

Owner: EP-003B / EP-007 · Runtime: OPEN

**F-005**

High · Risk

PASS

Write authentication does not establish resource authorization.

Owner: EP-007 · Runtime: OPEN

**F-006**

High · Verified

PASS

Same-row target leakage and validation defects confirmed.

Owner: CP4 · Runtime: OPEN

**F-007**

High · Risk

HOLD

Additional registry and repository eligibility paths require incorporation.

Owner: CP4 · Runtime: OPEN

**F-008**

High · Risk

HOLD

Separate artifact-loading path must be included.

Owner: CP4 / CP6 · Runtime: OPEN

**F-009**

High · Verified

PASS

Persistence helpers contain logging placeholders.

Owner: EP-004 / CP4 · Runtime: OPEN

**F-010**

High · Verified

PASS

Flask and Werkzeug dependency constraints conflict.

Owner: EP-005 · Runtime: OPEN

**F-011**

High · Verified

PASS

Docker COPY data/ and missing tracked data path independently verified.

Owner: EP-005 · Runtime: OPEN

**F-012**

Medium · Risk

PASS

Accessible disabled protection and absent CI confirmed; integration still HOLD.

Owner: EP-006 · Runtime: OPEN

**F-013**

Medium · Verified

PASS

No explicit lock or coverage enforcement in inspected workflow.

Owner: EP-005 / CP5 · Runtime: OPEN

**F-014**

Medium · Verified

HOLD

Historical path discrepancies need explicit source/path crosswalk.

Owner: EP-006 · Runtime: OPEN

**F-015**

Medium · Unverified

PASS

Target Pi compatibility claim is not benchmark evidence.

Owner: CP3 · Runtime: OPEN

**F-016**

Medium · Unverified

PASS

Unit-keyed locking observed; actual shared topology remains unqualified.

Owner: EP-003D · Runtime: OPEN

**F-017**

Medium · Risk

PASS

Unbounded parallelism setting supports workload contention concern.

Owner: CP3 / CP4 · Runtime: OPEN

**F-018**

Medium · Unverified

PASS

Limited error and SQL inspection cannot establish complete remediation.

Owner: EP-007 · Runtime: OPEN

**F-019**

Medium · Unverified

HOLD

Test names overstate concurrency evidence; clarify actual test oracles.

Owner: CP5 · Runtime: OPEN

**F-020**

Medium · Verified

PASS

Branch identities, tree differences and ancestry reproduced.

Owner: EP-006 · Runtime: OPEN

**F-021**

Medium · Verified

PASS

Concrete CI backlog discrepancy confirmed.

Owner: EP-006 / CP7 · Runtime: OPEN

**F-022**

Medium · Verified

PASS

Application cache and reload configuration observed.

Owner: CP3 · Runtime: OPEN

**F-023**

High · Verified

PASS

Shared polling service registration and per-unit stop path observed.

Owner: EP-002 · Runtime: OPEN

**F-024**

High · Verified

PASS

Event subscriptions and missing explicit disposal in inspected path.

Owner: EP-002 · Runtime: OPEN

**F-025**

High · Verified

PASS

Shutdown orchestration gaps supported; indirect calls remain conditional.

Owner: EP-002 / EP-003F · Runtime: OPEN

**F-026**

High · Verified

PASS

Alternative methods lack same local safety check.

Owner: EP-003A · Runtime: OPEN

**F-027**

High · Verified

PASS

Release operation lacks owner binding.

Owner: EP-003D · Runtime: OPEN

**F-028**

Medium · Risk

PASS

Queue saturation can drop deliveries; safety impact not reproduced.

Owner: EP-002 / CP3 · Runtime: OPEN

**F-029**

High · Verified

PASS

Database context commits in finally.

Owner: EP-004 · Runtime: OPEN

**F-030**

High · Risk

PASS

Migration and corruption recovery paths support ownership concern.

Owner: EP-004 · Runtime: OPEN

**F-031**

Medium · Risk

PASS

Separate file locking does not establish atomic read-modify-write.

Owner: EP-004 · Runtime: OPEN

**F-032**

High · Risk

PASS

Fixed temp path, persistence failure and concurrent writer risks supported.

Owner: CP4 · Runtime: OPEN

**F-033**

Critical · Verified

PASS

Pending claims and execution-time approval gap supported.

Owner: EP-003C · Runtime: OPEN

**F-034**

Critical · Verified

PASS

Alternative command and construction paths supported.

Owner: EP-003A · Runtime: OPEN

**F-035**

Critical · Verified

PASS

None-to-success and conditional actuator outcome discrepancy supported.

Owner: EP-003B · Runtime: OPEN

**F-036**

High · Verified

PASS

Local resource ownership checks absent in inspected response path.

Owner: EP-007 · Runtime: OPEN

**F-037**

High · Verified

PASS

Room join helper permits paths without established membership.

Owner: EP-007 · Runtime: OPEN

**F-038**

Medium · Verified

PASS

Health write exemption and alert-creation endpoint confirmed.

Owner: EP-007 · Runtime: OPEN

**F-039**

High · Verified

PASS

Conditional detection freshness and execution revalidation gap.

Owner: EP-003E · Runtime: OPEN

**F-040**

High · Verified

PASS

Valve operation ordering and uncertain cleanup confirmed.

Owner: EP-003D / EP-003F · Runtime: OPEN

**F-041**

High · Verified

PASS

Update contract lacks expected-state condition.

Owner: EP-003C / EP-004 · Runtime: OPEN

**F-042**

High · Verified

PASS

Schedule and bulk callers do not inspect returned outcomes.

Owner: EP-003B · Runtime: OPEN

**F-043**

High · Verified

HOLD

Downstream trust, additional OTA utility and replay destination discrepancy.

Owner: EP-007 · Runtime: OPEN

**F-044**

High · Verified

PASS

Publish signature mismatch confirmed; actual wiring remains conditional.

Owner: EP-003B · Runtime: OPEN

These are bounded source-evidence dispositions within Reviewer 3's remit. They do not replace Reviewer 1's architectural assessment or Reviewer 2's physical safety assessment.

### **Additional anchor observations**

- F-004: the existing MQTT wrapper connection anchor ends before its publish implementation. The necessary publish evidence exists at [mqtt_broker_wrapper.py, L201–223](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/mqtt/mqtt_broker_wrapper.py?utm_source=chatgpt.com#L201-L223), already cited elsewhere under F-044. Add that reference directly to F-004.
- F-014: the historical architecture describes older runtime components and paths, while the replacement relies partly on current implementation observations not directly anchored within that row. Add explicit current-versus-historical path mappings.
- F-011: the direct application tree contains no tracked `data/` entry. This independently strengthens the Docker build-input observation, although no Docker build was executed.
- F-028: queue saturation causes the publisher to record a dropped delivery and break out of the callback loop. The Medium severity should remain subject to escalation if a direct safety-deadline dependency is established.

No severity downgrade is recommended in this review.

## **10. Historical documentation and review preservation**

**Disposition: PASS — Git content preservation.**

I compared the complete recursive trees of:

- Parent governance tree: `63cdc7d73456bc18eb6a77646283da2d9908976f`.
- Candidate tree: `6afe5fa9a1838137e80a290ccbb35eab6ea70172`.

The parent contains 804 tracked file entries; the candidate contains 808.

Of the existing parent file entries, only `docs/INDEX.md` changed. The four new evidence documents account for the remaining additions.

This establishes preservation of the existing documentary files, including:

| Historical record               | Preservation |
| ------------------------------- | ------------ |
| Original CP0–CP2 consolidation  | Unchanged    |
| Starting findings register      | Unchanged    |
| G0/G0.2/G0.3 review records     | Unchanged    |
| Seven archived reviewer reports | Unchanged    |
| Review provenance manifest      | Unchanged    |
| Existing remediation plans      | Unchanged    |
| Qualification profiles          | Unchanged    |

The directly inspected archived Reviewer 3 reports retain their historical HOLD conclusions.

- [G0.1 Reviewer 3](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/reviews/G0.1-reviewer-3.md?utm_source=chatgpt.com)
- [G0.2 Reviewer 3](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/reviews/G0.2-reviewer-3.md?utm_source=chatgpt.com)
- [Archive provenance manifest, L3–17](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/reviews/PROVENANCE.md?utm_source=chatgpt.com#L3-L17)

**Limitation:** Git blob preservation establishes equality with the parent governance revision. I did not independently obtain the original external reviewer attachments and recompute their SHA-256 checksums.

Archive preservation and original external-report authenticity are different claims.

## **11. Permanent original-report provenance limitation**

**Disposition: HOLD — original historical provenance.**

I made an additional attempt to retrieve the original SYSGrow CP0–CP2 reports and complete recovery response.

The retrieval returned earlier conclusions and conversation-summary information, rather than complete primary originals with durable export identities and checksums.

The following cannot be independently reproduced:

| Required provenance                        | Status      |
| ------------------------------------------ | ----------- |
| Complete original CP0 report               | Unavailable |
| Complete original CP1 report               | Unavailable |
| Complete original CP2 durable export       | Unavailable |
| Stable original report identifiers         | Unavailable |
| Original report checksums                  | Unavailable |
| Complete original P0–P5 recovery export    | Unavailable |
| Original authoring and extraction evidence | Incomplete  |
| CP0 discovery count discrepancy            | Unresolved  |

### **CP0 22-versus-32 discrepancy**

The current documentary register contains the following attribution:

| Phase | Finding IDs | Count |
| ----- | ----------- | ----- |
| CP0   | F-001–022   | 22    |
| CP1   | F-023–032   | 10    |
| CP2   | F-033–044   | 12    |
| Total | F-001–044   | 44    |

It is plausible that 32 represented the cumulative CP1 count. That interpretation cannot be elevated to historical fact without the original CP0 and CP1 reports.

The replacement document correctly refuses to make that inference.

**PASS for disclosure of historical provenance loss. HOLD for recovery of the original evidence.**

The limitation must survive any eventual EGA-001 acceptance. Future recovery, if possible, must produce a dated superseding record without rewriting today's historical limitation.

Pinned evidence: [CP0–CP2.md, L36–42](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/CP0-CP2.md?utm_source=chatgpt.com#L36-L42) and [EVIDENCE-RECOVERY-CROSSWALK.md, L3–15](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/EVIDENCE-RECOVERY-CROSSWALK.md?utm_source=chatgpt.com#L3-L15).

## **12. EGA-001 — Governance amendment assessment**

Pinned document: [EVIDENCE-GOVERNANCE-AMENDMENT.md](https://github.com/PatoruzuyX/SYSGrow/blob/a10107a4f78eea8c37a0b1a6ab7d616a61b4df87/docs/qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md?utm_source=chatgpt.com).

### **12.1 Amendment eligibility**

| Requirement                                                     | Disposition                                    |
| --------------------------------------------------------------- | ---------------------------------------------- |
| Explicitly proposed rather than already effective               | PASS                                           |
| Narrow substitution of historical provenance prerequisite       | PASS                                           |
| Permanent disclosure of missing originals                       | PASS                                           |
| Preservation of adverse historical reviews                      | PASS                                           |
| Exact application and governance identities                     | PASS                                           |
| Preservation of all 44 finding identities and OPEN dispositions | PASS                                           |
| Independent reproduction of ER-01 inventory                     | PASS                                           |
| Independent reproduction of ER-02 structural comparisons        | PASS                                           |
| ER-03 source leakage evidence                                   | PASS                                           |
| Complete semantic replacement sufficiency                       | HOLD                                           |
| Documented recovery attempts                                    | Partial — original recovery export unavailable |
| Three independent final-candidate qualifications                | Not established                                |
| Explicit owner acceptance of exact EGA-001 candidate            | Not established                                |

### **12.2 Scope of permitted substitution**

The amendment's central principle is acceptable: historical-report provenance and current technical evidence are separable.

A newly constructed, independently qualified evidence basis may establish present technical findings without pretending that the original historical report has been recovered.

However, the amendment cannot transform an unverified technical claim into a verified finding solely because its original supporting report is unavailable.

The wording at L7–11 is appropriately restrictive on this point.

### **12.3 Future evidence-preservation clauses**

| Clause                            | Assessment                                        |
| --------------------------------- | ------------------------------------------------- |
| 1 — Before work                   | PASS                                              |
| 2 — During work                   | PASS                                              |
| 3 — Checkpoint preservation       | PASS                                              |
| 4 — Pre-integration integrity     | PASS                                              |
| 5 — Post-integration preservation | PASS                                              |
| 6 — Retention and retrieval       | PASS, with operational policy still to be defined |

The future preservation requirements correctly address immutable revision identity, artifact checksums, raw versus derived evidence, complete logs, independent verification, controlled access and explicit supersession.

They must not be represented as implemented preservation infrastructure.

### **12.4 Acceptance and integration separation**

**Replacement amendment prepared**

Documentary mechanism exists

**Independent technical evidence qualification**

HOLD — outstanding Reviewer 3 corrections

**Explicit owner acceptance of EGA-001**

Not eligible yet

**Exact-HEAD CI and effective enforcement**

Separate mandatory integration gates

**Owner-authorized G0 integration**

No runtime or production authority

**Amendment design: PASS. Amendment acceptance eligibility: HOLD.**

No conflict was identified between the intended narrow substitution and the existing qualification-profile hierarchy, provided all other gates remain mandatory and the final acceptance record explicitly identifies the superseded historical prerequisite.

## **13. Reviewer 3 findings against the candidate**

The following reviewer findings are separate from the existing 44 application findings. Their identifiers and severities are assigned for this review.

| Review ID | Severity | Finding                                                                                                            | Disposition |
| --------- | -------- | ------------------------------------------------------------------------------------------------------------------ | ----------- |
| ER-R3-001 | High     | Incomplete ML eligibility evidence across enabling, version selection and promotion                                | OPEN        |
| ER-R3-002 | High     | Artifact trust evidence does not explicitly cover the additional artifact-loading boundary                         | OPEN        |
| ER-R3-003 | High     | Firmware evidence lacks downstream trust qualification and full queued replay semantics                            | OPEN        |
| ER-R3-004 | Medium   | Reliability-test description does not sufficiently distinguish sequential exclusion from concurrency qualification | OPEN        |
| ER-R3-005 | Medium   | F-004 and F-014 require more precise per-row semantic anchors                                                      | OPEN        |
| ER-R3-006 | Medium   | Recovery crosswalk does not yet incorporate the newly reproduced primary ER-01 and ER-02 results                   | OPEN        |

Critical

# **0**

High

# **3**

Medium

# **3**

Six candidate evidence findings. These are not additional canonical runtime finding IDs.

ER-R3-006 is not an allegation that the original candidate fabricated its recovery observations. The candidate disclosed its limitations accurately. New independent evidence is now available and should be incorporated into the final qualification record.

## **14. Required corrections and convergence criteria**

| Correction                    | Required acceptance evidence                                                                                                        |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| ER-R3-001                     | Expanded F-007 anchors, explicit eligibility lifecycle distinctions and preservation of existing safeguards                         |
| ER-R3-002                     | F-008 coverage of model and auxiliary artifact loading; conditional exploitability preserved                                        |
| ER-R3-003                     | Complete queue-replay source evidence, additional OTA utility applicability, downstream trust disposition and accountable follow-up |
| ER-R3-004                     | F-019 actual test-oracle descriptions and explicit unexecuted concurrency/fault requirements                                        |
| ER-R3-005                     | Direct F-004 publish anchor and F-014 historical/current architecture crosswalk                                                     |
| ER-R3-006                     | Durable record of the independently reproduced test inventory, tree identities, branch heads, comparisons and ancestry              |
| Final technical qualification | Resolve material source-evidence gaps and preserve all 44 OPEN findings                                                             |
| EGA-001 acceptance            | Three independent exact-candidate reports, explicit owner acceptance and permanent provenance limitations                           |
| Integration enforcement       | Complete authorized effective-policy inspection and successful applicable exact-HEAD CI                                             |
| G0 integration                | Separate explicit owner authorization after all mandatory prerequisites                                                             |

The independently reproduced metadata can be preserved outside the candidate tree as revision-linked qualification evidence. Material corrections to the replacement matrix itself require a new candidate revision.

Any new candidate commit requires fresh applicable evidence and independent review. The current report cannot automatically qualify that future HEAD.

## **15. ER-01–ER-05 consolidated disposition**

| Workstream | Independently established                                           | Remaining gate                                               | Result          |
| ---------- | ------------------------------------------------------------------- | ------------------------------------------------------------ | --------------- |
| ER-01      | Complete tree inventory; 66 test-named modules                      | Actual collection, execution, coverage and simulation        | Structural PASS |
| ER-02      | Four current branch identities, complete trees, counts and ancestry | Individual semantic recovery decisions                       | Structural PASS |
| ER-03      | Forecasting leakage and preprocessing/validation defects            | CP4 remediation and model qualification                      | Evidence PASS   |
| ER-04      | Application OTA chain and queued replay discrepancy                 | Downstream firmware trust and safe maintenance qualification | HOLD            |
| ER-05      | Missing candidate CI and accessible enforcement deficiencies        | Effective administrative policy and successful final CI      | HOLD            |

### **Original recovery P0–P5**

| Milestone                                  | Disposition                      |
| ------------------------------------------ | -------------------------------- |
| P0 — Original inventory                    | Partial                          |
| P1 — Complete original recovery            | HOLD                             |
| P2 — Original artifact integrity           | HOLD                             |
| P3 — Finding reconciliation                | Structural PASS; technical HOLD  |
| P4 — Discovery attribution                 | Unresolved historical limitation |
| P5 — Independent replacement qualification | HOLD                             |

The replacement process represents a viable path away from an indefinitely blocked original-report gate. It has not yet completed that transition.

## **16. Review limitations and scope compliance**

This review performed read-only GitHub retrieval, source inspection, tree comparison, reference inventory, branch ancestry verification and documentary analysis.

The following were not independently established: original-report bytes and checksums, full external reviewer-attachment authenticity, complete historical branch semantic equivalence, complete effective administrative policy, deployed bridge/firmware behaviour, actual service reachability under production configuration, test execution, model performance, physical outcomes or hardware safety.

The initial bulk source-verification attempt reached a connector call limit. Smaller retrieval batches were used instead. The resulting evidence supports the bounded source conclusions presented here, but not a claim of exhaustive repository-wide call-graph or runtime qualification.

I also assigned six candidate review identifiers, assessed their severities, and distinguished row-level evidence sufficiency from runtime finding closure. These are reviewer judgments, not owner-approved register modifications.

No repository files, branches, commits, settings or submitted GitHub reviews were modified. No CI was dispatched or rerun. No deployment, firmware update, physical operation, model training, promotion or merge was performed.

## **17. Final independent verdict**

**Replacement technical evidence sufficiency**

HOLD

Candidate identity and documentary scope

PASS

Finding register continuity

PASS

Historical Git blob preservation

PASS

Original-report provenance disclosure

PASS

Original-report recovery

HOLD

EGA-001 amendment design

PASS

EGA-001 acceptance eligibility

HOLD

Integration qualification

HOLD

**Production safety**

NOT QUALIFIED

**Reviewer 3 verdict: HOLD — three High and three Medium candidate evidence findings, with separate mandatory integration gates outstanding.**

The rebaseline is a credible foundation for replacement technical qualification. Its strongest advancement is that previously inherited test-inventory and historical branch comparisons have now been independently reproduced against primary Git objects.

Nevertheless, EGA-001 should not yet be accepted for candidate `a10107a4f78eea8c37a0b1a6ab7d616a61b4df87`.

The appropriate next step is a bounded evidence correction and requalification cycle, not runtime remediation or integration.

All 44 application findings remain OPEN. All four Critical findings retain their existing severity and activation restrictions. PR #3 remains unmerged.

**End of Reviewer 3 independent qualification.**