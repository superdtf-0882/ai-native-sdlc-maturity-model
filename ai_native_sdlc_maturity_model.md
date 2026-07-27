# AI-Native SDLC Maturity Model — Matrix

**Version 1.2.0 — 2026-07-23** (D1–D3 extracted to `shared_intelligence_layer.md`, the new canonical, shared-with-PDLC source for those three dimensions; this matrix inherits them by reference. D4–D13 and the Pre-AI/Exempt mechanics are unchanged from v1.1.0 — see `CHANGELOG.md`). **No version bump 2026-07-27:** D4–D13's transition and verification notes (previously a separate companion, `sdlc_transition_states_d4_d13.md`) and the family-wide maturity-level names (Nascent/Modeled/Continuous/Integral/Telemetric) are now folded directly into this document — consolidation and presentation only, no change to any dimension's maturity content. See `CHANGELOG.md`.

This is the full A–E maturity matrix for all 13 dimensions (D1–D3 by reference, D4–D13 in full below), readable in-browser and directly usable as input to AI tools. **This markdown document is the source of truth for D4–D13** -- `ai_native_sdlc_maturity_model.xlsx` is a derived distribution rendering of it; if the two ever diverge, this document is authoritative and the spreadsheet should be regenerated. D1–D3 are sourced from `shared_intelligence_layer.md`, not this file.

For the design principles, handoff structure, research finding, and open items behind this matrix, see `README.md`. For the diagram of how these 13 dimensions hand off to each other, see `sdlc_handoff_diagram.png` / `sdlc_handoff_diagram.html`.

---

## How to read this matrix

Each dimension below has a definition followed by a five-level maturity ladder (A through E). Levels describe **realistically adjacent states** -- each step up implies a roughly costable set of changes, not "more AI, more thoroughly." A given level is not inherently good or bad; it is appropriate or inappropriate for an organization's size, regulatory context, and risk tolerance (see Design Principle 3 in the working framework document).

Dimensions are independently scored -- an organization can be advanced in one dimension and nascent in another. See the working framework document for how dimensions hand off to, constrain, and converge with each other.

For D4–D13, each level is followed by the transition required to reach the next level and a verification statement -- a practical test of whether the destination state has actually been reached, not just claimed. Level E is followed by a sustainment note instead of a further transition, since there is no Level F: at the top of the ladder, the work shifts from climbing to keeping the capability from quietly regressing.

### Maturity-level names

The five letters A–E carry a family-wide name, identical across every dimension and every model in this family (SDLC, and PDLC/Prioritization once their own repos exist), used as column headers wherever the matrix is rendered:

| Letter | Name | In one line |
|---|---|---|
| A | **Nascent** | Ad hoc and inconsistent -- nobody has yet defined what "good" looks like here. |
| B | **Modeled** | A real, deliberate method exists, but it's manual and owned by one person or function. |
| C | **Continuous** | The method runs constantly on its own cadence, still narrowly owned but always on. |
| D | **Integral** | The capability is load-bearing and shared beyond its original owner -- removing it would break something real. |
| E | **Telemetric** | A continuous two-way loop: signal flows in, action flows back out, close to real time. |

These names describe a general shape of maturity, not this dimension's own specific content -- read each level's own text below for what that shape means concretely at D4, D5, and so on. Locked 2026-07-24; full generic definitions at `briefs/2026-07-25-model-data-architecture/01a-maturity-column-definitions.md` in the governing corpus.

---

### Pre-AI — The Threshold State

**Pre-AI** designates a dimension in which an organization has not
yet adopted AI-assisted practices of any kind. It is a threshold
position, not a maturity level: it sits outside the A–E scale and
carries no letter.

An organization scores Pre-AI on a dimension when the activities of
that dimension are performed — possibly with great discipline — using
entirely pre-AI methods and tooling.

**Pre-AI is not an assessment of general SDLC maturity.** A shop with
rigorous CMMI-style discipline, comprehensive CI/CD automation, and
mature release engineering — but no AI tooling — scores Pre-AI on the
relevant dimensions exactly as a shop with none of that discipline
does. This is deliberate: the model measures AI-native maturity, and
general SDLC excellence is already well measured by existing
frameworks. What existing discipline determines is not the starting
*level* but the transition *velocity* — see below.

**Using Pre-AI as an on-ramp.** Organizations at the beginning of an
AI transformation can adopt this model directly from the threshold:
Pre-AI names the starting position honestly, and Level A becomes the
first milestone of adoption for any dimension, not a judgment of
failure. Dimensional focus applies from the first step — an
organization moves one or two dimensions from Pre-AI to A deliberately,
rather than attempting broad simultaneous adoption.

**Transition velocity.** Existing engineering discipline is
transferable substrate. An organization with mature automation,
strong requirements traceability, or rigorous release gates will
typically cross levels faster than an organization without them —
the discipline transfers; the tooling changes. Assessments of Pre-AI
dimensions may optionally carry a **readiness note** recording the
non-AI maturity that predicts transition speed. The readiness note
is narrative, not a score.

---

### Exempt — The Governed Stance

**Exempt** designates a dimension that an organization has
deliberately excluded from AI adoption as a matter of governed
policy. It is a stance, not a state: where Pre-AI describes a
position an organization intends to move from, Exempt records a
decision an organization has made and stands behind.

