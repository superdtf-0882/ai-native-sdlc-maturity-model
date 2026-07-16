# AI-Native SDLC Maturity Model — Feedback Log

## What this is

A running, public log of feedback received on the model during its introduction and evaluation period. Each entry tracks a point of feedback through to its resolution — adopted, deferred to a later version, or declined with reasoning given. The goal is to make the model's evolution visible and auditable, in keeping with its own design principle that this is a living document, not a fixed standard (see the working framework material for more on that).

If you've given feedback and want to see where it landed, or you're considering contributing and want to see how past feedback has been handled, this file is the record.

**Attribution note:** contributors are credited by first name only. If you'd like fuller attribution, less attribution, or removal of an entry referencing you, open an issue or reach out directly.

## How this works

Each entry is a piece of feedback from one source, broken into the discrete points worth tracking individually. Every point gets a **status**, and most eventually get a **resolution** — what we decided and why, or a pointer to where it landed (a model revision, a v2.0 backlog item, a "no action" with reasoning).

**Statuses:**
- 🆕 **New** — received, not yet discussed
- 🔍 **Triaged** — categorized/understood, not yet decided
- ✅ **Resolved** — decision made, action taken or explicitly declined
- 🕒 **Deferred** — good idea, intentionally pushed to a later version
- 🔗 **Merged** — turned out to be the same thread as another entry

Weekly batch review: scan for 🆕 and 🔍 first. 🕒 entries are worth a periodic second look in case "later" has arrived.

---

## Open (🆕 / 🔍)

### F-001 — Context engineering vs. context propagation (self-identified, ongoing)
**Status:** 🔍 Triaged
**Source:** Internal — noticed while comparing Thomas's feedback (S-001, point 4) against the SaaS Product Engineering function model's interpretive layer.
**Point:** Thomas's "context engineering" (context quality as a cause that propagates into specs/code/tests/decisions) may or may not be the same thread as the function model's paramorphic interpretive layer (context propagation: Historical reconciliation, Constraint translation, Signal triage, Conflict resolution). Tentative shared name offered to Thomas: "continually available context quality." Not yet confirmed whether these are the same concept from two angles or just superficially similar.
**Next step:** Compare both documents side by side properly; await Thomas's reaction to the proposed name/framing.

---

## Deferred (🕒)

### F-002 — Flavor 3 / transition-boundary expansion
**Status:** 🕒 Deferred to v2.0
**Source:** Thomas, LinkedIn feedback, 2026-06-16 (recommendation 1, and recommendation 5 re: legacy/reverse-engineering, which is largely the same issue)
**Point:** The model scopes out "flavor 3" organizations (traditional SDLC transitioning toward AI-enabled delivery) and legacy/reverse-engineering scenarios. This may limit adoption, since many organizations want exactly this transition guidance.
**Resolution:** Acknowledged as a fair challenge. Scoped out deliberately because that space is already well-served (Harness Model, ELEKS, DORA, CMU SEI/Accenture AI Adoption Maturity Model). Expanding scope to cover the transition path is a real v2.0 candidate, once v1 has real-world mileage.

### F-003 — Platform ownership & people/operating-model layer
**Status:** 🕒 Deferred — needs design work, not a quick fix
**Source:** Thomas, LinkedIn feedback, 2026-06-16 (recommendations 2 & 3)
**Point:** The model is strong on lifecycle capabilities but doesn't name *who* owns a capability's evolution (standards, guardrails, agent permissions, context sources, toolchain integration, continuous improvement backlog) or address role clarity, incentives, learning loops, and leadership sponsorship as organizations shift.
**Resolution (partial):** Acknowledged as a real gap, not a deliberate omission. As a diagnostic, the model has deliberately avoided prescribing organizational structure — but maturity itself implies asking who owns a capability's evolution, and where that accountability sits is itself a maturity signal worth surfacing. Not yet decided whether this becomes a cross-cutting note (like D6/D11's relationship) across relevant dimensions, an explicit "ownership" sub-question within each dimension's maturity indicators, or something else. Needs real design thought before resolving further.

---

## Resolved (✅)

### F-004 — D13 as executive anchor
**Status:** ✅ Resolved — reflected in v1.0 (README framing, 2026-07-15)
**Source:** Thomas, LinkedIn feedback, 2026-06-16 (recommendation 6)
**Point:** D13 (feedback loop velocity) is the dimension that connects the delivery system to competitiveness, and could become the executive anchor for the whole framework rather than sitting as the 13th of 13 dimensions.
**Resolution:** Agreed. Aligns with internal framing of the AI-Native Delivery Cycle as the differentiator — if cycle time can be accurately measured and safely manipulated, an organization can deliver functionality better and faster than the rest of the market. D13 should be elevated in how the model is presented/discussed, even if its position in the numbered list doesn't change. **Reflected 2026-07-15, as part of the v1.0 lock:** the README's Purpose section now establishes D13 as the model's executive anchor, and D13's own entry is titled and framed as the capstone the other twelve dimensions feed. Position in the numbered list unchanged, as resolved.

---

## Reference: full source feedback

### S-001 — Thomas (LinkedIn), 2026-06-16
Six numbered recommendations plus a closing caution about balancing practitioner specificity with executive narrative. Broken into entries F-002, F-003, F-004 above; recommendation 4 (context engineering) generated F-001 above; the closing caution (avoid becoming too internally focused on SDLC mechanics) is not yet broken into its own tracked entry — captured here for now.

**Untracked thread from S-001:** the closing point about serving both practitioner and executive audiences simultaneously — worth its own entry if it doesn't naturally resolve as a side effect of F-003/F-004.

---

*Next batch review: weekly. Add new entries as feedback arrives; don't wait for the batch review to log something, just to discuss/resolve it.*
