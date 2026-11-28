# **SYSGROW-EVIDENCE-REBASELINE-001-R1**

## **Independent requalification — Reviewer 3: Evidence, Integration and ML**

**Review date:** 28 November 2026\
**Repository:** [PatoruzuyX/SYSGrow](https://github.com/PatoruzuyX/SYSGrow?utm_source=chatgpt.com)\
**Pull request:** [PR #3](https://github.com/PatoruzuyX/SYSGrow/pull/3?utm_source=chatgpt.com)\
**Assignment:** REB-02/05/07/08/10/13/14, all 44 foundation findings, source semantics, primary Git evidence, ML qualification, archive preservation and integration enforcement.

This review distinguishes the sufficiency of replacement technical evidence from historical provenance recovery, implementation qualification, effective integration enforcement and production safety.

## **1. Candidate identity and scope verification**

**Revision identity and documentary scope**

PASS

Exact candidate HEAD — confirmed

47794834e009334aa417b913fcc6818407ad234e

Exact candidate tree — confirmed

1f29e1d88a612712d957914d0f37c0e8af0b3e97

Direct parent — confirmed

a10107a4f78eea8c37a0b1a6ab7d616a61b4df87

Application baseline — confirmed as PR base

2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21

R1 changed paths

# **17**

All Markdown

Cumulative changed paths

# **39**

All Markdown

Removed baseline paths

# **0**

PR state

# **Open / Draft**

I independently retrieved the candidate Git commit object, PR metadata and recursive trees for the application baseline, superseded rebaseline and R1 candidate.

All three recursive tree responses were untruncated. Comparison of non-directory path, object SHA and file mode confirms that the cumulative changes are documentation-only. No application source, firmware, dependency, migration or CI configuration changes were identified.

Primary evidence: [candidate Git commit object](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/commits/47794834e009334aa417b913fcc6818407ad234e?utm_source=chatgpt.com), [candidate Git tree](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/1f29e1d88a612712d957914d0f37c0e8af0b3e97?recursive=1\&utm_source=chatgpt.com), [application baseline tree](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21?recursive=1\&utm_source=chatgpt.com).

### **1.1 Primary application inventory**

| Inventory measurement       | Independently reproduced |
| --------------------------- | ------------------------ |
| Application baseline blobs  | 780                      |
| Python files                | 487                      |
| Python files under `tests/` | 67                       |
| Test naming-pattern matches | 66                       |
| Candidate blobs             | 812                      |
| Review report archives      | 10                       |

The test naming-pattern count includes `test_*.py` and `*_test.py`. It is a source inventory measurement, not a pytest collection result, test execution count or passing-test count.

The distinction is essential to ER-01 and F-019.

## **2. Structural register and historical evidence qualification**

**Finding register continuity**

PASS

# **44 / 44**

Finding IDs and all seven core fields preserved

Critical

# **4**

High

# **26**

Medium

# **14**

Verified

## **29**

Risk

## **11**

Unverified

## **4**

All 44 application findings remain OPEN. These are inherited severity and classification counts, not newly established runtime outcomes.

I compared every finding's core fields across the starting governance register, the R1 replacement matrix and the R1 `FINDINGS.md`.

| Verification                    | Discrepancies |
| ------------------------------- | ------------- |
| Finding IDs                     | 0             |
| Inherited discovery attribution | 0             |
| Severity                        | 0             |
| Evidence classification         | 0             |
| Finding title                   | 0             |
| Owner mapping                   | 0             |
| OPEN status                     | 0             |

Pinned evidence: [starting register](https://github.com/PatoruzuyX/SYSGrow/blob/5d646ba58cb071b392cea94287371925ba82e626/docs/qualification/FINDINGS.md?utm_source=chatgpt.com), [R1 register](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/FINDINGS.md?utm_source=chatgpt.com), [replacement matrix](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-REBASELINE-001.md?utm_source=chatgpt.com#L19-L64).

Structural continuity passes. Historical discovery attribution remains unverified, and continuity does not prove that every inherited finding definition is technically sufficient.

## **3. REB-02 — Primary Git inventory and ancestry**

**Disposition: PASS — original High-priority correction reproduced.**

The application baseline is an ancestor of the R1 candidate. GitHub comparison reports six commits ahead, zero behind, and the authorized application baseline as the merge base. Current `main` also matches that baseline.

### **3.1 Historical branch verification**

Each of the four historical branch references was independently retrieved and matched its recorded commit SHA. Recursive trees were compared using path, object identity, file mode and object type.

| Historical branch                | Identical | Changed | Branch-only | Main-only |
| -------------------------------- | --------- | ------- | ----------- | --------- |
| `codex/main-snapshot-20260314`   | 156       | 372     | 1,169       | 252       |
| `codex/pi-db-init-fix`           | 156       | 372     | 1,169       | 252       |
| `codex/unit-create-fix-20260315` | 156       | 372     | 1,169       | 252       |
| `codex/stash-backup-20260315`    | 204       | 440     | 146         | 136       |

### **Historical tree differences**

Main snapshot

Pi DB fix

Unit creation fix

Stash backup

Identical

Changed

Branch-only

Main-only

| Historical branch | Independently verified ancestry        |
| ----------------- | -------------------------------------- |
| Main snapshot     | HTTP 404 — explicit No common ancestor |
| Pi database fix   | HTTP 404 — explicit No common ancestor |
| Unit creation fix | HTTP 404 — explicit No common ancestor |
| Stash backup      | Diverged: 1 ahead, 4 behind            |

The stash merge base is `1f2cd5bfa6cbf0acced68762d72ed45d66b41527`.

The three historical branches with equal aggregate counts have distinct tree identities. Equal counts must not be interpreted as equivalent content or interchangeable recovery branches.

Primary tree evidence: [main snapshot](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/cb85d04b5b5e5ec99bac9c366fac1732d5ce68e1?recursive=1\&utm_source=chatgpt.com), [Pi database fix](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/a146736a820afaf21be0a47061124f8c1a07b170?recursive=1\&utm_source=chatgpt.com), [unit creation fix](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/30235efb4ebf1657f9b1de5511bd9de06db6e246?recursive=1\&utm_source=chatgpt.com), [stash backup](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/bccd5eb1796116a9f27b613f8ba0c0a9184d0b12?recursive=1\&utm_source=chatgpt.com).

### **3.2 F-011 — Docker build context**

**Replacement evidence: PASS — High, Verified, OPEN.**

The complete baseline tree contains zero tracked descendants under `data/`.

[Dockerfile:50–56](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/Dockerfile?utm_source=chatgpt.com#L50-L56) contains an explicit `COPY data/ data/` instruction.

The corrected evidence is sufficient to establish the tracked-input discrepancy. It does not prove that every deployment build fails: an externally generated build context could supply the directory.

Actual clean-checkout build and platform qualification remain EP-005 responsibilities.

### **3.3 ER-01 and ER-02 dispositions**

| Evidence component                          | Disposition   |
| ------------------------------------------- | ------------- |
| Complete primary tree enumeration           | PASS          |
| Test naming-pattern discrepancy             | PASS          |
| Historical branch identity                  | PASS          |
| Tree comparison counts                      | PASS          |
| Historical ancestry                         | PASS          |
| Individual historical change reconciliation | OPEN — EP-006 |
| Runtime test collection and execution       | Not performed |
| Historical CP0–CP2 report recovery          | HOLD          |

The corrected [ER-01/02 primary crosswalk](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-RECOVERY-CROSSWALK.md?utm_source=chatgpt.com#L17-L41) accurately records these structural distinctions.

## **4. Archive preservation and reviewer observation mapping**

### **4.1 All ten review archives**

**Disposition: PASS for repository archive integrity.**

I retrieved the raw encoded contents of all ten archived GitHub files, decoded their bytes and independently recomputed their SHA-256 checksums. Every checksum matches the candidate's provenance manifest.

Archive checksums

# **10/10**

Existing blobs preserved

# **7/7**

New attachment texts matched

# **3/3**

| Archive               | Git blob identity, abbreviated | SHA-256 |
| --------------------- | ------------------------------ | ------- |
| G0 initial review     | `478f3d4aa867`                 | Match   |
| G0.1 Reviewer 1       | `2ff78c1e040f`                 | Match   |
| G0.1 Reviewer 2       | `0327c3f972eb`                 | Match   |
| G0.1 Reviewer 3       | `13aa4033df59`                 | Match   |
| G0.2 Reviewer 1       | `1539d3e14796`                 | Match   |
| G0.2 Reviewer 2       | `010266a464ca`                 | Match   |
| G0.2 Reviewer 3       | `395c660ecbf4`                 | Match   |
| Rebaseline Reviewer 1 | `dd061f3224ca`                 | Match   |
| Rebaseline Reviewer 2 | `d76d4e727921`                 | Match   |
| Rebaseline Reviewer 3 | `3cfe3e4f537d`                 | Match   |

The seven previously archived reports also retain exactly the same blob identities as the superseded candidate.

### **4.2 Independent attachment-content comparison**

I located the three original rebaseline review attachments in the Library using their matching identities, sizes, reviewed revisions and contents.

Raw-byte materialization was unavailable. However, I subsequently retrieved every indexed text line in contiguous windows and compared the reconstructed text with the corresponding GitHub archive.

| New archive | Attachment bytes reported | Lines compared | Exact text equality |
| ----------- | ------------------------- | -------------- | ------------------- |
| Reviewer 1  | 47,593                    | 938            | PASS                |
| Reviewer 2  | 71,468                    | 1,149          | PASS                |
| Reviewer 3  | 61,751                    | 1,358          | PASS                |

No missing line ranges or text discrepancies were found. This independently supports the attachment-content fidelity claim in [PROVENANCE.md:19–29](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/reviews/PROVENANCE.md?utm_source=chatgpt.com#L19-L29).

**Qualification boundary:** archive bytes, recorded checksums and available attachment texts match. Original conversation-export authenticity, independently authenticated session identity and direct access to the underlying raw attachment bytes remain outside the verified scope.

### **4.3 All 20 reviewer observations**

**Mapping completeness: PASS. Correction sufficiency: assessed separately below.**

The original review reports contain eight architecture/governance observations, six security/safety observations and six evidence/integration/ML observations.

Their aggregate severity counts are reproduced:

| Reviewer   | High  | Medium | Low   | Total  |
| ---------- | ----- | ------ | ----- | ------ |
| Reviewer 1 | 3     | 4      | 1     | 8      |
| Reviewer 2 | 3     | 3      | 0     | 6      |
| Reviewer 3 | 3     | 3      | 0     | 6      |
| **Total**  | **9** | **10** | **1** | **20** |

Every original observation ID is represented in the 14 correction packages:

| R1 package | Original observation IDs |
| ---------- | ------------------------ |
| REB-01     | REB-R1-01                |
| REB-02     | REB-R1-02, ER-R3-006     |
| REB-03     | REB-R1-03                |
| REB-04     | ERB-SS-01                |
| REB-05     | ERB-SS-02, ER-R3-003     |
| REB-06     | ERB-SS-03                |
| REB-07     | ER-R3-001                |
| REB-08     | ER-R3-002                |
| REB-09     | REB-R1-04                |
| REB-10     | REB-R1-05, ER-R3-005     |
| REB-11     | REB-R1-06                |
| REB-12     | ERB-SS-04, ERB-SS-05     |
| REB-13     | ERB-SS-06, ER-R3-004     |
| REB-14     | REB-R1-07, REB-R1-08     |

Source: [R1 correction record:5–24](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-REBASELINE-R1-REVIEW.md?utm_source=chatgpt.com#L5-L24), and the three independently reopened archived reports.

No original observation is missing from the mapping. The original HOLD verdicts remain intact. Mapping an observation to a correction package does not, however, establish that the correction is sufficient.

# **5. Independent requalification verdict**

# **Reviewer 3 — HOLD**

ML evidence corrections

Critical

# **0**

High

# **2**

Medium

# **1**

Low

# **0**

New candidate review observations, separate from the existing 44 foundation findings.

| Repository identity and scope                 | PASS          |
| --------------------------------------------- | ------------- |
| Finding register continuity                   | PASS          |
| Primary Git inventory and historical ancestry | PASS          |
| Archive integrity and observation mapping     | PASS          |
| Replacement technical evidence sufficiency    | HOLD          |
| Original historical provenance recovery       | HOLD          |
| EGA-001 amendment design                      | PASS          |
| EGA-001 acceptance eligibility                | HOLD          |
| Successful applicable CI                      | HOLD          |
| Effective integration enforcement             | HOLD          |
| Production safety                             | NOT QUALIFIED |

R1 resolves most of the original evidence defects. In particular, the primary Git evidence, archive preservation, firmware evidence boundary and reliability-test descriptions are materially stronger.

However, further inspection of the ML implementation reveals that the replacement matrix still does not fully characterize the actual model eligibility lifecycle.

The most important additional observation is that **saving a trained model through the dictionary-metadata interface can register it as active without invoking the explicit production-promotion method.**

That pathway must be included in F-007. Otherwise, remediation could qualify explicit promotion while overlooking an alternative route into production-version selection.

## **5.1 Assigned correction dispositions**

| Correction                                          | Original priority | Independent disposition                                               |
| --------------------------------------------------- | ----------------- | --------------------------------------------------------------------- |
| REB-02 — Primary Git evidence                       | High              | PASS                                                                  |
| REB-05 — Firmware maintenance trust                 | High              | PASS for bounded application evidence; downstream HOLD                |
| REB-07 — ML eligibility lifecycle                   | High              | HOLD                                                                  |
| REB-08 — Model and auxiliary artifact trust         | High              | HOLD                                                                  |
| REB-10 — MQTT and architectural evidence            | Medium            | PASS                                                                  |
| REB-13 — Fault-test evidence and acceptance oracles | Medium            | PASS for original physical/reliability corrections; ML extension HOLD |
| REB-14 — Retention and historical limitations       | Medium            | PASS                                                                  |

The downstream firmware HOLD does not automatically invalidate the replacement application-source observation. It remains a separate mandatory qualification gate for applicable maintenance, device and activation activities.

# **6. ER-03 and F-006 — ML leakage qualification**

**Disposition: PASS — High, Verified, OPEN.**

The replacement evidence correctly identifies same-row target leakage for a forecasting objective.

## **6.1 Direct source reproduction**

| Pinned source                                                                                                                                                               | Observation                                                                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| [ml_trainer.py:112–125](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L112-L125) | Temperature, humidity and soil moisture appear in both the environmental features and climate targets |
| [ml_trainer.py:137–192](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L137-L192) | Mean imputation and IQR filtering occur before dataset partitioning                                   |
| [ml_trainer.py:267–295](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L267-L295) | Same-row features and target are selected, then randomly split                                        |
| [ml_trainer.py:297–318](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L297-L318) | Scaling is fitted before cross-validation on the training partition                                   |

### **Observed training pipeline**

**Historical dataset**

Temperature, humidity, soil moisture, CO₂, lux

**Imputation and IQR filtering**

Statistics calculated before the train/test partition

**Features X**

Temperature

Humidity, moisture, CO₂, lux, time features

**Target y**

Temperature

Same observation row

**Random partition → scaling → training → evaluation**

Illustrated for the temperature target. The same feature/target overlap applies to humidity and soil moisture.

Three distinct evaluation problems are established:

1. **Target leakage:** the prediction target itself is present among the same-row inputs.
2. **Preprocessing leakage:** imputation and IQR statistics can incorporate information from the eventual test partition.
3. **Cross-validation leakage:** the scaler is fitted before cross-validation rather than independently inside each validation fold.

Random partitioning introduces an additional temporal-validation concern where observations are correlated across time, growth cycles or units.

## **6.2 Counterexample and qualification boundary**

If the intended task were explicitly same-row reconstruction or estimation, the meaning of target overlap would need to be evaluated against that objective.

It would not automatically establish invalidity for every possible model objective.

For forecasting future environmental conditions, however, the inspected feature/target construction does not establish an independent prediction horizon.

The candidate now captures that distinction correctly.

### **Required CP4 acceptance evidence**

| Requirement          | Minimum acceptance criterion                                      |
| -------------------- | ----------------------------------------------------------------- |
| Prediction objective | Explicit forecast target and prediction horizon                   |
| Feature availability | Every feature demonstrably available at inference time            |
| Target separation    | No target or future information in predictors                     |
| Dataset partition    | Chronological and appropriately grouped validation                |
| Preprocessing        | Fitted exclusively within the relevant training partition or fold |
| Baseline comparison  | Compare against simple persistence and other justified baselines  |
| Evaluation           | Independently held-out observations and documented uncertainty    |
| Promotion            | No eligibility based on contaminated validation results           |

**ER-03 passes for replacement source evidence. CP4 model qualification remains OPEN.**

# **7. REB-07 — Model eligibility, registration and promotion**

**Disposition: HOLD — High.**

New observation: **ER-R3-R1-001 — Incomplete model admission lifecycle and invalid-metric semantics.**

The R1 correction establishes several important defects, but inspection of the actual model lifecycle reveals additional routes that must be represented explicitly.

## **7.1 Corrected observations independently confirmed**

The following R1 statements are supported:

| Evidence                                                                                                                                                                                               | Confirmed observation                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| [ml_readiness_monitor.py:208–244](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_readiness_monitor.py?utm_source=chatgpt.com#L208-L244)        | Readiness is evaluated separately using sample counts                                             |
| [ml_readiness_monitor.py:368–399](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_readiness_monitor.py?utm_source=chatgpt.com#L368-L399)        | Activation validates the model name but does not repeat readiness qualification                   |
| [irrigation_ml.py:200–224](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/infrastructure/database/repositories/irrigation_ml.py?utm_source=chatgpt.com#L200-L224) | Repository enablement updates a configuration flag without checking sample readiness              |
| [drift_detector.py:157–212](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/drift_detector.py?utm_source=chatgpt.com#L157-L212)                    | Empty history yields favourable metrics and an `ok` recommendation                                |
| [model_registry.py:551–610](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L551-L610)                    | Explicit production promotion changes metadata without independently evaluating model eligibility |

These are genuine improvements over the superseded rebaseline.

Nevertheless, they do not fully describe how a newly trained model becomes selectable.

## **7.2 Additional defect A — Registration can bypass explicit promotion**

The dictionary-metadata branch of `ModelRegistry.save_model()` contains:

```
status = str(metadata.get("status") or "active")
```

Pinned source: [model_registry.py:249–287](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L249-L287).

That status is passed directly into registration.

The trainer supplies dictionary metadata without an explicit status in at least the inspected climate and irrigation-threshold training paths:

- [Climate trainer:323–341](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L323-L341).
- [Irrigation threshold trainer:894–913](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/ml_trainer.py?utm_source=chatgpt.com#L894-L913).

The registry appends the supplied status to its version entries at [model_registry.py:324–355](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L324-L355).

The explicit promote_to_production() method is not necessarily the only route to an active registry entry.

### **Counterexample**

An implementation could add rigorous checks exclusively inside `promote_to_production()` while leaving dictionary-based registration unchanged.

A training operation could then create an active entry without passing through that newly qualified promotion boundary.

The candidate's remediation objective would appear satisfied while the alternative registration pathway remains.

This is a material completeness issue in the replacement evidence.

## **7.3 Additional defect B — Production selection can prefer an inactive version**

The candidate identifies this issue correctly, but its strongest supporting anchor should be added.

[model_registry.py:141–167](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L141-L167) only restricts selection to active entries if at least one active entry exists.

Otherwise, the selection remains over the original entries.

Consequently, [get_production_version():529–549](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L529-L549) can return an inactive version from a list-based registry.

The explicit fallback at lines 542–543 is not the complete explanation. The preceding `_latest_entry(..., prefer_active=True)` implementation can itself select a non-active entry.

**Required correction:** anchor the actual selection semantics, rather than relying only on the calling method.

## **7.4 Additional defect C — Invalid metrics can become favourable metrics**

The existing irrigation-specific gates are real implemented safeguards. They must be preserved.

However, their input-validation boundary requires closer inspection.

[irrigation_predictor.py:178–193](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/irrigation_predictor.py?utm_source=chatgpt.com#L178-L193) converts missing or invalid metric values to a default of `0.0`.

The threshold and duration eligibility predicates then evaluate those converted values.

[irrigation_predictor.py:216–234](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/irrigation_predictor.py?utm_source=chatgpt.com#L216-L234) accepts low error values as favourable evidence.

### **Static eligibility counterexample**

Illustration of the inspected threshold-model MAE predicate, not executed repository code.

MAE key absent

MAE present but non-numeric

MAE present with null value

Valid MAE = 3.0

Valid MAE = 8.0

Value used by predicate

# **0.0**

MAE ≤ 4.0 check

# **PASS**

Invalid evidence becomes an apparently favourable error measurement.

The important distinction is between an absent metric key and a present but invalid metric value. Existing missing-metric tests do not necessarily establish safe handling of malformed values.

An eligibility system must reject invalid, non-finite or out-of-domain measurements rather than convert them into favourable evidence.

This remains a source-level counterexample, not an observed model promotion or irrigation action.

## **7.5 Additional defect D — Retraining completion does not establish successful training**

[automated_retraining.py:449–468](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/automated_retraining.py?utm_source=chatgpt.com#L449-L468) delegates irrigation retraining to the corresponding trainer methods.

The subsequent block:

- Retrieves the production version.
- Records returned metrics.
- Marks the retraining event `COMPLETED`.
- Records job success.
- Broadcasts training completion.

See [automated_retraining.py:473–508](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/automated_retraining.py?utm_source=chatgpt.com#L473-L508).

The inspected completion block does not first require a successful returned training result.

A trainer returning a failure dictionary without raising an exception is therefore a valid counterexample to the assumption that a completed retraining event proves successful training or a newly eligible model.

This should be mapped under F-007, with a cross-reference to F-032 persistence and durable outcome integrity.

## **7.6 Existing safeguards independently confirmed**

It would be inaccurate to conclude that SYSGrow has no ML eligibility controls.

| Model               | Implemented metric gate                     |
| ------------------- | ------------------------------------------- |
| Response predictor  | Macro F1 and balanced accuracy              |
| Timing predictor    | Top-three accuracy and mean reciprocal rank |
| Threshold optimizer | MAE or R²-based criterion                   |
| Duration optimizer  | MAE and MAPE                                |

Direct implementation: [irrigation_predictor.py:195–236](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/irrigation_predictor.py?utm_source=chatgpt.com#L195-L236).

Existing source tests include [test_ml_sprint4_gating.py](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/tests/test_ml_sprint4_gating.py?utm_source=chatgpt.com) and [test_irrigation_ml_gating_no_fallback.py](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/tests/unit/services/test_irrigation_ml_gating_no_fallback.py?utm_source=chatgpt.com).

Those tests are relevant evidence of intended metric gating and abstention behaviour. They were not executed in this review and are not end-to-end production eligibility qualification.

### **Mandatory correction**

Expand F-007 and its CP4 closure criteria to cover:

- Registration and implicit activation, not only explicit promotion.
- Strict version selection with no inactive-version fallback.
- Validity and provenance of eligibility metrics.
- Training completion versus successfully persisted eligible artifact.
- Consumer-specific inference admission and abstention.

The original High/Risk classification can remain at umbrella level, with the individual source-confirmed defects identified separately as Verified observations.

# **8. REB-08 — Primary and auxiliary artifact trust**

**Disposition: HOLD — High.**

New observation: **ER-R3-R1-002 — Model bundle assembly and pre-deserialization trust boundary incompletely characterized.**

The updated F-008 correctly includes auxiliary artifact loading. That correction is necessary, but the actual consumer composition adds another significant concern.

## **8.1 Deserialization boundaries**

| Source                                                                                                                                                                              | Direct observation                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| [model_registry.py:206–208](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L206-L208) | Model/version paths constructed directly from supplied identifiers |
| [model_registry.py:387–404](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L387-L404) | Primary artifact loaded using `joblib.load()`                      |
| [model_registry.py:412–448](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L412-L448) | Separate auxiliary artifact path also uses `joblib.load()`         |
| [model_registry.py:450–489](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L450-L489) | Metadata is independently selected and loaded                      |

The inspected loaders do not demonstrate cryptographic authenticity verification before deserialization.

That matters because joblib artifacts must be treated as trusted executable-equivalent inputs, rather than ordinary inert data files.

Actual malicious artifact control, deserialization exploitation or unauthorized execution has not been established.

## **8.2 Actual irrigation consumer composition**

[irrigation_predictor.py:105–166](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/irrigation_predictor.py?utm_source=chatgpt.com#L105-L166) constructs its model bundles using separate registry calls.

The consumer invokes:

```
model = self._model_registry.load_model(model_name)scaler = self._model_registry.load_artifact(model_name, "scaler")label_encoder = self._model_registry.load_artifact(    model_name, "label_encoder")metadata = self._model_registry.get_metadata(model_name)
```

The encoder is loaded for the relevant classification models.

Each applicable registry method resolves the production version independently when no explicit version is supplied.

### **Consequence**

If production selection changes during bundle assembly, the inspected implementation does not establish that every component necessarily belongs to the same immutable version.

A mixed-version bundle is a conditional concurrency outcome, not an observed incident.

This makes the distinction between individual artifact trust and whole-bundle integrity particularly important.

## **8.3 Metric gating occurs after artifact loading**

The predictor loads serialized artifacts while constructing its bundles. Model-specific metric eligibility is subsequently evaluated using bundle metadata.

Consequently, a later inference gate does not protect the earlier deserialization boundary.

A model might be rejected for inference after its serialized representation has already been loaded.

**Required correction:** explicitly distinguish pre-deserialization trust admission from post-load statistical eligibility.

Both are mandatory, but they protect different properties.

## **8.4 Required CP4/CP6 artifact acceptance contract**

**1**

**Resolve immutable bundle identity**

Model name, version, artifact manifest and provenance

**2**

**Verify trust before deserialization**

Approved source, integrity, path containment and permissions

**3**

**Bind all bundle components**

Model, scaler, encoder, metadata and feature schema

**4**

**Load the verified bundle**

No substitution or version drift during loading

**5**

**Evaluate statistical eligibility**

Validated metrics, readiness and explicit promotion

**6**

**Authorize consumer use**

Advisory inference only unless separately qualified

This is a proposed acceptance contract, not an accepted architecture decision.

The required tests must establish that:

- Invalid or substituted auxiliary artifacts are rejected before deserialization.
- Trusted metadata cannot authorize a different model or auxiliary artifact.
- Production selection changes cannot create a mixed-version bundle.
- Missing required artifacts do not silently become qualified optional components.
- Cached artifacts cannot retain revoked trust or obsolete eligibility.
- Failed persistence and restart cannot resurrect an unqualified production selection.

F-008 remains High/Risk because exploitability depends on the effective artifact-control boundary. The local loader behaviour itself is directly verified.

# **9. F-032 — Registry persistence and promotion integrity**

**Disposition: PASS for the corrected bounded source observation — High, Risk, OPEN.**

The R1 correction now captures the false-success persistence problem.

[model_registry.py:181–204](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L181-L204) establishes that registry loading can default to an empty structure after failure and `_save_registry()` catches persistence exceptions internally.

The temporary-file replacement mechanism is an existing safeguard, but it does not establish cross-process lifecycle atomicity.

[model_registry.py:310–355](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L310-L355) writes model artifacts, updates registry metadata, calls the save helper and returns a version identifier.

[model_registry.py:551–610](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/ai/model_registry.py?utm_source=chatgpt.com#L551-L610) can similarly return successful promotion after the internally handled persistence operation.

The corrected observation is technically supported.

The additional retraining-completion defect identified under F-007 must consume F-032's eventual durable-outcome contract, but it does not invalidate the specific registry persistence observation.

No concurrent writer, crash-recovery or registry rollback tests have been executed.

# **10. REB-05 and ER-04 — Firmware evidence boundary**

**Disposition: PASS for bounded replacement application evidence. HOLD for downstream trust qualification.**

The corrected F-043 now appropriately covers:

| Local source observation                                                             | Disposition        |
| ------------------------------------------------------------------------------------ | ------------------ |
| Maintenance route accepts device identity and firmware URL                           | Verified           |
| No complete privileged maintenance admission established in the inspected route body | Verified local gap |
| API returns `sent` despite distinct adapter outcomes                                 | Verified           |
| Offline queue does not preserve the supplied destination topic                       | Verified           |
| Queue expiration check exists                                                        | Verified safeguard |
| Legacy HTTP OTA utility exists                                                       | Verified           |
| Actual downstream bridge/device trust                                                | Unverified         |

### **Pinned application evidence**

[esp32.py:202–242](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/blueprints/api/devices/esp32.py?utm_source=chatgpt.com#L202-L242), [sysgrow_adapter.py:517–585](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L517-L585), [queue replay:587–610](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L587-L610), [OTA destination:826–842](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/adapters/sensors/sysgrow_adapter.py?utm_source=chatgpt.com#L826-L842).

The separate [scripts/ota_updater.py:27–56](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/scripts/ota_updater.py?utm_source=chatgpt.com#L27-L56) confirms an additional HTTP-based maintenance utility.

Its presence is not evidence that it is deployed, scheduled or used against existing devices.

## **10.1 Independent downstream inventory**

The untruncated application tree contains no identified conventional embedded firmware source, corresponding build configuration or Git submodule.

The relevant application-side entries include the ESP32 API, SYSGrow adapter, ESP32 documentation and the OTA updater utility.

No exact downstream bridge or firmware implementation revision was established.

**Application-side source evidence**

Bounded replacement observation qualified

PASS

**Downstream bridge implementation**

Exact source and deployment identity unavailable

HOLD

**Device firmware and boot chain**

Artifact authenticity, recovery and safety unqualified

HOLD

## **10.2 Is downstream HOLD necessarily a replacement-evidence blocker?**

Not for the corrected, bounded application-source claim.

The candidate no longer relies on an assumed downstream defect to establish F-043. Its application-side observations stand independently.

This allows the documentary evidence to be accepted as an OPEN baseline finding without declaring the firmware trustworthy.

It does not allow the downstream evidence to be waived before an activity that requires that trust.

| Future activity                                      | Required gate                                                   |
| ---------------------------------------------------- | --------------------------------------------------------------- |
| Document existing application-side defects           | Bounded source qualification                                    |
| Design maintenance-security contracts                | Resolve applicable mandatory interface questions                |
| Implement or qualify applicable firmware maintenance | Pinned downstream implementation and trust evidence             |
| Device-specific safety qualification                 | Applicable firmware, topology, protection and recovery evidence |
| Production maintenance or activation                 | Separate competent qualification and explicit authorization     |

R1's amended [replacement evidence:88](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-REBASELINE-001.md?utm_source=chatgpt.com#L88) preserves this distinction.

**REB-05 is therefore sufficiently corrected for the documentary replacement scope. ER-04 remains HOLD for applicable downstream maintenance and device qualification.**

No OTA operation or physical activity was performed.

# **11. REB-10 — MQTT and architectural evidence**

## **11.1 F-004 — MQTT acknowledgement semantics**

**PASS — Medium-priority candidate correction resolved.**

[mqtt_broker_wrapper.py:201–223](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/hardware/mqtt/mqtt_broker_wrapper.py?utm_source=chatgpt.com#L201-L223) is now explicitly cited.

The wrapper records publication return codes, exceptions and disconnected conditions internally but does not provide the caller with a meaningful typed delivery outcome.

This supports the corrected replacement observation.

It does not establish effective broker authentication, TLS, deployed ACLs or whether anonymous access is possible.

F-004 remains High/Risk and OPEN.

## **11.2 F-014 — Two-sided architectural reconciliation**

**PASS — Medium, Verified, OPEN.**

The R1 crosswalk is materially stronger because it compares historical documentation with both current source and primary Git inventory.

| Historical documentation                          | Current evidence                                     |
| ------------------------------------------------- | ---------------------------------------------------- |
| `infrastructure/hardware/unit_runtime_manager.py` | Exact path absent                                    |
| `app/services/growth.py`                          | Exact path absent                                    |
| `app/models/`                                     | No tracked descendants                               |
| `data/training/`                                  | No tracked `data/` descendants                       |
| Current GrowthService                             | `app/services/application/growth_service.py` present |

Historical references were independently reopened:

- [ARCHITECTURE.md:36–47](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/docs/architecture/ARCHITECTURE.md?utm_source=chatgpt.com#L36-L47) identifies the old GrowthService path.
- [ARCHITECTURE.md:147–175](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/docs/architecture/ARCHITECTURE.md?utm_source=chatgpt.com#L147-L175) describes the historical UnitRuntimeManager.
- [GrowthService:922–1002](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/application/growth_service.py?utm_source=chatgpt.com#L922-L1002) establishes current registration and controller composition.
- [Baseline Copilot instructions:9–30](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/.github/copilot-instructions.md?utm_source=chatgpt.com#L9-L30) contain the historical model and training-path references.

The crosswalk establishes concrete discrepancies without declaring every historical instruction obsolete.

No further mandatory correction to REB-10 is identified.

# **12. REB-13 — Reliability tests and fault-test acceptance**

## **12.1 F-019 — Existing test evidence**

**PASS — Original evidence correction resolved.**

The corrected description of `test_irrigation_reliability.py` now accurately distinguishes the tested assertions from their broader test names.

| Test                    | Actual source oracle                           | What it does not establish                 |
| ----------------------- | ---------------------------------------------- | ------------------------------------------ |
| Atomic claim            | Two sequential claim calls; second empty       | Concurrent-process atomicity               |
| Parallel-execution lock | Sequential acquire, reject, release, reacquire | Simultaneous worker exclusion              |
| Duration attribution    | One classification example                     | General attribution correctness            |
| Threshold attribution   | One classification example                     | General learning correctness               |
| Valve failure           | Stub-based failure; pump not called            | Lowest-interface containment               |
| No sleep                | Source-text assertion across selected files    | Runtime deadline or non-blocking behaviour |

Pinned evidence: [test_irrigation_reliability.py:91–179](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/tests/unit/irrigation/test_irrigation_reliability.py?utm_source=chatgpt.com#L91-L179).

The candidate correctly avoids claiming that these tests establish physical safety, process-crash recovery or concurrent runtime qualification.

## **12.2 Fault-design inventory**

Unique FT identifiers

# **45**

Missing FT identifiers

# **0**

Tests executed

# **0**

The remediation document retains all unique identifiers from FT-001 through FT-045.

The new [R1 oracle extensions:194–205](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/plans/REMEDIATION.md?utm_source=chatgpt.com#L194-L205) appropriately strengthen actual composition, typed outcomes, maintenance authority, queued destinations, calibration failure, shutdown and persistence testing.

I find no evidence that these extensions remove existing G0.3 physical-safety requirements.

## **12.3 Outstanding ML acceptance-design correction**

**HOLD — Medium.**

New observation: **ER-R3-R1-003 — CP4 acceptance oracles require explicit negative lifecycle and bundle-coherence tests.**

The revised CP4 requirements appropriately distinguish readiness, enablement, selection, promotion, artifact trust and restart. However, the newly identified ML counterexamples need specific measurable acceptance oracles.

| Proposed CP4 test case                              | Required outcome                                           |
| --------------------------------------------------- | ---------------------------------------------------------- |
| Training saves model without explicit status        | New model cannot acquire production eligibility implicitly |
| Registry contains only inactive versions            | No production version returned                             |
| Invalid or null error metric                        | Eligibility denied                                         |
| Non-finite or impossible metric                     | Eligibility denied                                         |
| No prediction history or ground truth               | Evidence unavailable; not perfect performance              |
| Trainer returns unsuccessful result                 | Retraining must not record success                         |
| Registry persistence fails                          | No successful durable-promotion outcome                    |
| Production version changes during loading           | One coherent immutable bundle or safe rejection            |
| Invalid scaler or encoder                           | Rejected before deserialization                            |
| Trust or eligibility revoked after caching          | No unauthorized subsequent inference                       |
| Different model and metadata versions               | Rejected; no borrowing of favourable metrics               |
| Eligibility passes but control policy denies action | No consequential physical-interface effect                 |

These are proposed synthetic oracles, not test executions.

They should be integrated into the CP4 validation design rather than unnecessarily expanding the existing physical-safety FT numbering.

**REB-13 passes for the original reliability and firmware/calibration corrections. Its complete ML acceptance sufficiency remains HOLD pending these extensions.**

# **13. REB-14 — Evidence retention and permanent historical limitations**

**Disposition: PASS.**

[EGA-001:20](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md?utm_source=chatgpt.com#L20) now requires preservation across all dependent releases, decisions, findings, safety cases, approvals and qualification records.

This addresses the original retention problem.

### **Counterexample challenge**

A release may be superseded while a still-active safety case, finding disposition or governance decision relies on evidence from that release.

The corrected policy no longer allows the release supersession alone to justify evidence disposal.

It explicitly requires reverse-dependency inspection, accountable custody and separately authorized disposition.

The previously duplicated F-025 anchor has also been replaced with a distinct actuator-management shutdown reference at [actuator_management_service.py:1449–1476](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/app/services/hardware/actuator_management_service.py?utm_source=chatgpt.com#L1449-L1476).

The permanent historical limitation is preserved in [replacement evidence:76–78](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-REBASELINE-001.md?utm_source=chatgpt.com#L76-L78).

No mandatory REB-14 correction remains in my assigned scope.

One minor editorial improvement is advisable: explicitly label the initial-rebaseline method limitation at EGA-001 line 22 as historical, so it cannot be confused with R1's subsequently completed primary tree verification. This is not an independent blocking observation.

# **14. All 44 foundation findings — semantic disposition matrix**

I extracted the application-baseline GitHub references from the replacement document and reopened the 55 distinct referenced source files.

Source reference occurrences

# **142**

Unique source references

# **119**

Distinct source files

# **55**

Counts include repeated references in supplementary narrative. All referenced files were retrieved and explicit line ranges checked. Targeted semantic excerpts and additional composition paths were inspected; this is not an exhaustive line-by-line audit of every referenced file or every possible runtime path.

The following PASS dispositions apply only to the bounded replacement observations. They do not close application findings.

## **14.1 CP0 — F-001–022**

| ID    | Evidence disposition | Independent semantic assessment                                                                                               |
| ----- | -------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| F-001 | PASS                 | Scheduler construction/start and two-worker configuration support the ownership concern; actual competing operation untested. |
| F-002 | PASS                 | Application-managed shutdown exists; independent protection remains unqualified.                                              |
| F-003 | PASS                 | Standard container injection establishes the pump-calibration signature incompatibility.                                      |
| F-004 | PASS                 | Broker configuration and wrapper publication semantics correctly distinguished.                                               |
| F-005 | PASS                 | Write authentication is not comprehensive resource authorization.                                                             |
| F-006 | PASS                 | Same-row forecasting leakage and preprocessing deficiencies established.                                                      |
| F-007 | **HOLD**             | Implicit active registration, invalid-metric handling and retraining completion need expanded evidence.                       |
| F-008 | **HOLD**             | Actual pre-deserialization and multi-component bundle assembly need stronger evidence.                                        |
| F-009 | PASS                 | Persistence placeholders and missing repository injection supported.                                                          |
| F-010 | PASS                 | Conflicting Flask/Werkzeug dependency constraints verified.                                                                   |
| F-011 | PASS                 | Missing tracked Docker build input independently established.                                                                 |
| F-012 | PASS                 | Source observation supported; actual effective enforcement remains HOLD.                                                      |
| F-013 | PASS                 | CI does not explicitly install from the lock or invoke coverage enforcement.                                                  |
| F-014 | PASS                 | Historical/current architecture discrepancy independently verified.                                                           |
| F-015 | PASS                 | Raspberry Pi target declaration is not measured platform qualification.                                                       |
| F-016 | PASS                 | Verified unit-keyed locking distinguished from unverified physical topology.                                                  |
| F-017 | PASS                 | Unbounded parallel training configuration supports conditional resource-contention risk.                                      |
| F-018 | PASS                 | Limited exception-wrapper evidence does not establish exhaustive SQL or disclosure remediation.                               |
| F-019 | PASS                 | Test inventory and actual source assertions accurately represented.                                                           |
| F-020 | PASS                 | Historical tree identities, counts and ancestry reproduced.                                                                   |
| F-021 | PASS                 | Backlog's historical zero-CI claim conflicts with existing workflow source.                                                   |
| F-022 | PASS                 | Unconditional template reload and zero static-file cache age supported.                                                       |

## **14.2 CP1 — F-023–032**

| ID    | Evidence disposition | Independent semantic assessment                                                                            |
| ----- | -------------------- | ---------------------------------------------------------------------------------------------------------- |
| F-023 | PASS                 | Shared polling lifecycle and unit-level stop concern supported.                                            |
| F-024 | PASS                 | Bound event subscriptions and incomplete disposal evidence supported.                                      |
| F-025 | PASS                 | Premature shutdown completion and ignored operation results supported.                                     |
| F-026 | PASS                 | Alternative actuator methods lack the same local safety check.                                             |
| F-027 | PASS                 | Reservation release is not owner-bound.                                                                    |
| F-028 | PASS                 | Queue saturation and dropped delivery risk supported.                                                      |
| F-029 | PASS                 | Database context commits through `finally`, including exceptional exits.                                   |
| F-030 | PASS                 | Migration/recovery ownership remains unqualified.                                                          |
| F-031 | PASS                 | Separate file locking and save-error handling do not establish atomic read-modify-write.                   |
| F-032 | PASS                 | Suppressed registry persistence failures and potentially false registration/promotion success established. |

## **14.3 CP2 — F-033–044**

| ID    | Evidence disposition | Independent semantic assessment                                                                      |
| ----- | -------------------- | ---------------------------------------------------------------------------------------------------- |
| F-033 | PASS                 | Pending approval and original-time versus delay predicate gaps supported.                            |
| F-034 | PASS                 | Registered attribute incompatibility correctly separated from discovery fallback.                    |
| F-035 | PASS                 | `None` interpreted as success despite adapter failure paths.                                         |
| F-036 | PASS                 | Inspected route/service authorization gap and identity fallback supported.                           |
| F-037 | PASS                 | Room selection does not establish authorized membership.                                             |
| F-038 | PASS                 | Health blueprint exemption and alert-creation endpoint supported.                                    |
| F-039 | PASS                 | Conditional detection freshness and missing final eligibility revalidation supported.                |
| F-040 | PASS                 | Partial valve/pump ordering and uncertain shutdown evidence supported.                               |
| F-041 | PASS                 | Status update lacks expected-state guard; ignored persistence outcomes supported.                    |
| F-042 | PASS                 | Schedule and bulk operation result-handling defects supported.                                       |
| F-043 | PASS                 | Bounded application maintenance observations supported; downstream trust HOLD.                       |
| F-044 | PASS                 | Standard MQTT-enabled adapter incompatibility supported; wireless and override conditions preserved. |

### **Replacement finding-row dispositions**

# **42**

Bounded PASS

# **2**

HOLD

All 44 runtime findings remain OPEN. Separate governance, CI, enforcement and downstream qualification gates are not included in this count.

The matrix's source anchors are substantially improved. The remaining ML corrections are based on actual semantic deficiencies, not invalid URL or line-number checks.

# **15. ER-05 — CI and effective integration enforcement**

**Disposition: HOLD — independently reproduced against the R1 candidate.**

Fresh GitHub metadata confirms that integration remains blocked independently of the replacement-evidence verdict.

## **15.1 Exact candidate and synthetic merge revision**

The current PR synthetic merge commit is:

`a9459b43735b53a9c91b0f5fd1e1293ef3c6794e`

Its two parents are the authorized application baseline and the R1 candidate HEAD.

The synthetic merge commit tree matches the candidate tree:

`1f29e1d88a612712d957914d0f37c0e8af0b3e97`

Primary evidence: [synthetic merge commit object](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/commits/a9459b43735b53a9c91b0f5fd1e1293ef3c6794e?utm_source=chatgpt.com).

This establishes tree equivalence for the inspected merge object. It does not establish that CI checked out or tested that object.

## **15.2 Fresh CI inspection**

| Evidence                       | Candidate HEAD  | Synthetic merge SHA |
| ------------------------------ | --------------- | ------------------- |
| Combined status                | Pending         | Pending             |
| Commit status entries          | 0               | 0                   |
| Check runs returned            | 0               | 0                   |
| Workflow runs returned for SHA | 0               | 0                   |
| Successful qualification       | Not established | Not established     |

Primary endpoints: [candidate check runs](https://api.github.com/repos/PatoruzuyX/SYSGrow/commits/47794834e009334aa417b913fcc6818407ad234e/check-runs?utm_source=chatgpt.com), [candidate combined status](https://api.github.com/repos/PatoruzuyX/SYSGrow/commits/47794834e009334aa417b913fcc6818407ad234e/status?utm_source=chatgpt.com), [merge-ref check runs](https://api.github.com/repos/PatoruzuyX/SYSGrow/commits/a9459b43735b53a9c91b0f5fd1e1293ef3c6794e/check-runs?utm_source=chatgpt.com).

The source [CI workflow](https://github.com/PatoruzuyX/SYSGrow/blob/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21/.github/workflows/ci.yml?utm_source=chatgpt.com) remains present and unchanged.

The absence of returned runs does not establish why execution is missing.

## **15.3 Effective enforcement inspection**

| Administrative evidence                    | Observed result               |
| ------------------------------------------ | ----------------------------- |
| Main branch SHA                            | Authorized baseline           |
| `protected`                                | `false`                       |
| `protection.enabled`                       | `false`                       |
| Status-check enforcement level             | `off`                         |
| Required contexts                          | Empty                         |
| Required checks                            | Empty                         |
| Returned rulesets including parent request | Empty                         |
| Detailed branch-protection endpoint        | HTTP 403                      |
| Effective branch-rules endpoint            | Unavailable through connector |
| Complete bypass/admin/review policy        | Not established               |

Source: [main branch metadata](https://api.github.com/repos/PatoruzuyX/SYSGrow/branches/main?utm_source=chatgpt.com), [rulesets query](https://api.github.com/repos/PatoruzuyX/SYSGrow/rulesets?includes_parents=true\&utm_source=chatgpt.com), [detailed protection endpoint](https://api.github.com/repos/PatoruzuyX/SYSGrow/branches/main/protection?utm_source=chatgpt.com).

The accessible metadata supplies positive evidence that branch protection and required status checks are disabled in the returned branch representation.

It does not establish a complete effective administrative policy.

**ER-05 and F-012 remain unresolved.** The separate `SYSGROW-INTEGRATION-ENFORCEMENT-001` workstream is still required before G0 integration.

No settings changes or CI dispatch were performed.

# **16. EGA-001 — Independent governance assessment**

## **16.1 Amendment lifecycle**

**Design disposition: PASS. Acceptance eligibility: HOLD.**

The new [EGA-001:24–48](https://github.com/PatoruzuyX/SYSGrow/blob/47794834e009334aa417b913fcc6818407ad234e/docs/qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md?utm_source=chatgpt.com#L24-L48) explicitly establishes the amendment's staged effectiveness.

**PROPOSED**

Original-report prerequisite still binding

Current

**Replacement qualified**

Three independent exact-candidate reports

HOLD

**Owner limited acceptance**

Only enumerated original-report prerequisite substituted

**G0 integration eligible**

All remaining CI, enforcement and review gates satisfied

**Integrated / canonical**

Separate integration authorization and closeout

This resolves the earlier ambiguity between accepting the evidence substitution and making the broader governance amendment normative.

## **16.2 Clause assessment**

| Amendment component                               | Disposition |
| ------------------------------------------------- | ----------- |
| Precisely limited original-report substitution    | PASS        |
| Permanent historical limitation                   | PASS        |
| Exact candidate identity and independent reports  | PASS        |
| Explicit owner acceptance outside candidate tree  | PASS        |
| Fresh qualification after candidate changes       | PASS        |
| Preservation of successful CI requirement         | PASS        |
| Preservation of effective enforcement requirement | PASS        |
| Separate integration approval                     | PASS        |
| Durable evidence preservation                     | PASS        |
| Dependency-aware retention and disposal           | PASS        |
| Acceptance readiness of current candidate         | HOLD        |

The revised AGENTS, guidelines, qualification profiles, workstreams and foundation ExecPlan references are consistent with the proposed limited substitution.

I identified no explicit waiver of applicable device-specific safety or downstream maintenance qualification.

No ADR has been accepted through this amendment. The twelve proposed ADRs and D0–R1a/R1b–R2a/R2b–R3a/R3b–Q ordering remain preserved.

## **16.3 Historical provenance**

The original CP0–CP2 reports and original recovery export remain unavailable.

Preserving subsequent review attachments does not recover those original reports.

The CP0 22-versus-32 discrepancy therefore remains historically unresolved. Neither the independently reproduced Git inventory nor the replacement findings can retrospectively establish the original discovery attribution.

EGA-001 provides a defensible potential resolution of the historical prerequisite, but it has not been accepted and cannot be accepted on the owner's behalf in this review.

# **17. New Reviewer 3 correction register**

| New observation | Severity | Affected scope | Required correction                                                                                                                          |
| --------------- | -------- | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| ER-R3-R1-001    | High     | F-007, REB-07  | Complete model eligibility evidence across implicit active registration, inactive selection, invalid metrics and false retraining completion |
| ER-R3-R1-002    | High     | F-008, REB-08  | Add actual consumer bundle-loading composition, immutable version coherence and pre-deserialization trust                                    |
| ER-R3-R1-003    | Medium   | CP4, REB-13    | Define explicit negative lifecycle, metric validity, artifact coherence and durable outcome oracles                                          |

These observations extend existing findings. I do not recommend introducing additional foundation finding IDs unless the owner determines that independent accountability requires it.

F-007 and F-008 retain their existing High severity. No existing foundation finding is closed or silently reclassified.

## **17.1 Recommended correction scope**

### **Proposed next-candidate checklist**

0/7

**ER-R3-R1-001**

Expand F-007 with save_model() default-active semantics and actual trainer callers.

**ER-R3-R1-001**

Add \_latest_entry() selection semantics and invalid metric coercion evidence.

**ER-R3-R1-001**

Document retraining completion versus successful training and durable promotion; cross-reference F-032.

**ER-R3-R1-002**

Add actual IrrigationPredictor model/scaler/encoder/metadata loading composition.

**ER-R3-R1-002**

Require immutable bundle identity, trust before deserialization and coherent version loading.

**ER-R3-R1-003**

Extend CP4 measurable negative, concurrency, persistence and eligibility test designs.

**Requalification**

Preserve all existing 44 findings, historical reports, 45 FT designs and reviewer verdicts; requalify exact resulting HEAD.

Manual tracking only. No repository changes or approval actions are performed by this checklist. Copy correction checklist

The required changes are documentary and qualification-design refinements. No ML implementation, training, model promotion or runtime activity is necessary to address this review.

# **18. Limitations and scope compliance**

This requalification is based on pinned GitHub source, primary Git metadata, archived reports and the available original attachment texts.

The principal limitations are:

- All referenced source files were retrieved and explicit anchor bounds checked, but semantic inspection was targeted rather than an exhaustive audit of every line and every possible runtime call path.
- The seven pre-existing review archives were verified against their unchanged parent blob identities and recorded SHA-256 values. Their original attachment bytes were not independently reopened in this review.
- All three newly archived reports were compared against complete indexed Library attachment texts. Raw attachment materialization and independent session authentication were unavailable.
- Historical CP0–CP2 originals and the original recovery response remain unrecovered.
- Effective inherited administrative policy, complete bypass rules and detailed branch protection remain inaccessible or unqualified.
- Downstream ESP32 bridge, firmware and bootloader implementations were not available in the inspected application tree.
- No actual model training, artifact deserialization, inference, promotion, pytest execution, Docker build, runtime fault injection or hardware test was performed.
- The three new observation identifiers, their severities and proposed mapping into existing findings are reviewer decisions, not owner-approved changes.

No repository modifications, Git mutations, submitted reviews, CI dispatch, settings changes, firmware updates, deployment, physical operations, EGA-001 acceptance or merge were performed.

# **19. Final independent acceptance record**

# **HOLD**

Reviewer 3

**SYSGROW-EVIDENCE-REBASELINE-001-R1**

Evidence, Integration and ML Qualification

Reviewed candidate HEAD

47794834e009334aa417b913fcc6818407ad234e

Reviewed candidate tree

1f29e1d88a612712d957914d0f37c0e8af0b3e97

New reviewer observations

**2 High / 1 Medium**

Finding register continuity

**44/44**

Archive checksum verification

**10/10**

Prior observation mappings

**20/20**

Existing Critical findings

**4 OPEN**

Total foundation findings

**44 OPEN**

Replacement technical evidence

HOLD

EGA-001 design

PASS

EGA-001 acceptance eligibility

HOLD

CI and effective enforcement

HOLD

G0 integration

HOLD

Production safety

NOT QUALIFIED

**Final recommendation:** retain the R1 corrections. The primary evidence recovery, historical branch verification, archive integrity and governance amendment design are now substantially resolved.

The remaining replacement-evidence HOLD is narrower and technically specific. Correct ER-R3-R1-001 through ER-R3-R1-003, preserve the existing findings and historical records, and obtain fresh independent qualification of the resulting exact candidate.

In parallel, under separate authorization, the integration-enforcement workstream remains necessary. Even a subsequent replacement-evidence PASS would not remove that mandatory gate.

The central ML requirement is that **training success, model registration, readiness, statistical eligibility, artifact trust, explicit promotion, inference admission and physical-control authority must remain distinct, independently verifiable decisions.** The replacement evidence should accurately describe every relevant route through that lifecycle before it becomes the authoritative foundation baseline.