**An Exempt designation is valid only when it cites a governing
constraint.** Acceptable constraint sources:

- **Regulatory** — a law, regulation, or supervisory requirement
  that prohibits or materially restricts AI use in the dimension's
  activities
- **Contractual** — a client, partner, or certification obligation
  with the same effect
- **Corporate policy** — a documented, owned internal policy decision
  (with named authority and review date), where the organization has
  weighed AI adoption and formally declined it for this dimension

An exemption without a citable constraint is not Exempt — it is
Pre-AI. The citation requirement is what distinguishes a governed
architectural decision from an unexamined default. Organizations
practicing formal enterprise architecture will recognize this as
constraint governance: the exemption is an architecture decision,
recorded with its rationale, owner, and review trigger.

**Exempt dimensions and overall maturity.** An Exempt dimension is
excluded from aggregate maturity calculations rather than scored as
a floor value. An organization with eleven dimensions at C and two
legitimately Exempt is a mature AI-native organization with a
governed boundary — not a shop dragged down by two failing scores.
Assessment renderings must, however, always show Exempt dimensions
visibly: an exemption is part of the organization's architecture,
not an omission from it.

**Exemptions are reviewable.** Every Exempt designation carries a
review trigger — at minimum, re-validation when the cited constraint
changes (regulation amended, contract renewed, policy revisited).
A lapsed constraint converts the dimension to Pre-AI at the next
assessment.

---

### Assessment values

**Legal score values per dimension:** `Pre-AI` · `A` · `B` · `C` ·
`D` · `E` · `Exempt(constraint-ref)`

- `Exempt` is invalid without a constraint reference. The reference
  points to the organization's own constraint record (in an EA OKF
  practice: a `constraint_or_principle` corpus ID; elsewhere: a named
  policy/regulation citation).
- Pre-AI dimensions may carry an optional `readiness_note` (narrative).
- Exempt dimensions carry a `review_trigger` (date or event).

---

## D1–D3. Shared Intelligence Layer

D1 (Market discovery & definition), D2 (Buyer & user persona development), and D3 (Positioning & competitive intelligence) are inherited by reference from `shared_intelligence_layer.md` (`STD-SHARED-INTELLIGENCE` v1.0.0), this repo's own canonical source for these three dimensions, shared with the AI-Native PDLC Maturity Model. This matrix no longer maintains its own copy of D1–D3 — see that document for full definitions, transitions, and the Level E convergence rule.

Ratified 2026-07-23 following a reconciliation between this matrix's own predecessor D1–D3 text (preserved verbatim, not current authority, at `d1-d3-superseded-v1.1.0.md`) and the Shared Intelligence Layer candidate. Fourteen of fifteen maturity cells carried forward unchanged or with clarification only; one real maturity-state revision landed at D2-B (see `shared_intelligence_layer.md`'s own reconciliation record for the full disposition).

---

## D4. Requirements management (specification quality & traceability)

*The capability to author precise, testable, machine-actionable specifications with full traceability from source through delivery, such that specification quality directly gates generation quality.*

**Level A — Nascent**

Specifications are written informally (tickets, docs) with no consistent structure, and traceability from source to delivery is manual or absent.

**Transition A → B — Establish a shared system of record**

Move specifications out of disconnected tickets and documents into one shared system of record. Define a minimum structure for every material requirement: source, intended user or buyer context, expected behavior, acceptance conditions, supporting design material, and delivery state. Preserve the path from originating need through implementation.

**Verification:** A Product, Engineering, QA, or Release participant can locate the current requirement, its supporting evidence, and its delivery status without asking the original author.

**Level B — Modeled**

Specifications are captured in a shared system of record with traceability from source to delivery. Relevant teams have shared access. Drawings, UX designs, wireframes, and functionality matrices are found in or linked to the system of record.

**Transition B → C — Make the requirement context cross-functional**

Extend the shared record across Product, Engineering, QA, and Release Management. Connect relevant buyer and user personas from D2, establish ownership for changes, and preserve visible history when meaning changes. The destination is shared interpretation, not yet generation-grade precision.

**Verification:** All participating functions use the same current requirement and persona context, and a material change becomes visible to each without manual redistribution.

**Level C — Continuous**

The shared system of record (per Level B) extends to cross-functional access -- Product, Engineering, QA, and Release Management all have shared access, and relevant user personas (per D2) are accessible to these teams within the same system.

**Transition C → D — Raise specifications to generation quality**

Introduce the precision required for routine specifications to generate code, prototypes, or tests with minimal additional interpretation. Add explicit schemas, edge cases, constraints, testable outcomes, and unambiguous acceptance conditions. Generated artifacts inherit traceability from the specification automatically. The specification remains the required starting point at this level -- generating or updating a specification from a prototype or test is not yet supported; that reversal is Level E's own step, not this one's.

**Verification:** A well-formed routine specification repeatedly generates at least one downstream artifact, and that artifact remains automatically traceable to its source.

**Level D — Integral**

Specifications are precise and testable enough to directly drive generation -- code, prototypes, and/or tests can be generated from the specification with minimal additional interpretation. Traceability and shared access (per Level C) are maintained automatically as generated artifacts are produced. The reverse direction -- generating or updating a specification from a prototype or test -- is not yet supported; the specification remains the required starting point.

