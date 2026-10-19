# ai-quality-scorecard, Claude Code Skill

A Claude Code skill that scores a single piece of AI-generated output against quality criteria and gives a specific, evidence-cited verdict on whether it's good enough to ship.

---

## What it does

Paste an AI-generated output plus the context it came from (the brief, prompt, or source input), and the skill:

1. **Scores each dimension 1–5** with a justification that cites the actual output: not a generic quality statement
2. **Gives an overall verdict**: Ship / Ship with edits / Do not ship: against a clear, stated threshold
3. **Flags the single biggest risk** if the output ships unchanged
4. **Offers a targeted rewrite** fixing the weakest dimension, without regenerating the whole piece unless the problems are pervasive

Works with a custom rubric, including one built with [eval-framework-builder](https://github.com/Bellistri-Nick/ProductManagerEvalFrameworkBuilder), or falls back to a sensible default rubric (relevance, correctness, instruction adherence, tone, structural completeness, originality, safety).

This is a spot-check tool for one piece of output. If you need to design a full evaluation system instead of scoring one output, use `eval-framework-builder`.

---

## Requirements

- [Claude Code](https://claude.ai/code) (CLI or desktop app)

---

## Installation

1. Clone or download this repo
2. Copy this repo's folder into your Claude Code skills directory as `ai-quality-scorecard`:

**macOS / Linux:**
```bash
cp -r ProductManagerAIQualityScorecard ~/.claude/skills/ai-quality-scorecard
```

**Windows (PowerShell):**
```powershell
Copy-Item -Recurse ProductManagerAIQualityScorecard "$env:USERPROFILE\.claude\skills\ai-quality-scorecard"
```

Your skills directory should look like:
```
~/.claude/skills/
  ai-quality-scorecard/
    SKILL.md
    evals/
      evals.json
```

3. Restart Claude Code (or reload the window in the desktop app)

---

## Usage

- "Score this AI-generated email, here's the brief it came from"
- "Is this good enough to send?" + paste the output and context
- "Grade this AI-generated draft against our rubric" + paste the rubric
- "Quality check this before it goes out"

Provide: the output itself, what it was generated from, and the intended audience. A custom rubric is optional, the skill falls back to a sensible default if you don't have one yet.

---

## Evals

Three test cases:

1. **Score AI-generated marketing copy with the default rubric**: tests dimension scoring, evidence-based justification, and verdict logic against the standard threshold
2. **Score against a custom rubric**: tests that a user-supplied rubric is used instead of the default, and that dimensions/anchors aren't blended
3. **Score a strong output**: tests that the skill gives an honest "ship" verdict without manufacturing criticism to appear balanced

---

## Customization

The default rubric and verdict thresholds are in `SKILL.md` under Steps 2 and 4. Adjust the threshold logic if your organization uses a different bar for "ship" versus "needs edits," or swap in dimensions specific to your content type.

---

## License

MIT
