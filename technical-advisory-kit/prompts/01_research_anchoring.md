# Module 01: Research Anchoring

**Version:** 1.0 (public starter kit release)
**Module type:** Study protocol
**Use on:** any external article, writeup, tool, technique, or product you want to actually learn from, not just read

## What this module does

Turns passive reading into anchored comprehension. Every piece of research gets tied to the governing frameworks for its domain, the frameworks' own blind spots get stated, and your personal gaps get named with a drill order. The founding insight: mapping material onto a framework is comprehension theater; the gap list is the deliverable.

## When NOT to use it

A quick factual lookup stays a one-line answer. This protocol fires on material you are studying for proficiency, never on cheap lookups.

---

## PROMPT TO PASTE INTO YOUR AI CHAT

You are running the **Research Anchoring protocol** on material the user provides. Make sure the user has pasted or attached: (1) the material itself (article, writeup, tool documentation), and (2) their knowledge registry from `my-data/knowledge_registry.md`.

Produce all five outputs below in the artifact, not just in conversation. The user saves the result to `my-data/learnings/`.

**Output 1 - Framework mapping.**
Map the material onto the frameworks that govern its domain. For adversary behavior: MITRE ATT&CK for techniques and the Diamond Model for events, threads, and campaign structure, with kill chain phase riding as a Diamond meta-feature. Other domains use their own governing set: NIST 800-171 or CIS benchmarks for control work, ATT&CK plus the detection lifecycle for detection engineering, and so on. Name the framework you chose and why.

**Output 2 - Framework gap analysis.**
State what the chosen frameworks FAIL to capture about this material. This is the half that gets skipped and the half that matters most. A control set derived from a framework inherits that framework's blind spots, so an unstated blind spot becomes an unstated exposure.

**Output 3 - The user's own gap read (the primary output).**
Against the knowledge registry, name what this material asks the user to understand and sort it three ways:
1. Already owned at peer level.
2. Adjacent-new: the base is there, the specific is missing.
3. Genuinely new: the concept itself is new.
Then give the drill order (highest leverage first) and the check for each drill, meaning how the user will know they have it. Add the new rows to the registry's named-gaps table. This output is about the user's comprehension, never about grading their employer's or clients' controls. Run an organizational control read only if the user explicitly asks, and keep it subordinate to the learning read.

**Output 4 - Leverage read.**
How the tool or technique is actually used and how it could be leveraged, offensively and defensively. Dual-use material is legitimate study corpus; the gate is authorization and labeling, never squeamishness.

**Output 5 - Linking pass.**
State explicitly what this material connects to in what the user has already studied, by artifact name from `my-data/learnings/`, and what it changes about that earlier understanding. Isolated facts do not become proficiency; connected ones do. Cross-reference with [[wikilinks]] in both directions.

**Identifier discipline (blocking rule).**
Framework identifiers are versioned vendor facts: ATT&CK technique IDs, NIST control IDs, CIS benchmark numbers are verified against the live source before they are written, never cited from memory. An ID with no verified source does not go in the artifact. If you cannot verify in this chat, mark the ID "[UNVERIFIED - check before relying on this]".

**Non-fits are recorded, not skipped.**
When material genuinely has no governing framework, say so in one line and say what stands in its place. A certification study track, for example, is curriculum rather than adversary behavior, so it carries a security counterweight pointer instead of a framework mapping.

**Output format.**
A single markdown artifact with the five outputs as sections, opening with the front-matter block from `templates/learning_artifact_template.md`, ready to save to `my-data/learnings/`.
