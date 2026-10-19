# User Interview Synthesis

A Claude Code skill that transforms raw, messy user interview notes into structured discovery output: themes, pain points, opportunity areas, supporting quotes, and frequency counts.

Built for product managers doing continuous discovery, works at any research stage from early problem exploration to solution validation.

---

## What it does

- Gathers context: raw notes, research question, user segments, participant count, discovery stage, and hypotheses to test
- Reads all notes fully before drawing conclusions, tags observations to participants, separates direct quotes from paraphrases
- Synthesizes themes with real frequency counts ("8 of 12, 6 unprompted") not vague descriptors
- Surfaces behavioral observations vs. stated preferences, where what users *did* differed from what they *said*
- Frames opportunity areas as user needs, not solutions
- Calls out contradictions and counter-signals rather than smoothing them over
- Offers optional JTBD framing, OST branches, or a stakeholder summary on request

---

## Who it's for

Product managers turning raw research into something shareable and actionable. Especially useful after a sprint of discovery interviews when you have 6–12 sets of notes and need to find the signal quickly.

---

## Output structure

1. Overview: who was interviewed, what was explored, honest signal quality read
2. Key themes: 3–6 themes with frequency counts and representative quotes
3. Pain points: specific friction ordered by frequency × severity
4. Behavioral observations vs. stated preferences
5. Opportunity areas: framed as user needs
6. Surprising or contradictory findings
7. Signal quality and gaps: what's well-supported vs. what needs more signal
8. Optional: JTBD statements, OST branches, stakeholder summary

---

## How to use it

Install via [Claude Code](https://claude.ai/code). Clone this repo and copy the folder into your skills directory:

**macOS / Linux:**
```bash
cp -r ProductManagerTranscriptAnalysis ~/.claude/skills/user-interview-synthesis
```

**Windows:**
```powershell
Copy-Item -Recurse ProductManagerTranscriptAnalysis "$env:USERPROFILE\.claude\skills\user-interview-synthesis"
```

Restart Claude Code. Then trigger with natural language:

- "Synthesize these 8 user interviews, we were exploring why users abandon onboarding"
- "What patterns are in my research notes?"
- "Turn these interview notes into a shareable insight doc"
- "Help me make sense of this research" + paste notes

Paste notes in whatever format you have them, fragments, timestamps, stream-of-consciousness. Don't clean them up first.

---

## Optional output formats

Add these to your request:

- **"Include JTBD framing"**, rewrites top opportunity areas as Jobs-to-be-Done statements
- **"Map to an OST"**, structures findings as Opportunity Solutions Tree branches
- **"Give me a stakeholder summary"**, 5–7 bullet exec-ready version for Slack or a leadership update

---

## What makes it rigorous

- Frequency counts are real ("5 of 8"), not rounded ("most users")
- Contradictions between participants are surfaced, not smoothed over
- Thin or low-quality notes are called out, no confident synthesis built on weak data
- Behavioral evidence is separated from stated preferences

---

## Evals

Three test cases in `evals/`:

1. **8 interviews on workflow automation abandonment**: mixed user types, clear outlier (the one user who succeeded)
2. **10 interviews on a solution concept (enterprise vs. SMB split)**: conflicting signals across segments, JTBD framing requested
3. **6 rough interviews on a potential new product**: tests honesty about thin data quality, OST framing requested
