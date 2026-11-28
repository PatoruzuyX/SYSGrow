SYSGROW-EVIDENCE-REBASELINE-001
Independent qualification — Reviewer 1: Architecture and Governance
Review date: 28 November 2026
Repository: PatoruzuyX/SYSGrow
Pull request: PR #3
Review mode: Independent, read-only documentary and technical evidence qualification.
1. Candidate identity and change containment
Identity	Revision
Candidate HEAD	a10107a4f78eea8c37a0b1a6ab7d616a61b4df87
Declared candidate tree	6afe5fa9a1838137e80a290ccbb35eab6ea70172
Parent governance HEAD	5d646ba58cb071b392cea94287371925ba82e626
Application baseline	2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21

The direct GitHub comparison between the parent governance revision and candidate establishes:
Commits ahead of parent1


Commits behind parent0


Changed documentation files5


Deleted lines0



Changed path	Added lines
docs/INDEX.md	5
docs/qualification/EVIDENCE-GOVERNANCE-AMENDMENT.md	22
docs/qualification/EVIDENCE-REBASELINE-001.md	74
docs/qualification/EVIDENCE-REBASELINE-REVIEW.md	13
docs/qualification/EVIDENCE-RECOVERY-CROSSWALK.md	15
Total	129

Pinned evidence: candidate commit · parent-to-candidate comparison

GitHub reports PR #3 as open, draft and unmerged, targeting main.

Change containment: PASS for the parent-to-candidate documentary delta. This establishes that the replacement package adds documentation without modifying application source, existing remediation plans, archived reviews or existing governance instructions within that delta. Direct verification of the declared tree identity is a separate requirement.

The additional comparison against the application baseline establishes:
- Five commits ahead and zero behind the authorized application baseline.
- 35 changed paths, all Markdown.
- No deleted files.
- PR #3's actual HEAD and base SHA match the supplied candidate and application baseline respectively.
Pinned application-to-candidate comparison
2. Independent qualification verdict
HOLD

Integration blocked

The replacement evidence approach is architecturally sound in principle, but its technical qualification and governance adoption require further corrections and evidence.
Critical review defects0

High3

Medium4

Low1



Finding register continuity

PASS

Architecture and dependency preservation

PASS

Replacement technical evidence

HOLD

EGA-001 adoption readiness

HOLD

Historical provenance recovery

HOLD

Integration eligibility

HOLD

Production safety

NOT QUALIFIED


The review defect severities above are separate from the existing 44 foundation findings. No finding severity or status is modified by this review.

The central distinction is that replacing an unobtainable historical evidence basis can be legitimate; replacing mandatory technical evidence with an assertion that evidence once existed is not. EGA-001 generally recognizes that distinction, but its operational adoption mechanism and certain replacement findings require strengthening.
3. Structural integrity of the replacement register
I independently compared the first seven fields of every finding row in the parent governance register against the replacement matrix.
Attribute	Result
Original finding count	44
Replacement finding count	44
Finding ID changes	0
Discovery attribution changes	0
Severity changes	0
Classification changes	0
Finding definition/title changes	0
Owner mapping changes	0
Status changes	0
Critical foundation findings	4
Open foundation findings	44

The four Critical findings remain:
- F-001 — Runtime ownership.
- F-033 — Required approval policy.
- F-034 — Alternative command boundary.
- F-035 — False physical success.
Pinned records: parent FINDINGS.md and replacement matrix, L15–64.

Disposition: PASS — structural continuity.

This is stronger than comparing aggregate finding counts. It establishes field-level continuity for all 44 findings. It does not establish that inherited classifications are semantically correct or that they faithfully represent the missing original CP reports.
4. Assigned finding qualification matrix
For this review:
- PASS means the replacement documentary basis is adequately supported within the inspected scope.
- HOLD means additional evidence, clarification or correction is required.
- Neither disposition constitutes remediation closure or runtime qualification.
Finding	Existing severity	Classification	Owner	Replacement disposition
F-001	Critical	Verified	EP-001	PASS
F-009	High	Verified	EP-004 / CP4	HOLD
F-010	High	Verified	EP-005	PASS
F-011	High	Verified	EP-005	HOLD
F-014	Medium	Verified	EP-006	HOLD
F-015	Medium	Unverified	CP3	HOLD
F-020	Medium	Verified	EP-006	HOLD
F-021	Medium	Verified	EP-006 / CP7	PASS
F-022	Medium	Verified	CP3	PASS
F-023	High	Verified	EP-002	PASS
F-024	High	Verified	EP-002	PASS
F-025	High	Verified	EP-002 / EP-003F	HOLD
F-028	Medium	Risk	EP-002 / CP3	PASS
F-029	High	Verified	EP-004	PASS
F-030	High	Risk	EP-004	PASS
F-031	Medium	Risk	EP-004	PASS
F-032	High	Risk	CP4	HOLD

10 PASS

7 HOLD




17 assigned findings assessed. All 17 remain OPEN in the foundation register.
5. Independent technical challenges
All application source references in this section are pinned to 2ab6bfa764c8ad587a027bd3b5155b53b7e5ae21, rather than mutable branch references or the older project attachments.
5.1 F-001 — Competing runtime ownership

