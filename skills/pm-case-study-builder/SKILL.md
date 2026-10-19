---
name: pm-case-study-builder
description: >
  Turn raw PM work experience into a polished, portfolio-ready case study. Takes
  a product initiative — a feature, a 0-to-1 build, a platform redesign, a hard
  decision — and transforms it into a structured narrative that demonstrates PM
  thinking: the problem, the process, the decisions, the outcome, and the lessons.
  Output formats include written case study (for portfolio sites, Notion, or
  interview prep), a condensed LinkedIn article version, and a talking-points
  outline for verbal storytelling. Use this skill whenever the user asks to write
  a PM case study, turn past work into a portfolio piece, write up a product
  project, document a product decision, or prep a work sample. Also triggers for:
  "case study", "portfolio piece", "write up my work", "turn this project into a
  story", "PM portfolio", "product story", "help me explain what I built", or when
  the user describes a product initiative and asks how to present it. Invoke
  immediately — gather context as part of the skill flow.
---

# PM Case Study Builder

## What this skill does

Takes a product initiative the user worked on — at any stage of completion, with
or without polished metrics — and builds a structured, compelling case study
that demonstrates PM thinking. The goal is not to write marketing copy. It's to
surface the decisions that were hard, the context that made them hard, and the
outcome that resulted.

A good case study shows how a PM thinks, not just what they shipped.

---

## Step 1: Gather the raw material

Ask for the following in one prompt. If anything is already in context, skip
asking for it. Imperfect information is fine — you'll work with what's there
and flag gaps rather than blocking on them.

1. **The initiative** — What did you work on? (Feature, product, platform,
   redesign, 0→1 build, strategy project, cancellation, etc.)
2. **Context and constraints** — What company, what stage, what team size? What
   constraints mattered (timeline, resources, tech debt, org dynamics)?
3. **The problem you were solving** — What was broken, missing, or unclear?
   Whose problem was it?
4. **What you did** — The key decisions you made, the approaches you considered,
   the work you led
5. **The outcome** — What shipped? What changed? Any metrics, even rough ones?
6. **What you'd do differently** — Optional, but makes the story more credible
7. **Where this will be used** — Portfolio site, interview, LinkedIn, internal
   doc, writing sample?

Once you have this, proceed. Don't wait for perfect information.

---

## Step 2: Identify the story spine

Before writing, identify the narrative structure that makes this case study
work. Every strong PM case study has:

- **The problem worth caring about** — Why did this matter? Who was affected?
- **The non-obvious decision** — The moment where multiple reasonable paths
  existed and judgment was required. This is the heart of the case study.
- **The constraint that shaped everything** — What made this hard? (Technical
  debt, stakeholder misalignment, ambiguous data, tight timeline, competing
  priorities)
- **The outcome that proves something** — Not just "we shipped it" but what
  changed in the world

Name these four elements explicitly before writing. If you can't find a
"non-obvious decision," ask the user: "What was the hardest call you made?"
That's usually the real story.

---

## Step 3: Write the full case study

Structure:

### [Initiative Title]
*One-line framing: what it was and what it changed*

---

#### The problem
What was broken or missing? Whose problem? How did you know it was a real
problem worth solving? (2–4 sentences. Resist the urge to start with company
background.)

#### Context
What were you working with? Team size, product stage, constraints that mattered.
Keep it tight — only context that explains why decisions were hard.

#### What I did
Narrative of the key decisions, not a list of activities. Structure as a story:
what you tried, what you learned, what you changed, what you decided.

Include:
- The hardest decision and the reasoning behind it
- What you considered and ruled out
- How you handled uncertainty or conflicting signals
- Who you worked with and why that mattered

Don't include:
- Everything that happened (this is a highlight, not a journal)
- Process steps that didn't require judgment ("I ran standups")
- Contribution language ("I supported the team in...")

#### The outcome
What shipped. What changed. Metrics if available — real ones, not vanity numbers.
If you don't have metrics, describe what observable change occurred.

#### What I'd do differently
One honest observation. Makes the story feel real and signals a PM who learns.
Skip if the user prefers.

---

## Step 4: Produce output formats

After writing the full case study, produce two additional versions:

### LinkedIn article version (600–900 words)
Same structure, tighter prose. Opens with the "so what" — the insight or
decision that made the project interesting — not with background. Ends with a
clear takeaway or open question. Appropriate for publishing on LinkedIn.

### Talking-points outline (for verbal storytelling)
A structured outline the user can internalize for interviews or portfolio walkthroughs:
- One-sentence setup: "This was a [type of problem] at [company] during [context]"
- The non-obvious decision: what it was, what you considered, what you decided
- The outcome: what happened
- The lesson: what you'd do differently or what this taught you

---

## Step 5: Offer refinements

After delivering all three formats, offer:

> "Want me to adjust the angle, tighten a section, sharpen the metrics framing,
> or tailor this for a specific role or company? Just say what needs changing."

Common refinements:
- **Tailoring for a specific role** — Reframe which decisions to emphasize based
  on what the target company cares about
- **Metrics coaching** — Help the user figure out what numbers they can actually
  claim, and how to frame them honestly if they're partial or indirect
- **Condensing for a portfolio** — Cut to the essential narrative for a 2-minute
  portfolio walkthrough
- **Strengthening the decision narrative** — If the case study reads like a
  feature announcement, reframe it around the judgment calls

---

## Tone and voice guidance

The default voice for case studies:
- **First person, active** — "I decided to..." not "The team decided to..."
- **Specific about decisions** — Name the trade-off, not just the outcome
- **Honest about uncertainty** — "We didn't know X, so we..." is stronger than
  pretending everything was planned
- **Lean** — One idea per sentence. Cut the preamble.
- **No jargon** — "We improved retention" not "We drove user engagement through
  a frictionless onboarding optimization"

If the user has their own voice, match it. Ask for a writing sample if they
want a specific style.

---

## What makes a PM case study strong vs weak

**Strong:**
- Centers on a decision, not a feature
- Names what was hard and why
- Has a specific outcome, even an imperfect one
- Shows judgment: what was considered and ruled out
- Reads like a person, not a job description

**Weak:**
- Leads with company background before the problem
- Describes process steps without explaining why they mattered
- Skips the hard decision — just says "we shipped X and it worked"
- Generic metrics ("improved NPS") without context
- Passive voice throughout ("the team was able to...")

If the raw material the user gives you would produce a weak case study, name
the gap and ask the right question to unlock the real story.
