# PM Resume Reviewer

A Claude Code skill that runs a structured PM resume review using a simulated panel of three reviewers: Recruiter, Hiring Manager, and CPO.

Built for product managers targeting any level, APM through VP. The review adapts to whatever role and companies you're targeting. The reviewer criteria (outcomes vs. outputs, roadmap ownership, strategic scope) are PM-specific by design.

---

## What it does

- Gathers context: target role, target companies, and specific concerns
- Runs a three-lens panel review, each reviewer citing specific bullets and sections
- Produces a scorecard with scores and top concerns per reviewer
- Prioritizes the top 5 edits by impact with specific guidance on what to fix and why
- Offers to rewrite weak sections on the spot

The tone is direct. If something will get filtered before a human reads it, the skill says so.

---

## Who it's for

Product managers preparing for a job search, refreshing a stale resume, or targeting a specific level or company type. Especially useful before submitting to a role you actually want.

---

## Output structure

1. Three reviewer panels: Recruiter, Hiring Manager, CPO: each with specific citations
2. Per-reviewer scores and top concern
3. Overall scorecard
4. Top 5 prioritized edits (what's wrong, what to do, why it matters)
5. Offer to rewrite any section

---

## How to use it

Install via [Claude Code](https://claude.ai/code). Clone this repo and copy the folder into your skills directory:

**macOS / Linux:**
```bash
cp -r PMResumeReviewer ~/.claude/skills/resume-review
```

**Windows:**
```powershell
Copy-Item -Recurse PMResumeReviewer "$env:USERPROFILE\.claude\skills\resume-review"
```

Restart Claude Code. Then trigger with natural language, no slash commands needed:

- "Review my resume, I'm targeting Staff PM roles at AI companies"
- "Can you critique my PM resume?"
- "Is my resume strong enough for a Director of Product role?"
- "Help me improve my resume for fintech companies"
- Paste your resume and ask for feedback

---

## The reviewer lenses

- **Recruiter**: formatting, ATS keyword coverage, scannability, first-pass qualification signal
- **Hiring Manager**: outcomes vs. outputs, metrics quality, cross-functional evidence, strategic scope
- **CPO**: career narrative, scope progression, executive presence, AI depth (where relevant)

---

## Evals

The `evals/` folder contains three test cases with fictional resumes across different PM seniority levels and target roles, used for testing and iterating on skill behavior.