PASS — replacement evidence
 Critical baseline finding

The replacement observation is supported by multiple independently retrieved source paths.
Pinned evidence	Verified observation
smart_agriculture_app.py, L16–36	Application construction explicitly enables runtime bootstrap.
app/init.py, L106–144	Runtime flag is forwarded to container construction.
container.py, L137–159	Scheduler configuration is called independently of that flag.
scheduled_tasks.py, L1525–1540	Scheduler configuration defaults to start=True.
Dockerfile, L77–83	Two Gunicorn workers are configured.
container_builder.py, L1058–1102	MQTT and hardware components are constructed independently of coordinator activation.
container_builder.py, L327–357	MQTT construction is conditional on enable_mqtt.
mqtt_broker_wrapper.py, L121–153	Constructor attempts broker connection and starts the MQTT loop on successful connection.
Actuator factory, L62–103	GPIO adapter construction is part of actuator creation.
gpio_relay.py, L27–42	Constructor configures the physical GPIO interface when available.
Actuator management, L418–424	Registration creates the actuator through the factory.

Verified baseline construction paths
Static construction paths and conditional effects; not an observed execution trace.
Counterexample: Setting bootstrap_runtime=False does not establish passive application construction. Scheduler startup still occurs through the container, and MQTT construction remains controlled by a different flag.

A single configured worker would reduce one competing-process scenario but would not establish ownership across CLI entry points, process replacement, recovery or independently started processes.

Assessment: Critical severity remains justified by potential consequences. The replacement correctly separates verified source behavior from unobserved competing physical operations.

Retain full F-001 closure exclusively at Q, following R3a/R3b and applicable qualification profiles.
5.2 F-009 — Sensor calibration persistence placeholders

HOLD
 High baseline finding

The original defect is verified.

The methods _save_calibration() and _delete_calibration() contain placeholder comments and logging rather than actual repository writes.

Pinned calibration service, L358–374

Additional evidence independently identified during this review strengthens the finding:

SensorManagementService, L140–162 constructs CalibrationService() without supplying a repository.

This matters because the issue is not limited to unimplemented persistence helpers. The inspected actual composition also lacks the injected persistence dependency.

Counterexample: Implement both persistence helper methods, but leave the sensor management service constructing the calibration service without a repository. An isolated calibration unit test could pass while composed runtime calibration remains non-persistent.

Required correction: Add the composition anchor and explicitly require repository-backed calibration through the actual application service graph. Include restart recovery, failed persistence, deletion, calibration provenance and applicable CP4 consumption tests.

EP-004 and CP4 ownership should remain, with explicit coordination with EP-003E for calibration eligibility.
5.3 F-010 — Conflicting dependency constraints

PASS
 High baseline finding

Directly verified:
Dependency	pyproject.toml	requirements-essential.txt
Flask	>=2.3.0,<3.0.0	'==3.1.2
Werkzeug	>=2.3.0,<3.0.0	'==3.1.5

Pinned evidence: pyproject.toml, L29–32, requirements-essential.txt, L5–11.

Counterexample: CI installing only the essential requirements may succeed while installation using project metadata resolves a different dependency profile.

The replacement correctly identifies inconsistent declarations without asserting that every installation path fails.

EP-005 ownership and reproducible platform-specific dependency qualification remain appropriate. No dependency installation or resolver execution was performed.
5.4 F-011 — Missing Docker clean-checkout input

HOLD
 High baseline finding

The Dockerfile directly contains:
COPY data/ data/


Pinned Dockerfile, L50–56

The replacement acknowledges that the absence of a tracked data/ path is inherited evidence rather than newly reproduced tree evidence.

The problem is therefore a compound claim:
Component	Qualification
Dockerfile requires data/ input	Verified
Exact application tree lacks required input	Not independently verified here
Clean-checkout build fails	Not executed; conditional
Deployment profile is reproducible	Not established

Counterexample: A local build succeeds because an ignored data/ directory exists in the developer's build context, while a pristine checkout lacks that directory.

The reverse is also possible if the documented build process legitimately creates the required input beforehand.

Required correction: Obtain complete pinned tree evidence and inspect the declared build context and .dockerignore. Retain the existing finding metadata while separately identifying the verified and unresolved components of the claim. A subsequent authorized clean build must establish the actual outcome.
5.5 F-014 — Stale architecture and agent documentation

HOLD
 Medium baseline finding

The architectural discrepancy is directly supported.

The historical architecture describes UnitRuntimeManager, including infrastructure/hardware/unit_runtime_manager.py, and refers to app/services/growth.py.

Pinned historical architecture, L36–47, L147–175.

The inspected application implementation instead references shared hardware services and creates controllers through GrowthService.

Pinned GrowthService, L922–1002.

The historical Copilot instructions also refer to development and deployment paths requiring validation.

Pinned Copilot instructions, L19–30.

Counterexample: Both an old compatibility module and a new implementation could coexist. Finding a newer implementation does not establish that every historical path is absent or every associated instruction obsolete.

Required correction: Add a two-sided architectural crosswalk with exact source ranges, identifying each historical claim, current implementation, compatibility status and intended disposition. Do not infer path absence without tree verification.

