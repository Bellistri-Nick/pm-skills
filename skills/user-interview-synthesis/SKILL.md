---
name: user-interview-synthesis
description: >
  Transform raw user interview notes into structured discovery output: themes,
  pain points, opportunity areas, supporting quotes, and frequency counts.
  Optionally reframes findings as Jobs-to-be-Done or Opportunity Solutions Tree
  branches. Use when the user asks to synthesize, analyze, or make sense of
  user research, interview notes, or discovery sessions. Also triggers for:
  "synthesize these interviews", "what patterns are in my research", "turn these
  notes into insights", "what did users say about X", "help me make sense of this
  research", or when the user pastes interview notes and asks for analysis.
  Invoke immediately — gather context as part of the skill flow.
---

# User Interview Synthesis

## What this skill does

Takes raw, messy interview notes and produces structured discovery output that's
ready to share with a team or feed into a roadmap. Every claim is grounded in
the source material — no invented insights, no unearned conclusions.

The output distinguishes observed behavior from stated preferences, flags
contradictions, and surfaces the surprising things alongside the expected ones.

---

## Step 1: Gather context

Collect in one prompt. Skip anything already in context:

1. **Raw notes** — paste everything. Messy is fine: stream-of-consciousness, bullet fragments, timestamps, direct quotes mixed with paraphrases. Don't clean up before pasting.
2. **Research question** — what were you trying to learn? (e.g., "Why do users abandon the onboarding flow?" or "What does the weekly planning process actually look like?")
3. **User segments** — who was interviewed? Were there multiple segments? (e.g., "8 enterprise finance managers and 4 SMB owners")
4. **Number of participants** — total count, and breakdown by segment if multiple
5. **Stage of discovery** — problem discovery, solution validation, usability testing, or general continuous discovery
6. **Specific hypotheses** — anything they were trying to confirm or disprove (optional)
7. **Output format preferences** — any specific framing requested (e.g., JTBD, OST branches, stakeholder summary)

Once you have what you need, proceed. If notes are very long, process all of them — don't truncate or sample.

---

## Step 2: Process the notes

Before producing output, do internal work:

- Read all notes fully before drawing any conclusions
- Tag each observation to a participant (use generic IDs if names aren't provided: P1, P2, etc.)
- Distinguish direct quotes from paraphrases — only use exact quotes when the language is verbatim or near-verbatim
- Flag contradictions between participants or between what participants said vs. what they did
- Note frequency: how many participants mentioned each theme unprompted vs. when asked

---

## Step 3: Synthesis output

Present findings in this order:

---

### Overview

A 2–4 sentence framing of the research: who was interviewed, what was explored, and the headline takeaway. One honest sentence on the quality of the signal — e.g., "Strong convergence across 9 of 12 participants on the core pain point" or "Mixed signals — enterprise and SMB users described the problem differently."

---

### Key themes

3–6 themes, ordered by frequency and strength of signal. For each:

**[Theme name]**
- **What it is**: 1–2 sentences describing the pattern
- **Frequency**: how many participants expressed this (e.g., "8 of 12, 6 unprompted")
- **Representative quote**: one direct quote that best captures it
- **Behavioral signal**: what did users *do* (not just say) that supports this? (omit if not present in notes)

---

### Pain points

Specific friction, frustration, or unmet needs. Distinct from themes — more concrete and actionable. Each pain point should be:
- Named specifically (not "users find X hard" but "users lose context when switching between X and Y")
- Grounded in at least 2 participant observations
- Tagged with a frequency count
- Accompanied by 1–2 supporting quotes

Order by frequency × severity signal.

---

### Behavioral observations vs. stated preferences

A short section (bullet list or brief prose) noting where what users *said* differed from what they *did* or described doing. This is often where the real insight lives. If there's no meaningful gap, say so and move on.

---

### Opportunity areas

3–5 opportunity areas derived from the pain points and themes. Frame each as:

> "Users need a way to [job to be done] so that [desired outcome], but today [current friction or gap]."

These should be problem-space statements, not solutions. Don't name features here.

---

### Surprising or contradictory findings

Anything that challenged a hypothesis, contradicted another participant, or was unexpected given the research question. 2–4 bullets. If nothing was surprising, omit this section rather than manufacturing surprises.

---

### Signal quality and gaps

An honest read on what the research does and doesn't establish:
- What's well-supported (strong convergence, behavioral evidence)
- What's directional but needs more signal
- What questions weren't answered and should drive the next round

---

## Step 4: Optional output framings

If the user requests a specific framing, add one of the following sections after the synthesis:

### Jobs-to-be-Done framing

Rewrite the top 3 opportunity areas as JTBD statements:

> "When [situation], I want to [motivation], so I can [expected outcome]."

One job per opportunity area. Include the functional, emotional, and social dimension where the notes support it.

---

### Opportunity Solutions Tree branches

Map the findings to an OST structure:

- **Desired outcome**: restate the product goal or OKR this research maps to
- **Opportunity nodes**: each pain point or unmet need becomes a branch
- **Sub-opportunities**: break each branch into more specific needs where the data supports it

Present as an indented list. Don't add solutions or experiments — this is the opportunity layer only.

---

### Stakeholder summary

A 5–7 bullet exec-ready summary of the research. No jargon. Suitable for a Slack message to a Director or VP. Each bullet is one clear, specific finding.

---

## Step 5: Offer follow-on artifacts

After the synthesis, offer:

> "Want me to go deeper on any of this? I can rewrite the opportunity areas as JTBD statements, map findings to an OST, draft a stakeholder summary, or turn a specific pain point into a discovery brief. Just say what's useful."

---

## Tone guidance

Rigorous and honest.

- Don't invent patterns that aren't in the data. If only 2 of 10 participants mentioned something, say "2 of 10" — don't present it as a theme.
- Don't round up. "Half the participants" when it was 5 of 12 is imprecise — use the actual number.
- Don't smooth over contradictions. If enterprise users said one thing and SMB users said the opposite, that's a finding, not a problem to resolve.
- If the notes are thin or low-quality, say so. "These notes don't give enough detail to draw strong conclusions about X" is more useful than a confident-sounding synthesis built on weak data.
