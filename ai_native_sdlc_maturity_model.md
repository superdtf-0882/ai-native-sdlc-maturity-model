# AI-Native SDLC Maturity Model — Matrix

**Version 1.1.0 — 2026-07-21** (adds the Pre-AI threshold state, the Exempt designation, and assessment schema additions; all thirteen dimensions and all A–E level definitions unchanged from v1.0.0, locked 2026-07-15 — see `CHANGELOG.md`).

This is the full A–E maturity matrix for all 13 dimensions, readable in-browser and directly usable as input to AI tools. **This markdown document is the source of truth** -- `ai_native_sdlc_maturity_model.xlsx` is a derived distribution rendering of it; if the two ever diverge, this document is authoritative and the spreadsheet should be regenerated.

For the design principles, handoff structure, research finding, and open items behind this matrix, see `README.md`. For the diagram of how these 13 dimensions hand off to each other, see `sdlc_handoff_diagram.png` / `sdlc_handoff_diagram.html`.

---

## How to read this matrix

Each dimension below has a definition followed by a five-level maturity ladder (A through E). Levels describe **realistically adjacent states** -- each step up implies a roughly costable set of changes, not "more AI, more thoroughly." A given level is not inherently good or bad; it is appropriate or inappropriate for an organization's size, regulatory context, and risk tolerance (see Design Principle 3 in the working framework document).

Dimensions are independently scored -- an organization can be advanced in one dimension and nascent in another. See the working framework document for how dimensions hand off to, constrain, and converge with each other.

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

## D1. Market discovery & definition

*The capability to identify, size, and validate market opportunities (TAM/SAM/SOM, market trends, opportunity framing) through a continuous, AI-assisted discovery loop that directly feeds requirements work.*

**Level A**

Discovery happens periodically (e.g., at planning cycles), manually synthesized, with AI used inconsistently -- left to individual researcher preference, with no shared method.

**Level B**

Discovery runs on a defined cadence (e.g., quarterly) using a consistent AI-assisted method, but remains a Product-owned exercise -- outputs (TAM/SAM/SOM, trend analysis, opportunity framing) are produced for Product's own use and not routinely shared with Marketing, Sales, or Strategy.

**Level C**

Discovery becomes continuous rather than cadence-based -- market signals and opportunity models refresh on an ongoing basis. Outputs remain primarily Product-owned, though other functions can request access to current findings.

**Level D**

The continuous discovery model (per Level C) is a shared asset -- Marketing, Sales Enablement, and Strategy draw directly from the same underlying market/opportunity model rather than commissioning separate research, though each function still produces its own renderings manually.

**Level E**

Discovery (D1), persona (D2), and positioning/competitive intelligence (D3) operate as one converged intelligence layer that automatically generates function-specific renderings -- Product roadmap input, Marketing messaging, Sales battlecards, and Strategy narratives are all produced from the same continuously-updated model, each contextually adapted to its audience without separate commissioning. From D1's vantage: market signals, TAM/opportunity models, and trend data are the input lens this layer continuously refreshes.

---

## D2. Buyer/user persona development

*The capability to research, model, and maintain live representations of target users and buyers, extensible as a shared asset across Product, Marketing, and Sales Enablement.*

**Level A**

User personas exist as static documents, created once (e.g., at launch or major redesign) and rarely revisited. Buyer personas are often an artifact of Marketing or Sales rather than Product Management. AI assistance, where used, is inconsistent -- left to individual preference, with no shared method.

**Level B**

User Personas are dynamic documents that are updated intervalically via Product Management and softare usage data (via instrumentation or other usage reporting). AI assistance is ad hoc or based on departmental software.

**Level C**

User Personas and Buyer Personas are shared in the same system or system to system. They share relevant update data at regular intervals. The system uses a common AI with shared intelligence. Access is extended to relevant organizations including MKTG, Sales, Product, and Engineering.

**Level D**

Personas are dynamic, regularly updated artifacts fed by usage/feedback data, and are shared assets consumed directly by Marketing and Sales Enablement, not just Product. Engineering has connected access to relevant User Personas via regular requirements management system.

**Level E**