**Transition D → E — Make generation sequence-agnostic**

Support the reverse direction as well as forward generation: a prototype or test may create or update the governing specification. Define conflict resolution when specification, prototype, test, and implementation imply different meanings, and preserve provenance through every update.

**Verification:** Work can begin from a specification, prototype, or test and produce a coherent, traceable artifact set without a manual translation project.

**Level E — Telemetric**

Specifications are precise, testable, and machine-actionable with full traceability, and generation is sequence-agnostic -- code, prototypes, and tests can be generated from the specification, or the specification can be generated or updated from a prototype or test. The system doesn't care which artifact type initiates the work, though the team may choose a preferred sequence.

**Sustainment**

Continuously test artifact equivalence and conflict resolution. Sequence-agnostic generation must not permit the specification, prototype, test, and implementation to drift into parallel meanings.

---

## D5. Prototyping & the prototype-to-code boundary

*The capability to produce functional prototypes for validation, and to govern -- explicitly and consistently -- whether and how those prototypes transition into production code.*

**Level A — Nascent**

Prototyping is ad hoc and the boundary between prototype and production code is undefined or unenforced -- prototypes may become production code by default.

**Transition A → B — Make the boundary explicit**

Label prototypes as non-production by default and define where they may run. Establish a shared expectation that exploratory or generated code does not become production code merely because it appears to work. Name the categories of carry-forward concern that will eventually matter -- architecture, security, verification, maintainability, and data handling -- without yet evaluating any given prototype against them; that formal evaluation is Level C's own gate, not this one's.

**Verification:** A prototype cannot enter the production path accidentally or through ambiguity about its status, though no defined checklist or gate yet exists to evaluate it against.

**Level B — Modeled**

Prototyping is common and AI-assisted, but the prototype-to-code boundary is governed only informally -- teams generally understand that prototypes need rework before production, but there is no defined process, checklist, or gate. Whether and how much rework happens depends on individual judgment and time pressure.

**Transition B → C — Create a formal disposition decision**

Establish an explicit prototype-to-production gate. Define the evidence required to choose among rewrite, partial reuse, carry-forward, and discard-and-rebuild, including architectural fit from D6, verification coverage from D7, and security implications from D11. Record the decision and rationale.

**Verification:** Every prototype contributing code to production has a visible disposition decision against defined criteria.

**Level C — Continuous**

A defined decision point exists between prototype and production -- prototypes are explicitly evaluated against criteria (e.g., architectural fit per D6, test coverage per D7) before any code carries forward, and the decision (rewrite, partial reuse, or discard-and-rebuild) is documented. The evaluation is manual and happens after the prototype exists.

**Transition C → D — Apply production criteria during prototyping**

Use the Level C decision criteria while the prototype is being built rather than only afterward. Identify the prototype class in advance -- disposable learning artifact, partial-reuse candidate, or production-viable experiment -- and apply relevant architectural and verification constraints from the beginning. The carry-forward decision itself should become faster and less all-or-nothing than Level C's binary rewrite-or-discard call, since most of the evidence needed to decide is now available before the decision point rather than only after it.

**Verification:** Teams can state before construction what would make the prototype reusable, and post-prototype review rarely discovers basic production requirements for the first time. The carry-forward decision is measurably quicker to reach than at Level C, and fewer decisions land as pure discard-or-full-rewrite.

**Level D — Integral**

The decision criteria from Level C are applied during prototyping, not only after -- prototypes are built with carry-forward viability in mind from the start (e.g., generated against the same architectural constraints per D6-D), reducing the frequency of discard-and-rebuild outcomes driven by avoidable misalignment. The prototype-to-production decision remains an explicit, governed step, but is faster and less binary than at Level C.

**Transition D → E — Fuse specification, prototype, and test**

Produce specification, prototype, and test as one governed motion with D4-E and D7-E. Permit any of the three to initiate the work while preserving common intent, traceability, architecture, and verification. Make both carry-forward and discard low-cost outcomes.

**Verification:** A prototype can be discarded without discarding the validated understanding around it, or carried forward without reconstructing its specification and tests.

**Level E — Telemetric**

Specification, prototype, and test are produced as a single governed motion (per D4-E / D7-E), sequence-agnostic about which artifact initiates the others. From D5's vantage: because the prototype is produced as part of this fused motion rather than as separate upfront investment, the carry-forward-vs-discard decision (per Levels C/D) is immediate and low-cost in either direction -- a prototype built purely to validate understanding can be discarded without having consumed the specification or test work, and a prototype that is viable carries forward with its specification and test already in hand. Discard-and-rebuild remains a normal, context-appropriate outcome at this level -- what changes is that the decision is no longer expensive.

**Sustainment**

Preserve the explicit disposition decision even when it becomes nearly instantaneous. Low-cost carry-forward must not turn every prototype into production code by default.

---

## D6. Architecture governance

*The capability to define, encode, and enforce architectural standards and design judgment ("taste") across a codebase as code is generated, modified, or extended by agents.*

**Level A — Nascent**

Architectural standards exist only as tribal knowledge or informal conventions, enforced inconsistently through manual review.

**Transition A → B — Externalize architectural judgment**

Document the architectural standards and design judgment currently held in reviewer memory. Capture recurring decisions, constraints, preferred and prohibited patterns, rationale, and reference examples. Assign ownership for maintaining the record.

