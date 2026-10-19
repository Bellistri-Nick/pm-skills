---
name: ai-quality-scorecard
description: >
  Score a single piece of AI-generated output against quality criteria and get
  a specific, evidence-cited verdict on whether it's good enough to ship or
  send as-is. Takes the output plus the context it was generated from (the
  brief, prompt, or input) and scores it dimension by dimension, flags the
  single biggest risk, and offers a rewritten version fixing the weakest
  dimension. Works with a custom rubric (e.g. one built with
  eval-framework-builder) or a sensible default. Use when the user pastes
  AI-generated content and asks if it's good, ready to send, or ready to
  ship. Also triggers for: "score this AI output", "is this good enough to
  send", "grade this AI-generated draft", "quality check this AI output", "AI
  output review", or when the user pastes generated copy, code, or content
  and asks for an assessment. Invoke immediately — gather context as part of
  the skill flow.
---

# AI Quality Scorecard

## What this skill does

Takes one piece of AI-generated output and scores it against quality criteria
— either a rubric the user already has (from `eval-framework-builder` or
elsewhere) or a sensible default rubric if they don't. Gives a score per
dimension with a specific justification citing the actual output, an overall
verdict against a threshold, the single biggest risk if this ships as-is, and
an offer to fix the weakest dimension on the spot.

This is a spot-check tool for one output, not a framework-building exercise —
if the user needs to design an eval system rather than score one piece of
content, point them to `eval-framework-builder` instead.

---

## Step 1: Gather context

Collect in one prompt. Skip anything already in context:

1. **The output** — the actual AI-generated content to be scored (paste it or share a file)
2. **What it was generated from** — the brief, prompt, source document, or input that produced it
3. **Intended use case and audience** — who sees this and what happens if it's weak (internal draft, customer email, published copy, production code)
4. **A rubric, if one exists** — dimensions and scoring criteria already defined (e.g., from an eval framework). If none, say so and the default rubric in Step 2 will be used
5. **Shipping threshold, if known** — what score or bar counts as "good enough." Default to the standard in Step 4 if not specified

If the output type is unusual (code, structured data, an image description),
adapt the default rubric's dimension names to fit rather than forcing a bad
match — note the adaptation.

Once you have what you need, proceed. Don't ask follow-up questions — use
judgment on anything ambiguous.

---

## Step 2: Default rubric (used only if no custom rubric is provided)

| Dimension | What it measures |
|---|---|
| Relevance | Does the output actually address the input/brief, or is it generic filler? |
| Correctness | Are facts, claims, numbers, or logic in the output accurate and traceable to the input? |
| Instruction adherence | Did it follow the explicit constraints in the brief — required elements, format, length, exclusions? |
| Tone / fit | Does it match the expected voice and register for this audience and use case? |
| Structural completeness | Are all required components present and correctly formatted? |
| Originality | Does it avoid generic, template-y, or repetitive phrasing? |
| Safety | Does it avoid unsupported claims, policy violations, or anything that would be reputationally or legally risky to publish? |

If a custom rubric was provided in Step 1, use its dimensions and anchors
instead of this table — do not blend the two.

---

## Step 3: Score each dimension

For each dimension (custom or default), score 1–5:

**[Dimension name] — [score]/5**
[1–2 sentence justification that cites specific language, structure, or
content from the actual output being scored — not a generic statement of
what the score means]

If a dimension doesn't apply to this output type, mark it N/A and say why
rather than forcing a score.

---

## Step 4: Verdict

Aggregate into an overall read:

**Overall: [average score]/5 — [Ship / Ship with edits / Do not ship]**

Default threshold logic if no custom threshold was given in Step 1:
- **Ship** — no dimension below 3, average ≥4.0
- **Ship with edits** — no dimension below 2, average between 3.0–4.0, or exactly one dimension below 3
- **Do not ship** — any dimension at 1, safety dimension below 3, or average below 3.0

State which rule triggered the verdict, not just the verdict itself.

---

## Step 5: Biggest risk

Name the single biggest risk if this output ships unchanged. One or two
sentences. Be specific about the actual consequence — "the discount claim in
the second sentence isn't supported by the brief, which could get flagged as
misleading if a customer checks" beats "accuracy could be improved."

If nothing rises to the level of a real risk, say so plainly rather than
manufacturing one.

---

## Step 6: Offer a fix

After the verdict, offer:

> "Want me to rewrite this to fix [the weakest dimension]? I can also do a
> full pass across everything that scored below [threshold]."

If the user says yes, rewrite only what's needed to address the flagged
issues — don't regenerate the whole piece from scratch unless the low scores
are pervasive enough that a full rewrite is actually the faster path. If so,
say that's what you're doing and why.

---

## Tone guidance

Specific and honest, not diplomatic-by-default.

- Every score needs a reason tied to the actual text in front of you — "tone
  is a 3, the second paragraph shifts into a much more casual register than
  the rest of the piece" beats "tone is decent"
- If the output is genuinely strong, say so without hedging — don't manufacture
  criticism to seem balanced
- If the output has a real problem, lead with it — don't bury a ship-blocking
  issue under three paragraphs of minor notes
- Match the standard of someone whose job is on the line if this ships broken —
  not someone being nice about a first draft