The evidence supports scoped architectural drift, not blanket invalidation of historical documentation.
5.6 F-015 — Raspberry Pi performance and compatibility

HOLD
 Medium baseline finding

The README explicitly identifies Raspberry Pi 3B+, 4 and 5 as targets.

Pinned README, L65–85

The replacement appropriately retains Unverified classification. A target statement does not establish measured compatibility or performance.

However, the owner column identifies CP3, while the existing remediation plan also assigns F-015 to EP-005.

Pinned remediation plan, L32–34

These responsibilities should be explicitly complementary:
Workstream	Accountability
EP-005	Installation, dependencies, Python/OS/ARM compatibility and reproducible deployment profiles
CP3	Representative workload performance, resource budgets, latency, thermal behavior and recovery
Q	Applicable profile qualification
Owner	Separate deployment authorization

Counterexample: A CP3 benchmark succeeds on a Raspberry Pi 4 using a manually assembled environment. That does not establish a reproducible installation or Pi 3B+ compatibility.

Required correction: Preserve the inherited owner field but add EP-005 as an explicit closure dependency. Define supported model-specific applicability and approved measurable budgets before qualification.
5.7 F-020 — Unreconciled historical branches

HOLD
 Medium baseline finding

The replacement correctly states that branch existence and aggregate tree counts do not establish semantic equivalence.

The consolidated historical record retains branch identity and aggregate comparison information.

Pinned CP0–CP2 consolidation, L15–25.

However, the replacement matrix primarily references the application baseline BACKLOG.md. That is not sufficient direct evidence for the branch tree and ancestry claims.

Counterexample: Two branches have identical aggregate counts of same, changed and unique paths. They may contain entirely different changes, incompatible migrations or different fixes.

The recovery crosswalk explicitly acknowledges that current branch SHA and tree identities were not independently reproduced.

Required correction: Obtain, for each historical branch:
Evidence field	Requirement
Branch identity	Ref name and directly observed HEAD SHA
Tree identity	Exact Git tree SHA
Historical identity	Previously recorded pinned SHA
Relationship	Verified ancestry or absence of common ancestor
Path comparison	Complete path/blob/mode comparison
Semantic disposition	Retain, already incorporated, superseded, unique or unresolved
Preservation	No deletion, force-push or bulk integration

Complete semantic branch reconciliation remains a separate EP-006 activity. The replacement qualification must establish enough primary evidence to support F-020 itself without pretending that reconciliation is complete.
5.8 F-021 — Historical backlog drift

PASS
 Medium baseline finding

The baseline backlog's I-1 entry says that no CI exists.

Pinned BACKLOG.md, L23.

The actual baseline contains GitHub Actions definitions for Ruff, pytest and Bandit.

Pinned CI workflow, L22–56.

This directly establishes at least one material backlog discrepancy.

Counterexample: Treating the presence of CI as proof that every part of I-1 is complete would be incorrect. Required check enforcement remains a separate unresolved issue under F-012.

The replacement criterion appropriately requires item-by-item reconciliation rather than reopening all historical work or closing all partially implemented items.
5.9 F-022 — Production frontend cache configuration

PASS
 Medium baseline finding

Direct source inspection confirms:
flask_app.config["TEMPLATES_AUTO_RELOAD"] = Trueflask_app.jinja_env.auto_reload = Trueflask_app.config["SEND_FILE_MAX_AGE_DEFAULT"] = 0



Pinned app factory, L101–104.

The configuration is verified. Production performance and effective end-to-end caching are not.

Counterexample: A reverse proxy could independently cache static assets despite this Flask configuration. Conversely, an inappropriate caching configuration could expose stale or user-specific content.

CP3 should measure representative response headers, cache behavior, resource consumption and asset freshness. Blanket enabling of caching is not an acceptable closure criterion.

The replacement correctly preserves that distinction.
5.10 F-023 — Shared polling lifecycle ownership

PASS
 High baseline finding

The source evidence is particularly strong.

SensorManagementService, L157–162 constructs a single global polling service.

GrowthService, L946–950 stores that shared instance against a unit ID.

GrowthService, L1054–1067 calls stop_polling() on the stored reference during unit shutdown.
Shared ownership defect demonstrated structurally; cross-unit interruption requires a composed test.
Counterexample: Two units run correctly. Stopping unit A calls the installation-wide poller shutdown while unit B still references that same service.

The EP-002 closure criterion must verify per-unit registration and deregistration without transferring ownership of the shared poller to individual units.

The replacement preserves this architectural responsibility correctly.
5.11 F-024 — Controller subscription disposal gap

PASS
 High baseline finding

The controller subscribes bound methods but does not retain the unsubscribe handles in the inspected subscription method.

ClimateController, L178–217.

EventBus stores the callbacks and returns an unsubscribe closure.

EventBus, L85–107.

The inspected unit shutdown removes controller references without explicitly invoking subscription disposal.

GrowthService, L1054–1088.

Counterexample: Unit A stops and restarts. The old controller remains subscribed while a new controller is registered. Alternatively, previously queued callbacks survive successful unsubscription.

