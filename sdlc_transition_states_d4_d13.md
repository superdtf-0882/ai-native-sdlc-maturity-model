# AI-Native SDLC Maturity Model
## Transition-State Notes for D4–D13

**Version 0.2 — 2026-07-26**
**Applies to:** AI-Native SDLC Maturity Model v1.2.0
**Scope:** D4–D13 only. D1–D3 inherit their transition notes from `shared_intelligence_layer.md`.

**PROVENANCE:** v0.1 was reviewed by Deputy TOGAF dimension-by-dimension
against `ai_native_sdlc_maturity_model.md` at commit `4730189` (tag
`v1.2.0`) -- prose and verification clause both, not just plausibility.
Four sections were revised as a result (D4 C→D, D5 A→B, D5 C→D, D6
C→D); everything else is byte-identical to v0.1. `source_matrix_version`
below is the checkable claim, same discipline as `short_form.yml`: run
`git diff v1.2.0 HEAD -- ai_native_sdlc_maturity_model.md` from this
repo's root -- an empty diff means these notes are still current
against the locked matrix; any output means re-verification is needed
before this file is trusted.

`source_matrix_version: "1.2.0"`
`source_matrix_commit: "4730189dbcb975d3c200d0e6d9f57ae4f39eb1a1"`

These notes are written for progressive disclosure in the whole-model matrix:

- Levels **A–D** show the transition required to reach the next level.
- Level **E** shows sustainment rather than a further maturity step.
- Each transition describes a change in operating capability, not merely the adoption of another AI tool.
- Verification statements are practical tests of whether the destination state has actually been reached.

---

# D4. Requirements management
## Specification quality & traceability

### A → B — Establish a shared system of record

Move specifications out of disconnected tickets and documents into one shared system of record. Define a minimum structure for every material requirement: source, intended user or buyer context, expected behavior, acceptance conditions, supporting design material, and delivery state. Preserve the path from originating need through implementation.

**Verification:** A Product, Engineering, QA, or Release participant can locate the current requirement, its supporting evidence, and its delivery status without asking the original author.

### B → C — Make the requirement context cross-functional

Extend the shared record across Product, Engineering, QA, and Release Management. Connect relevant buyer and user personas from D2, establish ownership for changes, and preserve visible history when meaning changes. The destination is shared interpretation, not yet generation-grade precision.

**Verification:** All participating functions use the same current requirement and persona context, and a material change becomes visible to each without manual redistribution.

### C → D — Raise specifications to generation quality

Introduce the precision required for routine specifications to generate code, prototypes, or tests with minimal additional interpretation. Add explicit schemas, edge cases, constraints, testable outcomes, and unambiguous acceptance conditions. Generated artifacts inherit traceability from the specification automatically. The specification remains the required starting point at this level — generating or updating a specification from a prototype or test is not yet supported; that reversal is Level E's own step, not this one's.

**Verification:** A well-formed routine specification repeatedly generates at least one downstream artifact, and that artifact remains automatically traceable to its source.

### D → E — Make generation sequence-agnostic

Support the reverse direction as well as forward generation: a prototype or test may create or update the governing specification. Define conflict resolution when specification, prototype, test, and implementation imply different meanings, and preserve provenance through every update.

**Verification:** Work can begin from a specification, prototype, or test and produce a coherent, traceable artifact set without a manual translation project.

### Level E sustainment

Continuously test artifact equivalence and conflict resolution. Sequence-agnostic generation must not permit the specification, prototype, test, and implementation to drift into parallel meanings.

---

# D5. Prototyping & the prototype-to-code boundary

### A → B — Make the boundary explicit

Label prototypes as non-production by default and define where they may run. Establish a shared expectation that exploratory or generated code does not become production code merely because it appears to work. Name the categories of carry-forward concern that will eventually matter — architecture, security, verification, maintainability, and data handling — without yet evaluating any given prototype against them; that formal evaluation is Level C's own gate, not this one's.