**Verification:** A capable engineer or agent unfamiliar with the codebase can locate the governing standard and understand the reason behind its most important constraints.

**Level B — Modeled**

Architectural standards are documented (style guides, architecture decision records, design docs) but enforcement remains manual -- reviewers check generated and human-written code against documentation, with consistency dependent on reviewer familiarity with the docs.

**Transition B → C — Encode critical architectural rules**

Select the most common and consequential violations and encode them as deterministic controls: linters, structural tests, dependency rules, schema validation, or CI gates. Retain manual review for judgment that cannot yet be encoded.

**Verification:** The encoded controls prevent or flag a defined set of critical violations consistently across human- and agent-generated changes.

**Level C — Continuous**

Core architectural rules are encoded as automated checks (linters, structural tests, CI gates) covering the most common and critical violations -- but coverage is partial, and violations outside the encoded rules still rely on manual review per Level B.

**Transition C → D — Make the rules usable during generation**

This is a change in *when* enforcement happens, not primarily how much of it exists -- Level C's gates catch violations after code is written; Level D requires the same rules to be readable and applicable by an agent before and during generation, so violations are avoided rather than caught and sent back. Convert encoded checks into constraints agents consume as input to generation itself, not just as a check afterward. Expanding coverage where repeated manual findings reveal missing rules is worth doing alongside this shift, but it doesn't substitute for it -- comprehensive after-the-fact coverage is still Level C if agents never read the rules before generating.

**Verification:** Agents routinely produce compliant changes on the first pass because they consumed the rules before generation -- not because a larger after-the-fact gate caught fewer violations.

**Level D — Integral**

Architectural rules are encoded comprehensively enough that agents read and respect them directly during generation, not just check against them after the fact. Violations are caught and, where possible, accompanied by remediation guidance the agent can act on, reducing round-trips between generation and review.

**Transition D → E — Let agents propose evolution of the standard**

Create a governed mechanism for agents to propose additions or changes to the encoded standard. Each proposal identifies the uncovered or obstructive pattern, supplies evidence and examples, and recommends an enforceable rule or remediation. Human architectural authority accepts, rejects, or revises the proposal.

**Verification:** Repeated novel findings or rule friction produce reviewable, versioned improvements to the standard, with a visible record of why the standard changed.

**Level E — Telemetric**

Agents participate in evolving the encoded standard itself -- when an agent encounters a pattern not covered by existing rules, or notices a rule that has become a recurring obstacle, it proposes an addition or change to the encoded ruleset (linters, structural tests, remediation guidance) for human review. The team's architectural taste and the enforced standard co-evolve, with agents as active contributors to that evolution rather than only subjects of it.

**Sustainment**

Continuously verify that agent-proposed rules improve architectural coherence rather than merely optimizing for easier generation. Architectural taste remains a human-governed capability.

---

## D7. Test-driven development (specification-driven verification)

*The capability to couple test/specification authoring with implementation as one motion, and to scale verification coverage as generation volume scales.*

**Level A — Nascent**

Tests exist and are written close in time to the code they cover, but are authored independently after implementation -- the test verifies what the code happens to do, rather than the code being written to satisfy a pre-specified test.

**Transition A → B — Move tests before implementation**

Establish a test-first workflow for defined classes of work. Require expected behavior and failure conditions before code is written, while allowing the specification and tests to remain separately authored.

**Verification:** For the targeted work classes, implementation begins against a pre-existing test rather than tests being written to describe completed code.

**Level B — Modeled**

Tests are written before implementation (test-first), but as a separate authoring step from the specification -- a developer or agent translates the specification into tests manually, introducing a translation gap between what the specification says and what the test actually checks.

**Transition B → C — Derive tests directly from specifications**

Define a repeatable method that converts D4 specifications into tests. Specify which requirement elements generate which test types, how unsupported or ambiguous cases are surfaced, and who reviews generated tests.

**Verification:** Re-running the method against the same well-formed specification produces materially equivalent tests without routine manual reinterpretation.

**Level C — Continuous**

Test generation is derived directly from the specification (per D4) using a consistent, repeatable method -- the translation gap from Level B is closed for routine cases, though specification authors don't see the generated tests until after the fact.

**Transition C → D — Generate tests during specification authoring**

Generate corresponding tests as the specification is written. Use them to expose missing edge cases, undefined states, contradictory acceptance conditions, and other ambiguities while meaning is still being formed.

**Verification:** Specification authors routinely revise requirements in response to test-generation feedback before implementation begins.

**Level D — Integral**

Test generation occurs concurrently with specification authoring -- as a specification is written, corresponding tests are generated in the same step, surfacing ambiguities in the specification (e.g., undefined edge cases) at authoring time rather than later.

**Transition D → E — Fuse specification, test, and prototype**

Combine specification authoring, test generation, and prototyping into one governed, sequence-agnostic motion with D4-E and D5-E. Ensure that verification coverage scales with generation volume rather than becoming a downstream human bottleneck.

**Verification:** Whether work begins from a specification, prototype, or test, the corresponding verification set is created or updated automatically and remains aligned.

**Level E — Telemetric**

Test generation, specification authoring, and prototyping are a single governed motion (per D4-E / D5-E) -- verification coverage scales automatically as generation volume scales, and the system is sequence-agnostic about which artifact initiates the others.

