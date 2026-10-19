---
name: eval-framework-builder
description: >
  Turn a description of an AI feature into a complete evaluation framework:
  quality dimensions, a scored rubric with anchors, a golden test set
  structure, and pass/fail thresholds for shipping decisions. Optionally
  drafts an automated judge prompt for scaling the rubric. Use when the user
  asks to build an eval, define quality criteria for an AI feature, set a
  quality bar, design a golden set, or figure out how to know if an AI
  feature is "good enough" to ship. Also triggers for: "build an eval
  framework", "how do I evaluate this AI feature", "define a quality bar",
  "golden set", "eval rubric", "is this AI feature ready to ship", or when
  the user describes an AI-generated output type and asks how to measure
  its quality. Invoke immediately — gather context as part of the skill flow.
---

# Eval Framework Builder

## What this skill does

Takes a plain description of an AI feature — what it generates, for whom, and
what "good" means for it — and produces a shipping-grade evaluation framework:

1. **Quality dimensions** — the specific axes this feature needs to be judged on
2. **Scored rubric** — a 1–5 scale per dimension with anchor descriptions, not just labels
3. **Golden set structure** — what categories of test cases to include and how many
4. **Pass/fail thresholds** — the actual bar for "ready to ship," including hard-fail dimensions
5. **Judge prompt (optional)** — a draft prompt for automating dimension scoring at scale

The output is a working eval, not a lecture on eval theory. Every dimension and
threshold should be specific enough that two different people scoring the same
output would land within one point of each other.

---

## Step 1: Gather context

Collect in one prompt. Skip anything already in context:

1. **What the feature generates** — the actual output type (e.g., subject lines, ad copy, campaign briefs, code, summaries, images)
2. **The input** — what goes in to produce that output (a brief, a prompt, a document, structured data)
3. **Audience and use case** — who consumes the output and what happens if it's bad (internal draft a human edits vs. something that ships unreviewed to a customer)
4. **Known failure modes** — anything already observed going wrong (hallucination, off-brand tone, ignoring constraints, repetitive output, wrong format)
5. **Existing eval process, if any** — spot-checking, no process, an existing rubric to improve on
6. **Shipping bar context** — is this framework for a launch decision, a regression gate in CI, ongoing quality monitoring, or model/prompt comparison

If the shipping bar context is unclear, default to building a framework general
enough to serve both a launch decision and ongoing monitoring, and say so.

Once you have what you need, proceed. Don't ask follow-up questions — use
judgment on anything ambiguous and note the assumption.

---

## Step 2: Define quality dimensions

This is the core judgment call in the framework. Bad eval frameworks either
use one vague dimension ("quality") or twelve overlapping ones nobody can
score consistently. Aim for 4–6 dimensions that are independent, observable,
and matter for this specific feature.

Draw from this set, keep what applies, and add feature-specific ones:

| Dimension | What it measures | When it applies |
|---|---|---|
| Correctness / grounding | Are claims, facts, or data in the output accurate and traceable to the input? | Any feature that generates claims, numbers, or summaries |
| Instruction adherence | Did the output actually follow the brief — constraints, required elements, format? | Any feature driven by a structured input or brief |
| Relevance | Does the output address the actual input, or is it generic filler that could apply to anything? | Any generative feature |
| Tone / brand fit | Does the output match the voice, register, and brand guidelines expected? | Customer-facing or brand-sensitive content |
| Structural completeness | Are all required components present and correctly formatted? | Multi-part outputs (emails with subject + body, structured docs) |
| Novelty / non-repetitiveness | Does it avoid generic phrasing, repeated patterns across outputs, or template-y language? | Content generated at volume |
| Safety / policy compliance | Does it avoid disallowed claims, PII exposure, off-limits topics, or compliance violations? | Anything regulated, public-facing, or reputationally risky |
| Actionability | Could someone act on this output without needing to redo the underlying work? | Analysis, recommendations, decision support outputs |

Name each dimension specifically to the feature — not "correctness" in the
abstract but "does the subject line accurately reflect the email's actual
offer." Vague dimensions produce vague scores.

---

## Step 3: Build the scored rubric

For each dimension, write a 1–5 scale with a concrete anchor at each point —
not just "1 = bad, 5 = good." A rubric only works if a 2 and a 4 are
distinguishable without the scorer guessing.

**Format per dimension:**

