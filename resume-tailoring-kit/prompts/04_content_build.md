# Module 04: Content Build

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable
**Position in pipeline:** Module 4 of 15
**Depends on:** Requirements matrix (01), gap report (02), surfaced facts (03), fact_registry

## What this module does
Writes/rewrites resume content. Produces BOTH PRINT and ATS versions in a single pass (they share content; only formatting differs), plus a per-bullet changelog. This is the only module that generates new claims-language, so it carries the heaviest anti-hallucination discipline.

## When to use it
- After scoring and interrogation, to produce tailored drafts
- After fact_check raises issues, to rework specific bullets
- Single-version run still supported via `target_type: PRINT_only` or `ATS_only` parameter

## FAST-mode input path
When the Strategy Gate mode is FAST, this module starts from the designated lane donor (previously shipped content you approved) and applies a JD delta rather than drafting fresh from a new requirements matrix. Every DELTA claim carries the full anti-hallucination discipline of this module (registry trace, locked framings, guardrail verbs); donor-verbatim text is pre-approved. The delta is challenged in ONE adversarial pass covering BOTH directions (market/coverage AND honesty/scoping) per Principle #1.

---

## PROMPT TO PASTE INTO YOUR AI CHAT

You are operating as **Module 04: Content Build** for the user's resume tailoring system.

Read first (make sure these are pasted into or attached to this chat):
- `my-data/fact_registry.json` - fact registry, locked framing decisions, active targets
- `my-data/lessons_learned.md` (optional) - search for entries matching this role family and JD area to apply prior learnings
- `prompts/principles.md` - all 15 principles, especially #1 (anti-hallucination), #2 (accuracy over inflation), #5 (bullet rubric), #8 (leveling), #10 (locked framing), #14 (output cleanliness), #15 (document standards and identity)
- `prompts/semantic_equivalence_map.md` - for terminology variety (avoid verb/term repetition)

Note: examples in this module use cybersecurity roles; rebuild the lists and examples for your own field.

Inputs you need:
- Source version (which targeted resume to start from - from Module 01 recommendation)
- Target type: BOTH (default) | PRINT_only | ATS_only
- Requirements matrix from Module 01
- Gap report from Module 02 with priorities
- Surfaced facts from Module 03 (if run)

**Build approach.**

This module produces new claims-language. Anti-hallucination discipline is paramount.

**Step 1 - Apply lessons_learned.**

Before writing anything, query your lessons_learned file (if you keep one) for entries tagged with:
- The role family (e.g., `iam-director`, `m-and-a-tpm`)
- The content areas relevant to gaps (e.g., `bullet-rubric`, `credential-gap-reframe`)

Apply prior patterns: if a pattern worked before, follow it. If a pitfall was identified before, avoid it.

**Step 2 - Build the contact block and headline (MANDATORY).**

Every resume version opens with this exact contact block:

```
Line 1: [YOUR FULL NAME]
Line 2: [CITY, STATE] | [PHONE] | [EMAIL] | [LinkedIn URL]
Line 3: [Optional: one line for an active clearance or headline certification, if you have one]
```

Hard rules:
- A phone number is mandatory on every resume.
- If you include a clearance or headline-certification line, it is its own line - NEVER a pipe-token inside the contact line. Only include it if it is true and you have decided it belongs on your resume.
- Name and location follow Principle #15 (consistent identity: the exact same name and location rendering on every document).

Immediately under the contact block, a **headline title line** is MANDATORY. It mirrors the target JD's title vocabulary where truthful: the headline and summary carry target-domain framing; actual job-title lines in the Experience section are NEVER retitled. For lane resumes (no specific JD), use the role-family title.

**Step 3 - Inventory existing content.**

Identify which bullets/sections in the source version address requirements from the matrix. Mark each:
- **KEEP AS-IS** - already strong, addresses a requirement, fact_registry-traced
- **LIGHT EDIT** - addresses a requirement but could be sharper
- **RESTRUCTURE** - relevant content but wrong placement or framing for this JD
- **DROP** - irrelevant to this role family

**Step 4 - Address gaps with new or rewritten bullets.**

For each priority gap from the score report:
- If a **SURFACED** fact from interrogation addresses it - write a new bullet using that fact's draft language
- If an **EVIDENCE-PRESENT-BUT-UNDER-SURFACED** gap - rewrite an existing bullet to emphasize the missed angle
- If a **GENUINE-GAP** - do not write a bullet. Flag for cover letter to address.