**Verification:** A prototype cannot enter the production path accidentally or through ambiguity about its status, though no defined checklist or gate yet exists to evaluate it against.

### B → C — Create a formal disposition decision

Establish an explicit prototype-to-production gate. Define the evidence required to choose among rewrite, partial reuse, carry-forward, and discard-and-rebuild, including architectural fit from D6, verification coverage from D7, and security implications from D11. Record the decision and rationale.

**Verification:** Every prototype contributing code to production has a visible disposition decision against defined criteria.

### C → D — Apply production criteria during prototyping

Use the Level C decision criteria while the prototype is being built rather than only afterward. Identify the prototype class in advance—disposable learning artifact, partial-reuse candidate, or production-viable experiment—and apply relevant architectural and verification constraints from the beginning. The carry-forward decision itself should become faster and less all-or-nothing than Level C's binary rewrite-or-discard call, since most of the evidence needed to decide is now available before the decision point rather than only after it.

**Verification:** Teams can state before construction what would make the prototype reusable, and post-prototype review rarely discovers basic production requirements for the first time. The carry-forward decision is measurably quicker to reach than at Level C, and fewer decisions land as pure discard-or-full-rewrite.

### D → E — Fuse specification, prototype, and test

Produce specification, prototype, and test as one governed motion with D4-E and D7-E. Permit any of the three to initiate the work while preserving common intent, traceability, architecture, and verification. Make both carry-forward and discard low-cost outcomes.

**Verification:** A prototype can be discarded without discarding the validated understanding around it, or carried forward without reconstructing its specification and tests.

### Level E sustainment

Preserve the explicit disposition decision even when it becomes nearly instantaneous. Low-cost carry-forward must not turn every prototype into production code by default.

---

# D6. Architecture governance

### A → B — Externalize architectural judgment

Document the architectural standards and design judgment currently held in reviewer memory. Capture recurring decisions, constraints, preferred and prohibited patterns, rationale, and reference examples. Assign ownership for maintaining the record.

**Verification:** A capable engineer or agent unfamiliar with the codebase can locate the governing standard and understand the reason behind its most important constraints.

### B → C — Encode critical architectural rules

Select the most common and consequential violations and encode them as deterministic controls: linters, structural tests, dependency rules, schema validation, or CI gates. Retain manual review for judgment that cannot yet be encoded.

**Verification:** The encoded controls prevent or flag a defined set of critical violations consistently across human- and agent-generated changes.

### C → D — Make the rules usable during generation

This is a change in *when* enforcement happens, not primarily how much of it exists — Level C's gates catch violations after code is written; Level D requires the same rules to be readable and applicable by an agent before and during generation, so violations are avoided rather than caught and sent back. Convert encoded checks into constraints agents consume as input to generation itself, not just as a check afterward. Expanding coverage where repeated manual findings reveal missing rules is worth doing alongside this shift, but it doesn't substitute for it — comprehensive after-the-fact coverage is still Level C if agents never read the rules before generating.

**Verification:** Agents routinely produce compliant changes on the first pass because they consumed the rules before generation — not because a larger after-the-fact gate caught fewer violations.

### D → E — Let agents propose evolution of the standard

Create a governed mechanism for agents to propose additions or changes to the encoded standard. Each proposal identifies the uncovered or obstructive pattern, supplies evidence and examples, and recommends an enforceable rule or remediation. Human architectural authority accepts, rejects, or revises the proposal.

**Verification:** Repeated novel findings or rule friction produce reviewable, versioned improvements to the standard, with a visible record of why the standard changed.

### Level E sustainment

Continuously verify that agent-proposed rules improve architectural coherence rather than merely optimizing for easier generation. Architectural taste remains a human-governed capability.

---

# D7. Test-driven development
## Specification-driven verification

### A → B — Move tests before implementation

Establish a test-first workflow for defined classes of work. Require expected behavior and failure conditions before code is written, while allowing the specification and tests to remain separately authored.

