# Building the deck

Use the Slides artifact type. Start with the slides quickstart, which returns the
type link and any design systems the account has, then create the deck and fill
its files.

## Generate the slides, do not hand-write them

Write a Python script that emits every slide file plus the deck index, and run
it. Writing sixteen HTML files by hand is slow, drifts in style between slides,
and makes a copy edit expensive. A generator gives you shared helpers for the
repeated elements and one place to change the palette.

Structure the script as:

- **Palette and type constants at the top.** One dark, one light, one accent,
  plus a card tone and a border tone. Tone the whites and blacks toward the
  palette rather than using pure white or black.
- **Small helpers** for the elements that repeat: the section wrapper, the
  heading, the eyebrow label, a card, a table, the footer row with source and
  page number.
- **One block per slide**, in order, with its speaker notes.
- **A final loop** writing each slide file and the index.

Save the generator with the drafts. Copy edits then regenerate in one step, and
the user can change a headline without touching HTML.

## The layout budget

A slide is 1920 by 1080 with 128px margins, so the usable area is 1664 by 824.
Give the footer band room by using bottom padding of 160px on slides that have
one. Nothing else sits below y 920.

What actually overflows, in order of how often it bites:

- **Tables.** A row costs roughly 2.1 times the font size per line of text. Nine
  rows at 24px with a heading above is close to the limit. If a table does not
  fit, cut a row rather than shrinking below 24px, which is the floor everywhere
  including footers and labels.
- **Card rows.** Four or five cards across 1664px leaves about 300px each. Text
  wraps only at spaces, so a long word forces the card wider. Budget about 0.6
  times the font size per character for the longest word.
- **Dense content slides.** If a slide needs more than about seven rows plus
  supporting text, it is two slides.

When something does not fit, split the slide. Nothing shrinks gracefully.

## Slide craft for a case study

- **Headlines are assertions.** The headline carries the claim; the body
  supports it. A reader who only reads headlines should get the argument.
- **Numbers go in stat tiles or tables**, never buried in a sentence.
- **Two dark statement slides** break up a light deck. The cover and one
  high-energy slide, usually why-now, work well.
- **Reference IDs in brackets** next to every figure, with a source appendix at
  the end. The appendix does not count toward a slide limit, but say so.
- **Speaker notes on every slide**, holding the trade-off rather than restating
  the slide. These become the walkthrough prep, which is often the real reason
  the deck exists.
- **Repeat layouts across slides of the same kind** so headings do not hop
  between slides.

## Mechanics worth knowing

- Every style is inline and drawn from a closed subset. No classes, no `var()`,
  no margin. Check the type's format reference before reaching for anything
  unusual.
- Fonts are declared once in the deck index, not in slide files. Two families is
  the norm: one display, one text.
- Publish every slide file and the index in one call. Later edits send only the
  changed files, and the index only when the title, order, sections or fonts
  change.
- On Windows, a long generator passed inline to a shell can fail to spawn. Write
  the script to a file, then run it.
- Do not open, screenshot, or verify the published deck unless the user asks.
  Hand over the link and the judgment calls instead.

## After publishing

Tell the user the link, that it is private until they share it, and that it
downloads as PowerPoint or PDF. Then name the two or three layout decisions you
made that they might want to overrule, particularly any slide where content was
cut or restructured to fit.
