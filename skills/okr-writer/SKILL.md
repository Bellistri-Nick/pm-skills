---
name: okr-writer
description: >
  Generate or review OKRs for a product team. Drafts well-structured objectives
  and key results from strategic context, or reviews and rewrites existing OKRs
  to fix common failures (task KRs, vanity metrics, output-focused results,
  too many KRs per objective). Use when the user asks to write, draft, review,
  fix, or improve OKRs. Also triggers for: "help me write OKRs", "review my
  OKRs", "are these OKRs good", "my KRs feel like tasks", "OKR planning",
  "quarterly goals", or when the user pastes OKRs and asks for feedback.
  Invoke immediately — gather context as part of the skill flow.
---

# OKR Writer

## What this skill does

Two modes:

**Generate** — Drafts OKRs from strategic context. Takes what the team is trying
to accomplish and turns it into well-structured objectives and key results.

**Review** — Takes existing OKRs, scores them against clear criteria, rewrites
the weak ones on the spot, and explains what made them weak.

In both modes, the output should be OKRs a team can actually use — not corporate
filler dressed up as goals.

---

## Step 1: Gather context

Collect in one prompt. Skip anything already in context:

1. **Mode** — generate new OKRs, or review existing ones (default to generate if unclear)
2. **Team and product context** — what does this team own? What problem are they solving for which users?
3. **Timeframe** — quarter, half-year, annual
4. **Strategic priorities or bets** — what does the company or leadership expect from this team right now? (e.g., "grow activation," "reduce churn," "expand into enterprise," "ship the AI features on the roadmap")
5. **Existing OKRs** — required for review mode; optional for generate mode (paste if they have a starting draft)
6. **Constraints** — anything the team can't or won't own (e.g., "we don't control pricing," "eng capacity is limited this quarter")

Once you have what you need, proceed. Don't ask follow-up questions.

---

## Step 2: OKR quality standards

Apply these in both modes. These are the criteria an OKR is evaluated against.

### What makes a good Objective

- **Qualitative and directional** — describes a desired state, not a metric
- **Aspirational but grounded** — should feel like a stretch, not a fantasy
- **Time-bound by the cycle** — implicit in the quarterly/half framing
- **Answers "what do we want to achieve?"** not "what will we do?"
- **One clear idea** — not a compound sentence with two goals

Bad: "Improve the product and grow revenue this quarter"
Good: "Become the go-to tool for onboarding new enterprise accounts"

### What makes a good Key Result

- **Measurable** — has a number. No number = not a KR.
- **Outcome-focused** — measures a change in user behavior, business metric, or system state. Not a task or deliverable.
- **Time-bound** — has a baseline and a target, or is anchored to the cycle
- **Independently verifiable** — could someone else look it up and confirm it?
- **3–4 per objective maximum** — more than 4 means the objective is too broad or the team is over-committed

### Common failures — name them explicitly when they appear

| Anti-pattern | Example | Why it fails |
|---|---|---|
| Task KR | "Launch the onboarding redesign" | Binary, no measurement of whether it worked |
| Vanity metric | "Increase page views by 20%" | Doesn't connect to user or business outcome |
| Output masquerading as outcome | "Ship 3 new features" | Measures activity, not impact |
| Too many KRs | 6+ KRs per objective | Signals lack of prioritization, not ambition |
| Unmeasurable objective | "Make the product more delightful" | Can't tell if you got there |
| Stretch target without baseline | "Achieve 90% NPS" with no current NPS stated | Unanchored, can't evaluate success |

---

## Step 3A: Generate mode

Draft 1–3 objectives based on the strategic context provided. For each:

**Objective:** [clear, qualitative, directional statement]

**Key Results:**
- KR1: [metric] from [baseline] to [target] by end of [period]
- KR2: [metric] from [baseline] to [target] by end of [period]
- KR3: [metric] from [baseline] to [target] by end of [period]

**Why this objective:** 1–2 sentences connecting it to the strategic priority. Why this, why now.

**Assumptions:** Note any baseline metrics that are estimated or unknown and would need to be confirmed before committing to this OKR.

After drafting, add a short calibration note:
- Are these 1–3 objectives the right number for this team's capacity?
- Are the KRs measurable with what this team likely has access to?
- Is there a risk that any of these OKRs are fully outside the team's control?

---

## Step 3B: Review mode

For each existing objective, assess:

**[Objective as written]**

| Criterion | Assessment | Score |
|---|---|---|
| Qualitative and directional | [finding] | Pass / Needs work |
| Aspirational but grounded | [finding] | Pass / Needs work |
| Single clear idea | [finding] | Pass / Needs work |

For each key result under that objective, assess:

**[KR as written]**
- Anti-pattern present? [Yes/No — name it if yes]
- Measurable? [Yes/No]
- Outcome-focused? [Yes/No]
- Verdict: Keep / Rewrite

If verdict is Rewrite, rewrite it immediately:
> **Rewritten:** [improved KR with baseline → target format]
> **What changed:** [one sentence on what was wrong and what the rewrite fixes]

After reviewing all OKRs, give an overall verdict:
- How many objectives are well-structured?
- What's the most common failure pattern across the KRs?
- Is the overall set achievable for this team in this timeframe?

---

## Step 4: Offer iterations

After generating or reviewing, offer:

> "Want me to adjust any of these? I can tighten a specific objective, reframe KRs around different metrics, add a missing objective, or trim if the set is over-committed. Just say what needs work."

If the user asks for a specific iteration, make only that change — don't regenerate the full set unless asked.

---

## Tone guidance

Honest about quality.

- If a KR is a task dressed up as a result, say so plainly — "this is a task, not a key result"
- If the team's strategic priorities are vague, write OKRs that expose that vagueness: "I've had to make assumptions about X — you'll want to confirm these baselines before committing"
- If the set is over-committed or unrealistic, say so
- Good OKRs are specific enough that it's obvious whether you hit them at the end of the quarter — write toward that standard
