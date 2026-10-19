# PM Take-Home Case Study Builder

A Claude Code skill that runs a PM case study from the raw assignment to a finished deck or doc you can send. It parses what the assignment is actually testing, researches the company before the market, keeps every number traceable to a primary source, and pressure-tests your framing from three hostile seats before anything gets designed.

Most case studies are not graded on the answer. They are graded on whether you can turn an ambiguous thesis into a sharp, defensible decision and explain the trade-offs. This skill front-loads that call and then attacks it.

## What it does

- Names the literal deliverables, the constraints, and what the assignment is really testing
- Researches the company first (founder interviews, customers, stage, sales motion), then the market
- Builds a source ledger in its own folder, including a do-not-use list for numbers that only trace to content farms
- Writes a framing memo that takes a position and names the rejected alternative
- Runs an adversarial check from the buyer's, founder's, and evaluator's seats
- Merges findings into a locked strategy with a decisions table you can reread before the walkthrough
- Writes the deliverable copy in markdown, then builds the deck with a generator script
- Final pass against the prompt's literal requirements, including an honest counter-signal

## Who it's for

Product managers with a take-home case study, work sample, or product exercise to build. Especially useful for founding or Staff PM loops, where the prompt is deliberately vague and the grading is about judgment rather than completeness.

If you already have a draft and want it critiqued instead, use [ProductManagerTakeHomeCaseStudyReviewer](https://github.com/Bellistri-Nick/ProductManagerTakeHomeCaseStudyReviewer).

## How to use it

Install via [Claude Code](https://claude.ai/code). Drop the contents into `~/.claude/skills/pm-take-home-case/`, keeping the `references/` folder intact.

Trigger it with:

> "I'm interviewing for a founding PM role and they gave me a case study. Collaborate with me on it."
> "They said every number has to be cited to a credible source. Help me with this assignment."
> "Before I build the deck, tear my framing apart the way the hiring manager would."

Paste or attach the assignment prompt. The skill does not interview you first. It researches, forms a view, and brings it back for you to push on.

## The adversarial check

The step that most separates a good case study from a generic one, and the one most likely to get skipped. Three seats, each with a different killer question:

- **The buyer** asks about liability and credibility, not price. This seat usually produces a better value proposition than the one in your memo, plus the adoption landmine your framing quietly assumed away.
- **The founder** asks why this, why us, why now, and what it costs in focus. This seat produces the kill criteria and the competitive window.
- **The evaluator** asks what would rank this below another candidate. This seat catches missing sections, scope that was never cut, and the obvious answer you failed to name.

Findings get folded back into the deliverable, usually as a headline, a risk row, or a phasing decision. Simulated critique is never presented as user research. It appears as reasoning or as a hypothesis to test, because an evaluator who catches a fabricated interview will discount everything else.

## Source discipline

Case prompts increasingly say some version of "we will check your numbers." This skill takes that literally:

- Every figure gets a ledger row before it gets used, with a reference ID carried into the deliverable in brackets
- Numbers that circulate widely but trace only to SEO pages get a do-not-use row naming the bad source
- When a number does not exist publicly, the skill gives the formula with the audience's own inputs and one sourced anchor, then says plainly that the first phase measures it
- Counter-signals are searched for deliberately and included, because an evaluator who knows the market will think of them anyway

## Common failure modes it prevents

- **Fabricated statistics** that trace back to content farms and end the candidacy
- **A pitch with no counter-signal**, which reads as a candidate who did not look hard
- **Scope that was never cut**, since the cut list is graded as heavily as the build list
- **No stated behavior change**, which means the product is not real
- **The obvious framing left unnamed**, so the evaluator assumes it was never considered
- **Topic-label slides** instead of assertion headlines

## Files

| File | What it holds |
|---|---|
| `SKILL.md` | The nine-step workflow |
| `references/source-discipline.md` | Credible sources, missing numbers, the do-not-use list, counter-signals |
| `references/adversarial-check.md` | The three seats and how to fold findings back in |
| `references/deck-build.md` | The slide generator pattern and the layout budget |
| `evals/evals.json` | Three test prompts covering the full workflow, a sourcing dead end, and a standalone adversarial pass |

## License

MIT
