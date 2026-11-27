# Security and physical safety policy

Status: G0 proposed policy, pending owner-approved integration. This is not a claim of certified safety or a promise of a supported release lifetime.

## Reporting

Report suspected vulnerabilities privately to the repository owner using a private channel or GitHub private vulnerability reporting if available. Do not post credentials, private telemetry, exploit instructions or device identifiers in public issues. Include affected revision, impact and sanitized reproduction evidence. No testing against others' installations or real equipment without explicit consent.

## Current qualification

The [CP0–CP2 report](docs/qualification/CP0-CP2.md) and [findings register](docs/qualification/FINDINGS.md) record the baseline and unresolved risks. Production safety is NOT QUALIFIED. F-001, F-033, F-034 and F-035 are Critical and open. No new autonomous irrigation or external physical-control activation while these or applicable safety prerequisites are unresolved. Existing installations require owner risk assessment; G0 does not operate or reconfigure them.

## Required boundaries

Authenticate principals and authorize each resource/action, including HTTP, Socket.IO, background tasks and broker operations. Public endpoints are explicitly allowlisted. Reject unknown or unsupported energizing commands. Preserve CSRF, cookie, rate limiting, secure-secret and existing safety protections. No implicit user identity for protected actions. MQTT needs qualified identities, topic ACLs, transport protection or isolated legacy gateway, bounded command lifetime and reconciliation. Firmware requires trusted provenance and privileged maintenance. External K.I.T.T. and community content are untrusted input; no direct broker authority or safety override.

Only an exclusive runtime may execute physical operations. Enforce device-specific limits, fresh required observations, approval and resource reservations. Separate requested, authorized, dispatched, acknowledged, verified, rejected, failed and unknown outcomes. Never treat a publish as proof of physical state. Uncertain shutdown blocks further ordinary use of the resource pending safe reconciliation; retain appropriate independent protection and emergency recovery. Physical fail-safe design requires qualified hardware/wiring/firmware evidence, not a software-only assertion.

## Release gates

Close applicable Critical/High safety issues with source, synthetic tests, independent review and device-specific qualification as applicable. Require owner approval for integration, deployment and activation as distinct gates. No secrets, live private data, provider calls or physical operation in read-only or synthetic qualification. No default universal safe state or runtime limit is approved.