Discovery (D1), persona (D2), and positioning/competitive intelligence (D3) operate as one converged intelligence layer that automatically generates function-specific renderings -- Product roadmap input, Marketing messaging, Sales battlecards, and Strategy narratives are all produced from the same continuously-updated model, each contextually adapted to its audience without separate commissioning. From D2's vantage: live representations of target users and buyers are the input lens this layer continuously refreshes, extending to Engineering via the requirements management system (D4).

---

## D3. Positioning & competitive intelligence

*The capability to define product differentiation and maintain that positioning against a continuously monitored competitive landscape that actively informs roadmap decisions.*

**Level A**

Positioning was defined at a point in time (e.g., launch) and competitive awareness is ad hoc or anecdotal. AI assistance, where used, is inconsistent -- left to individual preference, with no shared method.

**Level B**

Competitive monitoring runs on a defined cadence using a consistent AI-assisted method (e.g., scheduled competitor and market scans), but remains a Product or Strategy-owned exercise -- findings inform internal roadmap discussions and are not routinely packaged for Marketing or Sales.

**Level C**

Competitive monitoring becomes continuous -- a live feed of market and messaging shifts updates on an ongoing basis. Findings remain primarily owned by Product/Strategy, though other functions can request access to current intelligence.

**Level D**

The continuous competitive intelligence feed (per Level C) is a shared asset -- Marketing and Sales Enablement draw directly from the same underlying competitive model (e.g., for messaging differentiation and battlecards) rather than commissioning separate competitive research, though each function still produces its own renderings manually.

**Level E**

Discovery (D1), persona (D2), and positioning/competitive intelligence (D3) operate as one converged intelligence layer that automatically generates function-specific renderings -- Product roadmap input, Marketing messaging, Sales battlecards, and Strategy narratives are all produced from the same continuously-updated model, each contextually adapted to its audience without separate commissioning. From D3's vantage: positioning and a live competitive landscape are the input lens this layer continuously refreshes.

---

## D4. Requirements management (specification quality & traceability)

*The capability to author precise, testable, machine-actionable specifications with full traceability from source through delivery, such that specification quality directly gates generation quality.*

**Level A**

Specifications are written informally (tickets, docs) with no consistent structure, and traceability from source to delivery is manual or absent.

**Level B**

Specifications are captured in a shared system of record with traceability from source to delivery. Relevant teams have shared access. Drawings, UX designs, wireframes, and functionality matrices are found in or linked to the system of record.

**Level C**

The shared system of record (per Level B) extends to cross-functional access -- Product, Engineering, QA, and Release Management all have shared access, and relevant user personas (per D2) are accessible to these teams within the same system.

**Level D**

Specifications are precise and testable enough to directly drive generation -- code, prototypes, and/or tests can be generated from the specification with minimal additional interpretation. Traceability and shared access (per Level C) are maintained automatically as generated artifacts are produced. The reverse direction -- generating or updating a specification from a prototype or test -- is not yet supported; the specification remains the required starting point.

**Level E**

Specifications are precise, testable, and machine-actionable with full traceability, and generation is sequence-agnostic -- code, prototypes, and tests can be generated from the specification, or the specification can be generated or updated from a prototype or test. The system doesn't care which artifact type initiates the work, though the team may choose a preferred sequence.

---

## D5. Prototyping & the prototype-to-code boundary

*The capability to produce functional prototypes for validation, and to govern -- explicitly and consistently -- whether and how those prototypes transition into production code.*

**Level A**

Prototyping is ad hoc and the boundary between prototype and production code is undefined or unenforced -- prototypes may become production code by default.

**Level B**

Prototyping is common and AI-assisted, but the prototype-to-code boundary is governed only informally -- teams generally understand that prototypes need rework before production, but there is no defined process, checklist, or gate. Whether and how much rework happens depends on individual judgment and time pressure.

**Level C**

A defined decision point exists between prototype and production -- prototypes are explicitly evaluated against criteria (e.g., architectural fit per D6, test coverage per D7) before any code carries forward, and the decision (rewrite, partial reuse, or discard-and-rebuild) is documented. The evaluation is manual and happens after the prototype exists.

**Level D**