The proposed closure criterion correctly requires both disposal and queued-work invalidation. Unsubscription alone is insufficient.

EP-002, FT-016, FT-031 and FT-043 remain appropriate.
5.12 F-025 — Incomplete container shutdown orchestration

HOLD
 High baseline finding

The replacement's source observations are correct, but the indirect shutdown trace can be strengthened substantially.

The container sets _shutdown_complete=True before completing its shutdown sequence.

Pinned container, L161–213.

The actuator management service has a separate shutdown method that attempts to turn off registered actuators.

Pinned actuator management, L1449–1476.

I additionally retrieved the implementation of GrowthService.shutdown().

Pinned GrowthService, L1883–1900.

It iterates unit IDs and invokes stop_unit_runtime(). It does not inspect that method's Boolean return value before logging that all runtimes have stopped.

The inspected unit shutdown path does not explicitly invoke the separate actuator management shutdown method.

Counterexamples:
1. device_coordinator.stop() raises after _shutdown_complete is set. A subsequent shutdown call returns early, even though later shutdown steps may never have run.
2. stop_unit_runtime() returns False. GrowthService can still log that all runtimes stopped.
3. A component completes software cleanup without obtaining a trustworthy physical outcome. Software shutdown must not be reported as verified physical safety.
Required correction: Incorporate the transitive shutdown anchor, ignored failure return and premature completion marker into the replacement observation and closure criteria.

Preserve EP-002 lifecycle ownership, EP-003F protection/recovery responsibility and applicable EP-004 durable uncertainty requirements.

No claim of actual actuator shutdown failure or unsafe physical state is established by this source analysis.
5.13 F-028 — EventBus saturation and critical delivery

PASS
 Medium baseline finding

The EventBus publishes callbacks through a non-blocking queue operation and catches Full.

Pinned EventBus, L120–148.

The queue behavior is verified. The impact on critical safety delivery remains a Risk, not an experimentally established event.

Counterexample: A saturated telemetry queue drops a callback relevant to a safety decision. If deterministic safety authority depends exclusively on successful delivery through that queue, its operation may be delayed or lost.

A suitable design must ensure that critical protection does not depend exclusively on best-effort EventBus delivery.

Retain EP-002 and CP3 ownership and FT-023, including deliberate saturation, measured safety deadlines, drop instrumentation and positive controls.

Severity should be reassessed if subsequent composition evidence establishes a direct safety-critical dependency. The current replacement does not justify an automatic downgrade or upgrade.
5.14 F-029 — Database context commits on exception

PASS
 High baseline finding

The actual implementation confirms the defect:

Pinned SQLite handler, L201–207.

The connection context yields its connection and calls commit() in finally, including exceptional exits.

Conceptual counterexample, not executed:
with database.connection() as conn:    write_first_record(conn)    raise RuntimeError("Second operation failed")



If the first write belongs to an active transaction and remains pending, the context's finalizer can commit it despite the exception.

The exact effect depends on transaction state and caller behavior; the unconditional commit is nevertheless directly verified.

EP-004 ownership is correct. Closure must qualify transaction nesting, rollback, commit failures, durable admission ordering and callers relying on current behavior.

Simply replacing finally with a rollback statement would not independently establish correctness across every repository and transaction boundary.
5.15 F-030 — Migration and corruption recovery ownership

PASS
 High baseline finding

Direct inspection establishes:
Source	Observation
SQLite handler, L60–114	Initialization runs migrations; errors can be logged without propagation.
L116–129	Corruption handling attempts quarantine and reopens the database.
L150–172	Quarantine failures can produce a None outcome.

Counterexample: Two application processes independently enter initialization and determine that a migration has not yet been applied. Another scenario involves recovering an obsolete database that lacks outstanding operations or quarantine records.

The replacement appropriately does not claim these scenarios were reproduced.

EP-004 ownership and FT-034/041/044 remain appropriate, subject to EP-001 ownership and EP-003D/F recovery contracts.

The critical acceptance invariant is not merely reopening a database. It is establishing that the recovered state remains trustworthy before granting consequential authority.
5.16 F-031 — JSON concurrency and failure semantics

PASS
 Medium baseline finding

The inspected persistent store uses an advisory lockfile and separately locked read and write functions.

Pinned persistent store, L27–108.

Atomic file replacement is present. Whole read-modify-write atomicity is not established by those individual operations.
Lost-update counterexample
Illustrative concurrency scenario. Not an executed test or observed data-loss incident.
Additional concerns supported by the source include load failures returning empty dictionaries and write failures being logged without a typed failure outcome.

The replacement criterion appropriately requires concurrent writer, crash, stale lock, corruption and false-success testing.

Retain Medium severity and EP-004 ownership, pending assessment of every affected consumer and whether any stored state participates in safety authority.
5.17 F-032 — Model registry concurrent writer integrity

HOLD
 High baseline finding

The replacement correctly identifies atomic JSON replacement without demonstrated writer coordination.

However, direct inspection reveals a materially stronger evidence chain than the replacement currently records.

