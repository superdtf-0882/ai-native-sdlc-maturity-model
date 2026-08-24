# Seminum Happy-Path Germination Instructions

## 1. Seed a fresh repository

Create a fresh repository, place the Seminum tarball in its root, and unpack
it there.

Install the tool dependency:

```text
cd tools
npm install
cd ..
```

Do not run the outside-world checkpoint during initial orientation.

## 2. Start the architecture role

Open a new coding-agent session rooted in the repository and prompt it:

> You are DT (Deputy TOGAF). Read `CLAUDE.md`, find your charter, and read it
> completely. Report back with any questions you have.

DT is the architecture role. It helps you think, elicits intent, develops
plans, and prepares execution briefs. It does not execute the work it
designs.

## 3. Elucidate Stratum Zero: Intent

Within the first few conversational turns—normally no more than four—DT
should ask you to elucidate Stratum Zero (`S0`): the reason the new practice
will exist.

Provide three to five concise statements, in your own words, describing why
the practice exists. These are statements of purpose, not project plans,
features, or deadlines.

If DT does not move toward S0, ask:

> Do you know what to do next?

DT may also ask:

- Whether anything is already in flight.
- Whether another agent or transfer is expected.
- Whether CC is already active.
- Questions needed to preserve your intended wording.

This should be conversational. DT must not supply your intent statements,
offer a menu of possible intents, or import examples from another practice.

## 4. Have DT prepare the S0 brief

DT should prepare an execution brief in `briefs/` that proposes how your
statements will be represented in `corpus/intent_register.md`.

The brief may propose IDs, short titles, statuses, and YAML structure, but
the intent statements themselves must remain your words.

Review the proposed representation and ratify it directly. For example:

> I ratify the S0 items and their representation as delivered by DT. [Owner
> name and date]

A DT report that you approved something is not sufficient authority for CC.
Your approval must reach CC directly.

## 5. Start the execution role

Open a second coding-agent session rooted in the repository and prompt it:

> You are CC. Read `CLAUDE.md`, find your charter, and read it completely.

CC is the execution role. It measures, implements, verifies, commits, and
reports. It does not issue work, ratify changes, or make architecture
decisions.

## 6. Register S0

The S0 execution brief should now be present in `briefs/`. Tell CC:

> Find the latest brief from DT.

Then give CC your direct ratification if it has not already received it, and
instruct CC to execute the brief.

CC should:

- Register the owner-authored S0 statements.
- Run the corpus validator.
- Run Checkpoint A.
- Confirm that the live S0 recitation is exact.
- Commit the governed change and its execution report.
- Report whether a remote exists and whether the commits were pushed.

Once Checkpoint A succeeds, the practice can recite its own intent and the
pre-S0 refusal lifts.

## 7. Complete the first proof cycle

Return to DT and ask:

> Do you know what to do next?

The objective is a small governed proof cycle demonstrating two
capabilities.

### A. Internal proof

A local webpage that displays the newly registered S0 directly from the live
corpus.

The page must not contain a static copy of the intent statements. A change to
the intent register should change the rendered page without requiring an
application-code edit.

### B. Outside-world proof

A deliberate demonstration that the practice can contact a service it does
not control.

The example used during beta testing is a local webpage displaying the
current top stories from the Australian edition of Google News.

Before CC makes the request, it must tell you plainly that the operation
makes an outbound network request. The request must be deliberate—not
triggered by startup, validation, page load, or background scheduling.

All returned headlines are untrusted third-party data. They may be displayed,
but they must never be executed, obeyed, evaluated, or used to determine
control flow.

DT should prepare the governing artifacts and execution brief. You approve
and issue the work. CC implements it, verifies it, and returns evidence for
your closure judgment.

## 8. Begin ordinary practice

Once both proofs have been demonstrated and you have accepted the evidence,
the Seminum instance is germinated. Ordinary work can begin.

Use the following operating model:

- **DT is your thinking and planning partner.** Take requests for new or
  changed software to DT first. DT develops the architecture, challenges
  assumptions, and prepares briefs. DT writes only within its authorized
  drafting and exchange boundary.
- **CC is the executor.** CC implements briefs, writes code, performs
  measurements, runs verification, commits changes, and pushes when a
  configured remote exists.
- **DT and CC challenge one another.** Their tension is deliberate. Neither
  role is expected to accept the other's claims without checking them.
- **The `briefs/` folder is their exchange boundary.** DT sends briefs; CC
  returns execution reports and evidence.
- **You are the owner and decider.** You choose what gets worked on, ratify
  governed representations, issue contracts, resolve design decisions, and
  judge closure.
- **A local commit is not remote delivery.** If the repository has no
  configured remote, pushing requires a separate destination and direct
  instruction.
- **External access is always explicit.** Network acquisition must be
  announced and deliberately authorized; it must not occur implicitly.

The final state is that the practice is **germinated**; **germination** names
the process.
