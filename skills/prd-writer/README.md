# PM PRD Writer

A Claude Code skill that writes a PRD from scratch through a short, adaptive PM intake interview, then drafts the doc against PM best practices.

Works from raw notes, a rough brief, or nothing at all. Pastes existing context in and it extracts what's already answered, asking only about the gaps.

---

## What it does

- Runs a conversational intake interview, one question at a time, problem and evidence, current state, proposed solution, why now, success metrics, non-goals, risks and open questions, and doc stage
- Applies a quality bar to each section as it drafts (specific problem statements, measurable success metrics, real non-goals, not hedges)
- Drafts a structured PRD: Context, Problem, Solution, So What, Success Metrics, Non-Goals, Open Questions, and Risks & Dependencies for leadership-stage docs
- Self-checks the draft against common PRD failure modes before presenting it
- Offers to hand off to [PM PRD Reviewer](https://github.com/Bellistri-Nick/ProductManagerPRDReviewer) for a scored panel critique before you send it out

---

## Who it's for

Product managers who need a first draft of a PRD fast, starting from a rough idea, a pile of meeting notes, or a blank page, and want the draft to already reflect PM best practices instead of needing a full rewrite after review.

---

## Output structure

```markdown
# [Feature Name]

**Status:** Draft · **Owner:** · **Last updated:**

## Context
## Problem
## Solution
## So What
## Success Metrics
## Non-Goals
## Open Questions
## Risks & Dependencies
```

---

## How to use it

Install via [Claude Code](https://claude.ai/code). Clone this repo and copy the folder into your skills directory:

**macOS / Linux:**
```bash
cp -r ProductManagerPRDWriter ~/.claude/skills/prd-writer
```

**Windows:**
```powershell
Copy-Item -Recurse ProductManagerPRDWriter "$env:USERPROFILE\.claude\skills\prd-writer"
```

Restart Claude Code. Then trigger with natural language:

- "Help me write a PRD for this feature"
- "Draft a spec for X"
- "I need to write up this feature before I hand it to engineering"
- "Turn this idea into a PRD" (paste notes, a brief, or a Slack thread)
- "Help me think through this feature before I write it up"

---

## Pairs with

[PM PRD Reviewer](https://github.com/Bellistri-Nick/ProductManagerPRDReviewer), draft here, then stress-test there through Peer PM, Lead PM, and CPO lenses before it goes out.
