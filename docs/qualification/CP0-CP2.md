# SYSGROW-FOUNDATION-001 — CP0–CP2 qualification record

Review date 27 November 2026; repository PatoruzuyX/SYSGrow; baseline [2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21](https://github.com/PatoruzuyX/SYSGrow/commit/2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21). This is a consolidated record of the preceding read-only ChatGPT qualification reports, not a fresh exhaustive audit or independent review. G0 owner authorized documentation only; CP0–CP2 delivered, owner acceptance of technical decisions pending. See [all 44 findings](FINDINGS.md).

## CP0 baseline

Complete Git tree: 780 files, 487 Python files; 65 Python test modules by test naming pattern. Main commit 15 March 2026, unit creation reliability/UI payload handling. Five remote branches, no open PRs/issues at CP0. GitHub [CI run 23113018823](https://github.com/PatoruzuyX/SYSGrow/actions/runs/23113018823) recorded Ruff, pytest and Bandit success on exact HEAD. No fresh independent tests run. Main protection flag false; detailed enforcement unavailable; tags unqualified. Existing Flask/Jinja2/Socket.IO/SQLite WAL/MQTT architecture, event bus, repository abstractions and optional AI are to be retained. CP0 recorded F-001–022.

Preserve the February [audit](../AUDIT_EXECUTIVE_REPORT.md) as dated historical evidence. Existing CI, lock file, compression, hardware-aware SQLite defaults, per-unit locks, irrigation decomposition/atomic claims/valve support, security headers/write auth, shutdown handlers and ML metric gates are implemented capabilities, not full qualification. Old audit counts are historical; no blanket assertion that all SQL or error disclosures are remediated. Dependency specification conflicts, clean Docker build input and unmeasured Pi performance remain open.

## CP1 architecture

F-023–032 add shared polling lifecycle, controller disposal, shutdown gaps, inconsistent safety checks, ownerless irrigation lock release, event saturation, transaction commit-on-exception, recovery ownership, JSON read-modify-write and registry concurrency. F-001 strengthened: production two-worker config and constructor side effects; bootstrap_runtime=False does not alone suppress scheduler/MQTT. No actual competing physical operation reproduced. Preserve ServiceContainer/ContainerBuilder, GrowthService, controllers, existing irrigation façade, repository contracts and EventBus. See [baseline](../architecture/FOUNDATION_BASELINE.md). CAP-001: local condition-profile sharing, visibility, import and source identity exist; not distributed federation or qualified consent.

Branch preservation (complete tree comparison; aggregate counts do not establish semantic equivalence):

| Branch | Pinned HEAD | Same / changed / branch-only / main-only paths | Ancestry |
|---|---|---|---|
| codex/main-snapshot-20260314 | b1f17eb39cd0558de2a16af713df37b6bf1c6113 | 156 / 372 / 1169 / 252 | no common ancestor reported |
| codex/pi-db-init-fix | 0e44e006de22c083fd3bdae536ae1ceb89200b59 | 156 / 372 / 1169 / 252 | no common ancestor reported |
| codex/unit-create-fix-20260315 | b9305e281e12ca74659bab0a20fb6563564028c4 | 156 / 372 / 1169 / 252 | no common ancestor reported |
| codex/stash-backup-20260315 | 9182885cd50b11d317c58fb893e51f1eb26795ab | 204 / 440 / 146 / 136 | diverged 1 ahead, 4 behind; common ancestor 1f2cd5bfa6cbf0acced68762d72ed45d66b41527 |

Preserve all refs; no bulk unrelated-history merge or deletion. Individual recovery review outstanding. CP1 extended doc retrieval reached connector call limit; no final HEAD recheck in CP1, but CP2 reverified baseline.

## CP2 security and physical safety

F-033–044 added. Critical: required approval policy gap, alternative command bypass, false physical success, in addition to F-001. Source evidence is pinned in the register. Ordinary turn_on path has SafetyService checks, but level/pulse/protocol paths do not demonstrate equivalent policy. Preserve CSRF, login limiter, secure cookies/production secret checks, scoped room design, parameterized queries and existing irrigation safeguards. Verified resource authorization and room membership gaps; firmware policy and MQTT security not qualified in real deployment. F-044 signature mismatch is conditional on wrapper composition. No proof of actual exploitation, device unsafe state or hardware incidents.

Threat categories: T-001 runtime competition; T-002 approval bypass; T-003 alternative command policy; T-004 false shutdown success; T-005 resource access; T-006 stale/false telemetry; T-007 duplicate/delayed commands; T-008 shared resources; T-009 firmware trust; T-010 audit integrity; T-011 queue/worker saturation; T-012 external AI instructions; T-013 knowledge manipulation; T-014 public diagnostics exhaustion. T-001–004 Critical, T-005–013 High (T-012/013 future), T-014 Medium. Mitigate via [safety invariants](../architecture/FOUNDATION_BASELINE.md), EP-001–004, EP-007 and CP6. Production safety NOT QUALIFIED. CP2 final HEAD unchanged.

## Limitations and status

Targeted source inspection, not exhaustive call graph, penetration test, electrical assessment or certification. No deployed Pi, local worktree, uncommitted files, real broker, live private data, firmware/wiring, network tests, fresh tests, hardware operations or independent AI reviews. Effective broker rules, branch enforcement, physical limits and actual device safeguards unverified. Full dependency installation, SQL/error audit, service graph and individual branch recovery outstanding. Proposed severities, candidate ADRs and revised sequencing remain proposals. No CP0–CP2 repository changes. G0 does not close any finding or authorize deployment, implementation of remediation, or production activation.

## G0.1 original-report provenance

The original reports were produced in preceding ChatGPT qualification sessions on 27 November 2026. Recovered conversation-summary metadata identifies CP0 (16:12 UTC), CP1 (16:17 UTC), CP2 (16:23 UTC), the same authorized baseline and the CP1/CP2 totals of 32/44 findings. This is discovery metadata, not the complete original report content. The consolidated record attributes F-001–022 to CP0, F-023–032 to CP1, and F-033–044 to CP2; the full original CP0 text, original finding rows and stable conversation/document references were not recovered. The CP0 summary also mentions 32 findings, so original phase attribution must be reconciled against the actual reports rather than guessed. Preserve original reports when supplied, record their stable locations/revisions, and compare each row's ID, title, severity, classification, evidence and disposition before closing the G0 provenance gate. Do not reconstruct missing reports from this consolidation or present the summary as independent evidence. See [G0 review record](G0-REVIEW.md).

## G0.2 provenance investigation

Re-requested original CP0/CP1 report texts and stable references via conversation retrieval; only discovery summaries and prior limitation statements returned. CP2 response text is visible in the working conversation, but no durable original export/reference or checksum has been supplied. Do not present a reconstruction as an original. G0-EI-03 OPEN: owner must provide original exports or separately authorize a replacement pinned-source qualification with explicit loss of historical provenance; current mandatory gate is not waived. The three G0.1 reviewer attachments are archived under [reviews](reviews/) and are not substitutes for CP0–CP2 originals.