**Sustainment**

Continuously test whether generated verification still measures intended behavior rather than merely confirming the implementation produced alongside it.

---

## D8. Code verification & review

*The capability to apply human and automated judgment to generated code for correctness, security, maintainability, and alignment with intent, scaled appropriately to risk. Note: review of generated code is not a substitute for execution containment (D11) -- at any D8 level, review happens on code, while execution risk (e.g., an agent running a destructive shell command) is governed by D11's sandboxing and runtime controls. The two dimensions address different surfaces and neither compensates for the other's absence.*

**Level A — Nascent**

Verification relies primarily on human line-by-line review of all generated code, regardless of risk or volume. Review capacity does not scale with generation volume -- as the rate of code generation increases, review either becomes a bottleneck or is skipped under pressure.

**Transition A → B — Put deterministic gates before human review**

Run linters, static analysis, secret detection, basic CI, and other repeatable checks on all generated and human-written code before human review. Retain human review for correctness, design, maintainability, security judgment, and alignment with intent.

**Verification:** Code cannot reach human review or merge while failing the agreed deterministic gates.

**Level B — Modeled**

Deterministic automated gates (linters, SAST, basic CI checks) run on all code before human review, catching style and known-pattern issues. Human review remains the primary mechanism for correctness, design, and intent, and is still applied uniformly regardless of risk.

**Transition B → C — Allocate review by risk**

Define change-risk tiers using factors such as blast radius, data sensitivity, novelty, reversibility, architectural significance, and security consequence. Permit routine low-risk changes to pass with automated gates, while routing higher-risk or novel changes to human review.

**Verification:** Review effort is visibly concentrated according to defined risk rather than applied uniformly or skipped under volume pressure.

**Level C — Continuous**

Review is risk-tiered -- routine, low-risk changes pass with automated gates alone (per Level B), while higher-risk or novel changes are routed to human review. Tiering criteria are defined but applied judgmentally on a per-change basis.

**Transition C → D — Add structurally independent AI review**

Introduce an AI review layer independent from the agent or model that generated the code. Review correctness, security, performance, architecture, maintainability, and intent in parallel; preserve the evidence behind findings; and route high-severity findings and high-risk changes to humans.

**Verification:** Independent review identifies material issues before human review, and humans can inspect the basis and severity of each finding.

**Level D — Integral**

An AI review layer, structurally independent from the agent or model that generated the code, performs first-pass review across multiple concern areas (correctness, security, performance, standards) in parallel, surfacing findings ranked by severity. Human review is concentrated on findings the independent reviewer flags as high-severity, or on changes tiered as high-risk per Level C.

**Transition D → E — Calibrate the review system against outcomes**

Track confirmed findings, dismissed findings, escaped defects, false positives, false negatives, and the accuracy of risk-tier assignments. Use those outcomes to adjust reviewer instructions, rules, severity thresholds, and human-review allocation.

**Verification:** The organization can show how observed review outcomes changed thresholds, criteria, or reviewer behavior.

**Level E — Telemetric**

The independent review layer's findings and the team's risk-tiering criteria (per Levels C/D) are continuously calibrated against outcomes -- false-positive and false-negative rates are tracked, tiering thresholds adjust accordingly, and the review system's own effectiveness is itself under ongoing verification.

**Sustainment**

Keep the independent reviewer under continuous evaluation. A review layer that is no longer calibrated becomes another unchecked generator of confidence.

---

## D9. Environment management

*The capability to provision, configure, and maintain the environments (dev/QA/staging/prod, etc.) through which code moves, including parity, ephemerality, self-provisioning, and cleanup.*

**Level A — Nascent**

No standard environment separation exists -- development happens against a single shared, mutable environment (or directly against production), with no consistent dev/QA/staging/prod distinction.

**Transition A → B — Establish standard environment separation**

Create standard environment classes such as development, QA, staging, and production, with documented purpose, access, ownership, and promotion paths. Separate development and testing from production even if provisioning remains manual.

**Verification:** Teams no longer develop against one shared mutable environment or production by default.

**Level B — Modeled**

Standard environments (dev/QA/staging/prod, etc.) exist but are manually provisioned and configured, with inconsistent parity between them.

**Transition B → C — Define environments as code**

Capture infrastructure, configuration, dependencies, secrets interfaces, and policy in repeatable, versioned definitions. Eliminate known parity gaps and govern environment changes through the same change discipline as application code.

**Verification:** Rebuilding an environment from the governed definition produces a materially equivalent environment without undocumented manual configuration.

**Level C — Continuous**

Environments are defined as code (infrastructure-as-code) with consistent, repeatable configuration -- parity between environments is reliable. Provisioning a new environment instance still requires a human-initiated process.

**Transition C → D — Make environments on-demand and ephemeral**

Create templates and human-triggered lifecycle workflows. A pull request, command, or approved workflow provisions an isolated environment from the governed definition and tears it down predictably.

**Verification:** A team member can create and remove an isolated environment through one standard action without infrastructure-specialist intervention.

**Level D — Integral**

Environments can be spun up and torn down on demand from templates, triggered by a human action (e.g., opening a PR, running a command). Ephemeral environments exist, but provisioning and cleanup remain human-triggered events rather than autonomous.

**Transition D → E — Delegate environment lifecycle to agents**