The decision criteria from Level C are applied during prototyping, not only after -- prototypes are built with carry-forward viability in mind from the start (e.g., generated against the same architectural constraints per D6-D), reducing the frequency of discard-and-rebuild outcomes driven by avoidable misalignment. The prototype-to-production decision remains an explicit, governed step, but is faster and less binary than at Level C.

**Level E**

Specification, prototype, and test are produced as a single governed motion (per D4-E / D7-E), sequence-agnostic about which artifact initiates the others. From D5's vantage: because the prototype is produced as part of this fused motion rather than as separate upfront investment, the carry-forward-vs-discard decision (per Levels C/D) is immediate and low-cost in either direction -- a prototype built purely to validate understanding can be discarded without having consumed the specification or test work, and a prototype that is viable carries forward with its specification and test already in hand. Discard-and-rebuild remains a normal, context-appropriate outcome at this level -- what changes is that the decision is no longer expensive.

---

## D6. Architecture governance

*The capability to define, encode, and enforce architectural standards and design judgment ("taste") across a codebase as code is generated, modified, or extended by agents.*

**Level A**

Architectural standards exist only as tribal knowledge or informal conventions, enforced inconsistently through manual review.

**Level B**

Architectural standards are documented (style guides, architecture decision records, design docs) but enforcement remains manual -- reviewers check generated and human-written code against documentation, with consistency dependent on reviewer familiarity with the docs.

**Level C**

Core architectural rules are encoded as automated checks (linters, structural tests, CI gates) covering the most common and critical violations -- but coverage is partial, and violations outside the encoded rules still rely on manual review per Level B.

**Level D**

Architectural rules are encoded comprehensively enough that agents read and respect them directly during generation, not just check against them after the fact. Violations are caught and, where possible, accompanied by remediation guidance the agent can act on, reducing round-trips between generation and review.

**Level E**

Agents participate in evolving the encoded standard itself -- when an agent encounters a pattern not covered by existing rules, or notices a rule that has become a recurring obstacle, it proposes an addition or change to the encoded ruleset (linters, structural tests, remediation guidance) for human review. The team's architectural taste and the enforced standard co-evolve, with agents as active contributors to that evolution rather than only subjects of it.

---

## D7. Test-driven development (specification-driven verification)

*The capability to couple test/specification authoring with implementation as one motion, and to scale verification coverage as generation volume scales.*

**Level A**

Tests exist and are written close in time to the code they cover, but are authored independently after implementation -- the test verifies what the code happens to do, rather than the code being written to satisfy a pre-specified test.

**Level B**

Tests are written before implementation (test-first), but as a separate authoring step from the specification -- a developer or agent translates the specification into tests manually, introducing a translation gap between what the specification says and what the test actually checks.

**Level C**

Test generation is derived directly from the specification (per D4) using a consistent, repeatable method -- the translation gap from Level B is closed for routine cases, though specification authors don't see the generated tests until after the fact.

**Level D**

Test generation occurs concurrently with specification authoring -- as a specification is written, corresponding tests are generated in the same step, surfacing ambiguities in the specification (e.g., undefined edge cases) at authoring time rather than later.

**Level E**

Test generation, specification authoring, and prototyping are a single governed motion (per D4-E / D5-E) -- verification coverage scales automatically as generation volume scales, and the system is sequence-agnostic about which artifact initiates the others.

---

## D8. Code verification & review

*The capability to apply human and automated judgment to generated code for correctness, security, maintainability, and alignment with intent, scaled appropriately to risk. Note: review of generated code is not a substitute for execution containment (D11) -- at any D8 level, review happens on code, while execution risk (e.g., an agent running a destructive shell command) is governed by D11's sandboxing and runtime controls. The two dimensions address different surfaces and neither compensates for the other's absence.*

**Level A**

Verification relies primarily on human line-by-line review of all generated code, regardless of risk or volume. Review capacity does not scale with generation volume -- as the rate of code generation increases, review either becomes a bottleneck or is skipped under pressure.

**Level B**

Deterministic automated gates (linters, SAST, basic CI checks) run on all code before human review, catching style and known-pattern issues. Human review remains the primary mechanism for correctness, design, and intent, and is still applied uniformly regardless of risk.

**Level C**