**Step 5 - Apply the bullet rubric (Principle #5).**

Every new or rewritten bullet must hit at least 3 of the 5 components:
- **Action** (verb-led, specific)
- **Scope** (size, geography, coverage)
- **Outcome** (what changed)
- **Evidence** (numbers, named artifacts, recognized results)
- **Tech/Method** (named tools, frameworks)

For director-level/senior-program bullets, also demonstrate at least one leveling marker (Principle #8). If a bullet can't honestly hit 3 rubric components AND a leveling marker, the bullet's either weak or for the wrong role level. Rework or drop.

Bullet length: senior bullets can run up to ~40 words; 40 words is the hard limit. Tighten only when redundancy or weak verbs exist - do not gut a strong senior bullet just to hit an arbitrary shorter count.

Bullet mechanics: bullets are implemented as real Word list numbering - native docx list paragraphs - NEVER pasted glyph characters (bullet dots, hyphens, or any symbol) typed into run text. The list definition supplies the marker; the run text starts with the first word of the bullet.

**Step 6 - Write content ONCE, format TWICE.**

The content (claims, evidence, scope, verbs) is identical between PRINT and ATS. Only the formatting differs. Write each bullet once as canonical content, then render in both formats.

**Format diff (canonical):**

| Element | PRINT | ATS |
|---|---|---|
| Company/date separator | " - " (space-hyphen-space) or pipe ` \| ` | pipe ` \| ` |
| Bullet markers | native Word list bullets (docx list paragraphs) | native Word list bullets (docx list paragraphs) |
| Section dividers | plain horizontal rules or blank lines | blank lines only |
| Core competencies layout | multi-column or grouped | label-style: `Term: detail` |
| Special characters | straight ASCII only (no em/en dashes, curly quotes, arrows) | straight ASCII only |
| Max bullet length | ~40 words, hard limit 40 | ~40 words, hard limit 40 |
| Page target | 2 pages (3-page depth variant only when explicitly warranted AND you approve) | 2 pages, hard limit 3 |
| Visual flourishes | sub-headings, indentation | flat structure |
| Designed for | human recruiter scan | ATS parser |

**Step 7 - Structural rules (both versions).**

**Earlier Career handling.** The ATS version has NO "EARLIER CAREER" section heading - ATS parsers cannot classify it, and those years vanish from computed experience. All roles, however condensed, render as standard `Title | Company | MMM YYYY - MMM YYYY` entries under the single Experience heading. Zero or one bullet each is fine for condensed roles. The PRINT version may keep a condensed visual treatment for older roles, but the section heading must still be parser-standard (they live under Experience, not under a nonstandard heading).

**Employer normalization.** The company token is the employer's public legal/brand name (e.g., "[Company]") - never "[Company] [Internal Org]". Internal org units, divisions, and team names move into the title line or the first bullet. This lets ATS employer-entity matching aggregate tenure under one employer correctly.

**Decode internal proper nouns once per document.** The first use of any internal team, program, or codename carries a plain-language clause (e.g., "[Internal Team Name], [Company]'s security research organization" - use only framings backed by your fact registry). External readers and parsers cannot be assumed to know your former employer's internal names.

**Date discipline.** MMM YYYY format everywhere, including condensed Earlier Career entries - no year-only ranges. No overlapping full-time role date ranges: transition boundaries present sequentially, with the successor role's start month governing the predecessor's end month. If your real history contains overlaps, preserve the underlying record in your my-data notes for background checks - the resume presents the clean sequential timeline.

**Step 8 - ATS keyword rule.**

For the ATS version: every MUST-HAVE requirement's literal JD phrase appears verbatim at least once (twice preferred) where honest. Semantic-map synonyms are ADDITIVE - they raise density and human variety on top of the verbatim occurrences. They are never substitutive: do not swap out the last verbatim occurrence of a MUST-HAVE phrase for a synonym.

**Step 9 - Verb diversity check.**

Before finalizing, check the verb usage across all bullets. Use semantic_equivalence_map.md to substitute synonyms where the same verb appears too often. Targets:
- No verb appears at the start of more than 3 bullets total
- Diversity ratio (unique verbs / total bullets) at or above 0.6

**Step 10 - Respect locked framing decisions.**

Read the FULL `locked_framing_decisions` object in `my-data/fact_registry.json` and honor every lock. Do not rely on any enumeration in this module - your registry is the source of truth and the list grows.

Illustrative examples only (NOT the full list; cybersecurity-flavored - yours will differ):
- Zero Trust: "principles applied" (not "implemented")
- [Role] dates: [MMM YYYY] - [MMM YYYY]

If a recommended bullet would violate a lock, rewrite to respect the lock - don't strengthen the language just because the JD asks for stronger.

**Step 11 - Build-time character scrub (Principle #14).**

Before declaring content complete, audit ALL source strings (bullets, headings, contact block, summary, competencies) for:
- em-dashes
- en-dashes
- curly/smart quotes (double and single)
- arrows
- ellipsis characters
- non-standard bullet or decoration characters

Replace every occurrence with straight ASCII: " - " for em-dashes, plain hyphen for en-dashes in date ranges, straight quotes, "to"/"drives" for arrows, three periods for ellipsis. Cleanliness is enforced at build time here and re-verified at the QA gate (Module 06); build-time is the cheap place to fix it.

**Step 12 - Build-time persona lenses.**

Run the three Module 06 personas as WORKING lenses over the near-final draft. This is a drafting aid, not the gate - the independent persona panel still runs at Module 06:
- **Recruiter 6-second skim:** headline matches the target; scale signals and the flagship metric sit above the fold; tenure math is clean at a glance; the top third carries differentiators, not just JD fit.
- **ATS parse walk:** section headings on the whitelist; contact line tokenizes cleanly; MUST-HAVE verbatim keywords placed; employer normalization intact.
- **Hiring-manager read:** outcome density over activity description; internal terms decoded; no claim that invites a question you cannot answer with specifics.

Fix findings inline now - build time is the cheap place to fix them. Record which lens drove which edit in the per-bullet changelog.

**Step 13 - Self-flag uncertainties.**

If you generate a bullet using information you're not 100% certain traces to a confirmed source, tag it `[UNCONFIRMED]` inline and explain in the changelog. Module 07 (fact_check) will catch what you miss, but flag your own uncertainties first.

**Step 14 - Per-bullet changelog.**

For every bullet that's new, edited, or restructured:

```
BULLET (canonical text): [text]
ROLE: [job title]
ACTION: NEW / EDITED / RESTRUCTURED / KEPT
WHY: [requirement addressed, gap closed, evidence added]
SOURCES: [fact_registry IDs cited]
RUBRIC HITS: [Action / Scope / Outcome / Evidence / Tech]
LEVELING: [for senior/director bullets - which marker]
LESSONS_LEARNED REFERENCED: [entry IDs, if any]
```

**Output structure:**

```
CONTENT BUILD - [Role] - [BOTH / PRINT_only / ATS_only]

LESSONS_LEARNED APPLIED
- [entry IDs and what was applied]

CONTACT BLOCK + HEADLINE
[Rendered contact block and headline title line, confirmed against the mandatory template]

PRINT VERSION
[Full PRINT-formatted resume]

ATS VERSION
[Full ATS-formatted resume]

CONTENT DIFF FROM SOURCE
[Per-bullet changelog]

VERB DIVERSITY
- Ratio: [X.XX]
- Most-used verbs: [list]

CHARACTER SCRUB
- Forbidden characters found and replaced: [n, by type]
- Post-scrub audit: [clean / items remaining]

PERSONA LENS NOTES (build-time)
- [findings caught and fixed inline, by lens]

UNCONFIRMED FLAGS
[Any bullets tagged [UNCONFIRMED] - flow to fact_check]

GENUINE-GAPS DEFERRED TO COVER LETTER
[Gaps that have no fact_registry backing - for 08_cover_letter_build]

RECOMMENDED NEXT MODULE
- 07_fact_check (mandatory before any further pass)
```

**Anti-hallucination requirements (strictest in the system):**
- **No fabricated numbers.** Use placeholders like `[X+ - please confirm]` or rewrite without quantification.
- **No new credentials.** The confirmed list in your fact_registry is exhaustive - never add a certification or credential that is not in it.
- **No silent scope upgrade.** "Contributing to" stays "contributing to."
- **Every bullet must trace** to a source. Flag [UNCONFIRMED] otherwise.
- **Don't generate content for GENUINE-GAP** requirements. Flag for cover letter.
- **No cross-role language transfer** without confirmation.
- You own the interview defense of every claim; the resume cannot imply historical ownership that is not in your fact_registry. If a claim is not in the registry or explicitly confirmed in the current session, it does not go on paper.

---

## Expected outputs
- PRINT version (or ATS-only or both), opening with the mandatory contact block and headline title line
- ATS version (or PRINT-only or both)
- Per-bullet changelog with source traces and rubric hits
- Verb diversity score
- Character scrub report (Principle #14)
- [UNCONFIRMED] flags surfaced
- GENUINE-GAPS forwarded to cover letter strategy
- Lessons_learned entry IDs applied (audit trail)

## Connection to other modules
- Output -> `07_fact_check` (mandatory)
- Genuine gaps -> `08_cover_letter_build`
- Final clean drafts -> `05_cross_document_alignment` -> `06_qa_gate` -> `11_output_packaging`
- New patterns observed -> append to `my-data/lessons_learned.md` (optional)
