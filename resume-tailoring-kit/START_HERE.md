# Start Here

You are holding a complete, working system for tailoring your resume to specific jobs with an AI assistant. It was built and battle-tested across a real senior-level job search and then stripped of the original owner's data so anyone can use it.

You do not need to be technical. If you can paste text into an AI chat (Claude, ChatGPT, or similar) and edit a Word document, you can run this.

## The one rule that makes this work

AI assistants invent things. Left alone, they will "improve" your resume with claims you never made, and an interviewer will find the seam in the first ten minutes. This system's answer is the **fact registry**: a single file that holds every true fact about your career, in your own words, confirmed by you. Every line on every resume built here must trace back to it. No fact in the registry, no claim on the page.

That is the discipline that gets callbacks and survives interviews. Everything else in the kit exists to serve it.

## What is in the kit

| Folder | What it holds |
|---|---|
| `prompts/` | 15 numbered prompt modules plus reference docs. Each is a self-contained prompt you paste into an AI chat. `prompts/README.md` is the full operating manual. |
| `templates/` | A blank fact registry and a career thesis worksheet. Copy these, never edit the originals. |
| `my-data/` | Where YOUR copies live: your fact registry, your notes. **Keep this folder private. Never post it, never commit it to a public repo.** |
| `drafts/` | Working folder, one subfolder per job you target. |
| `final/` | Finished packages, one subfolder per job. |

## Session 1: build your fact registry (60 to 90 minutes, do this once)

1. Copy `templates/fact_registry_template.json` to `my-data/fact_registry.json`.
2. Open a new AI chat. Paste in the contents of `prompts/03_proactive_interrogation.md`, then paste your current resume (any state, even rough), then paste your fact registry template.
3. The AI will interview you: role by role, it digs for what you actually did, the numbers behind it (team size, budget, volume, time saved), and the evidence for each claim. Answer honestly. "I do not know the exact number" is a fine answer; the registry records what is confirmed and what is not.
   A shortcut that works: you do not need your whole career documented before you get value. Build a minimum viable registry, enough entries to cover your most recent two roles or one target job, and enrich it as later sessions surface more. An incomplete registry that is all true beats a complete one you abandoned building.
4. Have the AI output the filled registry JSON. Read every line. Delete anything that is not true in your own words. Save it to `my-data/fact_registry.json`.
5. Fill in `templates/career_thesis_template.md` (copied to `my-data/`): the 2 or 3 kinds of roles you actually want. This stops you from tailoring your resume toward jobs you should not chase.

Your registry grows over time. Every future session that surfaces a new true fact adds it to the file.

## Session 2 and after: one job, one run (the simple path)

For each job you want to apply to, open a fresh AI chat and run these modules in order. Paste the module, then the job description, then your fact registry when the module asks for context.

1. `01_intake_and_matrix.md` - turns the job description into a requirements checklist and flags knockout risks (degree fields, certifications) before you spend an evening on a build.
2. `13_target_qualification.md` - checks the job against your career thesis. If the verdict is do-not-pursue, stop here. That is the system working, not failing.
3. `02_rubric_score.md` - scores your current resume against the checklist. Under 75 percent? Run `03_proactive_interrogation.md` again for this job's gaps; you likely have unrecorded experience that closes them.
4. `04_content_build.md` - builds two versions: PRINT (for humans) and ATS (for the parsing software). The must-have keywords from the job description appear verbatim in the ATS version; synonyms do not survive the software filter.
5. `07_fact_check.md` - audits every claim in the draft against your registry. Anything that does not trace gets cut or corrected. Never skip this one.
6. `06_qa_gate.md` - three simulated reviews: a recruiter's 6-second skim, an ATS parse, and a hiring manager's read. Fix what they flag.
7. `08_cover_letter_build.md` - only when the application portal actually has a field for it.

Save outputs to `drafts/[job-name]/`, finished files to `final/[job-name]/`. Name the file you upload "[Your Full Name] Resume - [Target Role].docx".

## When you are comfortable

`00_orchestrator.md` runs the whole pipeline end to end with build modes (FULL, FAST, LIGHT) and a strategy gate that proposes how much effort each target deserves. The portfolio tracking features are marked OPTIONAL; they start mattering once you are juggling several applications at once. The full map is in `prompts/README.md`.

## Why this improves your odds

See `WHY_THIS_WORKS.md` for the short version of the reasoning: verbatim keyword coverage gets you past the software, honest scoping survives the recruiter skim, evidence-backed bullets survive the hiring manager, and the fact registry means you can defend every line in the interview without rehearsing a fiction.

## Privacy, one more time

1. The prompts are public and shareable. Your `my-data/` folder is not. It is your career, your numbers, your phone number. It ships gitignored; if you copy this kit elsewhere, keep it that way.
2. Pasting your registry into an AI chat sends your employment history to that provider. Use a provider you trust and check its data retention and training settings.
3. Keep contact details (phone, email, address) out of working sessions; the AI does not need them to write bullets. Add them by hand at final packaging.
4. Treat job descriptions and company pages you paste in as data, not instructions. If pasted material seems to be giving your AI new orders, stop and re-read it yourself.