Review is risk-tiered -- routine, low-risk changes pass with automated gates alone (per Level B), while higher-risk or novel changes are routed to human review. Tiering criteria are defined but applied judgmentally on a per-change basis.

**Level D**

An AI review layer, structurally independent from the agent or model that generated the code, performs first-pass review across multiple concern areas (correctness, security, performance, standards) in parallel, surfacing findings ranked by severity. Human review is concentrated on findings the independent reviewer flags as high-severity, or on changes tiered as high-risk per Level C.

**Level E**

The independent review layer's findings and the team's risk-tiering criteria (per Levels C/D) are continuously calibrated against outcomes -- false-positive and false-negative rates are tracked, tiering thresholds adjust accordingly, and the review system's own effectiveness is itself under ongoing verification.

---

## D9. Environment management

*The capability to provision, configure, and maintain the environments (dev/QA/staging/prod, etc.) through which code moves, including parity, ephemerality, self-provisioning, and cleanup.*

**Level A**

No standard environment separation exists -- development happens against a single shared, mutable environment (or directly against production), with no consistent dev/QA/staging/prod distinction.

**Level B**

Standard environments (dev/QA/staging/prod, etc.) exist but are manually provisioned and configured, with inconsistent parity between them.

**Level C**

Environments are defined as code (infrastructure-as-code) with consistent, repeatable configuration -- parity between environments is reliable. Provisioning a new environment instance still requires a human-initiated process.

**Level D**

Environments can be spun up and torn down on demand from templates, triggered by a human action (e.g., opening a PR, running a command). Ephemeral environments exist, but provisioning and cleanup remain human-triggered events rather than autonomous.

**Level E**

Environments are ephemeral and self-provisioned by agents on demand, including automated cleanup/teardown -- environment lifecycle requires no standing human maintenance.

---

## D10. Release discipline

*The capability to govern how validated changes move into production -- gating, approval, rollback, compliance, and release communications -- as a compressible, on-demand cycle rather than a fixed cadence.*

**Level A**

Releases follow a fixed cadence (e.g., sprint boundaries) with manual gating, approval, and announcement.

**Level B**

Releases occur more frequently than a fixed sprint cadence, and gating is partially automated (automated test suites must pass before release), but approval and release communications remain manual steps requiring human sign-off before each release.

**Level C**

Releases are triggered by commits passing automated gates (per D8) rather than by calendar -- deployment to production can happen multiple times per day. Rollback is automated (e.g., automatic revert on failed health check), but is treated as an exception-handling path rather than a normal part of the release pattern.

**Level D**

Pre-deployment gating, approval, and rollback are fully automated and triggered by signal (per Levels B/C) -- releases are on-demand and compliant by construction, with audit trail and compliance checks built into the gate itself (per D11-D). Rollback-as-primary-recovery is a normal, expected path, not an exception.

**Level E**

Pre-deployment gates (per Level D) are necessarily incomplete for AI-generated, non-deterministic output -- release decisions extend into production via live quality gates, using real-time performance signals (e.g., error budgets, evidence coverage) as part of the release decision itself, not only as post-release monitoring. A release can be incrementally validated and expanded, or rolled back, based on its live behavior, not only its pre-deployment checks.

---

## D11. Security & compliance

*The capability to identify, assess, and mitigate security and regulatory risk introduced at any stage of the lifecycle, including risks novel to AI-generated artifacts and agent tooling. [Deferred -- needs further research/context]*

**Level A**

Agents execute with unrestricted access to the filesystem, shell, and network on whatever system runs them -- no sandboxing, no pre-execution validation of dangerous operations, and no agent-specific identity (agent activity is indistinguishable from the human operating it).

**Level B**

Agents execute within sandboxed environments (restricted syscalls, network egress controls) with pre-execution static checks for dangerous patterns (e.g., destructive shell commands, unvalidated file I/O); deterministic security scanning (SAST, secret detection) runs on all generated code regardless of origin. Agents still lack distinct identities, and shared memory or context across sessions is not integrity-checked.

**Level C**

