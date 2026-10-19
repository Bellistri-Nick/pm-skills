---
name: pm-take-home-case
description: >
  Run a PM take-home case study end to end, from the raw prompt to a finished
  deck or doc the user can send. Parses what the assignment is really testing,
  researches the company and market with verified sources only, builds a framing
  memo with an actual point of view, pressure-tests it from the buyer's, founder's
  and evaluator's seats, then produces the deliverable with every number traceable
  to a source. Use this skill whenever the user has a PM case study, take-home, or
  work sample to BUILD (not review). Also triggers for: "I have a case study",
  "founding PM case study", "product take-home", "they gave me an assignment",
  "help me with this case", "work sample for an interview", "PM exercise", "case
  study for [company]", or when the user shares an assignment PDF and asks for
  help. Distinct from take-home-reviewer, which critiques a submission that already
  exists. Invoke immediately and gather context as part of the flow rather than
  interviewing the user first.
---

# PM Take-Home Case Study Builder

## What this skill does

Takes a PM case study assignment from prompt to finished deliverable. The output
is something the user can send, plus the material they need to defend it in a
live walkthrough.

Most case studies are not graded on the answer. They are graded on whether the
candidate can turn an ambiguous thesis into a sharp, defensible decision and
explain the trade-offs. So this workflow front-loads the framing call and spends
real effort attacking it before it gets designed.

The user is a working PM under a time box. Do not interview them at the start.
Read the prompt, do the research, form a view, and bring it back for them to
push on. If something is genuinely unresolvable without them, note the assumption
and keep building.

---

## Step 1: Parse what the assignment is testing

Read the prompt and name three things before doing anything else:

1. **The literal deliverables.** List every required section. Case prompts
   usually enumerate them. Every one needs a home in the final artifact, and the
   evaluator will check.
2. **The constraints.** Format, page or slide count, time box, and the sourcing
   rules. If the prompt says figures must be cited, that is not boilerplate.
   Treat it as the primary grading criterion.
3. **What it is really testing.** Usually some mix of: can you scope ambiguity
   into a decision, do you reason from real user behavior, can you cite real
   numbers, and do you understand why *this company* would build *this thing*.

State these back in two or three sentences. It takes almost no time and it keeps
the rest of the work pointed at the right target.

---

## Step 2: Research the company before the market

This ordering matters and is easy to get backwards. What the company already is
constrains every good answer: their existing customers, their sales motion, the
phase of the workflow they live in, their team size and stage, and the founder's
stated philosophy.

Search for: the company's own materials, founder interviews and podcasts, funding
and team size, named customers, and what adjacent players exist. Founder
interviews are the highest-yield source and are usually overlooked. They tell you
the philosophy the product has to be consistent with and the objection the
founder will raise in the walkthrough.

Then research the market: size and shape, the structural trend that makes the
problem real, adoption data for the relevant technology, and every competitor
including the tools not built for this job.

Run these searches in parallel. Fetch the primary source behind any number worth
using, not just the search summary.

---

## Step 3: Build the source ledger, separate from everything else

Create a `sources/` folder holding a ledger, separate from the drafts. Every
number that will appear in the deliverable gets a row first: the fact, the link,
and a note on how to use it.

The ledger also records what NOT to use. When a number appears everywhere but
only traces back to a content farm or an SEO page, write a "do not use" row
naming the fake source. This is the single highest-value habit in the whole
workflow, because a fabricated stat is the one error that ends a candidacy, and
these numbers circulate widely enough to look real.

Read `references/source-discipline.md` for the rules on what counts as credible,
how to handle a number that does not exist, and how to cite honestly.

---

## Step 4: Write the framing memo, with a real point of view

Before any deliverable, write a working memo that takes a position. Not options.
A position, with the reasoning visible and the rejected alternatives named.

It needs:

- **The framing in one line.** Who it is for, what it does, how it evolves.
- **The insight.** The non-obvious reframe that makes the product make sense. A
  good one sounds slightly contrarian and then becomes obvious. Prompts usually
  hand you a surface problem; the insight is usually one level beneath it.
- **The assumptions, stated up front.** Five or six load-bearing ones. Prompts
  that say "state your framing and key assumptions" mean it, and stating them
  is also how you get credit for the scope you deliberately cut.
- **Who it is for and whose behavior has to change.** Name the person with the
  least incentive to change and the most leverage over whether it works. Design
  everything around making their change small. This question separates strong
  case studies from competent ones.