Allow agents to determine when an environment is needed, select the correct governed template, provision it within policy and quota, verify readiness, and remove it when the work completes or expires. Preserve attribution, exception handling, and human oversight.

**Verification:** Routine environment lifecycle occurs without standing human maintenance, while every environment remains attributable and reconstructable.

**Level E — Telemetric**

Environments are ephemeral and self-provisioned by agents on demand, including automated cleanup/teardown -- environment lifecycle requires no standing human maintenance.

**Sustainment**

Continuously test policy, quota, cleanup, access, and cost controls. Autonomous provisioning must remain bounded stewardship, not unmanaged infrastructure creation.

---

## D10. Release discipline

*The capability to govern how validated changes move into production -- gating, approval, rollback, compliance, and release communications -- as a compressible, on-demand cycle rather than a fixed cadence.*

**Level A — Nascent**

Releases follow a fixed cadence (e.g., sprint boundaries) with manual gating, approval, and announcement.

**Transition A → B — Decouple releases from the sprint calendar**

Permit validated changes to release outside fixed sprint or planning boundaries. Automate the minimum test gates required before release while retaining manual approval and communication.

**Verification:** A release can occur outside the fixed cadence when the automated tests pass and a human approves it.

**Level B — Modeled**

Releases occur more frequently than a fixed sprint cadence, and gating is partially automated (automated test suites must pass before release), but approval and release communications remain manual steps requiring human sign-off before each release.

**Transition B → C — Trigger release from validated change**

Deploy from commits or changes that pass the automated gates rather than from the calendar. Automate deployment and rollback based on deterministic health checks, while keeping human oversight for policy changes and material exceptions.

**Verification:** A qualifying change can reach production without a manually assembled release event, and a failed health check can restore the prior state automatically.

**Level C — Continuous**

Releases are triggered by commits passing automated gates (per D8) rather than by calendar -- deployment to production can happen multiple times per day. Rollback is automated (e.g., automatic revert on failed health check), but is treated as an exception-handling path rather than a normal part of the release pattern.

**Transition C → D — Make on-demand release compliant by construction**

Automate pre-deployment approval, compliance checks, audit evidence, and rollback under governed policy. Define which conditions permit release, block release, or require a named exception. Normalize rollback as a tested primary recovery path.

**Verification:** On-demand releases carry automatically assembled compliance evidence, and rollback works as a practiced response rather than an emergency improvisation.

**Level D — Integral**

Pre-deployment gating, approval, and rollback are fully automated and triggered by signal (per Levels B/C) -- releases are on-demand and compliant by construction, with audit trail and compliance checks built into the gate itself (per D11-D). Rollback-as-primary-recovery is a normal, expected path, not an exception.

**Transition D → E — Extend release judgment into production**

Use progressive delivery and live quality gates to decide whether a release should expand, hold, or roll back based on actual behavior. Include relevant measures such as error budgets, anomaly signals, evidence coverage, and other production-quality indicators.

**Verification:** A release can be expanded, constrained, or reversed automatically from live evidence while preserving its decision and audit trail.

**Level E — Telemetric**

Pre-deployment gates (per Level D) are necessarily incomplete for AI-generated, non-deterministic output -- release decisions extend into production via live quality gates, using real-time performance signals (e.g., error budgets, evidence coverage) as part of the release decision itself, not only as post-release monitoring. A release can be incrementally validated and expanded, or rolled back, based on its live behavior, not only its pre-deployment checks.

**Sustainment**

Continuously recalibrate live quality gates. Production evidence should govern exposure without allowing noisy or poorly understood signals to create release instability.

---

## D11. Security & compliance

*The capability to identify, assess, and mitigate security and regulatory risk introduced at any stage of the lifecycle, including risks novel to AI-generated artifacts and agent tooling. [Deferred -- needs further research/context]*

> **Draft caution:** The underlying D11 maturity definition remains marked for further research. The transitions below operationalize the current ladder but inherit that same provisional status.

**Level A — Nascent**

Agents execute with unrestricted access to the filesystem, shell, and network on whatever system runs them -- no sandboxing, no pre-execution validation of dangerous operations, and no agent-specific identity (agent activity is indistinguishable from the human operating it).

**Transition A → B — Contain agent execution**

Introduce sandboxing, filesystem and network restrictions, pre-execution checks for dangerous operations, and deterministic scanning for generated artifacts. Define the minimum actions an agent may perform and deny unrestricted use of shared human environments.

**Verification:** An agent cannot perform a destructive or unauthorized filesystem, shell, or network action merely because the initiating human could.

**Level B — Modeled**

Agents execute within sandboxed environments (restricted syscalls, network egress controls) with pre-execution static checks for dangerous patterns (e.g., destructive shell commands, unvalidated file I/O); deterministic security scanning (SAST, secret detection) runs on all generated code regardless of origin. Agents still lack distinct identities, and shared memory or context across sessions is not integrity-checked.

**Transition B → C — Give agent activity distinct identity and provenance**

Use per-agent or per-session credentials and associate each agent-authored change with the initiating human and session. Require this provenance in the change path, and add baseline integrity validation for shared memory or context.

**Verification:** Every material agent action is attributable to a specific agent session and initiating human, and shared context has inspectable provenance.

**Level C — Continuous**