**Verification:** For the targeted work classes, implementation begins against a pre-existing test rather than tests being written to describe completed code.

### B → C — Derive tests directly from specifications

Define a repeatable method that converts D4 specifications into tests. Specify which requirement elements generate which test types, how unsupported or ambiguous cases are surfaced, and who reviews generated tests.

**Verification:** Re-running the method against the same well-formed specification produces materially equivalent tests without routine manual reinterpretation.

### C → D — Generate tests during specification authoring

Generate corresponding tests as the specification is written. Use them to expose missing edge cases, undefined states, contradictory acceptance conditions, and other ambiguities while meaning is still being formed.

**Verification:** Specification authors routinely revise requirements in response to test-generation feedback before implementation begins.

### D → E — Fuse specification, test, and prototype

Combine specification authoring, test generation, and prototyping into one governed, sequence-agnostic motion with D4-E and D5-E. Ensure that verification coverage scales with generation volume rather than becoming a downstream human bottleneck.

**Verification:** Whether work begins from a specification, prototype, or test, the corresponding verification set is created or updated automatically and remains aligned.

### Level E sustainment

Continuously test whether generated verification still measures intended behavior rather than merely confirming the implementation produced alongside it.

---

# D8. Code verification & review

### A → B — Put deterministic gates before human review

Run linters, static analysis, secret detection, basic CI, and other repeatable checks on all generated and human-written code before human review. Retain human review for correctness, design, maintainability, security judgment, and alignment with intent.

**Verification:** Code cannot reach human review or merge while failing the agreed deterministic gates.

### B → C — Allocate review by risk

Define change-risk tiers using factors such as blast radius, data sensitivity, novelty, reversibility, architectural significance, and security consequence. Permit routine low-risk changes to pass with automated gates, while routing higher-risk or novel changes to human review.

**Verification:** Review effort is visibly concentrated according to defined risk rather than applied uniformly or skipped under volume pressure.

### C → D — Add structurally independent AI review

Introduce an AI review layer independent from the agent or model that generated the code. Review correctness, security, performance, architecture, maintainability, and intent in parallel; preserve the evidence behind findings; and route high-severity findings and high-risk changes to humans.

**Verification:** Independent review identifies material issues before human review, and humans can inspect the basis and severity of each finding.

### D → E — Calibrate the review system against outcomes

Track confirmed findings, dismissed findings, escaped defects, false positives, false negatives, and the accuracy of risk-tier assignments. Use those outcomes to adjust reviewer instructions, rules, severity thresholds, and human-review allocation.

**Verification:** The organization can show how observed review outcomes changed thresholds, criteria, or reviewer behavior.

### Level E sustainment

Keep the independent reviewer under continuous evaluation. A review layer that is no longer calibrated becomes another unchecked generator of confidence.

---

# D9. Environment management

### A → B — Establish standard environment separation

Create standard environment classes such as development, QA, staging, and production, with documented purpose, access, ownership, and promotion paths. Separate development and testing from production even if provisioning remains manual.

**Verification:** Teams no longer develop against one shared mutable environment or production by default.

### B → C — Define environments as code

Capture infrastructure, configuration, dependencies, secrets interfaces, and policy in repeatable, versioned definitions. Eliminate known parity gaps and govern environment changes through the same change discipline as application code.

**Verification:** Rebuilding an environment from the governed definition produces a materially equivalent environment without undocumented manual configuration.

### C → D — Make environments on-demand and ephemeral

Create templates and human-triggered lifecycle workflows. A pull request, command, or approved workflow provisions an isolated environment from the governed definition and tears it down predictably.

**Verification:** A team member can create and remove an isolated environment through one standard action without infrastructure-specialist intervention.

### D → E — Delegate environment lifecycle to agents

Allow agents to determine when an environment is needed, select the correct governed template, provision it within policy and quota, verify readiness, and remove it when the work completes or expires. Preserve attribution, exception handling, and human oversight.

**Verification:** Routine environment lifecycle occurs without standing human maintenance, while every environment remains attributable and reconstructable.

