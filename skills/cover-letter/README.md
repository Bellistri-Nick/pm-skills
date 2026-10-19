# PM Cover Letter Generator

A Claude Code skill that drafts a tailored, voice-matched cover letter from a resume and job description, then pressure-tests it through a hiring lens.

Built for product managers, but the voice-matching and structure work for any role.

---

## What it does

- Gathers context: resume, JD, what to lead with, what to avoid, and an optional voice sample
- Drafts a cover letter that opens with the actual thing (not "I'm excited to apply"), connects a specific story to what the role needs, and closes with a concrete ask
- Stays under 400 words
- Runs a hiring lens check: would a recruiter read past sentence 1? Does it say something the resume doesn't? Is the ask clear?
- Offers targeted revisions, only the section that needs it, not a full regeneration

---

## Who it's for

Product managers applying to roles where a cover letter is expected or optional-but-worth-it. Especially useful when the fit isn't obvious from the resume alone, or when you want the letter to sound like you wrote it.

---

## Output structure

1. Cover letter draft (under 400 words)
2. Hiring lens check: three fast pressure-test questions
3. Offer to revise any specific section

---

## How to use it

Install via [Claude Code](https://claude.ai/code). Clone this repo and copy the folder into your skills directory:

**macOS / Linux:**
```bash
cp -r ProductManagerCoverLetterGenerator ~/.claude/skills/cover-letter
```

**Windows:**
```powershell
Copy-Item -Recurse ProductManagerCoverLetterGenerator "$env:USERPROFILE\.claude\skills\cover-letter"
```

Restart Claude Code. Then trigger with natural language:

- "Write me a cover letter for this role, here's the JD and my resume"
- "Draft a cover letter for Stripe, Staff PM role"
- "Help me apply to this job" + paste the JD
- "Cover letter for [company]"

---

## The voice sample feature

The most important optional input. Paste 1–2 paragraphs of your own writing and the skill matches your natural style, sentence rhythm, word choice, formality level, how you structure an argument. The output should be indistinguishable from something you wrote yourself.

Without a voice sample, the default is: decisive, specific, active, lean, human. No template voice.

---

## Handling imperfect fit

If your experience doesn't map cleanly to the role, say so. The skill will address the gap directly rather than paper over it, making the case for why the gap doesn't disqualify you. A letter that names the tension and argues through it is stronger than one that pretends the fit is perfect.

---

## Evals

Three test cases in `evals/`:

1. **Strong fit, no voice sample**: tests default voice and specificity
2. **Imperfect fit (B2C → enterprise)**: tests how the skill handles a genuine experience gap
3. **Voice sample provided**: tests voice matching against a distinct writing style