Pinned registry persistence, L181–204:
- Registry writes use a shared .json.tmp path.
- Persistence errors are caught and logged.
- The inspected persistence helper does not return a typed failure result or propagate the caught exception.
Pinned model registration, L310–355 writes model artifacts, modifies registry metadata, calls _save_registry() and returns a version identifier.

Pinned production promotion, L561–602 modifies active model metadata, calls _save_registry() and can return True even when persistence has internally failed.

Counterexample: Model promotion changes in-memory registry metadata, but saving the registry fails. The promotion method returns success. After restart, the disk-backed registry may identify a different active model.

A second scenario involves independently instantiated registry writers replacing each other's metadata or competing for the same temporary file.

Required correction: Extend F-032's replacement observation and acceptance criteria to distinguish:
- Verified persistence error suppression and success-return paths.
- Conditional concurrent writer corruption or lost updates.
- Artifact/metadata consistency and model version uniqueness.
- Durable promotion, rollback and recovery.
- Explicit model eligibility and production activation boundaries.
Retain the existing High severity and Risk classification for the compound concurrency finding, but identify the directly verified source defects separately. No model was loaded, promoted or executed during this review.

CP4 remains the primary owner, with applicable EP-004 persistence contracts as a dependency.

6. EGA-001 — Independent governance amendment qualification
Disposition: HOLD — amendment concept acceptable, adoption mechanism requires correction.

Pinned EVIDENCE-GOVERNANCE-AMENDMENT.md
6.1 Authority and instruction precedence
The existing governance establishes a clear authority hierarchy.
Authority	Pinned evidence
Explicit owner authorization	AGENTS.md, L5–10
Mandatory qualification gates	AGENTS.md, L17–21
Canonical document ownership	guidelines.md, L5–24
Integration requirements	guidelines.md, L40–54
Existing original-report prerequisite	Foundation ExecPlan, L9–11

EGA-001 currently identifies itself as proposed, explicitly preserves existing governance and requires separate acceptance.

That is correct.

However, there is an unresolved distinction between:
1. Owner acceptance of EGA-001 as a prerequisite for G0 integration.
2. EGA-001 becoming canonical repository governance through integration.
3. Future mandatory preservation obligations becoming effective.
6.2 EGA-001 clause-by-clause disposition
Clause	Subject	Verdict
L3	Proposed status and authority limitations	PASS
L7	Narrow substitution of original-report prerequisite	PASS in principle
L9	Replacement eligibility and non-waivable technical evidence	PASS
L11	Amendment acceptance and supersession record	HOLD
L15	Pre-work evidence manifest	PASS
L16	Original results, logs and privacy	PASS
L17	Durable artifact preservation and verification	PASS
L18	Exact-HEAD evidence and integration records	PASS
L19	Post-integration preservation	PASS
L20	Retention and evidence recovery	HOLD
L22	Non-retrospective compliance disclosure	PASS

6.3 REB-R1-01 — Amendment effectiveness and canonical precedence

High
 Blocking

Evidence: EGA-001 L3–11; AGENTS.md L3–9; guidelines.md L5–24 and L48–54; foundation ExecPlan L10.

The amendment permits a separate acceptance record outside the candidate tree. That is appropriate for avoiding self-referential commit hashes.

However, it does not sufficiently specify how that external acceptance resolves the still-present original-report prerequisites across canonical documents, particularly for subsequent agents or reviewers who read the repository without retrieving the PR acceptance record.

Counterexample:

An owner accepts EGA-001 against the exact candidate. One implementation agent consults the amendment and treats the replacement evidence prerequisite as controlling. Another consults the original foundation ExecPlan and determines that complete original reports remain mandatory.

AGENTS.md requires stopping when authorities conflict. The candidate does not sufficiently define the operational reconciliation of those authorities after acceptance.

There is also potential ambiguity about whether accepting the amendment independently makes all its proposed future governance requirements immediately effective, or only substitutes the prerequisite necessary to evaluate G0 integration.

Required correction: Define explicit amendment lifecycle states and their authority.
1. PROPOSED
   Original-report gate remains binding. No substitution or effective new policy.
2. REPLACEMENT QUALIFIED
   Independent exact-HEAD evidence supports replacement sufficiency. No owner acceptance implied.
3. OWNER ACCEPTED — LIMITED GATE SUBSTITUTION
   Only the explicitly enumerated historical-report prerequisite is replaced for the approved candidate.
4. G0 INTEGRATION ELIGIBLE
   All remaining mandatory CI, enforcement, review and integration prerequisites independently satisfied.
5. INTEGRATED / CANONICAL
   Accepted governance and future evidence-preservation obligations become effective as recorded.

The precise state names are a proposed reviewer correction, not an existing approved policy.

The amendment should also identify the exact affected prerequisite in every controlling document, including REMEDIATION.md, rather than relying on broad references to dependent records.

Preserve all historical text. A clearly identified normative supersession mechanism is sufficient; historical reports must not be rewritten.
6.4 Does EGA-001 waive mandatory technical evidence?
Disposition: PASS — subject to the effectiveness correction above.

EGA-001 L9 expressly requires independently qualified source evidence, reviewed severity/classification, ownership, acceptance criteria and resolution of blocking disagreements.