### Level E sustainment

Continuously test policy, quota, cleanup, access, and cost controls. Autonomous provisioning must remain bounded stewardship, not unmanaged infrastructure creation.

---

# D10. Release discipline

### A → B — Decouple releases from the sprint calendar

Permit validated changes to release outside fixed sprint or planning boundaries. Automate the minimum test gates required before release while retaining manual approval and communication.

**Verification:** A release can occur outside the fixed cadence when the automated tests pass and a human approves it.

### B → C — Trigger release from validated change

Deploy from commits or changes that pass the automated gates rather than from the calendar. Automate deployment and rollback based on deterministic health checks, while keeping human oversight for policy changes and material exceptions.

**Verification:** A qualifying change can reach production without a manually assembled release event, and a failed health check can restore the prior state automatically.

### C → D — Make on-demand release compliant by construction

Automate pre-deployment approval, compliance checks, audit evidence, and rollback under governed policy. Define which conditions permit release, block release, or require a named exception. Normalize rollback as a tested primary recovery path.

**Verification:** On-demand releases carry automatically assembled compliance evidence, and rollback works as a practiced response rather than an emergency improvisation.

### D → E — Extend release judgment into production

Use progressive delivery and live quality gates to decide whether a release should expand, hold, or roll back based on actual behavior. Include relevant measures such as error budgets, anomaly signals, evidence coverage, and other production-quality indicators.

**Verification:** A release can be expanded, constrained, or reversed automatically from live evidence while preserving its decision and audit trail.

### Level E sustainment

Continuously recalibrate live quality gates. Production evidence should govern exposure without allowing noisy or poorly understood signals to create release instability.

---

# D11. Security & compliance

> **Draft caution:** The underlying D11 maturity definition remains marked for further research. These transitions operationalize the current ladder but should inherit that same provisional status.

### A → B — Contain agent execution

Introduce sandboxing, filesystem and network restrictions, pre-execution checks for dangerous operations, and deterministic scanning for generated artifacts. Define the minimum actions an agent may perform and deny unrestricted use of shared human environments.

**Verification:** An agent cannot perform a destructive or unauthorized filesystem, shell, or network action merely because the initiating human could.

### B → C — Give agent activity distinct identity and provenance

Use per-agent or per-session credentials and associate each agent-authored change with the initiating human and session. Require this provenance in the change path, and add baseline integrity validation for shared memory or context.

**Verification:** Every material agent action is attributable to a specific agent session and initiating human, and shared context has inspectable provenance.

### C → D — Make controls centrally enforced and non-bypassable

Replace individually bypassable controls with mandatory gates and a named, logged exception process. Inventory skills, plugins, MCP servers, and other agent tooling as supply-chain components subject to approval and scanning. Automate audit-evidence assembly.

**Verification:** An individual cannot silently bypass required controls, and every exception identifies its authority, rationale, scope, and duration.

### D → E — Enforce policy at the point of action

Apply least privilege, runtime authorization, behavior guardrails, and real-time termination capability during agent execution. Actively monitor shared memory and context for injected, poisoned, anomalous, or unauthorized content.

**Verification:** The organization can constrain or terminate unsafe behavior while it is occurring and can detect active context-integrity threats.

### Level E sustainment

Exercise kill switches, exception paths, context-integrity controls, and least-privilege boundaries regularly. Runtime enforcement that is not tested is only documented intent.

---

# D12. Instrumentation & observability

### A → B — Retain build-time generation traces

Capture enough of D4–D8 generation activity to investigate why a deterministic artifact was produced: agent or model identity, relevant inputs and outputs, timing, tool activity, and artifact lineage. Begin with workflows where failure is frequent or consequential.

**Verification:** When generated output fails, the team can inspect the relevant generation record instead of relying on memory or recreating the session.

### B → C — Turn traces into systematic evaluation

Standardize retention and use traces to identify recurring failure patterns rather than merely debug isolated incidents. Define failure categories, quality measures, and review practices, and feed findings back into specification, generation, architecture, testing, and review.

