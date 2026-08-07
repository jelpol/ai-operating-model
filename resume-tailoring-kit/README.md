# Resume Tailoring Kit

A complete, working prompt pipeline for tailoring your resume to specific jobs with an AI assistant, without letting the AI invent your career. Built and battle-tested across a real senior-level job search inside the operating model this repository documents, then sanitized into a public starter kit.

**New here? Read [START_HERE.md](START_HERE.md). It is the whole onboarding.**

## What it is

1. Fifteen numbered prompt modules in [prompts/](prompts/) that you paste into any capable AI chat: job description intake, scoring, gap interrogation, content build (human PRINT and parser ATS versions), fact-checking, cover letter, QA with simulated recruiter, ATS, and hiring manager reviews, interview prep, and more. [prompts/README.md](prompts/README.md) is the operating manual.
2. A [fact registry template](templates/fact_registry_template.json): the anti-hallucination backbone. Every resume claim must trace to a fact you confirmed in your own words.
3. A [career thesis worksheet](templates/career_thesis_template.md) so the pipeline can tell you which jobs deserve your effort at all.
4. [WHY_THIS_WORKS.md](WHY_THIS_WORKS.md): one page on the reasoning, the three filters between you and an interview, and what this kit deliberately will not do.

## What it is not

It does not fabricate experience, pad titles, or promise interviews. The discipline runs the other way: honest scoping, evidence-backed claims, and a registry you can defend line by line in the room.

## Privacy

The prompts are public; your data is not. Everything personal lives in `my-data/`, which ships empty and must stay private. If you fork this kit, `my-data/` is already gitignored; keep it that way.

## Relation to the wider repository

This kit is the job-search domain of the [operating model](../thesis.md) exported for reuse, the same way the [starter kit](../starter-kit/) exports the framework skeleton. Prose is CC BY 4.0, templates and prompt modules are MIT; see [LICENSE](LICENSE).