Agent actions are mapped to identifiable, auditable identities (per-agent or per-session credentials, not shared human credentials) -- every agent-authored change can be traced to a specific agent, session, and initiating human. PR gates require this labeling, though individual override of the gate remains possible. Shared memory/context stores have basic integrity validation (e.g., provenance tagging) but no active poisoning detection.

**Level D**

PR gates for agent-authored changes are mandatory and non-bypassable by individual override -- required checks (security scanning, review, labeling) can only be waived through a named, logged exception process. Agent tooling itself (skills, MCP servers, plugins) is inventoried and treated as supply-chain surface subject to the same scanning. Audit evidence generation is automated rather than manually assembled.

**Level E**

Security policy for agent behavior is enforced at the point of action -- least-privilege scoping and runtime guardrails constrain what an agent can do during execution, with real-time termination ('kill switch') capability rather than after-the-fact logging alone. Shared memory and context are actively monitored for injected or anomalous content, not merely provenance-tagged.

---

## D12. Instrumentation & observability

*The capability to monitor, trace, and evaluate system behavior in production, and to structure organizational knowledge (decisions, plans, metrics) for equal consumption by humans and agents, closing the loop back to upstream dimensions. If AI is only used to generate deterministic artifacts (e.g., code, tests, IaC) and is not in the runtime decision path, production observability requirements stay primarily classical; AI-specific tracing/evaluation applies at build time.*

**Level A**

Monitoring covers infrastructure/application metrics; organizational knowledge (decisions, plans, metrics) lives in human-readable formats not structured for agent consumption.

**Level B**

Build-time generation steps (D4-D8) produce some trace of agent reasoning (e.g., logs of prompts and outputs), but this is ad hoc, not systematically retained, and not used for evaluation -- when something goes wrong, the org has a deterministic output but no reliable visibility into why the agent produced it.

**Level C**

Build-time tracing (per Level B) is systematic and feeds evaluation -- generation-step traces are retained and used to diagnose recurring failure patterns in D4-D8's output (e.g., why D8's review keeps flagging the same kind of issue from generation), as a continuous practice rather than per-incident debugging.

**Level D**

The organization has identified where, if anywhere, AI participates in its own delivery system's runtime decisions (e.g., D9-E's self-provisioning, D10-E's live release gating) and applies runtime tracing and evaluation there, distinct from and in addition to the build-time tracing per Level C. If the shipped product also has AI in its runtime path, that is recognized as a separate observability surface from the delivery system's own.

**Level E**

Build-time generation traces (per C), delivery-system runtime traces (per D), and production telemetry are equally and directly accessible to agents alongside humans, and observability data feeds back into upstream dimensions (e.g., D1) as part of a closed loop. The organization continuously re-evaluates where non-determinism lives in its delivery system as D1-D11 mature, rather than treating the answer from Level D as fixed.

---

## D13. Feedback loop velocity

*The end-to-end cycle time from signal (market, user, incident, failure) to shipped response, as a property of the whole system rather than any individual stage.*

**Level A**

End-to-end cycle time from signal (market, user, incident) to shipped response is unmeasured and dominated by handoffs between disconnected stages/teams.

**Level B**

Cycle time is measured retrospectively for major releases or incidents (e.g., post-mortems calculate how long the response took), but isn't tracked continuously and isn't used to identify which handoff in the chain is the bottleneck.

**Level C**

Cycle time is tracked continuously as a standing metric, broken down by stage and handoff (per the D1-D3 -> fused D4/D5/D7 -> D6/D8 -> D9/D10 chain) -- the organization can identify which handoff currently dominates total cycle time, though addressing it requires separate prioritization and planning work.

**Level D**

Improving cycle time is a routine input to prioritization across D1-D12 -- when D13's measurement identifies a dominant bottleneck, closing it via the relevant dimension's next maturity step is treated as comparable in priority to feature work, not a separate platform initiative competing for attention.

**Level E**

End-to-end cycle time is short enough to be a competitive differentiator, operating on a days, not months, cadence -- achieved not by any single dimension but by D12-E's closed loop keeping every stage's transit time visible and D13-D's prioritization continuously compressing whichever handoff currently dominates.

---

*Status: locked baseline. All 13 dimensions A-E. See `README.md` for open items, flagged candidate "lumpy" transitions, and known areas expected to evolve.*