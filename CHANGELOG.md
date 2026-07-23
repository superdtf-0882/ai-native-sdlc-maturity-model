# Changelog — AI-Native SDLC Maturity Model

All notable changes to the model are documented here. The model is a living document by design (Design Principle 10); this file is where its evolution is visible at a glance. Feedback and its disposition are tracked separately in `feedback_log.md`.

## v1.2.0 — 2026-07-23

D1–D3 reconciled and extracted to a new canonical source shared with
the AI-Native PDLC Maturity Model. Ratified by David Facer ("I ratify
the D1–D3 reconciliation — David, 7/23/26").

Changed:
- D1 (Market discovery & definition), D2 (Buyer/user persona
  development), and D3 (Positioning & competitive intelligence) are
  removed from this file's own text and inherited by reference from
  the new `shared_intelligence_layer.md` (`STD-SHARED-INTELLIGENCE`
  v1.0.0). This matrix no longer maintains its own copy of D1–D3.
- One real maturity-state revision, confirmed by a fifteen-cell,
  five-axis reconciliation against the predecessor text: D2-B moves
  from "AI assistance is ad hoc" to "a consistent AI-assisted
  research and synthesis method," for coherence with D1-B and D3-B,
  which already used identical cadence/method language at that
  letter. The other fourteen cells carried forward unchanged or with
  wording clarification only — no other maturity-state shift.

Added:
- `shared_intelligence_layer.md` — the new canonical D1–D3 source,
  full reconciliation record, and the canonical-source rule governing
  it (sole source of truth; SDLC and PDLC inherit by reference;
  derived distributions may embed rendered copies but are not
  independently editable; changes propagate atomically).
- `d1-d3-superseded-v1.1.0.md` — the predecessor D1–D3 text, preserved
  verbatim as it read through the locked `v1.1.0` release, kept as
  regression control and historical evidence, not current authority.

Unchanged: D4–D13 and all A–E level definitions for those dimensions;
the Pre-AI/Exempt mechanics; all prior assessments against D4–D13
remain valid. Assessments scored against the old D1–D3 text should be
read through this changelog, the same way v1↔v2 stratum letter
changes are read through their own translation table elsewhere in this
practice's governance.

Provenance, stated precisely: the reconciliation methodology and
framing came from a conversation between David Facer and Craig (an
ontologist). The fifteen-cell analysis and disposition record is
David Facer's own direct work, not delegated. Full record:
`shared_intelligence_layer.md`'s own Reconciliation Record section,
and the governing corpus at
`briefs/2026-07-23-d1-d3-reconciliation/` (`OKF TOGAF` repo).

## v1.1.0 — 2026-07-21

Added:
- Pre-AI threshold state (outside the A–E scale): honest on-ramp
  position for organizations beginning AI adoption; transition
  velocity note distinguishing existing discipline (predicts speed)
  from starting level.
- Exempt designation (governed stance, per dimension): deliberate,
  constraint-cited exclusion of a dimension from AI adoption.
  Requires citable regulatory, contractual, or corporate-policy
  constraint; excluded from aggregates; always rendered; reviewable.
- Assessment schema: Pre-AI and Exempt(constraint-ref) as legal
  values; readiness_note and review_trigger fields.

Unchanged: all thirteen dimensions; all A–E level definitions;
all prior assessments remain valid.

Acknowledgments: the Exempt mechanism was driven by practitioner
feedback from a regulated contact-center context — the observation
that some dimensions can be necessarily AI-free by regulatory or
corporate requirement, and that a credible model must govern that
case rather than penalize it.

## v1.0.0 — 2026-07-15

First locked baseline. The 13 capability dimensions and their A–E maturity ladders are locked as drafted — content unchanged from the reviewed strawman. Changes in this release are currency and packaging, not model content:

- Strawman framing retired (draft banner, "Straw-man complete" status lines).
- Filenames normalized: `ai_native_sdlc_maturity_model_STRAWMAN.xlsx` → `ai_native_sdlc_maturity_model.xlsx`, `ai_native_sdlc_maturity_model_MATRIX.md` → `ai_native_sdlc_maturity_model.md`; internal references fixed.
- Source-of-truth declaration inverted: the markdown matrix governs; the spreadsheet is a derived rendering.
- D12 definition synced: a scoping sentence (build-time vs. runtime-decision-path observability) that existed only in the spreadsheet now appears in the markdown matrix and README.
- D13 (feedback loop velocity) established as the model's executive anchor in the README, per reviewer feedback (`feedback_log.md`, F-004).
- License replaced with the canonical CC BY 4.0 legal code (machine-detectable).
- Link added to the live self-assessment tool.
- Stale Word-export `index.htm` removed.

Known open items (D9 top-of-ladder, lumpy-transition candidates, and others) are documented in the README's *Open items* section and carried forward deliberately.

## Pre-1.0

Strawman drafted June 2026; shared with select practitioners for review via LinkedIn 2026-06-16. Reviewer feedback tracked in `feedback_log.md` from that date.
