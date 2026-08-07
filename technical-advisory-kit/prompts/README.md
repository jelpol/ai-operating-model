# Technical Advisory Kit - Operating Manual

**Version:** 1.0 (public starter kit release)

## What this is

A method for using an AI as a technical study partner and design reviewer without absorbing its hallucinations or its flattery. Three paste-in modules plus a principles file, built around two artifacts you own: a knowledge registry (what you know, at what depth, and which gaps are open) and a growing folder of anchored learnings and kept verdicts.

## The modules

| Module | Purpose |
|---|---|
| `01_research_anchoring.md` | Study protocol: map material to governing frameworks, state the frameworks' blind spots, name YOUR gaps with a drill order, read the leverage, link to prior learnings |
| `02_validate_a_design.md` | Verdict engine: six dimensions, three verdicts (Sound / Sound with caveats / Flawed) |
| `03_verification_gate.md` | Session-wide answer gate: anti-hallucination rules, Tier A/B rigor, source-trust hierarchy |
| `principles.md` | The standing rules, tiered by precedence |

## Your data files (all in `my-data/`, all private)

| File | What it holds |
|---|---|
| `knowledge_registry.md` | Expert domains, working proficiency, named open gaps, growth domains, learning log. Copy from `templates/knowledge_registry_template.md`. |
| `learnings/` | Anchored study artifacts from Module 01, one file each, front-matter per the template |
| `validations/` | Kept verdicts from Module 02 worth citing later |

## Promotion criteria - what gets kept

Most session content deserves no file at all. Promote only when it clears the bar:

1. To `learnings/` when the teaching is durable and reusable: you would want it again in a future session and it is more than a one-line fact. Tag type: explanation (durable why) or reference (expiring facts). Never both in one file.
2. To `validations/` when a verdict is worth citing later: a design decision, a product evaluation, a "we chose X because Y" your future self will reference.
3. Everything else stays in session notes or nowhere. A bloated learnings folder nobody reads is worse than a thin one. Promotion is a tax; spend it only where it pays.

## Artifact front-matter

Every durable artifact opens with the block in `templates/learning_artifact_template.md` (title, type, domain, tags, dates, confidence, sources, expiry). Flat folders without front-matter rot into an unsearchable pile.

## The rhythm

1. **Per session:** paste `03_verification_gate.md` first; it governs the whole chat. Close by updating the registry if your level shifted.
2. **Per study item:** run Module 01. The gap list and drill order are the deliverable; the mapping alone is comprehension theater.
3. **Per design decision:** run Module 02. Keep the verdict only if future-you will cite it.
4. **Monthly:** re-check anything past its expiry, reconcile contradictions, confirm the registry still matches reality.