Agent actions are mapped to identifiable, auditable identities (per-agent or per-session credentials, not shared human credentials) -- every agent-authored change can be traced to a specific agent, session, and initiating human. PR gates require this labeling, though individual override of the gate remains possible. Shared memory/context stores have basic integrity validation (e.g., provenance tagging) but no active poisoning detection.

**Transition C → D — Make controls centrally enforced and non-bypassable**

Replace individually bypassable controls with mandatory gates and a named, logged exception process. Inventory skills, plugins, MCP servers, and other agent tooling as supply-chain components subject to approval and scanning. Automate audit-evidence assembly.

**Verification:** An individual cannot silently bypass required controls, and every exception identifies its authority, rationale, scope, and duration.

**Level D — Integral**

PR gates for agent-authored changes are mandatory and non-bypassable by individual override -- required checks (security scanning, review, labeling) can only be waived through a named, logged exception process. Agent tooling itself (skills, MCP servers, plugins) is inventoried and treated as supply-chain surface subject to the same scanning. Audit evidence generation is automated rather than manually assembled.

**Transition D → E — Enforce policy at the point of action**

Apply least privilege, runtime authorization, behavior guardrails, and real-time termination capability during agent execution. Actively monitor shared memory and context for injected, poisoned, anomalous, or unauthorized content.

**Verification:** The organization can constrain or terminate unsafe behavior while it is occurring and can detect active context-integrity threats.

**Level E — Telemetric**

Security policy for agent behavior is enforced at the point of action -- least-privilege scoping and runtime guardrails constrain what an agent can do during execution, with real-time termination ('kill switch') capability rather than after-the-fact logging alone. Shared memory and context are actively monitored for injected or anomalous content, not merely provenance-tagged.

**Sustainment**

Exercise kill switches, exception paths, context-integrity controls, and least-privilege boundaries regularly. Runtime enforcement that is not tested is only documented intent.

---

## D12. Instrumentation & observability

*The capability to monitor, trace, and evaluate system behavior in production, and to structure organizational knowledge (decisions, plans, metrics) for equal consumption by humans and agents, closing the loop back to upstream dimensions. If AI is only used to generate deterministic artifacts (e.g., code, tests, IaC) and is not in the runtime decision path, production observability requirements stay primarily classical; AI-specific tracing/evaluation applies at build time.*

**Level A — Nascent**

Monitoring covers infrastructure/application metrics; organizational knowledge (decisions, plans, metrics) lives in human-readable formats not structured for agent consumption.

**Transition A → B — Retain build-time generation traces**

Capture enough of D4–D8 generation activity to investigate why a deterministic artifact was produced: agent or model identity, relevant inputs and outputs, timing, tool activity, and artifact lineage. Begin with workflows where failure is frequent or consequential.

**Verification:** When generated output fails, the team can inspect the relevant generation record instead of relying on memory or recreating the session.

**Level B — Modeled**

Build-time generation steps (D4-D8) produce some trace of agent reasoning (e.g., logs of prompts and outputs), but this is ad hoc, not systematically retained, and not used for evaluation -- when something goes wrong, the org has a deterministic output but no reliable visibility into why the agent produced it.

**Transition B → C — Turn traces into systematic evaluation**

Standardize retention and use traces to identify recurring failure patterns rather than merely debug isolated incidents. Define failure categories, quality measures, and review practices, and feed findings back into specification, generation, architecture, testing, and review.

**Verification:** Repeated generation failures produce measurable upstream changes, and the organization can show the pattern that justified each change.

**Level C — Continuous**

Build-time tracing (per Level B) is systematic and feeds evaluation -- generation-step traces are retained and used to diagnose recurring failure patterns in D4-D8's output (e.g., why D8's review keeps flagging the same kind of issue from generation), as a continuous practice rather than per-incident debugging.

**Transition C → D — Identify and observe runtime non-determinism**

Classify every place where AI participates in runtime decisions within the delivery system, such as environment provisioning, release gating, or rollback. Instrument and evaluate those surfaces separately from build-time generation, and distinguish them from any AI behavior inside the shipped product.

**Verification:** The organization can enumerate its build-time, delivery-runtime, and product-runtime AI surfaces and show the tracing and evaluation applied to each.

**Level D — Integral**

The organization has identified where, if anywhere, AI participates in its own delivery system's runtime decisions (e.g., D9-E's self-provisioning, D10-E's live release gating) and applies runtime tracing and evaluation there, distinct from and in addition to the build-time tracing per Level C. If the shipped product also has AI in its runtime path, that is recognized as a separate observability surface from the delivery system's own.

**Transition D → E — Make observability directly usable by humans and agents**

Expose build-time traces, delivery-runtime traces, production telemetry, decisions, and plans through governed structures available to both humans and agents. Connect observed behavior back to upstream dimensions, including the Shared Intelligence Layer.

**Verification:** A material production or delivery signal can be traced to the relevant upstream decision and enter the governed feedback path without manual evidence reconstruction.

**Level E — Telemetric**

Build-time generation traces (per C), delivery-system runtime traces (per D), and production telemetry are equally and directly accessible to agents alongside humans, and observability data feeds back into upstream dimensions (e.g., D1) as part of a closed loop. The organization continuously re-evaluates where non-determinism lives in its delivery system as D1-D11 mature, rather than treating the answer from Level D as fixed.

