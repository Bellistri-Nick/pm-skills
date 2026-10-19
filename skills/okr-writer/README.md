# PM OKR Writer

A Claude Code skill that generates well-structured OKRs from strategic context, or reviews and rewrites existing OKRs to fix the common failures that make them useless.

---

## What it does

Two modes in one skill:

**Generate**, Takes your team's context (product area, strategic priorities, timeframe, team size) and drafts 1–3 objectives with 3–4 key results each. Each KR includes a baseline → target format and a calibration note on whether the set is realistic for your team's capacity.

**Review**, Takes your existing OKRs and scores each objective and KR against clear criteria. Names the anti-pattern when it finds one, rewrites weak KRs on the spot, and gives an overall verdict on the set.

---

## Who it's for

Product managers writing quarterly or half-yearly OKRs, or teams that keep ending up with task lists dressed up as key results. Also useful before OKR review season when you want to pressure-test a draft before leadership sees it.

---

## Output structure

**Generate mode:**
1. 1–3 objectives with 3–4 KRs each
2. Baseline → target format for each KR
3. Calibration note on capacity and ambition

**Review mode:**
1. Score and verdict per objective and KR
2. Named anti-pattern for each weak KR
3. Rewrite of every KR that doesn't pass
4. Overall verdict on the set

---

## How to use it

Install via [Claude Code](https://claude.ai/code). Clone this repo and copy the folder into your skills directory:

**macOS / Linux:**
```bash
cp -r ProductManagerOKRWriter ~/.claude/skills/okr-writer
```

**Windows:**
```powershell
Copy-Item -Recurse ProductManagerOKRWriter "$env:USERPROFILE\.claude\skills\okr-writer"
```

Restart Claude Code. Then trigger with natural language:

**To generate:**
- "Help me write OKRs for my team, we own activation and onboarding, Q3"
- "Draft OKRs for our AI features team this half"

**To review:**
- "Review my OKRs, I think some of them are tasks not results"
- "Are these OKRs good?" + paste your OKRs
- "My KRs feel like tasks, can you fix them?"

---

## Anti-patterns it catches

| Anti-pattern | Example |
|---|---|
| Task KR | "Launch the new onboarding flow" |
| Vanity metric | "Increase page views by 20%" |
| Output as outcome | "Ship 3 new features" |
| Too many KRs | 6+ KRs per objective |
| Unmeasurable objective | "Make the product more delightful" |
| Unanchored target | "Achieve 90% NPS" with no current NPS stated |

---

## Evals

Three test cases in `evals/`:

1. **Generate OKRs for an activation/onboarding team**: straightforward strategic context, tests baseline → target format
2. **Review weak OKRs with common anti-patterns**: task KRs, vanity metrics, unmeasurable objectives
3. **Generate OKRs for an AI product with measurement challenges**: tests how the skill handles subjective quality metrics
