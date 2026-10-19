---
name: cover-letter
description: >
  Generate a tailored, voice-matched cover letter for a product manager role from
  a resume and job description. Follows with a hiring lens check and offers
  targeted revisions. Use when the user asks to write, draft, or generate a cover
  letter — especially for PM roles. Also triggers for: "write me a cover letter",
  "help me apply to this job", "draft a letter for this role", "cover letter for
  [company]", or when the user pastes a JD and asks for application help.
  Invoke immediately — gather context as part of the skill flow.
---

# Cover Letter Generator

## What this skill does

Drafts a tailored PM cover letter from a resume and job description — in the user's
voice, not a template. Follows with a quick hiring lens check to pressure-test it,
then offers targeted revisions.

The goal: a letter that earns a read, says something the resume doesn't, and ends
with a clear ask. Not a summary of the resume. Not a declaration of passion.

---

## Step 1: Gather context

Collect everything in one prompt. Skip anything already in context:

1. **Resume** — paste the full resume or share a file path
2. **Job description** — paste the full JD, or provide company name + role title if no JD is available
3. **What to lead with** — 1–2 things they most want to highlight (optional; use judgment if not provided)
4. **What to avoid** — anything they don't want in the letter (optional)
5. **Voice sample** — paste a paragraph or two of their own writing so the letter can match their natural style (optional but strongly improves output)

Once you have what you need, draft immediately. Don't ask follow-up questions.

---

## Step 2: Draft the cover letter

### Structure

**Opening paragraph — lead with the actual thing**
Don't open with "I'm excited/thrilled/passionate to apply." Don't open with a biographical
sentence. Open with the specific insight, experience, or conviction that makes this application
worth reading. One to two punchy sentences that pull the reader in.

**Middle — 2 paragraphs, specific and connected**
Each paragraph does one job:
- Paragraph 2: Connect the most relevant experience to what this role actually needs. Use a specific example. Show impact, not just involvement. One concrete story beats three vague claims.
- Paragraph 3: Show you understand what this company is actually building or solving. Reference something specific — a product decision they've made, a problem in their space, a bet they're taking. Don't flatter. Demonstrate attention.

**Close — specific ask, clean exit**
Name what you want (a conversation, a call, a chance to go deeper on a specific topic).
Don't say "please let me know if you have any questions." Don't say "I look forward to hearing from you." Close like someone who expects to get the meeting.

### Length
3–4 paragraphs. Under 400 words. Every sentence earns its place.

### Voice defaults (apply when no voice sample is provided)
- **Decisive, not tentative** — "I built" not "I was involved in building"
- **Specific, not vague** — real metrics, real company names, real decisions made
- **Active, not passive** — "I shipped" not "work was completed"
- **Lean, not padded** — cut every word that doesn't do work
- **Human, not stiff** — this should sound like a person wrote it, not a template

If a voice sample is provided, match it above all else. Study the sentence length, word choice, formality level, and rhythm. The letter should be indistinguishable from something the user wrote themselves.

### Never do this
- "I'm thrilled/excited/passionate to share..." → Lead with the actual thing
- "As a seasoned PM with X years..." → Show, don't label
- "I believe I would be a great fit..." → State it through specifics, not declaration
- "Please let me know if you have any questions" → Specific ask or clean close
- Summarizing the resume → Say something the resume doesn't

---

## Step 3: Hiring lens check

After drafting, run a fast three-question check. Don't turn this into a full review — it's a pressure test.

**1. Recruiter scan (6 seconds)**
Would a recruiter read past sentence 1? Does the opening signal a qualified, interesting candidate? Is there anything that would trigger a skip?

**2. Hiring manager read**
Does this letter say something the resume doesn't? Is there a specific story or insight that makes the application feel real, not templated? Does it demonstrate genuine understanding of the role?

**3. Clarity of ask**
Is the close specific? Does it feel like someone who expects the meeting, or someone who's hoping for a callback?

For each check: one sentence verdict and, if there's an issue, a specific fix.

---

## Step 4: Offer revisions

After the check, offer:

> "Want me to revise anything? I can rework the opening, strengthen the middle paragraphs, adjust the tone, or tailor it more specifically to the JD. Just say what needs work."

If the user requests a revision, rewrite only the section that needs it — don't regenerate the whole letter unless asked.

---

## Tone guidance

This is a tool for getting a job. Write accordingly.

- If the user's experience is a strong fit, the letter should show confidence
- If the fit is imperfect, don't paper over it — address the gap directly and make the case for why it doesn't matter
- A letter that says one true, specific thing memorably is better than a letter that says five true things generically
