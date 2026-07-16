# AI-Native SDLC Maturity Model — Transition Character Grid

## Purpose

This is a working artifact, not a finished assessment. For each of the 13 dimensions, it provides space to characterize the *nature* of the lift required for each level transition (A→B, B→C, C→D, D→E) — not a numeric cost estimate, but a category that indicates what *kind* of organizational effort the transition represents.

See `ai_native_sdlc_maturity_model.md` for the full A-E content this grid characterizes, and `ai_native_sdlc_maturity_model.xlsx` for the source-of-truth spreadsheet.

This grid operationalizes two things from the model's design principles:

- **Design Principle 8** (levels are roughly effort-equiprobable within a dimension, with lumpy transitions named explicitly rather than smoothed over) — this grid is where lumpy transitions get identified and characterized.
- The **"Stranded / Starved / Harmonized" diagnostic framing** — once transitions are categorized, an organization's profile across all 13 dimensions can be read for stranded capability (advanced dimensions whose value can't be consumed by lagging neighbors), starved dimensions (advanced downstream capability fed by a low-fidelity upstream bottleneck), or harmonized balance (consistent maturity with no stranded capital and no starvation — which Design Principle 3 treats as a legitimate target, not a failure to reach E).

## How to use this grid

For each dimension's four transitions, select the category that best characterizes the **primary** nature of the lift. Transitions often involve more than one category — pick the one that dominates cost and effort, and use the Notes column for anything that doesn't fit cleanly or is genuinely context-dependent.

**Disagreement between reviewers on a given transition's category is itself useful data** — it suggests the transition's character is context-dependent, which is worth surfacing rather than resolving prematurely.

A useful framing question when working through this grid: *"When you look at the transition from Level C to Level D across these dimensions, where do you see the most significant 'lumpy' capital expenditure, and where do you see the transition being purely operational/behavioral?"*

---

## Transition Character Categories

| Category | Description |
|---|---|
| **Tooling/Procurement** | Primarily acquiring, configuring, or licensing tools/platforms. Cost is largely vendor spend and integration time; low organizational behavior change required. |
| **Process/Policy** | Primarily defining, documenting, and adopting new processes, policies, or decision criteria. Cost is largely time/effort to design and roll out; tooling impact is secondary. |
| **Behavioral/Cultural** | Primarily a shift in how people work day-to-day — habits, norms, or roles change even if tools and policies already exist. Cost is largely change-management and adoption time. |
| **Structural/Architectural** | Primarily a change to system architecture, organizational structure, or a foundational capability that other transitions depend on. Often the heaviest lift; candidate for "lumpy" per Design Principle 8. |
| **Other (see notes)** | Doesn't fit cleanly into the above, or is genuinely context-dependent — use the Notes column to explain. |

---

## The Grid

| Dimension | A→B | B→C | C→D | D→E | Notes |
|---|---|---|---|---|---|
| **D1.** Market discovery & definition | | | | | |
| **D2.** Buyer/user persona development | | | | | |
| **D3.** Positioning & competitive intelligence | | | | | |
| **D4.** Requirements management (specification quality & traceability) | | | | | |
| **D5.** Prototyping & the prototype-to-code boundary | | | | | |
| **D6.** Architecture governance | | | | | C→D flagged as candidate lumpy/structural transition (encode tribal taste as agent-actionable rules). |
| **D7.** Test-driven development (specification-driven verification) | | | | | |
| **D8.** Code verification & review | | | | | |
| **D9.** Environment management | | | | | D→E may already be understated relative to frontier practice (sub-second provisioning, rollback-as-recovery) — revisit before treating as a fixed lift. |
| **D10.** Release discipline | | | | | |
| **D11.** Security & compliance | | | | | C→D flagged as candidate lumpy/structural transition (mandatory gates + supply-chain inventory) — possibly same underlying shift as D6 C→D. |
| **D12.** Instrumentation & observability | | | | | |
| **D13.** Feedback loop velocity | | | | | Transitions depend heavily on D12 reaching C/D first (stage-resolved attribution) — character here may be more about D12 dependency than independent D13 effort. |

---

## After the grid is filled in

Once populated, the grid can support:

- **Identifying lumpy transitions empirically** — any cell categorized as Structural/Architectural is a candidate. Comparing against the flagged candidates above (D6 C→D, D11 C→D, D9 D→E) tests whether our reasoning-based flags hold up against domain experience.
- **The "Stranded / Starved / Harmonized" diagnostic** — given an organization's current 13-dimension profile, transitions categorized as cheap (Behavioral/Cultural or Process/Policy) represent quick wins; transitions categorized as Structural/Architectural represent capital commitments that should be planned and budgeted separately, and are the ones most likely to create or resolve stranded/starved conditions in adjacent dimensions.
- **A sane pathway** — not a single prescribed sequence, but a way to separate "what can move now, cheaply" from "what requires a planned investment," informed by each organization's actual current profile and how the 13 dimensions hand off to, constrain, and converge with each other (see `ai_native_sdlc_maturity_model.md`).

---

*Status: Empty grid with flagged candidates noted. Intended to be populated with input from domain reviewers — disagreement is informative, not a problem to resolve before populating.*
