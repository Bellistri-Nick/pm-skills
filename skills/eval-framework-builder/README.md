# eval-framework-builder, Claude Code Skill

A Claude Code skill that turns a plain description of an AI feature into a shipping-grade evaluation framework: quality dimensions, a scored rubric with anchors, a golden test set structure, and pass/fail thresholds.

---

## What it does

Describe an AI feature, what it generates, for whom, and what "good" looks like, and the skill produces:

1. **Quality dimensions**: 4–6 axes specific to the feature, not generic "quality"
2. **Scored rubric**: a 1–5 scale per dimension with concrete anchors at every point, so a 2 and a 4 are actually distinguishable
3. **Golden set structure**: test case categories (typical, edge case, known failure modes, adversarial, ambiguous, out-of-scope) with recommended proportions
4. **Pass/fail thresholds**: a concrete, checkable shipping rule, including which dimensions are hard-fails
5. **Judge prompt (optional)**: a draft prompt for automating rubric scoring at volume

The output is a working eval you can run against real outputs next week, not a framework for thinking about evals.

---

## Requirements

- [Claude Code](https://claude.ai/code) (CLI or desktop app)

---

## Installation

1. Clone or download this repo
2. Copy this repo's folder into your Claude Code skills directory as `eval-framework-builder`:

**macOS / Linux:**
```bash
cp -r ProductManagerEvalFrameworkBuilder ~/.claude/skills/eval-framework-builder
```

**Windows (PowerShell):**
```powershell
Copy-Item -Recurse ProductManagerEvalFrameworkBuilder "$env:USERPROFILE\.claude\skills\eval-framework-builder"
```

Your skills directory should look like:
```
~/.claude/skills/
  eval-framework-builder/
    SKILL.md
    evals/
      evals.json
```

3. Restart Claude Code (or reload the window in the desktop app)

---

## Usage

- "Build an eval framework for our AI-generated ad copy feature"
- "How do I evaluate whether our AI campaign brief generator is any good?"
- "I need a golden set and quality bar for this AI feature before we ship it"
- "Define pass/fail thresholds for our AI output before it goes to CI"

Provide: what the feature generates, the input it works from, who consumes the output, and any known failure modes. The skill will note assumptions where context is missing rather than stall on follow-up questions.

---

## Evals

Three test cases:

1. **Build a framework for AI-generated marketing email copy**: tests dimension selection, rubric anchor specificity, and golden set proportions for a brand-sensitive, customer-facing feature
2. **Build a framework for an internal AI summarization tool**: tests how the skill calibrates thresholds differently for a lower-stakes, human-reviewed use case
3. **Build a framework with a request for a judge prompt**: tests that the optional automated scoring prompt is offered and correctly incorporates the rubric anchors

---

## Customization

The dimension library and golden set category proportions are in `SKILL.md` under Steps 2 and 4. Adjust the proportions if your feature has a different risk profile, or extend the dimension table with axes specific to your domain (e.g., localization accuracy, accessibility compliance).

---

## License

MIT
