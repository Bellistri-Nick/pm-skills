# PM Take-Home Assignment Reviewer

A Claude Code skill that reviews a completed PM take-home or case assignment before you submit it. It evaluates your work through the lens of what hiring panels actually look for, scores it across five dimensions, simulates two reviewer voices, and tells you exactly what to fix and in what order given your remaining time.

## What it does

- Identifies the assignment type (prioritization, strategy, metrics, execution, product critique, 0-to-1)
- Scores across five dimensions: problem framing, prioritization logic, user/market understanding, execution realism, communication clarity
- Simulates a Senior PM reviewer and a Hiring Manager with distinct concerns
- Flags the most common take-home failure modes before the panel sees them
- Delivers a prioritized fix list with time estimates (~5 min, ~15 min, ~30 min)
- Offers to rewrite specific sections while preserving your voice and ideas

## Who it's for

Product managers preparing to submit a PM take-home assignment, product case, or strategy exercise as part of an interview process. Especially useful when you're time-pressured and need to know what to fix first.

## How to use it

Install via [Claude Code](https://claude.ai/code). Drop the `SKILL.md` into your `~/.claude/skills/take-home-reviewer/` directory.

Trigger it with:

> "I have a PM take-home due tomorrow, can you review it before I submit?"
> "Review my case assignment for a Staff PM role at [company]."
> "Is this product strategy exercise ready to send?"

Paste the assignment prompt and your response. Tell it how much time you have left, that shapes which fixes to prioritize.

## Output structure

1. Assignment type identification
2. Five-dimension scoring table
3. Senior PM reviewer simulation
4. Hiring Manager simulation
5. Top fixes ordered by impact × time-to-fix
6. Offer to rewrite specific sections

## Common failure modes it catches

- **Framework theater**, using RICE or Kano without showing the judgment behind the inputs
- **Missing the user**, all strategy, no evidence that real people have this problem
- **No point of view**, listing options without committing to a recommendation
- **Undefended assumptions**, entire strategy rests on something never named or tested
- **Polished but shallow**, well-formatted, doesn't hold up to one "why?"