**[Dimension name]**
- **5 —** [what a clearly excellent output looks like, specific to this feature]
- **4 —** [strong, with a minor gap]
- **3 —** [usable but has a real flaw — the line between ship and don't-ship often sits here]
- **2 —** [significant problem, would need human rework]
- **1 —** [fails this dimension outright]

Write anchors using language specific to the actual output type from Step 1,
not generic quality-speak. If the feature is ad copy, a "3" anchor should
describe an actual kind of mediocre ad copy, not "somewhat adequate."

---

## Step 4: Build the golden set structure

A rubric is only as good as the test cases it's run against. Specify what
categories of inputs the golden set needs and roughly how many of each —
don't just say "collect some examples."

**Standard categories:**

| Category | Purpose | Rough share of set |
|---|---|---|
| Typical / happy path | Confirms the feature works for the common case | ~40% |
| Edge case | Unusual but valid inputs — very short/long inputs, sparse data, multiple valid interpretations | ~20% |
| Known failure modes | Cases built directly from Step 1's known failures, to confirm they're caught | ~15% |
| Adversarial | Inputs designed to break instruction adherence or safety (conflicting constraints, prompt injection attempts, edge-of-policy topics) | ~10% |
| Ambiguous / underspecified | Inputs that don't give the model enough to work with — tests graceful degradation | ~10% |
| Out-of-scope | Inputs the feature shouldn't handle — tests it fails safely rather than confidently producing garbage | ~5% |

Recommend a minimum total size (generally 30–50 for a first pass, more if the
feature has high variance or the team needs statistical confidence in
regression detection). Note where cases should come from: real production
inputs, real user complaints, or synthetic if no real data exists yet, and
flag if the set is currently synthetic-only since that's a known limitation.

---

## Step 5: Set pass/fail thresholds

Translate the rubric into an actual shipping decision. Be explicit about
three things:

1. **Per-dimension minimum** — the lowest acceptable score on any single dimension (commonly 3/5 — "usable")
2. **Hard-fail dimensions** — dimensions where even one low score on the golden set blocks shipping regardless of the average (safety and correctness usually qualify; tone usually doesn't)
3. **Aggregate threshold** — the average score or pass-rate across the golden set required to ship (e.g., "average ≥4.0 across all dimensions, zero hard-fails, ≥90% of cases scoring ≥3 on every dimension")

State the threshold as a concrete, checkable rule — not "generally good
quality." If the user gave a shipping bar context in Step 1 (launch vs. CI
gate vs. monitoring), calibrate strictness accordingly: a CI regression gate
can be stricter and cheaper to fail than a one-time launch decision.

---

## Step 6: Judge prompt (offer, don't force)

After presenting Steps 2–5, offer:

> "Want me to draft a judge prompt so an LLM can score outputs against this
> rubric automatically? Useful for running this at volume instead of scoring
> by hand."

If yes, draft a prompt that:
- Includes the full rubric with anchors inline
- Asks for a score per dimension plus a one-sentence justification citing the actual output
- Asks for the hard-fail flag explicitly if applicable
- Outputs in a structured format (JSON or a fixed template) so scores can be aggregated programmatically
- Includes 1–2 calibration examples per dimension where possible, pulled from the golden set categories in Step 4

Flag honestly that an LLM judge needs periodic spot-checking against human
scores to confirm it isn't drifting, especially on subjective dimensions like
tone.

---

## Step 7: Deliver the framework

Present the full framework as one structured document:

1. **Feature summary** — one paragraph restating what's being evaluated and for whom
2. **Quality dimensions** — the table from Step 2
3. **Scored rubric** — full 1–5 anchors per dimension from Step 3
4. **Golden set spec** — category breakdown and sourcing guidance from Step 4
5. **Shipping thresholds** — the concrete rule from Step 5
6. **Judge prompt** — if requested in Step 6
7. **Open assumptions** — anything guessed in Step 1 that should be confirmed before this framework is treated as final

---

## Tone guidance

Precise, not academic. This is a working tool a PM will actually run against
real outputs next week, not a paper on evaluation methodology.

- If the feature description is too vague to build real dimensions from, say
  so and ask what "bad" has looked like in practice — that's usually the
  fastest way to get specific
- If a proposed dimension can't be scored consistently by two different
  people, flag it and tighten the anchor language
- Don't inflate the dimension count to look thorough — 4 dimensions that are
  actually used beat 8 that aren't
- Be explicit when a threshold is a judgment call versus a hard rule, so the
  user knows what's negotiable
