# Engineering and integration guidelines

Status: G0 proposal; becomes canonical only after owner-approved integration. See [AGENTS.md](../AGENTS.md).

## Document ownership

| Record | Canonical location |
|---|---|
| Agent rules | ../AGENTS.md |
| Engineering workflow | this document |
| Security and safety release policy | ../SECURITY.md |
| Current architecture and target invariants | architecture/FOUNDATION_BASELINE.md |
| Accepted/proposed decisions | architecture/adr/README.md |
| Qualification history | qualification/CP0-CP2.md |
| Open findings and evidence | qualification/FINDINGS.md |
| Execution scope and gates | plans/ |
| Programme sequence | ../ROADMAP.md |
| Historical backlog and reconciliation | ../BACKLOG.md |
| Release history | ../CHANGELOG.md |
| Integration approval and closeout | Applicable GitHub PR discussion/review records; see qualification/QUALIFICATION-PROFILES.md |
| Qualification profiles and applicability | qualification/QUALIFICATION-PROFILES.md |
| Foundational design interfaces | plans/D0-CONTRACTS.md |

Historical audits remain immutable evidence of their dates; current source and pinned evidence take precedence for factual claims. Update the canonical record instead of duplicating decision ownership. Use [INDEX.md](INDEX.md) for navigation.

## Preflight and planning

Record repository, owner authorization, exact remote HEAD, current branch, local worktree/status (if available), existing branches/PRs and applicable instructions. Reconcile any main advance; stop on material conflicts. Use read-only qualification before remediation. Each plan must state finding IDs, owner, in/out scope, baseline, dependencies, test matrix, rollback, checkpoint and integration/activation gates. A proposed plan is not authority.

## Implementation

Prefer modular Flask, domain/application logic, repositories, and explicit adapters. Composition roots wire implementations; passive construction and non-owner paths must not produce unauthorized consequential physical-interface effects (target invariant); initialization, registration, discovery, reconnect, disposal and cleanup require applicable ownership, recovery, resource authorization and safety boundaries. Keep public contracts stable or version and migrate them explicitly. Use strict schemas, parameterized SQL, bounded resources, structured errors, authorization and no implicit identity defaults for protected operations. Keep the UI token-driven; preserve light/dark, accessibility and existing integration hooks. New dependencies, device protocols, migrations, deployment configuration and physical control changes require specific approval.

## Verification

Existing CI runs Ruff lint/format, pytest and Bandit on Python 3.13. For a local isolated environment with the qualified dependencies, reproduce the commands from [.github/workflows/ci.yml](../.github/workflows/ci.yml): `ruff check .`, `ruff format --check .`, `pytest tests/ -x -q --tb=short --timeout=30`, `bandit -r app/ -c pyproject.toml -q -ll`. Set testing environment and use synthetic devices/data; do not use production broker, database, secrets or devices. Validate dependencies before installation. For documentation-only changes, verify changed paths, links, preserved historical content and finding/plan consistency, and inspect CI on the exact HEAD. Do not claim coverage enforcement, platform compatibility or hardware safety from these checks alone.

Safety changes additionally require contract, concurrency, negative and fault-injection tests with actual service composition. Read-only, documentation and synthetic software qualification prohibit real-device operation and live private data access. Controlled device-specific hardware-in-the-loop (HIL) qualification requires separate explicit owner authorization, competent device-specific assessment, controlled equipment, established safety limits and a bounded qualification plan with stop/recovery criteria. HIL is not production activation or permission to use live private data. HIL results are scoped evidence; no production installations or scope expansion. See [foundation plan](plans/SYSGROW-FOUNDATION-001.md) and [remediation plans](plans/REMEDIATION.md).

## Integration and rollback

Submit a bounded PR; include evidence, scope, limitations, finding mappings, rollback/recovery steps and explicit unresolved risks. Independent reviewers must assess the exact HEAD, not the author's self-check. Any Critical/High candidate review defect blocks integration until corrected and re-reviewed; a mandatory checkpoint invariant, required evidence or independent review cannot be waived by ordinary risk acceptance. Existing out-of-scope baseline findings may remain OPEN with documented owner, containment, follow-up and residual-risk disposition, never as qualified safety or permission to activate. Record exact approved HEAD, baseline, review identifiers, CI run/job evidence, owner approval and resulting integration revision; accepting governance does not accept candidate ADRs. Require applicable successful exact-HEAD CI, effective check-enforcement evidence and owner approval; repository enforcement is not established by G0 (F-012). Never bypass checks or auto-merge. If a candidate fails, keep it unmerged; revert only authorized changes using reviewed procedures. For persistence/hardware changes, qualify backup, restoration and safe recovery separately. No merge implies deployment or activation permission.

## Evidence states

Verified = directly observed source/metadata; Risk = credible scenario, impact not reproduced; Unverified = missing evidence. Keep historical observations dated. Closure needs a corrective revision, test evidence, review and owner disposition. A missing test, unavailable local environment or unavailable review is a blocker, not a pass.

## Authority and staged qualification

Use the applicable accepted ADR and approved bounded ExecPlan together; neither a tool profile nor an implementation example grants permission. If an accepted decision conflicts with the scope or safety policy, stop. Separate design acceptance (context, alternatives, risks, contract and proposed validation), implementation authorization, synthetic implementation qualification, integration approval, deployment approval and device-specific activation approval. Each is a distinct record. Proposed validation may support a design decision without claiming the resulting implementation is qualified. No approval substitutes for missing mandatory evidence. See [ADR register](architecture/adr/README.md), [remediation dependencies](plans/REMEDIATION.md) and [G0 review record](qualification/G0-REVIEW.md).

## G0.2 integration records and qualification profiles

The canonical pre-integration and post-integration records live in the applicable GitHub PR discussion/review history (stable revision-linked references and content hashes where practicable; PR discussion is editable, so edits require explicit superseding record, not silent replacement). See [qualification profiles](qualification/QUALIFICATION-PROFILES.md) for fields, applicability and evidence. No commit, even evidence-only, inherits exact-HEAD CI or review approval. Record pre-integration evidence outside the candidate tree; obtain independent final exact-HEAD reviews and owner approval before merge. Record resulting integration SHA after authorized integration without modifying the qualified candidate. A follow-up repository documentation change needs its own authorization/qualification. G0 documentation qualification never qualifies runtime, deployment or activation.
