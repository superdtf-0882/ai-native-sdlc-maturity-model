# Changelog — AI-Native SDLC Maturity Model

All notable changes to the model are documented here. The model is a living document by design (Design Principle 10); this file is where its evolution is visible at a glance. Feedback and its disposition are tracked separately in `feedback_log.md`.

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
