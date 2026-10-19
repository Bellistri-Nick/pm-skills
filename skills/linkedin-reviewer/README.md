# PM LinkedIn Profile Reviewer

A Claude Code skill that reviews a product manager's LinkedIn profile through the lens of three hiring personas: a Recruiter, a Hiring Manager, and a Head of Product. Each reviewer scores your profile sections, quotes specific weaknesses, and delivers prioritized rewrites.

## What it does

- Scores every section: Headline, About, each Experience role, Featured, and Skills
- Simulates three distinct reviewers with different priorities, discoverability, story coherence, and leadership trajectory
- Quotes actual text from your profile when calling out problems
- Delivers a Top 5 rewrite list ordered by hiring impact
- Offers to rewrite any section on request

## Who it's for

Product managers preparing for a job search, updating a stale profile, or optimizing for a specific role (Staff PM, Group PM, Director of Product).

## How to use it

Install via [Claude Code](https://claude.ai/code). Drop the `SKILL.md` into your `~/.claude/skills/linkedin-reviewer/` directory.

Then just paste your LinkedIn profile content and ask:

> "Review my LinkedIn profile, I'm targeting Staff PM roles at AI startups."

Or trigger it directly:

> "help me improve my LinkedIn"
> "is my LinkedIn good for a Group PM role?"
> "optimize my LinkedIn for recruiters"

## Output structure

1. Section scoring table (Headline, About, Experience, Featured, Skills: each scored /10)
2. Three reviewer panels with specific, quoted feedback
3. Panel scorecard
4. Top 5 prioritized rewrites
5. Offer to rewrite any section

## Eval results

Tested against three profile archetypes, weak (all activity, no outcomes), strong (ex-Google/Stripe, real metrics), and mixed (solid metrics but poor framing). The skill hit 100% assertion pass rate vs. 63% for baseline Claude, the structural gaps it closes are: section scoring table, three-reviewer panel format, and explicit rewrite offer.
