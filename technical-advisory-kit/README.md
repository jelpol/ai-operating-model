# Technical Advisory Kit

A method for using an AI as a technical study partner and design reviewer without absorbing its hallucinations or its flattery. Built and battle-tested inside the operating model this repository documents, then sanitized into a public starter kit.

**New here? Read [START_HERE.md](START_HERE.md). It is the whole onboarding.**

## What it is

1. Three paste-in modules in [prompts/](prompts/): a research anchoring protocol (map material to its governing frameworks, state the frameworks' blind spots, name YOUR gaps with a drill order), a design validation engine (six dimensions, three verdicts), and a session-wide verification gate (anti-hallucination rules with a source-trust hierarchy and stakes-tiered rigor). [prompts/README.md](prompts/README.md) is the operating manual.
2. A [knowledge registry template](templates/knowledge_registry_template.md): the honest map of what you know at what depth, which the AI reads to calibrate teaching versus peer review.
3. A [learning artifact template](templates/learning_artifact_template.md) with front-matter that keeps your knowledge base searchable and expiry-aware.

## The core insight

Mapping study material onto a framework is comprehension theater. The deliverables that compound are the framework's stated blind spots, your named gaps with drills to close them, and the links back to what you already learned. Same for design review: an AI that agrees with you is worthless; the six-dimension verdict forces the pentester's, the auditor's, and the 3 AM on-call engineer's reads.

## Privacy

Your registry and learnings live in `my-data/`, which ships empty and gitignored. The prompts are public; your map of your own strengths, weaknesses, and environment is not.

## Relation to the wider repository

This kit is the technical advisory domain of the [operating model](../thesis.md) exported for reuse, alongside the [starter kit](../starter-kit/) (the framework skeleton) and the [resume tailoring kit](../resume-tailoring-kit/) (the job-search domain). Prose is CC BY 4.0, templates and prompt modules are MIT; see [LICENSE](LICENSE).