**Verification:** Repeated generation failures produce measurable upstream changes, and the organization can show the pattern that justified each change.

### C → D — Identify and observe runtime non-determinism

Classify every place where AI participates in runtime decisions within the delivery system, such as environment provisioning, release gating, or rollback. Instrument and evaluate those surfaces separately from build-time generation, and distinguish them from any AI behavior inside the shipped product.

**Verification:** The organization can enumerate its build-time, delivery-runtime, and product-runtime AI surfaces and show the tracing and evaluation applied to each.

### D → E — Make observability directly usable by humans and agents

Expose build-time traces, delivery-runtime traces, production telemetry, decisions, and plans through governed structures available to both humans and agents. Connect observed behavior back to upstream dimensions, including the Shared Intelligence Layer.

**Verification:** A material production or delivery signal can be traced to the relevant upstream decision and enter the governed feedback path without manual evidence reconstruction.

### Level E sustainment

Continuously reassess where non-determinism lives as the delivery system evolves. Observability architecture must change when AI crosses a new build-time, sanction/runtime, or product-runtime boundary.

---

# D13. Feedback loop velocity

### A → B — Make the end-to-end cycle measurable

Define the start and end points of the response cycle and measure them retrospectively for major releases, incidents, failures, or market responses. Preserve timestamps and handoffs well enough to reconstruct elapsed time.

**Verification:** The organization can calculate how long a completed response took from originating signal to shipped change and identify the major handoffs involved.

### B → C — Measure continuously by stage and handoff

Instrument the full cycle across D1–D12 and establish a standing view of cycle time by stage and handoff. Use consistent definitions so the organization can identify which current handoff dominates total elapsed time.

**Verification:** At any point, the organization can name the dominant contributor to end-to-end cycle time using current evidence rather than retrospective opinion.

### C → D — Treat bottleneck removal as normal priority work

When D13 identifies the dominant delay, treat the relevant dimension’s next maturity step as comparable to feature work. Assign ownership, investment, and an expected cycle-time effect, then verify whether the bottleneck moved or merely changed form.

**Verification:** At least one identified handoff constraint has been funded and improved through the normal prioritization system with before-and-after evidence.

### D → E — Compress the complete closed loop

Optimize the full cycle rather than isolated stages. Ensure a market, user, incident, failure, or outcome signal can be observed, interpreted, returned to the appropriate upstream model or intent, reprioritized through proper authority, delivered, and observed again. Repeatedly remove whichever handoff currently dominates.

**Verification:** The organization demonstrates repeated governed signal-to-response cycles operating on a days-not-months cadence, including upstream reconsideration where warranted.

### Level E sustainment

Protect quality, evidence, authority, and intent while compressing time. The loop is not mature if speed is achieved by bypassing the very gates that make the response trustworthy.

---

# Cross-dimension boundary checks

## D4 / D5 / D7

- D4 governs specification quality and traceability.
- D5 governs the prototype-to-production disposition.
- D7 governs verification derived from intended behavior.
- Their Level E convergence is one governed motion, not the disappearance of their distinct concerns.

## D6 / D8

- D6 prevents and remediates architectural nonconformance.
- D8 evaluates broader correctness, security, maintainability, performance, and alignment with intent.
- Encoded architecture rules do not eliminate the need for risk-tiered review.

## D8 / D11

- D8 reviews code and artifacts.
- D11 contains agent execution and governs agent identity, tooling, runtime action, and context integrity.
- Strong code review does not make unrestricted agent execution safe.

## D9 / D10

- D9 supplies the environments through which code moves.
- D10 governs whether and how validated changes advance into production.
- Self-provisioning environments do not imply autonomous release authority.

## D12 / D13

- D12 supplies the evidence of the feedback return.
- D13 measures and compresses the time required for that evidence to change understanding, priority, and shipped behavior.

> **D12 makes the loop observable. D13 makes the loop competitive.**