- **The rejected framing.** Name the obvious answer and say why it loses. This
  is often the single clearest demonstration of judgment in the deliverable.
- **Every required section**, at working-draft depth.

Save it in `drafts/`. Then bring the user the point of view, the two or three
calls where their answer changes the work, and any honest weak spot. Give a
recommendation for each open call rather than a survey.

---

## Step 5: Run the adversarial check

This is the step that most separates a good case study from a generic one, and
it is the step most likely to get skipped. Do not skip it.

Attack the framing from three seats: the buyer, the founder, and the evaluator.
Each one has a different killer question, and each one surfaces material that
belongs in the final deliverable.

Read `references/adversarial-check.md` for how to run each seat and what to do
with the findings.

Two rules about the output:

- Findings get folded into the deliverable. The best ones usually become a value
  proposition, a risk row, or a phasing decision.
- Simulated critique is never presented as user research. If a finding came from
  reasoning in a persona's seat, it is a hypothesis to test, not a finding. Say
  so plainly in the deliverable and in the walkthrough.

---

## Step 6: Merge into a locked strategy

Fold the pressure-test findings and the user's answers into a single strategy
doc that the deliverable traces back to. Open it with a decisions table: the
call, and one line on why. This is what the user will reread the night before
the walkthrough, and it is what makes them sound decisive instead of
reconstructing their own reasoning live.

Where a number would help but does not exist, give the formula with the
audience's own inputs and one sourced anchor. A formula an evaluator can run
beats a fabricated figure, and it turns a gap into a display of rigor.

---

## Step 7: Write the deliverable copy before building it

Write the full copy in markdown first, with a section or slide per required
deliverable. This separates the argument from the production work, and it is far
cheaper to fix a weak headline in markdown than in a built artifact.

For a deck:

- One assertion per slide headline. Not topics. "The problem isn't capture, it's
  organization by decision" beats "Problem statement."
- Map each slide to the prompt's required sections and make sure all are covered.
- Bracketed reference IDs tie each figure to a ledger row. A source appendix
  slide carries the links.
- Speaker notes on every slide, holding the trade-off behind the choice. These
  are the walkthrough prep.

For a doc, the same logic applies with sections instead of slides.

---

## Step 8: Build it

For a deck, use the Slides artifact type. Generate the slide HTML from a Python
script rather than writing each file by hand, so copy edits regenerate in one
step and stay consistent.

Read `references/deck-build.md` for the generator pattern, the layout budget,
and the density limits that actually bite.

Save the generator alongside the drafts so the user can regenerate after edits.

---

## Step 9: Final pass before handing it over

Check these, and report honestly on any that fail:

1. **Every required deliverable is present.** Walk the prompt's list one by one.
2. **Every number traces to a ledger row.** No exceptions, including numbers
   that feel like common knowledge.
3. **At least one honest counter-signal appears.** Every real market has
   evidence cutting against the thesis. Including it and explaining why the
   argument survives reads as credibility, not weakness. Omitting it reads as
   a pitch.
4. **The rejected alternative is named.**
5. **Voice matches the user.** Check their style rules and apply any global
   instructions file they keep. A case study that reads like generic consulting
   prose is forgettable, and the walkthrough will expose the mismatch when they
   have to speak the words out loud.
6. **It stands alone.** The prompt usually says so explicitly. A reader who was
   not in the room should get the argument without narration.

Then tell the user what was built, where the files are, the two or three places
you made a judgment call they might want to overrule, and any weak spot you
could not resolve.

---

## Working files

Keep sources apart from drafts so nothing unsourced leaks into the deliverable:

```
case-studies/<company>-<role>/
├── sources/
│   └── source-ledger.md      every number, its link, and the do-not-use list
└── drafts/
    ├── 01-strategy.md        framing, decisions table, all required sections
    ├── 02-deck-copy.md       slide-by-slide or section-by-section copy
    └── 03-deck-generator.py  builds the slide files from the copy
```

If earlier attempts exist, leave them alone and start a new folder. Old drafts
are cheap to keep and occasionally hold a better phrasing.

---

## Reference files

- `references/source-discipline.md`: what counts as a credible source, handling
  numbers that do not exist, and honest citation.
- `references/adversarial-check.md`: the three seats, their killer questions,
  and how to fold findings back in.
- `references/deck-build.md`: the slide generator pattern and layout budget.