It also explicitly prohibits treating mandatory missing evidence as ordinary residual risk.

That preserves the correct distinction:
Evidence category	Permitted treatment
Unrecoverable original historical report	Explicitly record loss and seek narrowly authorized substitution
Missing source evidence needed to establish a replacement observation	HOLD until resolved
Unresolved baseline runtime defect	May remain OPEN under applicable documented restrictions
Missing mandatory checkpoint evidence	HOLD
Missing required exact-HEAD CI	HOLD
Missing independent final-candidate review	HOLD
Missing applicable physical qualification	NOT QUALIFIED / HOLD

The amendment must never be interpreted as an exception to technical qualification merely because an equivalent historical claim once appeared in a report.
6.5 Proposed future evidence-preservation policy
The new preservation rules are substantially appropriate and represent a useful improvement over chat-dependent evidence retention.

They cover exact revision identity, original artifacts, checksums, provenance, redaction, accountable custody, failed and skipped results, restoration and explicit supersession.

One improvement remains necessary.

REB-R1-07 — Medium: evidence retention and dependency continuity.

EGA-001 L20 establishes minimum retention and retrieval requirements but should explicitly cover evidence referenced by multiple dependent releases, decisions or qualification records.

Counterexample: A release is superseded and its evidence archive is scheduled for disposal. A still-active ADR or downstream safety qualification depends on one of those archived results.

Release supersession alone must not permit deletion of evidence with surviving dependencies.

Require an evidence dependency inventory and accountable disposition before disposal. Where an original contains sensitive material requiring restricted retention or deletion, preserve lawful, sanitized traceability without claiming unavailable evidence is still independently verifiable.

7. Preservation of the D0/R1–R3/Q architecture
Disposition: PASS — architectural preservation.

The replacement commit does not modify the remediation dependency graph, foundation ExecPlan, D0 contracts or qualification profiles.

More importantly, its assigned replacement acceptance criteria do not establish an alternative runtime architecture or grant premature closure authority.

Pinned controlling documents:

REMEDIATION.md, L85–92, D0-CONTRACTS.md, L3–24, qualification profiles, L3–30.
Preserved programme dependency graph
Principal dependency sequence. Independent offline activities remain governed by their applicable profile prerequisites; this is not a blanket prohibition on all offline work before Q.
7.1 Cross-package ownership
The existing architecture continues to distinguish policy ownership, enforcement and evidence ownership.
Responsibility	Accountable package
Installation runtime authority	EP-001
Unit lifecycle and quiescence	EP-002
Final command admission	EP-003A
Typed physical outcomes	EP-003B
Irrigation authorization policy	EP-003C
Resource reservation and quarantine policy	EP-003D
Observation and calibration eligibility	EP-003E
Independent protection and recovery	EP-003F
Atomic persistence and recovery evidence	EP-004
Deployment and platform profiles	EP-005
Governance and historical reconciliation	EP-006
Identity and resource authorization	EP-007

The replacement does not grant EP-004 ownership of authorization policy simply because it implements transactional persistence. Nor does it allow EP-001 ownership acquisition to override unresolved recovery evidence.

These distinctions are necessary to preserve the architectural corrections made during G0.1–G0.3.
7.2 Critical sequencing counterexamples
The preserved architecture correctly rejects the following interpretations:
Incorrect interpretation	Required governing behavior
R1a ownership lock permits ordinary energization	Strict inhibition remains until applicable contracts and minimum recovery are qualified
R1b allows ordinary irrigation because a request was approved	Applicable admission, persistence, resource and recovery prerequisites still apply
R2b closes F-001	Full F-001 closure remains at Q
R3b completes software shutdown and therefore establishes physical safety	Physical outcomes and independent protection require applicable evidence
Q synthetic PASS permits production activation	Deployment and activation are separately qualified and authorized
EGA-001 acceptance permits D0 implementation	Qualified G0 integration and explicit bounded authorization remain necessary

No regression in these architectural boundaries was identified in the replacement delta.

8. Preservation of CP3–CP7 dependencies
The replacement qualification does not establish new programme advancement authority.
Checkpoint	Preserved prerequisites	Disposition
CP3	Qualified measured composition, approved workloads, safe isolated platform prerequisites	Preserved
CP4	Data provenance, artifact trust, isolated evaluation, applicable control-integration qualification	Preserved
CP5	Bounded software baseline, appropriate isolation and repeatable fault qualification	Preserved
CP6	Capability contracts, identity, consent, local independence and separate external-call authority	Preserved
CP7	Explicit scoped dispositions, evidence traceability and mandatory closure requirements	Preserved

Pinned qualification profiles, L21–30.

The following prior architectural review observations remain correctly addressed by the inherited G0.3 documentation within the inspected scope.
Historical review observation	Current documentary assessment
G0.2-AG-01 — Physical qualification authority contradiction	PASS: separately authorized HIL distinguished from documentary and synthetic qualification
G0.2-AG-02 — Profile-specific programme advancement	PASS: activity-specific prerequisites defined
G0.2-AG-03 — Unresolved ADR question classification	PASS: mandatory and demonstrably deferrable questions distinguished

Evidence: Archived G0.2 Reviewer 1, G0.3 correction record.

