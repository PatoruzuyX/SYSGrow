# Security and physical safety policy

Status: G0 proposed policy, pending owner-approved integration. This is not a claim of certified safety or a promise of a supported release lifetime.

## Reporting

Report suspected vulnerabilities privately to the repository owner using a private channel or GitHub private vulnerability reporting if available. Do not post credentials, private telemetry, exploit instructions or device identifiers in public issues. Include affected revision, impact and sanitized reproduction evidence. No testing against others' installations or real equipment without explicit consent.

## Current qualification

The [CP0–CP2 report](docs/qualification/CP0-CP2.md) and [findings register](docs/qualification/FINDINGS.md) record the baseline and unresolved risks. Production safety is NOT QUALIFIED. F-001, F-033, F-034 and F-035 are Critical and open. No new autonomous irrigation or external physical-control activation while these or applicable safety prerequisites are unresolved. Existing installations require owner risk assessment; G0 does not operate or reconfigure them.

## Required boundaries

Authenticate principals and authorize each resource/action, including HTTP, Socket.IO, background tasks and broker operations. Public endpoints are explicitly allowlisted. Reject unknown or unsupported energizing commands. Preserve CSRF, cookie, rate limiting, secure-secret and existing safety protections. No implicit user identity for protected actions. MQTT needs qualified identities, topic ACLs, transport protection or isolated legacy gateway, bounded command lifetime and reconciliation. Firmware requires trusted provenance and privileged maintenance. External K.I.T.T. and community content are untrusted input; no direct broker authority or safety override.

Only an exclusive runtime may produce ordinary consequential physical-interface effects, subject to applicable admission, recovery and device-specific safety requirements; independent protective hardware and separately qualified emergency authority remain distinct. This covers interface configuration, registration, initialization, discovery, reconnect, disposal and cleanup; command-only denial is insufficient. Enforce device-specific limits, fresh required observations, approval and resource reservations. Separate requested, authorized, dispatched, acknowledged, verified, rejected, failed and unknown outcomes. Never treat a publish as proof of physical state. Uncertain shutdown blocks further ordinary use of the resource pending safe reconciliation; retain appropriate independent protection and emergency recovery. Physical fail-safe design requires qualified hardware/wiring/firmware evidence, not a software-only assertion.

## Release gates

Close applicable Critical/High safety issues with source, synthetic tests, independent review and device-specific qualification as applicable. Require owner approval for integration, deployment and activation as distinct gates. Read-only, documentation and synthetic software qualification prohibit real-device operation and live private data access. Controlled device-specific hardware-in-the-loop (HIL) qualification requires separate explicit owner authorization, competent device-specific assessment, controlled equipment, established safety limits and a bounded qualification plan with stop/recovery criteria. HIL is not production activation or permission to use live private data. No secrets or live provider calls in read-only, documentation or synthetic qualification. No default universal safe state or runtime limit is approved.

## G0.1 containment and emergency boundaries

Existing installations are not grandfathered as safe. Independently of future change requests, the owner must promptly identify affected existing installations and record affected installation scope, existing automation and unresolved hazards, a device-specific risk assessment, interim containment and escalation/recovery arrangements. This documentation does not instruct or authorize live shutdown, reconfiguration or changes to physical equipment. If safe operation cannot be established, seek a competent device-specific assessment and separate owner disposition; do not infer permission to continue or expand operation from G0.

Exclusive runtime authority covers ordinary software commands. Independent protective hardware and separately qualified emergency intervention remain available without granting unrestricted normal control authority. Uncertain physical state or recovery evidence must inhibit ordinary energization across process replacement, lock expiry and restart. An owner cannot waive a mandatory safety gate by ordinary risk acceptance. See [target contracts](docs/architecture/FOUNDATION_BASELINE.md) and [remediation plans](docs/plans/REMEDIATION.md).

## G0.2 existing-installation disposition and rearm

Existing exposure requires assessment when identified, not only before the next change. The accountable installation owner records scope, device/firmware and current operating modes, applicable hazards, independently established safeguards, evidence of interim containment, unresolved risks, competent assessment, escalation route, review due date and triggers (incident, changed state/configuration, lost evidence, new finding or failed safeguard). Missing assessment or evidence is NOT QUALIFIED; promptly escalate to the accountable owner and competent device-specific assessor. Document any disposition and its limits; no implicit permission to continue operating. G0.2 authorizes no live assessment, physical shutdown, reconfiguration or continued operation. Operational measures require separate competent assessment and authorization, with independent protective mechanisms preserved.

Emergency intervention inhibits routine command admission; pre-intervention authority is invalidated, state reconciled, qualified device-specific rearm completed and fresh ordinary authorization required. Restricted emergency authority cannot be reused for normal activation. See [qualification profiles](docs/qualification/QUALIFICATION-PROFILES.md).

## G0.3 qualification scope

G0.3 authorizes documentation only, not HIL, installation assessment, live operations or continued operation. Apply [qualification profiles](docs/qualification/QUALIFICATION-PROFILES.md) and [remediation plans](docs/plans/REMEDIATION.md). A current safe observation does not exclude unresolved transport effects; protective-intervention invalidation and quarantine survive process replacement and stale persistence restoration or fail closed. Each internal service identity has explicit action/resource scope; no privileged fallback.
