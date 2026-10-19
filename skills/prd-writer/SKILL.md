---
name: prd-writer
description: >
  Write a product requirements document from scratch through a short,
  adaptive PM intake interview — one question at a time — then apply PM
  best practices to draft a structured PRD. Works from raw notes, a rough
  brief, or nothing at all: if the user pastes existing context, extract
  what's already answered and only ask about the gaps. Use when the user
  asks to write, draft, start, or outline a PRD, product spec, feature
  brief, or one-pager. Also triggers for: "help me write a PRD", "draft a
  spec for X", "I need to write up this feature", "turn this idea into a
  PRD", "help me think through this feature before I write it up", or when
  the user describes a feature or problem and asks for help documenting it.
  Distinct from prd-reviewer, which critiques a PRD that already exists —
  this skill is for building one from zero. Invoke immediately and run the
  interview as part of the skill flow, don't wait for the user to supply a
  fully-formed brief first.
---

# PRD Writer

## What this skill does

Turns a rough idea, a pile of notes, or nothing but a problem statement into
a structured PRD. Runs a short PM intake interview to fill in what's
missing, applies the quality bar a strong PRD needs to survive review, and
drafts the doc in a template built for handoff — engineering can build from
it, leadership can approve it.

This skill writes the first draft. For a critique of a PRD that already
exists, that's `prd-reviewer` — the two are meant to chain: draft here,
then stress-test there before sending it out.

---

## Step 1: Gather context

The goal is to ask as little as possible while still getting a PRD with no
holes in it. Two paths in:

**If the user pastes notes, a brief, a Slack thread, meeting notes, or any
existing context** — read it first. Identify what's already answered and
what's genuinely missing. Only ask about the gaps.

**If the user starts from nothing** — run the interview.

Either way, interview conversationally: one question at a time (a tightly
coupled pair counts as one — "what's the problem, and who has it" is a
single question, not two), and let the user's answers shape what you ask
next. Don't fire off a ten-item questionnaire in one message — that turns a
conversation into a form. Move through these beats, skipping anything
already covered:

1. **Problem and who has it** — what can't the user do today? Whose problem
   is this, specifically — not "users," a segment.
2. **Evidence** — how do you know this is real? Data, support tickets,
   interview quotes, a metric moving the wrong way. If there's no evidence
   yet, note that as a gap rather than inventing some.
3. **Current state** — how are people solving this today, or going without?
4. **Proposed solution, at a high level** — what are you thinking of
   building? Don't let this replace the problem statement — if the user
   leads with the solution, get the problem afterward, not instead.
5. **Why now** — what makes this the right bet for this cycle specifically,
   not later, not never?
6. **Success metrics** — what changes if this works? Push for a number and
   a timeframe, not "improve engagement."
7. **Non-goals** — what's explicitly out of scope for this version?
8. **Risks, dependencies, open questions** — anything unresolved, any team
   this touches, anything that could block or reverse this.
9. **Doc stage** — is this an early exploration doc, a peer-review draft,
   or something headed to leadership? This sets the depth and formality of
   the draft — a one-pager doesn't need the same rigor as a leadership doc.

If an answer is thin, push once with a sharper follow-up before moving on
("improve retention" → "improve retention measured how, and by how much
would count as a win?"). Don't loop on the same question more than twice —
note it as an open question in the draft instead and move on.

---

## Step 2: The quality bar

Apply these while drafting — they're what separate a PRD that survives
review from one that bounces back with questions.

| Section | What makes it strong | What makes it weak |
|---|---|---|
| Problem | Specific, evidence-backed, describes user pain — not the feature | Vague ("users want more flexibility"), or actually a solution in disguise |
| Solution | Sized to the problem, explicit about what it does and doesn't cover | Over-built for the evidence, or so vague an engineer can't estimate it |
| Success metrics | A number, a baseline if known, a timeframe | "Improve X" with no target, or a vanity metric disconnected from the problem |
| Non-goals | Explicit exclusions someone could point to later ("we will not support X in v1") | Missing entirely, or hedged ("X may be out of scope") |
| Open questions | Named, owned if possible | Absent — which usually means they're hiding inside the solution section instead |
| So what | Connects the bet to why it matters now, in a sentence someone could repeat upward | Missing, or just a restatement of the problem |

If the interview didn't produce enough to hit this bar on a section, don't
paper over it — write the section with what you have and flag the gap in
Open Questions rather than inventing a metric or a piece of evidence that
wasn't given to you.

---

## Step 3: Draft the PRD

Use this structure. Depth scales with the doc stage from Step 1 — an early
exploration doc can be lighter on Context and skip Risks & Dependencies
entirely; a leadership-bound doc should have all of it.

```markdown
# [Feature Name]

**Status:** Draft · **Owner:** [name] · **Last updated:** [date]

## Context
Why this doc exists now. The strategic backdrop — what triggered this,
what it connects to. A few sentences, not a mission statement.

## Problem
The user problem, stated as something they can't do today, backed by the
evidence gathered in the interview. Not the solution.

## Solution
The proposed approach, at the altitude appropriate to the doc stage. What
it does, who it's for, the key requirements or scope. Bullets where they
earn it.

## So What
Why this bet, why now. What it unlocks or protects. The sentence someone
could repeat to their own leadership without losing the point.

## Success Metrics
Specific, measurable, time-bound. Baseline → target where known.

## Non-Goals
What's explicitly out of scope for this version, stated as calls, not
hedges.

## Open Questions
Known unknowns. Owner if there is one.

## Risks & Dependencies
[Include for peer-review or leadership-stage docs] Technical, timeline, or
adoption risk. Teams this touches. What needs to happen before this can ship.
```

Write it in the voice below — this is a working document, not a pitch deck.

---

## Step 4: Self-check before presenting

Before showing the draft, run it against the failure modes a reviewer would
catch:

- Does the Problem section describe the solution instead of the problem?
- Does any success metric lack a number or a timeframe?
- Are the non-goals actual calls, or hedged maybes?
- Is there an open question that got quietly buried inside the solution
  section instead of listed as unresolved?
- Would an engineer or designer be able to start from this, or does it need
  another pass first?

Fix what you can fix silently. Flag what you can't fix without more input
from the user — don't guess at a metric or a scope call that's genuinely
theirs to make.

---

## Step 5: Offer next steps

After presenting the draft:

> "Want me to tighten any section, or run this through `prd-reviewer` for a
> panel score before you send it out?"

If the user asks for a specific revision, make only that change — don't
regenerate the whole doc. If they want the review, hand off to
`prd-reviewer` with the drafted doc as input.

---

## Writing voice

PRDs read as decisions, not brainstorms.

- **User-problem-first** — open sections with what the user can't do
  today, not the feature name.
- **Decisive, not tentative** — "we will not support X in v1," not "X may
  be out of scope." "We need to," not "we might consider."
- **Specific, not vague** — real numbers, real scope, real constraints.
  "Reduced setup time by 40%" beats "improved the experience."
- **Active voice** — "we shipped X," not "X was completed."
- **Lean** — cut words that don't earn their place. Short declarative
  sentences carry more than long qualified ones. No em-dashes.
- **Evidence-backed** — ground problem claims in data, quotes, or observed
  behavior, not assertion.
- **Scannable** — headers and tables where they help, bullets where they
  earn it, prose everywhere else. Don't over-format a document that's
  mostly meant to be read top to bottom once.

If the user has stated their own voice preferences, those override the
defaults above.