These are targeted documentary assessments, not a substitute for comprehensive exact-HEAD G0.3 security and integration requalification.

9. ADR lifecycle and authority preservation
Disposition: PASS.

The ADR register continues to identify all 12 decisions as proposed.

Pinned ADR register, L7–28.

The following separation remains intact:
1. Proposed architectural decision
2. Explicit owner-approved design acceptance
3. Bounded implementation authorization
4. Applicable implementation qualification
5. Separate integration approval
6. Deployment qualification and approval
7. Device-specific activation qualification and approval

Accepting a replacement source-evidence basis does not authorize any of these downstream transitions automatically.

I found no evidence that the candidate silently accepts an ADR, closes a finding or replaces the existing edge-first architectural direction.

10. Historical provenance and recovery crosswalk
Disposition: HOLD for original historical provenance.

The candidate correctly distinguishes the replacement technical basis from the original CP0–CP2 reports.

Pinned evidence:
- CP0–CP2 consolidation, L36–42
- Archive provenance manifest
- Recovery crosswalk, L3–15
- Archived G0.2 Reviewer 3, L366–420
10.1 Provenance evidence categories
Evidence	Status
Original CP0–CP2 complete report bytes	Unrecovered
Stable original report references	Not established
Original report checksums	Not established
CP0 22-versus-32 attribution discrepancy	Unresolved
Archived G0.1/G0.2 review text	Present
Fidelity of supplied review attachments to original external exports	Not established
Original evidence recovery response	Not recovered
Replacement source qualification	Newly authored and independently challenged
Historical reviewer verdicts	Preserved in documentary delta

The absence of the raw recovery report also means that the reported 44/44 reconciliations and 82/82 reference validations cannot be credited as independently reproduced results.

The crosswalk appropriately attributes these to prior summary-derived observations.
10.2 ER-01–05 review
Recovery item	Reviewer 1 disposition
ER-01 — Test inventory	HOLD: primary complete-tree enumeration outstanding
ER-02 — Historical branches	HOLD: direct pinned tree, identity and ancestry evidence outstanding
ER-03 — ML leakage	Deferred to assigned Reviewer 3 technical challenge; not independently reproduced in this review
ER-04 — Firmware trust	Deferred to assigned Reviewer 2/3 technical challenge; not independently reproduced in this review
ER-05 — Check enforcement	HOLD: current successful CI evidence absent; effective enforcement not independently established

The replacement must not convert previously reported recovery counts into technical qualification results without primary verification.
10.3 Permanent limitation semantics
I support preserving the provenance limitation permanently as part of the historical record.

However, this must distinguish two statements:

Correct: At the time of this rebaseline, the original reports were unavailable, and replacement evidence was used instead.

Not established: The original reports can never be recovered.

EGA-001 already permits subsequent recovery and reconciliation. A future recovery must add a dated, independently qualified superseding record while preserving the original rebaseline limitation.

This clarification is important for long-term audit accuracy.

11. Formal reviewer findings
The following eight review findings consolidate the required corrections. These identifiers are newly assigned by this review and are not existing foundation findings.
ID	Severity	Review defect	Required disposition
REB-R1-01	High	EGA-001 effectiveness, canonical precedence and acceptance lifecycle underspecified	Correct
REB-R1-02	High	F-011/F-020 primary tree and branch evidence incomplete for compound Verified claims	Obtain primary evidence
REB-R1-03	High	F-025/F-032 omit directly supportable shutdown and persistence failure semantics	Correct
REB-R1-04	Medium	F-009 closure criterion does not explicitly cover missing repository injection in actual composition	Correct
REB-R1-05	Medium	F-014 lacks precise two-sided architectural discrepancy reconciliation	Correct
REB-R1-06	Medium	F-015 closure dependency on EP-005 insufficiently explicit	Correct
REB-R1-07	Medium	Evidence retention does not explicitly account for all surviving dependent records	Correct
REB-R1-08	Low	Minor reference duplication and historical limitation terminology	Clarify

Severity rationale
The High observations affect either the mandatory qualification authority boundary or the sufficiency of evidence for consequential runtime and deployment findings.

The Medium observations concern technical completeness, cross-package accountability and durable evidence lifecycle.

The Low observation concerns documentary precision rather than a demonstrated change in authority. For example, F-025 repeats its container shutdown anchor where the newly identified transitive GrowthService shutdown anchor would provide additional useful evidence.

None of these observations warrants changing the existing foundation register automatically.

12. Integration eligibility and CI
I queried the exact candidate HEAD for combined commit status and associated PR-triggered workflow runs.
Evidence	Directly observed result
Candidate combined status entries	0
Returned PR-triggered workflow runs	0
PR state	Open
Draft	Yes
Merged	No
GitHub mergeable flag	True
Effective required-check enforcement	Not independently established

PR #3 · Candidate commit checks

The workflow query's returned scope is limited; an empty result is not exhaustive proof that GitHub has never performed any check associated with the revision. It is sufficient to establish that successful mandatory CI was not demonstrated through the inspected evidence.

