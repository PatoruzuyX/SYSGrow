# Qualification profiles and integration records

Status: proposed G0.2 governance, pending qualified owner-approved integration. Profile evidence is scoped; no profile implies another. Identify exact revision, baseline, installation/profile identity (sanitized), applicable findings/invariants, tests and results, exclusions, approval authority and restrictions. Decide applicability before tests: record reason, evidence and accountable reviewer/owner for genuine non-applicability. Unavailable equipment, source, access or evidence is HOLD, never N/A. No mandatory gate waived through residual risk acceptance.

| Profile | Required evidence | Permitted consequence / approval |
|---|---|---|
| Documentation | Markdown-only scope, provenance, source semantics/anchors, preserved reviews, applicable exact-HEAD CI and effective enforcement evidence, independent final review | Owner may separately approve documentation integration; no runtime qualification |
| Synthetic software integration | Actual composed services on isolated fixtures, negative/concurrency/fault oracles, full applicable source and test evidence, CI, independent review | Owner may approve bounded software integration; no physical operation or deployment |
| Deployment platform | Specific OS/Python/architecture/config, reproducible build, isolated startup/recovery, exclusive lock boundary and operational readiness evidence | Separate owner deployment approval only for qualified profile; no activation |
| Device-specific safety | Device/firmware/wiring/topology and independent protection evidence; competent assessment, separately authorized HIL and safe limits, state verification/rearm | Separate device-specific safety disposition; no activation solely by test success |
| Production activation | Applicable software/deployment/device evidence, closed applicable Critical/High gates, site risk disposition and operational recovery plan | Explicit owner activation approval for qualified scope only |

Q records each applicable profile independently. Synthetic integration may pass while physical safety is NOT QUALIFIED; F-001 and other safety findings cannot be closed beyond demonstrated scope. No blanket N/A or global safety PASS.

## Canonical integration record lifecycle

The applicable GitHub PR discussion/review history is canonical. Use exact revision-linked records with stable references, dated author and explicit supersession; no silent edits. Before integration record: PR, authorized baseline, exact candidate SHA/tree, applicable check run/job IDs and enforcement evidence, independent reviewer report references and dispositions, scope, profile, residual baseline risks/containment, explicit owner integration approval and restrictions. Keep these outside the candidate tree to avoid changing the qualified SHA. If HEAD or target baseline advances, stop and requalify applicable evidence; even evidence-only commits do not inherit exact-HEAD approval.

After separately authorized integration, record approved candidate SHA, resulting integration SHA, method, ancestry or content-equivalence verification, resulting main ref, outcome, unresolved risks and restrictions. Post-integration evidence does not retroactively grant approval. A later documentation record commit is separately authorized and reviewed. No automatic merge, deployment or activation.

For G0.2, all three G0.1 reviewer reports concern the superseded correction HEAD only. Preserve them as historical evidence; obtain new final exact-HEAD reports before integration. See [review record](G0.2-REVIEW.md).
