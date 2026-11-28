# Qualification profiles and integration records

Status: proposed G0.3 governance, pending qualified owner-approved integration. Profile evidence is scoped; no profile implies another. Identify exact revision, baseline, installation/profile identity (sanitized), applicable findings/invariants, tests and results, exclusions, approval authority and restrictions. Decide applicability before tests: record reason, evidence and accountable reviewer/owner for genuine non-applicability. Unavailable equipment, source, access or evidence is HOLD, never N/A. No mandatory gate waived through residual risk acceptance.

| Profile | Required evidence | Permitted consequence / approval |
|---|---|---|
| Documentation | Markdown-only scope, provenance, source semantics/anchors, preserved reviews, applicable exact-HEAD CI and effective enforcement evidence, independent final review | Owner may separately approve documentation integration; no runtime qualification |
| Synthetic software integration | Actual composed services on isolated fixtures, negative/concurrency/fault oracles, full applicable source and test evidence, CI, independent review | Owner may approve bounded software integration; no physical operation or deployment |
| Deployment platform | Specific OS/Python/architecture/config, reproducible build, isolated startup/recovery, exclusive lock boundary and operational readiness evidence | Separate owner deployment approval only for qualified profile; no activation |
| Device-specific safety | Device/firmware/wiring/topology and independent protection evidence; competent assessment, separately authorized HIL and safe limits, state verification/rearm | Separate device-specific safety disposition; no activation solely by test success |
| Production activation | Applicable software/deployment/device evidence, closed applicable Critical/High gates, site risk disposition and operational recovery plan | Explicit owner activation approval for qualified scope only |

Q records each applicable profile independently, with exact revision, scoped PASS/HOLD/FAIL, evidence, exclusions and restrictions. Synthetic integration may pass while physical safety is NOT QUALIFIED; full F-001/EP-001 and EP-003C closure remains reserved for Q with all applicable evidence. No global safety PASS or blanket N/A.

## Qualification authority and advancement (G0.3)

Read-only, documentation and synthetic software qualification prohibit real-device operation and live private data access. Controlled device-specific hardware-in-the-loop (HIL) qualification requires separate explicit owner authorization, competent device-specific assessment, controlled equipment, established safety limits and a bounded qualification plan with stop/recovery criteria. HIL is not production activation or permission to use live private data. HIL may collect evidence for an unqualified device profile: its prerequisites are a competent approved test plan, controlled equipment, established limits and relevant software/platform readiness, not a premature final device-profile PASS. No HIL or physical operations under G0.3.

| Activity | Minimum prerequisite to authorize activity | Restrictions |
|---|---|---|
| CP3 isolated synthetic benchmarks | Applicable synthetic runtime Q qualification for measured composition | Synthetic fixtures; no real devices or live private data |
| CP3 isolated target-platform benchmarks | Applicable synthetic runtime Q qualification plus safe isolated platform prerequisites (reproducible environment, qualified containment/ownership and no physical authority) | May collect remaining platform evidence; full platform PASS required before deployment, not before collecting its own evidence |
| CP4 offline ML evaluation | Data provenance, artifact trust, isolated compute and evaluation plan; relevant synthetic runtime qualification if exercising control integration | Advisory offline evaluation; no promotion or actuation |
| CP5 synthetic regression/fault qualification | Relevant bounded software baseline, isolation and test prerequisites | May establish missing test evidence; release qualification requires applicable evidence to pass |
| CP6 external integration qualification | Applicable capability, security, consent, local independence and isolation contracts plus separately scoped authorization | Synthetic/mocked first; external calls/data transfer separately authorized; no physical authority |
| CP7 strategic closeout | Explicit scoped dispositions for CP0–CP6/Q, evidence and residual risks | Record HOLD/FAIL honestly; programme closure requires mandatory evidence and owner approval |
| Controlled HIL or physical benchmarks | Separately approved competent bounded device-specific test plan, established limits, controlled equipment and applicable software/platform readiness | No activation, unrestricted control or live private data |
| Production autonomous operation | Applicable software, deployment and device-specific PASS, all applicable Critical/High gates closed, qualified site disposition and explicit activation approval | Qualified scope only |

Programme advancement is activity-specific. An unresolved profile blocks dependent activities, not independent offline work with satisfied prerequisites and separate authorization. Earlier D0–R3 implementation gates remain intact. Q does not authorize any CP or physical operation by itself. Mandatory integration, deployment and activation gates remain non-waivable.

## Canonical integration record lifecycle

The applicable GitHub PR discussion/review history is canonical. Use exact revision-linked records with stable references, dated author and explicit supersession; no silent edits. Before integration record: PR, authorized baseline, exact candidate SHA/tree, applicable check run/job IDs, candidate/base/actual checkout SHA and tree identity (including qualified merge-ref correlation), required contexts and enforcement evidence, independent reviewer report references and dispositions, scope, profile, residual baseline risks/containment, explicit owner integration approval and restrictions. Keep these outside the candidate tree to avoid changing the qualified SHA. If HEAD or target baseline advances, stop and requalify applicable evidence; even evidence-only commits do not inherit exact-HEAD approval.

After separately authorized integration, record approved candidate SHA, resulting integration SHA, method, ancestry or content-equivalence verification, resulting main ref, outcome, unresolved risks and restrictions. Post-integration evidence does not retroactively grant approval. A later documentation record commit is separately authorized and reviewed. No automatic merge, deployment or activation.

G0.1 and G0.2 reviews concern their respective superseded HEADs only. Preserve historical evidence; obtain three new final exact-HEAD reports after candidate stabilization and applicable evidence recovery. See [G0.3 review record](G0.3-REVIEW.md).