GitHub mergeability is not governance integration eligibility.
Integration prerequisite	Disposition
Authorized application baseline consistency	PASS
Candidate PR HEAD consistency	PASS
Documentation-only change scope	PASS
Direct candidate tree SHA verification	HOLD
Finding register structural continuity	PASS
Replacement technical evidence sufficiency	HOLD
Historical-report gate substitution	HOLD — proposed
All applicable independent final-HEAD reviews	HOLD
Successful applicable exact-HEAD CI	HOLD
Effective check enforcement	HOLD
Explicit separate integration approval	Outstanding
Integration eligibility	HOLD

No prior CI or review verdict is inherited by this candidate.

13. Required requalification conditions
Requalification tracker

0/13


[ ] REB-R1-01 — Define amendment effectiveness, exact supersession scope and canonical authority.

[ ] REB-R1-02 — Obtain primary candidate/application tree and historical branch evidence.

[ ] REB-R1-03 — Strengthen F-025 and F-032 failure-path observations and closure criteria.

[ ] REB-R1-04 — Add F-009 actual composition and repository-injection evidence.

[ ] REB-R1-05 — Complete F-014 architectural discrepancy crosswalk.

[ ] REB-R1-06 — Make F-015 EP-005/CP3 dependencies explicit.

[ ] REB-R1-07 — Add dependency-aware evidence retention and disposal requirements.

[ ] REB-R1-08 — Correct duplicated anchors and clarify permanent historical limitations.

[ ] Identity — Verify the corrected exact candidate SHA, tree and parent.

[ ] Independent review — Obtain all three independent final-candidate qualifications.

[ ] EGA-001 — Record separate explicit owner acceptance of the precisely bounded amendment.

[ ] CI and enforcement — Establish successful applicable exact-HEAD CI and effective required-check enforcement.

[ ] Integration — Obtain separate explicit owner integration authorization.


 Copy checklistManual tracking only. Selecting an item does not create qualification evidence, change GitHub or grant approval.
Any correction that changes HEAD requires applicable fresh qualification evidence and independent review against the resulting revision.

14. Review limitations and operations performed
Completed
Direct read-only GitHub retrieval and inspection established the candidate and PR HEAD, parent-to-candidate comparison, application-to-candidate comparison, documentary change scope, 44-row field continuity, assigned source observations, controlling architecture and governance clauses, relevant archived reviewer observations and returned CI metadata.

I inspected additional source paths for calibration composition, shared polling, transitive shutdown and model promotion rather than relying solely on the author's replacement descriptions.
Limitations and blockers
Limitation	Consequence
Complete Git tree metadata was not exposed through the available read operations	Declared tree SHA and complete tree inventory not independently certified
Original report artifacts and raw recovery response unavailable	Historical provenance remains unqualified
Historical branch tree and ancestry comparison not independently reproduced	F-020 and ER-02 remain HOLD
Complete historical path inventory unavailable	F-011 and aspects of F-014 remain HOLD
Archived review bytes not independently hashed against original supplied attachments	No new byte-level provenance certification
No local repository or worktree inspection	Local state and environment not qualified
No exhaustive reading of every historical review or all 44 findings' secondary anchors	This is the assigned Reviewer 1 scope, not programme-wide evidence certification
No effective administrator-level enforcement audit	Integration enforcement remains HOLD
No runtime, synthetic, concurrency, build or hardware tests	Source-derived counterexamples remain unexecuted

The proposed review identifiers, severity aggregation, EGA-001 lifecycle states and strengthened acceptance criteria are independent reviewer judgments. They are not owner-approved governance changes.
Operations not performed
No repository files were modified. No commits, branches, tags or other Git resources were created, altered or deleted. No GitHub review was submitted. No CI was dispatched. No settings were changed. No live private data, physical devices, deployment or production environment was accessed. No merge was performed.

15. Final acceptance record
SYSGROW-EVIDENCE-REBASELINE-001 / Reviewer 1HOLD

Candidate revision and scope

PASS*

Replacement documentation qualification

HOLD

Architecture preservation

PASS

Historical provenance

HOLD

EGA-001 acceptance readiness

HOLD

Integration eligibility

HOLD

Production safety

NOT QUALIFIED


Open foundation findings44 / 44

Proposed ADRs12 / 12

Critical foundation findings4

Fault-test designs executed here0 / 45


* Commit and PR revision consistency and documentary delta passed; direct tree identity verification remains HOLD.
Reviewer recommendation
Continue with the replacement evidence strategy rather than indefinitely depending on unavailable historical conversation exports. The strategy is compatible with the existing architecture and provides a defensible way to establish a new technical qualification basis.

However, do not accept EGA-001 against the current candidate HEAD. Resolve the eight review observations, obtain the missing primary evidence and independently requalify the corrected candidate.

There is no justification from this review for redesigning the D0/R1–R3/Q architecture, reopening accepted historical corrections without evidence, reducing existing finding severities or relaxing mandatory safety gates.

The remaining work concerns evidence integrity, precise governance authority and technical qualification completeness.

Final verdict: HOLD — 0 Critical, 3 High, 4 Medium, 1 Low reviewer observations. All 44 foundation findings remain OPEN. No ADR acceptance, integration, deployment or physical activation authorized.