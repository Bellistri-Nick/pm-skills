---
name: take-home-reviewer
description: >
  Review and sharpen a PM take-home assignment or case interview submission
  before the user sends it. Evaluates the work through the lens of what hiring
  teams actually look for: clear problem framing, defensible prioritization,
  realistic execution thinking, and a point of view. Scores the submission,
  identifies the highest-risk gaps, and offers targeted rewrites. Use this skill
  whenever the user has completed a PM take-home and wants feedback before
  submitting. Also triggers for: "PM take-home", "case assignment", "product
  case", "interview assignment", "PM homework", "review my submission", "take-home
  exercise", "product strategy assignment", "PM case study interview", or when the
  user shares a completed assignment and asks if it's ready to submit. Invoke
  immediately — gather context as part of the skill flow.
---

# PM Take-Home Assignment Reviewer

## What this skill does

Reviews a completed PM take-home or case assignment and gives the user honest,
specific feedback before they submit. The goal is to catch the gaps that hiring
teams will flag and surface the opportunities to show stronger PM thinking —
without making the work sound like someone else wrote it.

Take-homes are high-stakes and time-pressured. This review simulates what a
hiring panel actually looks for, calls out risks plainly, and offers targeted
improvements the user can execute quickly.

---

## Step 1: Gather context

Ask for the following in one prompt. If anything is already in context, skip
asking for it:

1. **The assignment** — Paste or describe the prompt/question
2. **The submission** — Paste the full response or describe what they wrote
3. **The company and role** — Who is this for? What stage (Series A, enterprise,
   B2B SaaS, consumer)? What role level?
4. **Time remaining** — How long before submission? This affects how
   comprehensive the feedback can be
5. **Specific concerns** — Anything they already suspect is weak

Once you have this, proceed. Don't wait for more context.

---

## Step 2: Understand the assignment intent

Before scoring, identify what the assignment is actually testing. Most PM
take-homes fall into one of these types — name which one (or which combination):

- **Product sense / prioritization** — Given a product or metric, what would
  you do? Why? (Tests judgment, frameworks, user empathy)
- **Strategy / go-to-market** — How would you enter this space / launch this
  product? (Tests market thinking, business model understanding)
- **Analytical / metrics** — What's happening with this metric? What would you
  do? (Tests structured thinking, comfort with ambiguity)
- **Execution / roadmap** — What would you build in the next 6 months / quarter?
  (Tests prioritization, trade-off reasoning, delivery thinking)
- **Product critique** — What's wrong with this product? How would you improve
  it? (Tests user empathy, product intuition, communication)
- **0-to-1** — Design a product for this user problem / market. (Tests vision,
  scoping, feasibility thinking)

Knowing the type shapes the scoring criteria. A prioritization exercise is
graded differently than a metrics analysis.

---

## Step 3: Score the submission

Score across five dimensions, each 1–10:

| Dimension | Score | What you're evaluating |
|---|---|---|
| Problem framing | X/10 | Did they define the right problem? Is the scope clear? |
| Prioritization logic | X/10 | Are the choices defensible? Is the reasoning explicit? |
| User and market understanding | X/10 | Is there genuine insight about users/customers, or just assumptions? |
| Execution realism | X/10 | Is the plan achievable? Are trade-offs acknowledged? |
| Communication clarity | X/10 | Is it easy to follow? Does it show a clear POV? |
| **Overall** | **X/10** | Holistic signal: would a panel fight for this candidate? |

For each dimension, provide:
- A one-line verdict
- The specific evidence from the submission (quote or reference)
- The biggest risk if left unchanged

---

## Step 4: Hiring panel simulation

Simulate what two reviewers will likely say when they debrief:

### Senior PM Reviewer
What they'll notice first. What question they'll raise in debrief. Whether
they'd advocate for moving this candidate forward. Be direct — "This passes"
or "This gets flagged" with the reason.

### Hiring Manager
What signals they're looking for at this level. Whether the submission
demonstrates the right kind of thinking for the role. The thing that would
make them hesitate.

---

## Step 5: Top fixes — ordered by impact and feasibility

Given the time remaining, prioritize what to address first. Format each fix as:

**[Fix title]**
What's wrong: [specific issue with reference to the submission]
What to do: [concrete, actionable change]
Time to fix: [~5 min / ~15 min / ~30 min]
Why it matters: [what this unlocks in the panel review]

Order by: (1) gap severity × (2) fix difficulty. A 10-minute fix that closes
a major gap beats a 2-hour polish that improves a minor one.

---

## Step 6: Offer targeted rewrites

After the fixes, offer:

> "Want me to rewrite any specific sections? I can sharpen the problem framing,
> strengthen the prioritization rationale, tighten the executive summary, or
> rewrite a section that isn't landing. Just say which one."

When rewriting, preserve the user's voice and ideas. The goal is to make their
thinking clearer and more defensible — not to replace it.

---

## Common failure modes to flag

Watch for these patterns — they appear often and hiring panels are trained to
spot them:

**Framework theater** — Using 2x2s, rice/ice, or Kano without the judgment
that should drive them. "I used RICE to score these features" is not enough.
What were the inputs? Why those weights? What was the hardest call?

**Missing the user** — A submission that's all strategy and no users. Where is
the evidence that real people have this problem?

**Scope creep without acknowledgment** — The submission answers a different
(usually bigger) question than the one asked, without explaining why.

**No point of view** — A list of options with no recommendation. "We could do
A or B" without committing signals indecisiveness, not thoroughness.

**Undefended assumptions** — The entire strategy rests on an assumption that's
never named or tested. ("Assuming users want X...") Name assumptions explicitly
and note how you'd validate them.

**Polished but shallow** — Well-formatted, lots of headers and bullets, but the
actual thinking doesn't hold up to one question of "why." Formatting is not
the work.

---

## Tone guidance

This is a high-stakes review, not a cheerleading session.

- If the submission has a real problem, name it plainly. "A panel will flag
  this" is more useful than "there's room to tighten."
- If the submission is strong, say so specifically — and still find the one
  thing that would make it stronger.
- Be direct about time constraints. If there are 2 hours left and five things
  to fix, name the one that matters most.
- Match the urgency of someone who has been on hiring panels, has seen great
  submissions lose on execution, and actually wants this person to get the job.
