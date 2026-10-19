# pm-skills

Thirteen Claude Code skills for product managers. Each one takes a specific PM job, gives it structure, and returns something you can use the same day.

Built by [Nick Bellistri](https://github.com/Bellistri-Nick), a Senior PM working on AI quality at HubSpot. Most of these started as something I needed for my own work. The evals in several of them are the point: I wanted to know the skill beat plain Claude, not hope it did.

## The skills

### AI quality and evals

| Skill | What it does |
|---|---|
| [eval-framework-builder](skills/eval-framework-builder) | Turns an AI feature description into quality dimensions, a scored rubric with anchors, a golden set structure, and ship/no-ship thresholds. Optional automated judge prompt |
| [ai-quality-scorecard](skills/ai-quality-scorecard) | Scores one AI-generated output against quality criteria, cites the evidence, gives a ship/no-ship verdict, and rewrites the weakest dimension |

### Product work

| Skill | What it does |
|---|---|
| [prd-writer](skills/prd-writer) | Writes a PRD from scratch through an adaptive intake interview. Pairs with prd-reviewer |
| [prd-reviewer](skills/prd-reviewer) | Scored review through Peer PM, Lead PM, and CPO lenses. Supports custom reviewer voices |
| [user-interview-synthesis](skills/user-interview-synthesis) | Raw notes into themes, pain points, opportunity areas, frequency counts, JTBD and OST framing |
| [okr-writer](skills/okr-writer) | Drafts OKRs from strategy context, or reviews existing ones. Catches task KRs, vanity metrics, and unmeasurable objectives |
| [competitive-teardown](skills/competitive-teardown) | G2 reviews and website copy into a capabilities analysis, sentiment, gap analysis, and strategic implications |

### Career

| Skill | What it does |
|---|---|
| [resume-review](skills/resume-review) | Three-panel review (Recruiter, Hiring Manager, CPO) with scores, citations, and rewrite offers |
| [linkedin-reviewer](skills/linkedin-reviewer) | Three-panel profile review that scores each section and delivers a prioritized rewrite list |
| [cover-letter](skills/cover-letter) | Voice-matched cover letter from resume and JD, with a hiring lens check |
| [pm-case-study-builder](skills/pm-case-study-builder) | Raw project experience into a portfolio case study, a LinkedIn article, and interview talking points |
| [pm-take-home-case](skills/pm-take-home-case) | Runs a PM take-home end to end, from raw prompt to finished deck, with an adversarial check and every number traced to a source |
| [take-home-reviewer](skills/take-home-reviewer) | Reviews a take-home before you submit it: five-dimension scoring, hiring panel voices, fixes ranked by impact |

## Install

Each folder under `skills/` is one skill. Copy the folder into `~/.claude/skills/` and keep its name.

```bash
git clone https://github.com/Bellistri-Nick/pm-skills
cp -r pm-skills/skills/eval-framework-builder ~/.claude/skills/
```

```powershell
git clone https://github.com/Bellistri-Nick/pm-skills
Copy-Item -Recurse pm-skills\skills\eval-framework-builder "$env:USERPROFILE\.claude\skills\"
```

Restart Claude Code. Each skill triggers from natural language, so no slash command is needed.

## Also by me

[Job Scout](https://github.com/Bellistri-Nick/job-scout): two agents that find the jobs that fit and track applications after you apply. Unit tested, with eval reports and a written case study. This is the larger build.

## License

MIT. See [LICENSE](LICENSE).
