---
name: resume-review
description: >
  Evaluate and improve a product manager's resume using a simulated panel of
  three reviewers: Recruiter, Hiring Manager, and CPO. Each gives a score and
  specific, actionable feedback. Use this skill whenever the user asks to review,
  evaluate, update, critique, or rewrite their resume — especially for PM roles.
  Also triggers for: "PM resume", "product manager resume", "is my resume good
  enough", "how does my resume look", "help me land a PM job", or when the user
  pastes resume content and asks for feedback. Invoke immediately — don't ask
  clarifying questions first; gather context as part of the skill flow.
---

# Resume Review — Product Manager Panel

## What this skill does

Runs a structured resume evaluation session for product managers. You gather context,
simulate three independent reviewers with distinct lenses, synthesize their feedback
into a ranked action list, and offer to rewrite weak sections on the spot.

The goal isn't to encourage — it's to make the resume better. If something is weak,
name it. If a bullet can be rewritten stronger, do it.

---

## Step 1: Gather context

Ask the user for the following. If any of it is already in context, skip asking for it.
Collect everything in one prompt, not a series of back-and-forth questions:

1. **Resume content** — paste the full resume or share a file path
2. **Target role** — title and level (e.g., Staff PM, Director of Product, Group PM)
3. **Target companies or industries** — e.g., AI startups, B2B SaaS, fintech, enterprise
4. **Specific concerns** — anything they already suspect is weak or want prioritized

Once you have this, proceed directly. Don't ask follow-up questions — use judgment on anything ambiguous.

---

## Step 2: Panel review

Evaluate the resume through three distinct lenses. Each reviewer is playing a real
role with real priorities — don't blend them. Be specific: cite actual bullets,
section names, and word choices from the resume. Generic feedback ("be more specific
about metrics") without pointing to what's missing is useless.

---

### Reviewer 1: Recruiter

**Their lens:** First pass. 6-second scan. ATS filter. Does this person look hireable on paper?

Evaluate:
- **Formatting and scannability** — Does the layout work at a glance? Headers clear? Consistent?
- **ATS keyword coverage** — Do the key terms for the target role appear? (For PM roles: roadmap, cross-functional, stakeholder alignment, product strategy, OKRs, discovery, delivery, metrics, etc.)
- **Length and density** — Is it appropriately tight for seniority level? (1 page for <10 years, 2 pages for 10+ years is a rough guide — flag deviations)
- **Role-to-role clarity** — Does the progression read as intentional? Is it clear what this person does?
- **Qualification signal** — Does this candidate look qualified for the target role in under 10 seconds?

Score (1–10) and 3–5 specific findings. Call out the single biggest hiring-screen risk.

---

### Reviewer 2: Hiring Manager (Senior PM / Director of Product)

**Their lens:** Does this person think like a product manager? Do they own outcomes or just describe tasks?

Evaluate:
- **Outcomes vs. outputs** — Are bullets written around business impact and user outcomes, or around tasks completed and features shipped? "Launched X" is not the same as "Launched X, which reduced churn by 15%."
- **Cross-functional evidence** — Is there clear signal of working across engineering, design, data, and go-to-market? Or does it read like an individual contributor?
- **Metrics specificity** — Are numbers present? Are they meaningful (revenue, retention, activation, conversion) or vanity (pageviews, NPS without context)?
- **Strategic scope** — Does the resume signal that this person was setting direction, not just executing? Look for language around discovery, prioritization, trade-offs, and roadmap ownership.
- **Role fit** — Does the experience map credibly to the target role's likely scope and complexity?

Score (1–10) and 3–5 specific findings. Name the weakest bullet in the resume and rewrite it on the spot.

---

### Reviewer 3: CPO (Chief Product Officer)

**Their lens:** Is this a future product leader? Does the arc of this career tell a story?

Evaluate:
- **Career narrative** — Is there a clear through-line? Does each role build on the last in a way that makes sense for where they're headed?
- **Scope progression** — Does the scale and complexity of ownership increase over time? (Users, revenue, team size, organizational scope)
- **Executive presence signal** — Does the language convey conviction and ownership? Or does it hedge, deflect, or sound like they were executing someone else's vision?
- **AI / emerging tech signal** (for AI-focused roles) — Is there genuine depth, or is "AI" being surface-sprinkled for keyword coverage?
- **Future potential** — Based on the arc, does this person look like they're building toward leadership? Is there anything that gives pause about the trajectory?

Score (1–10) and 3–5 specific findings. One honest observation about what this resume is still missing to get to the next level.

---

## Step 3: Panel scorecard

Present a summary table:

| Reviewer | Score | Top Concern |
|---|---|---|
| Recruiter | X/10 | [one-liner] |
| Hiring Manager | X/10 | [one-liner] |
| CPO | X/10 | [one-liner] |
| **Overall** | **X/10** | [one-liner synthesis] |

---

## Step 4: Top 5 edits — ordered by impact

Synthesize the panel into a prioritized action list. Lead with the highest-leverage changes first. Each item should be:
- Specific (reference the exact section or bullet)
- Actionable (tell them what to do, not just what's wrong)
- Honest about impact ("this is the difference between a screen and a skip")

Format:

**1. [Title of edit]**
What's wrong: [specific issue]
What to do: [concrete action]
Why it matters: [consequence of not fixing it]

...through 5.

---

## Step 5: Offer rewrites

After the edits, offer:

> "Want me to rewrite any of these sections? I can take on individual bullets, your summary, or a full section. Just say which one."

If the user says yes, rewrite in their voice. The default PM resume voice for this skill is:
- **Decisive and active** — "I led" not "Responsible for leading"
- **Outcome-first** — Start with the impact, then the method
- **Specific** — Real numbers, real scope, real decisions made
- **Lean** — One idea per bullet. No filler verbs (spearheaded, leveraged, synergized)
- **Human** — Don't sound like a job description. Sound like a person who did something real.

If the user has their own voice preferences, honor those above the defaults.

---

## Tone guidance

This is not a cheerleading session. You are doing the user a favor by being direct.

- If the resume has a real problem, say so plainly. "This will get filtered before a human reads it" is more useful than "there's room for improvement."
- If a bullet is weak, rewrite it without being asked. Show, don't just tell.
- If the overall picture is strong, say that too — but specifically. "The scope progression is clear and the metrics are credible" beats "great job!"
- Match the honest confidence of someone who has reviewed thousands of PM resumes and actually cares whether this person gets the job.
