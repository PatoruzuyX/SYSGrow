# SYSGROW-EVIDENCE-RECOVERY-001 — recovery outcome crosswalk

Date 28 November 2026. Source recovery assignment concerned governance `5d646ba58cb071b392cea94287371925ba82e626` and application `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`. This is a newly authored crosswalk, NOT a recovered original report or original recovery export. Prior conversation-summary retrieval reports P0–P5 overall HOLD, 44/44 rows reconciled against available sources and 82/82 pinned references valid; no complete original CP0–CP2 exports, stable references/checksums, or resolution of CP0 22-versus-32 phase attribution. The raw full recovery response and stable source identifier were not available to this author; prior counts are attributed observations, not re-executed results or evidence of complete semantic sufficiency. Supplied review attachments were later G0 reviews, not CP originals, as recorded in [archive manifest](reviews/PROVENANCE.md). Preserve all historical reviewer HOLD dispositions.

| Recovery item | Reported prior result | Current verification and qualification boundary | Required follow-up |
|---|---|---|---|
| ER-01 / F-019, F-013 | 67 Python files under tests, 66 naming-pattern modules vs consolidated 65. | Inspected pinned reliability test source and CI command; no fresh complete-tree enumeration or pytest collection. Do not conflate files, collected tests and passing tests. | Verify direct tree identity and reproducible pattern count; record exclusions, actual collection and execution only in separately authorized isolated activity. Retain old 65 as historical claim, not authoritative count. |
| ER-02 / F-020 | Three branches each 156 same / 372 changed / 1169 branch-only / 252 main-only; stash 204 / 440 / 146 / 136. Matches consolidated historical report. | Current branch search confirms all four names; no current SHA/tree identity or semantic equivalence verified. Historical pinned heads and ancestry retained in [CP0–CP2 record](CP0-CP2.md). | Obtain direct pinned trees, compare path/blob/mode identities, verify ancestry and review unique changes individually; preserve refs. |
| ER-03 / F-006 | Forecasting target leakage supported; temporal qualification outstanding. | Directly verified same-row feature/target overlap and random split, preprocessing before split in pinned ml_trainer.py. | CP4 objective/horizon, train-only preprocessing, chronological/grouped validation, held-out outcomes; no model promotion. |
| ER-04 / F-043 | Downstream firmware trust unverified. | Direct source shows URL acceptance, adapter forwarding, tracked send/queue and wrapper call; no firmware validation evidence beyond this boundary. API sent label is not proof of delivery or trusted firmware. | Trace bridge and device source/config and verify security/rollback with separately authorized safe tests; no OTA in this scope. |
| ER-05 / F-012 | Accessible main protection false, required checks off/empty; effective policy incomplete. | Starting candidate combined statuses/workflow runs both empty on fresh queries. Historical [workstream](EVIDENCE-WORKSTREAMS.md) records reviewer metadata and inaccessible policy. Not a new admin-policy audit. | Separate enforcement workstream, effective repository/inherited policy and successful final-HEAD CI; no settings change or dispatch in this package. |

## P0–P5 disposition

P0/P1/P2: original discovery incomplete; no raw originals, stable refs or checksums. P3: prior 44-row reconciliation reported, replacement matrix newly authored and awaiting independent semantic verification. P4: CP0 discrepancy permanently unresolved absent originals. P5: independent qualification remains mandatory, not performed by author. Historical gate is not silently waived; replacement mechanism is proposed for separate acceptance. All findings OPEN. Technical and documentary HOLD; production safety NOT QUALIFIED.

## R1 primary structural reproduction — 28 November 2026

Read-only primary GitHub commit objects, untruncated recursive trees and comparison responses, independently retrieved again after Reviewer 3. Application commit `2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21`, tree [6f59af9c2fdeff431bfb83411ee17bdf6619a016](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/6f59af9c2fdeff431bfb83411ee17bdf6619a016?recursive=1); reviewed candidate `a10107a4f78eea8c37a0b1a6ab7d616a61b4df87`, tree `6afe5fa9a1838137e80a290ccbb35eab6ea70172`. Original G0.3 parent tree `63cdc7d73456bc18eb6a77646283da2d9908976f`. Initial rebaseline cumulative diff: 35 Markdown paths, 28 added/7 modified, zero removals; 808 file blobs vs 780. Direct parent 5 Markdown paths, 4 added/1 modified. These counts are structural, not implementation qualification.

| ER-01 inventory predicate | Observed |
|---|---:|
| Non-directory tracked files (baseline has no Gitlinks) | 780 |
| Paths ending .py | 487 |
| Paths under tests/ ending .py | 67 |
| Basename test_*.py or *_test.py under tests/ | 66 |
| Other Python under tests/ | 1 (tests/conftest.py) |
| Tracked data/ descendants | 0 |

Historical 65 test-module count preserved; original enumeration method unavailable. Count 66 independently reproduced, not pytest collection/execution/coverage. F-019 test oracles clarified in replacement matrix. Docker build depends on declared context; no actual build.

ER-02 compare all non-directory path identities by SHA/mode/type; same = exact identity, changed = shared path with unequal identity, branch-only/main-only = path set difference.

| Historical ref | HEAD | Exact tree | Same / changed / branch-only / main-only | Ancestry |
|---|---|---|---|---|
| codex/main-snapshot-20260314 | b1f17eb39cd0558de2a16af713df37b6bf1c6113 | [cb85d04b5b5e5ec99bac9c366fac1732d5ce68e1](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/cb85d04b5b5e5ec99bac9c366fac1732d5ce68e1?recursive=1) | 156 / 372 / 1169 / 252 | compare returned 404 No common ancestor |
| codex/pi-db-init-fix | 0e44e006de22c083fd3bdae536ae1ceb89200b59 | [a146736a820afaf21be0a47061124f8c1a07b170](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/a146736a820afaf21be0a47061124f8c1a07b170?recursive=1) | 156 / 372 / 1169 / 252 | compare returned 404 No common ancestor |
| codex/unit-create-fix-20260315 | b9305e281e12ca74659bab0a20fb6563564028c4 | [30235efb4ebf1657f9b1de5511bd9de06db6e246](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/30235efb4ebf1657f9b1de5511bd9de06db6e246?recursive=1) | 156 / 372 / 1169 / 252 | compare returned 404 No common ancestor |
| codex/stash-backup-20260315 | 9182885cd50b11d317c58fb893e51f1eb26795ab | [bccd5eb1796116a9f27b613f8ba0c0a9184d0b12](https://api.github.com/repos/PatoruzuyX/SYSGrow/git/trees/bccd5eb1796116a9f27b613f8ba0c0a9184d0b12?recursive=1) | 204 / 440 / 146 / 136 | diverged 1 ahead/4 behind; merge base 1f2cd5bfa6cbf0acced68762d72ed45d66b41527 |

All refs matched on preflight; no ref mutations. Same aggregate counts do not imply same trees. Structural ER-01/02 PASS (subject to final review), EP-006 semantic reconciliation and CP5 runtime evidence OPEN. ER-03 source evidence strengthened; CP4 temporal qualification OPEN. ER-04 bounded application evidence strengthened, downstream HOLD; EP-007 owns trust with EP-003A/B/F dependencies. ER-05 pre-G0 enforcement and successful final-HEAD CI HOLD; EP-006 / separate authorized administrative workstream. Historical recovery P0–P5 remains HOLD and original-report provenance permanently unresolved unless originals actually recovered. Prior historical observations above are retained, not silently rewritten. No source-runtime tests executed.
