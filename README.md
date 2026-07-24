# AI-Native SDLC Maturity Model — working framework

**Version 1.2.0 — 2026-07-23.** D1–D3 reconciled against a Shared Intelligence Layer candidate and extracted to `shared_intelligence_layer.md`, the new canonical source for those three dimensions shared with the AI-Native PDLC Maturity Model; this repo's matrix now inherits them by reference (predecessor text preserved verbatim at `d1-d3-superseded-v1.1.0.md`). D4–D13 and the Pre-AI/Exempt mechanics from v1.1.0 (2026-07-21) are unchanged. Changes are tracked in `CHANGELOG.md` and diff against the `v1.0.0` tag.

## Purpose

A diagnostic framework for assessing the maturity of a software delivery system that assumes an AI-native baseline — not a framework for transitioning a traditional SDLC onto AI tooling. The goal is a current-state read with enough granularity to identify realistically adjacent next states, not a description of pinnacle practice.

The model's executive anchor is **D13, feedback loop velocity** — the end-to-end cycle time from signal to shipped response. The other twelve dimensions ultimately exist in service of that composite loop: it is the dimension that connects the delivery system to competitiveness, and the measure that distinguishes a *merely* AI-native organization from a *competitively* AI-native one.

A free interactive self-assessment built on this model is available at [aisdlc.davidfacer.com/maturitymodelassessment](https://aisdlc.davidfacer.com/maturitymodelassessment/).

This document captures: (1) the design principles guiding the model, (2) the research finding that motivates it, (3) the 13 capability dimensions and their handoff structure, and (4) open items carried forward as the matrix itself is drafted.

## Scope: flavors 1 & 2 only

Organizations approaching AI and software delivery generally fall into three patterns:

1. **Greenfield AI-native** — building a new SDLC from scratch around an AI-native baseline.
2. **Native AI-native** — already operating with AI-native assumptions, seeking to baseline and plan further.
3. **Transitioning/AI-enabling** — a traditional SDLC adopting AI tooling incrementally.

This model targets flavors 1 and 2, which are treated as essentially the same target state (differing mainly in starting friction, not destination). As of v1.1, flavor 3 has a named position rather than a place in scope: **Pre-AI**, the threshold state — the starting position named honestly, where existing engineering discipline predicts transition *velocity* rather than starting *level*, and Level A is the first milestone of adoption, not a judgment of failure (see the Pre-AI section of the matrix). The model still does not attempt to be flavor 3's transition playbook: flavor 3 is explicitly out of scope. It is already well-served by a large and active body of consulting and vendor material (the Harness Model, ELEKS' AI-SDLC model, Grid Dynamics' 8-dimension assessment, the CMU SEI/Accenture AI Adoption Maturity Model, and others), and the transition dynamics from a pre-AI SDLC are sufficiently different — and sufficiently uncertain — to warrant a separate treatment entirely. Whether flavor 3 organizations can reach flavor 1/2 states, and at what cost, remains an open empirical question that this model does not attempt to answer.

The competitive framing motivating this scope: for organizations whose product is an AI capability (per Bessemer's definition — remove the AI and the product ceases to exist), AI-native delivery capability is not optional, it is definitional. For organizations where AI is one capability within a broader workflow, the gap matters but other moats (proprietary data, workflow embeddedness, switching costs) may offset it longer. Either way, the 13 dimensions below describe the capability profile of a flavor 1/2 organization — assessed independently, not against a flavor 3 starting line.

## Research finding

A review of currently published AI/SDLC maturity models (CMU SEI/Accenture AI Adoption Maturity Model, DORA AI Capabilities Model, ELEKS AI-SDLC Maturity Model, Gigacore AI Maturity Model, AWS AIPDLC, and the V-Bounce model) found no existing framework that combines:

- A flat set of capability dimensions spanning the full lifecycle, organized into a handoff structure (sequential, governing, and loop-closing relationships) rather than left unordered
- Independent maturity scoring per dimension (not a single linear ladder)
- The product-to-engineering handoff treated as a first-class, explicitly governed transition (the fused D4/D5/D7 specification motion)
- Graduated, adjacent-state granularity in the spirit of CMMI, rather than pinnacle ("AI-autonomous") description

Existing models tend toward one of two failure modes relative to this goal:

1. **Pinnacle description without granularity** (e.g., five-level models culminating in "AI-autonomous" or "AI-native" states) — tells an organization it isn't at the top, without identifying a costable next step.
2. **Cross-cutting enablers framed as a checklist** (e.g., DORA's seven AI capabilities — clear AI stance, healthy data ecosystems, AI-accessible internal data, strong version control, small batches, user-centric focus, quality internal platforms) — these are present/absent practices that amplify outcomes across all dimensions, but are not themselves a graduated lifecycle capability model.

The gap: CMMI's diagnostic posture (graduated, adjacent, costable current-to-next-state assessment) has not been applied to the set of SDLC capability dimensions that AI materially changes.

## Design principles

1. **Diagnostic, not aspirational.** Each dimension describes a current-state read, not a pinnacle. The model's value is locating where an organization sits now, not selling a destination.
2. **Adjacent achievability.** Maturity progression within a dimension moves between realistically adjacent states. Each step up implies a knowable, roughly costable set of changes — new practices, tooling, roles, or skills — not "more AI, more thoroughly."
3. **Context-relative targets, not universal ones.** A given level is not inherently good or bad — it is appropriate or inappropriate for an organization's size, regulatory context, and risk tolerance. The model does not penalize an organization for stopping at a lower rung when that is the right tradeoff for its context.
4. **Capabilities, not outcomes.** Following DORA's separation of capabilities from outcomes, these 13 dimensions describe what the delivery system is capable of doing. Outcome metrics (velocity, stability, defect rates) and team-capability/skill scoring are separate layers, to be addressed later.
5. **Independent axes.** Each dimension can mature independently of the others. An organization can be advanced in one dimension and nascent in another; the dimensions are not a single linear ladder.
6. **AI-nativeness as a property within dimensions, not the axis itself.** The dimensions describe lifecycle capabilities that existed pre-AI; what AI changes is how each capability is exercised. The maturity axis is capability sophistication, not AI adoption intensity.
7. **Boundaries and handoffs are first-class.** Where AI collapses traditional role boundaries (e.g., a PM producing a functional prototype that previously would have been a written spec), the relevant dimension measures the governance of that handoff explicitly, rather than assuming the boundary still exists in its pre-AI form.
8. **Levels are effort-equiprobable, by design, knowing it won't be exact.** Within a dimension, the level of effort (LOE) to move from one level to the next is targeted to be roughly consistent across the ladder — B→C should represent a similar lift to D→E. This will never be strictly true, and some transitions are genuinely "lumpy" (a single infrastructure or tooling investment that delivers more than one level's worth of capability at once). Where that happens, it should be named explicitly as a lumpy transition rather than papered over with artificially smooth level descriptions.
9. **Adjacent dimensions should not diverge by more than one level.** The model's diagnostic value depends on dimensions that hand off to each other (see *Handoff structure*, below) staying within roughly one maturity level of their neighbors. A dimension at level E whose immediate handoff partner is at level C is not very useful in practice — the high-performing dimension's output can't be consumed by the lagging one. This is a property of the handoff graph, not strictly the 1–13 numbering, though the numbering is a reasonable working proxy for it.
10. **This model is a living document, not a stable standard.** Unlike CMMI, which has remained relevant for decades, this model describes a landscape (AI-native SDLC practice) that is evolving month-to-month and will continue to do so for years. Level definitions — especially at the upper end (D/E) — should be expected to require revision as field practice advances. Where research suggests the current top of a ladder may already be surpassed by emerging practice, that should be flagged explicitly (see *Open items*) rather than treated as a permanent ceiling.

## The 13 capability dimensions

**D1. Market discovery & definition**
The capability to identify, size, and validate market opportunities (TAM/SAM/SOM, market trends, opportunity framing) through a continuous, AI-assisted discovery loop that directly feeds requirements work (D4).

**D2. Buyer/user persona development**
The capability to research, model, and maintain live representations of target users and buyers, extensible as a shared asset across Product, Marketing, and Sales Enablement. Pairs closely with D1 on the continuity/dynamism axis.

**D3. Positioning & competitive intelligence**
The capability to define product differentiation and maintain that positioning against a continuously monitored competitive landscape that actively informs roadmap decisions.

**D4. Requirements management (specification quality & traceability)**
The capability to author precise, testable, machine-actionable specifications with full traceability from source through delivery, such that specification quality directly gates generation quality.

**D5. Prototyping & the prototype-to-code boundary**
The capability to produce functional prototypes for validation, and to govern — explicitly and consistently — whether and how those prototypes transition into production code.

**D6. Architecture governance**
The capability to define, encode, and enforce architectural standards and design judgment ("taste") across a codebase as code is generated, modified, or extended by agents.

**D7. Test-driven development (specification-driven verification)**
The capability to couple test/specification authoring with implementation as one motion, and to scale verification coverage as generation volume scales.

**D8. Code verification & review**
The capability to apply human and automated judgment to generated code for correctness, security, maintainability, and alignment with intent, scaled appropriately to risk.

**D9. Environment management**
The capability to provision, configure, and maintain the environments (dev/QA/staging/prod, etc.) through which code moves, including parity, ephemerality, self-provisioning, and cleanup.

**D10. Release discipline**
The capability to govern how validated changes move into production — gating, approval, rollback, compliance, and release communications — as a compressible, on-demand cycle rather than a fixed cadence.

**D11. Security & compliance**
The capability to identify, assess, and mitigate security and regulatory risk introduced at any stage of the lifecycle, including risks novel to AI-generated artifacts and agent tooling. (Previously deferred; unblocked — see *Open items*.)

**D12. Instrumentation & observability**
The capability to monitor, trace, and evaluate system behavior in production, and to structure organizational knowledge (decisions, plans, metrics) for equal consumption by humans and agents, closing the loop back to upstream dimensions (notably D1). If AI is only used to generate deterministic artifacts (e.g., code, tests, IaC) and is not in the runtime decision path, production observability requirements stay primarily classical; AI-specific tracing/evaluation applies at build time.

**D13. Feedback loop velocity — the executive anchor**
The end-to-end cycle time from signal (market, user, incident, failure) to shipped response, as a property of the whole system rather than any individual stage. Distinguishes a "merely AI-native" organization from a "competitively AI-native" one — an org can score well on D1–D12 individually and still have a slow composite loop if the dimensions don't hand off to each other quickly. D13 is listed last but is not the least: it is the capstone the other twelve feed, and the single dimension an executive can anchor the whole model to — if cycle time can be accurately measured and safely manipulated, an organization can deliver functionality better and faster than the rest of its market. (Elevated per reviewer feedback — see `feedback_log.md`, F-004.)

## Handoff structure

The 13 dimensions are not a flat, unordered list — they form a working system with three kinds of relationships:

**Sequential handoffs (the "main line").** D1 → D2 → D3 feed forward into a fused specification motion (D4 / D5 / D7), which at high maturity produces a specification, a functional prototype, and an initial failing test as a single governed step rather than three separate handoffs — the system is sequence-agnostic about which artifact initiates the others (see D4-E). Downstream, D8 (verification) gates D9 (environments) and D10 (release), which at high maturity run in parallel/continuously (this is literally what happens in CI/CD — every release exercises both simultaneously).

**Governing/constraining relationships.** D6 (architecture governance) sits over the boundary between the upstream specification motion and downstream verification — constraining both what D5 prototypes can become production code and what D8 verification enforces. D11 (security & compliance) is expected to behave similarly, as a cross-cutting constraint touching D8–D10 (agent identity mapping, PR gating, supply-chain risk for agent tooling) — to be confirmed as D11 is drafted.

**Loop-closing relationships.** D12 (instrumentation & observability) receives signal from D9/D10 (production telemetry) and feeds back to D1, closing the discovery loop. D13 (feedback loop velocity) is not a node in the sequential chain — it is the measurement of the whole graph's transit time, sitting outside/around the other 12 dimensions.

A diagram of the sequential main line (D1–D3 → fused D4/D5/D7 motion; D6 → D8 → parallel D9/D10 → D12 → back to D1, with D13 wrapping the whole graph) is included in this repo as `sdlc_handoff_diagram.png`.

## Open items

- **D9 (Environment management) — top of ladder likely understated.** A landscape check against current agentic-infrastructure practice (Bunnyshell, Coder, shadow-deployment patterns) suggests our current D9-E ("ephemeral, self-provisioned, automated cleanup") may already describe a D-level capability relative to emerging practice. The field is converging on additional requirements at the top end: sub-second provisioning (not just "on demand"), and rollback-to-checkpoint as the primary recovery/debugging strategy rather than fix-in-place ("every failure is disposable — destroy the sandbox and start fresh"). A separate, actively-debated architectural pattern — shadow deployments within shared infrastructure rather than full ephemeral clones — may represent either an alternative E or a cheaper, less-isolated D. D9's D/E levels should be revisited once there is more settled practice to anchor to (see Design Principle 10 — this is an expected consequence of the model being a living document, not a flaw in the current draft). D10-E and D11-E were drafted with awareness of this same "boundary-checking becomes insufficient, gate must extend into the runtime/live signal" pattern — if D9's D/E levels are revised, D10/D11's analogous transitions should be checked for consistency.

- **D6's C→D and D11's C→D — candidate "lumpy" transitions.** Per Design Principle 8, both of these transitions ("turn tribal taste into agent-actionable encoded rules" for D6, "make PR gates mandatory + inventory agent tooling as supply chain" for D11) may represent a larger-than-average lift — possibly the same underlying organizational shift (moving from advisory/manual enforcement to mandatory/structural enforcement) viewed from two dimensions. Worth flagging to reviewers rather than smoothing over.

- **D4/D5/D7 fusion at E** — resolved via shared "sequence-agnostic" property language, each dimension describing the same fused motion from its own vantage (specification/prototype/test) without restating the others' content. **D1/D2/D3 fusion at E** — resolved via shared "converged intelligence layer" object language (anchored to a real-world reference: expona.ai), each dimension describing the same converged layer from its own input lens (market/buyer/competitive) without restating the others' content. Both patterns may be worth revisiting as a named structural feature of the model — dimensions that are organizationally distinct at low maturity but converge into one system at E, either around a shared property (D4/D5/D7) or a shared object (D1/D2/D3). D9/D10 (parallel/continuous in CI/CD) is a third instance of dimensions converging, though without merging language at the E-level text itself.

- **D5-E — discard-and-rebuild is preserved, not eliminated.** D5-E was deliberately worded so that fusion (per D4/D5/D7) makes the carry-forward-vs-discard decision cheap and fast, without implying that discarding a prototype is itself a sign of immaturity. Per Design Principle 3 (context-relative targets), "build to understand, then throw away" remains a legitimate choice at any maturity level.

- **D12/D13 — built on a non-determinism-location principle.** D12's ladder is organized around the question "where does non-determinism currently live in our delivery system — build-time generation (D4-D8) or runtime decisions (D9-E/D10-E)?" rather than "do we have RAG/trace/eval." This deliberately separates D12 (observability of the org's own delivery system) from the separate question of whether the org's product has AI in its runtime path (which is a product-architecture question, out of scope for this model). D13 depends on D12 reaching roughly C/D before stage-resolved cycle-time attribution is possible — D12 and D13 are closely coupled rung-for-rung.

- **D8/D11 relationship.** D8's "structurally independent AI review layer becomes enforceable" (C→D) and D11's "PR gates become mandatory" (C→D) are plausibly the same organizational shift viewed from two dimensions (review and security). D8's definition carries a permanent cross-reference note: review of generated code (D8) is not a substitute for execution containment (D11) at any maturity level — the two dimensions address different surfaces.

**Carried forward, not yet addressed:**

- Whether DORA's seven cross-cutting capabilities should eventually inform a separate "modifier" layer distinct from the 13 lifecycle dimensions.
- Team capability/skill scoring and outcome metrics remain explicitly out of scope for this phase.

## Status

Locked baseline. All 13 dimensions defined A–E. The open items above are carried forward deliberately, not left unresolved by accident — per Design Principle 10, this model is a living document, and revision driven by reviewer feedback and field evolution is expected. Feedback and its disposition are tracked publicly in `feedback_log.md`.

---

## Files in this repo

- `ai_native_sdlc_maturity_model.xlsx` — the full A–E maturity matrix for all 13 dimensions (D1–D3 pending regeneration — see `shared_intelligence_layer.md`)
- `ai_native_sdlc_maturity_model.md` — markdown version of the matrix for D4–D13; D1–D3 inherited by reference (2026-07-23)
- `shared_intelligence_layer.md` — canonical D1–D3 source (`STD-SHARED-INTELLIGENCE` v1.0.0), shared with the AI-Native PDLC Maturity Model
- `short_form.yml` — one-sentence-per-cell compression of all 13 dimensions, derived from this matrix and `shared_intelligence_layer.md`, for consumption by external sites (e.g. aimaturitymodels.com's Whole-Model View); not a source of truth, regenerate if it diverges
- `d1-d3-superseded-v1.1.0.md` — predecessor D1–D3 text, preserved verbatim as historical evidence, not current authority
- `sdlc_handoff_diagram.png` — visual diagram of the handoff structure described above
- `sdlc_handoff_diagram.html` — visual diagram of the handoff structure described above
- `transition_character_grid.xlsx` — working document to capture maturity transition lift characteristics
- `transition_character_grid.md` — markdown version of working document to capture maturity transition lift characteristics
- `feedback_log.md` — public log of feedback received and how each point was resolved
- `CHANGELOG.md` — version history from the v1.0.0 baseline
- `README.md` — Start here
- `LICENSE.md` — CC BY 4.0

---

*AI-Native SDLC Maturity Model © 2026 by David Facer is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).*