**Sustainment**

Continuously reassess where non-determinism lives as the delivery system evolves. Observability architecture must change when AI crosses a new build-time, delivery-runtime, or product-runtime boundary.

---

## D13. Feedback loop velocity

*The end-to-end cycle time from signal (market, user, incident, failure) to shipped response, as a property of the whole system rather than any individual stage.*

**Level A — Nascent**

End-to-end cycle time from signal (market, user, incident) to shipped response is unmeasured and dominated by handoffs between disconnected stages/teams.

**Transition A → B — Make the end-to-end cycle measurable**

Define the start and end points of the response cycle and measure them retrospectively for major releases, incidents, failures, or market responses. Preserve timestamps and handoffs well enough to reconstruct elapsed time.

**Verification:** The organization can calculate how long a completed response took from originating signal to shipped change and identify the major handoffs involved.

**Level B — Modeled**

Cycle time is measured retrospectively for major releases or incidents (e.g., post-mortems calculate how long the response took), but isn't tracked continuously and isn't used to identify which handoff in the chain is the bottleneck.

**Transition B → C — Measure continuously by stage and handoff**

Instrument the full cycle across D1–D12 and establish a standing view of cycle time by stage and handoff. Use consistent definitions so the organization can identify which current handoff dominates total elapsed time.

**Verification:** At any point, the organization can name the dominant contributor to end-to-end cycle time using current evidence rather than retrospective opinion.

**Level C — Continuous**

Cycle time is tracked continuously as a standing metric, broken down by stage and handoff (per the D1-D3 -> fused D4/D5/D7 -> D6/D8 -> D9/D10 chain) -- the organization can identify which handoff currently dominates total cycle time, though addressing it requires separate prioritization and planning work.

**Transition C → D — Treat bottleneck removal as normal priority work**

When D13 identifies the dominant delay, treat the relevant dimension's next maturity step as comparable to feature work. Assign ownership, investment, and an expected cycle-time effect, then verify whether the bottleneck moved or merely changed form.

**Verification:** At least one identified handoff constraint has been funded and improved through the normal prioritization system with before-and-after evidence.

**Level D — Integral**

Improving cycle time is a routine input to prioritization across D1-D12 -- when D13's measurement identifies a dominant bottleneck, closing it via the relevant dimension's next maturity step is treated as comparable in priority to feature work, not a separate platform initiative competing for attention.

**Transition D → E — Compress the complete closed loop**

Optimize the full cycle rather than isolated stages. Ensure a market, user, incident, failure, or outcome signal can be observed, interpreted, returned to the appropriate upstream model or intent, reprioritized through proper authority, delivered, and observed again. Repeatedly remove whichever handoff currently dominates.

**Verification:** The organization demonstrates repeated governed signal-to-response cycles operating on a days-not-months cadence, including upstream reconsideration where warranted.

**Level E — Telemetric**

End-to-end cycle time is short enough to be a competitive differentiator, operating on a days, not months, cadence -- achieved not by any single dimension but by D12-E's closed loop keeping every stage's transit time visible and D13-D's prioritization continuously compressing whichever handoff currently dominates.

**Sustainment**

Protect quality, evidence, authority, and intent while compressing time. The loop is not mature if speed is achieved by bypassing the very gates that make the response trustworthy.

---

## Cross-dimension boundary checks

These checks exist because a dimension reaching a high level can look, from a distance, like it has absorbed a neighboring dimension's job. It hasn't -- each pairing below names the boundary explicitly so that maturity in one dimension is never mistaken for coverage of another's.

### D4 / D5 / D7

- D4 governs specification quality and traceability.
- D5 governs the prototype-to-production disposition.
- D7 governs verification derived from intended behavior.
- Their Level E convergence is one governed motion, not the disappearance of their distinct concerns.

### D6 / D8

- D6 prevents and remediates architectural nonconformance.
- D8 evaluates broader correctness, security, maintainability, performance, and alignment with intent.
- Encoded architecture rules do not eliminate the need for risk-tiered review.

### D8 / D11

- D8 reviews code and artifacts.
- D11 contains agent execution and governs agent identity, tooling, runtime action, and context integrity.
- Strong code review does not make unrestricted agent execution safe.

### D9 / D10

- D9 supplies the environments through which code moves.
- D10 governs whether and how validated changes advance into production.
- Self-provisioning environments do not imply autonomous release authority.

### D12 / D13

- D12 supplies the evidence of the feedback return.
- D13 measures and compresses the time required for that evidence to change understanding, priority, and shipped behavior.

**D12 makes the loop observable. D13 makes the loop competitive.**

---

*Status: D4-D13 locked baseline, all A-E, now with inline transition and verification notes for every step and Level E sustainment guidance (folded in from `sdlc_transition_states_d4_d13.md` v0.2, 2026-07-27 -- see `CHANGELOG.md`). D1-D3 inherited by reference from `shared_intelligence_layer.md` (STD-SHARED-INTELLIGENCE v1.0.0) as of 2026-07-23, which carries its own transition notes inline already -- see that document's own status. Family-wide maturity-level names (Nascent/Modeled/Continuous/Integral/Telemetric) applied throughout as of 2026-07-27. See `README.md` for open items, flagged candidate "lumpy" transitions, and known areas expected to evolve.*