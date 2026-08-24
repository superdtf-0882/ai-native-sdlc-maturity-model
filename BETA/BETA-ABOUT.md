# Seminum — Beta

This note travels **with** the archive, not inside it. Everything here is
about the arrangement between us; everything about the framework itself is
in the archive, in `README.md`, `CLAUDE.md` and `MANIFEST.md`.

---

## What this is

Seminum is a **seed**: a governance framework packaged so that an AI coding
agent can unpack it into an empty repository and bootstrap a working
practice from nothing. It carries a small set of rules, principles,
standards and constraints, two role charters, a worked example, and a
toolchain that checks whether the resulting practice is actually
functioning rather than merely present.

It came out of an enterprise-architecture practice that governs its own
work this way. The framework is the part that generalises; the practice's
own content stays behind.

## What this is not

- **Not a product, and not supported.** There is no roadmap commitment, no
  release cadence, and no undertaking to fix what you report.
- **Not complete.** See *What's actually in the box* below — the honest
  number is that about 7% of the originating corpus travels.
- **Not licensed yet.** See *Licence and permissions*.
- **Not a test of whether you can run it.** Five AI agents have already
  germinated practices from it in isolated repositories. That question is
  answered. See *What we're actually asking*.

## Licence and permissions

**The archive carries no licence file, and that is deliberate rather than
an oversight.** The intention is CC BY 4.0 at v1.0. It is not applied now,
because a public licence is irrevocable and a beta ought to be something
you can take back.

So the beta runs on this note rather than on a licence. **You may:**

- unpack it, read it, and run every tool in it;
- germinate a practice from it and use that practice for real work;
- modify your copy however you like;
- keep it after the beta ends.

**The beta runs 30 days from the date you receive it.** We will come back
to you by then — to close it, extend it, or apply the licence.

**We ask that you not redistribute the archive or its contents during the
beta.** That request stands until you hear from us — **not until the
thirty days are up.** The window is our commitment to come back to you;
the request ends when we actually do, which is something you can observe.
If a licence is applied at v1.0, it governs from that point and the
request lapses with it.

If anything in the framework proves useful to you independently of this
arrangement, say so and we'll sort out the permission properly rather than
leaving you relying on an email.

## What's actually in the box

The archive is a **subset** of a larger corpus, and the packager decides
what travels by a per-item declaration rather than by judgment at pack
time. The current figures:

| | |
|---|---|
| items and sheet headers that ship | **28** |
| total in the originating corpus | **384** |
| | **7.3%** |

Concretely: nine Rules, five Principles, one Constraint, four Standards,
both role charters, a charter template, and a worked governance cycle.
`MANIFEST.md` inside the archive breaks this down per file and says why
each file is partial.

**We are telling you this up front because a thin payload is easy to
mistake for a broken build.** It is neither a bug nor an accident — but it
is a real limitation, and question 3 below is aimed squarely at it.

## Known rough edges

Stated rather than fixed, because a beta may legitimately ship with known
defects as long as you know about them:

- **The corpus is a spine, not a body.** Most of the governance content is
  withheld as practice-specific.
- **One tool reaches the internet.** `checkpoint-b.js` fetches a public
  news feed to demonstrate handling untrusted input. It sends one GET, uses
  no credentials, and treats everything it receives strictly as data. It is
  the only outbound connection in the archive. If you'd rather it didn't
  run, don't run it — nothing else depends on it.
- **A signal's label overstates what it checks.** `checkpoint-a.js`
  reports *"present with no `INT-*` items"* but counts every item in the
  intent register regardless of its id. If you name your intents with some
  other prefix the count is still correct and the label is not.
- **The germination check exits non-zero on a fresh seed, on purpose.**
  That is documented in `MANIFEST.md` and is not a failure — it clears as
  soon as you author your own intent.
- **It will then keep asking one question.** Until you set
  `germination_acknowledged` in `corpus/intent_register.md`, every run
  ends by asking whether you judge the practice live. **It asks; it never
  fails** — the exit code stays truthful about mechanics, and declaring
  the practice live is your act rather than something the tool infers
  from how old your repository looks.

## What we're actually asking

Five agent-driven germinations have already answered *does it work*. They
found real defects and the framework is better for it. **What no agent
could answer is whether a person with judgment would adopt this** — every
one of them was obliged to try, and none could say it wasn't worth the
effort.

So the question this beta asks is: **would you adopt this, and what stops
you?**

Four specific questions, because specific questions get judgments and open
feedback gets impressions:

1. **After reading the arrival layer — `README.md`, `CLAUDE.md`,
   `MANIFEST.md` — what did you think this was for?**
2. **What would you need before running it on real work?**
3. **What is missing that you expected to be there?**
4. **Where did the governance feel like overhead rather than protection?**

Question 4 is the one we most want answered honestly. The framework's whole
claim is that the discipline pays for itself; if it doesn't, the place
where it stops paying is the most useful thing you can tell us.

## Getting started

Everything you need is in the archive. In short:

```
tar -xzf seminum.tar.gz
cd seminum/tools && npm install && cd ..
node tools/validate-corpus.js
node tools/checkpoint-a.js
```

Then read `CLAUDE.md`, which is written for the agent rather than for you
and is the honest description of how the thing is meant to be driven.

## Sending things back

There is no form and no tracker. A conversation is fine — notes, a call, a
diff, whatever is least work for you. If you want to send something
written, prose against the four questions above is more useful than a bug
list.

---

*Nothing in this note grants rights beyond those stated above, and the
archive carries no licence. If you need something in writing that this
note doesn't cover, ask.*
