# Resume Tailoring Starter Kit - README (Operating Manual)

**Version:** 1.0 (public starter kit release)

## What this is

A modular prompt library for tailoring your resume to specific target roles. Built to enforce honest scoping, evidence-backed claims, cross-document alignment, leveling discipline, continuous state alignment, role-driven framing adaptation, and output cleanliness.

It works for a job seeker in any field. You paste these prompts into a plain AI chat (Claude, ChatGPT, or similar) - no git, no special software, no prior setup required. Some worked examples in the modules use cybersecurity roles; rebuild the example lists for your own field.

## Naming aliases

- **Resume Tailoring Kit** (formal - documentation)
- **Tailoring Pipeline** (operational - module flow)
- **Resume Generator** (shorthand - quick reference)

Any of these activates the system.

## Kit folder structure

Set this up anywhere on your computer:

```
resume-tailoring-kit/
  prompts/     - these modules plus the reference docs (this README lives here)
  templates/   - fact_registry_template.json, career_thesis_template.md
  my-data/     - YOUR private copies (fact registry, session notes).
                 Keep this folder OUT of any public location. Never share it.
  drafts/      - working builds, one subfolder per target: drafts/[target-name]/
  final/       - finished packages, one subfolder per target: final/[target-name]/
```

## Architecture

```
00_orchestrator - master sequencer
  Step 0:   Foundation read (prompts/README.md first - this operating manual -
            then your my-data files: fact registry, career thesis, and if you
            keep them, the outcome ledger and portfolio band; principles;
            semantic map)
  Step 0.5: Session-start reconciliation + workspace health check
  Step 1:   Run parameters (build mode is NOT chosen here - the gate proposes it)
  Step 2a:  STRATEGY GATE - after Module 13, ONE decision card per target:
            tier (A/B/C) | portfolio band (green 1-3 / yellow 4-6 / red 7+) |
            proposed mode FULL/FAST/LIGHT/NO-BUILD | network track (Module 14
            runs INSIDE the gate) | readiness-packet status | SINGLE timebox.
            You make ONE decision. At yellow, FAST/LIGHT/readiness is the
            default; FULL needs your explicit call plus a reason. Defaults
            never block; you override freely.
            (Portfolio bands are OPTIONAL - they become useful once you are
            juggling multiple applications.)
  Steps 2-6: Mode sequence, branching, wrap-up (card + ledger row recorded)
  Step 7:   Session closeout via Module 12, ending in saving your updated
            files. If you use git, commit at closeout (optional).

Build modes (Strategy Gate output; you decide):
  FULL   - the complete sequence below
  FAST   - lane donor + JD delta + ONE dual-direction adversarial pass +
           fact-check (never dropped) + full QA + recruiter + ATS + targeted
           HM risk pass (unconditional); scorer optional, first thing cut
  LIGHT  - existing lane/library artifact as-is + contact/QA hygiene only;
           ANY content change makes it FAST
  NO-BUILD - no new build; narrower than DON'T PURSUE, never kills pursuit

Pipeline detail (FULL mode):
  01_intake_and_matrix        JD to requirements matrix + framing_delta_report
  13_target_qualification     GATING CHECKPOINT: classify against your career
                              thesis; pursue / don't-pursue decision gates the
                              rest of the run (DON'T PURSUE or HOLD ends it here)
  STRATEGY GATE (Step 2a)     The single decision card; Module 14 inside it
                              (full pathway for A-tier, quick track otherwise)
  02_rubric_score (baseline)  Baseline scoring
  03_proactive_interrogation  Surface undocumented experience (if score < 75%
                              or you request it)
  09_company_research         Company context (DEFAULT ON for serious targets)
  04_content_build            PRINT + ATS in one pass
  07_fact_check               Anti-hallucination audit
  08_cover_letter_build       Cover letter (see COLD PORTAL MODE in Module 08)
  05_cross_document_alignment Consistency check
  06_qa_gate                  QA battery + persona review panel
  02_rubric_score (final)     Score after tailoring
  11_output_packaging         final/[target-name]/ + HANDOFF_MANIFEST.md
  10_interview_prep           (Typically separate session, post-submission)

  12_session_closeout         Runs LAST or surgically at any milestone;
                              ends in saving your updated files
```

## Why modular

Each pass requires a different mental lens:
- **Network pathway (Module 14)** - reconnaissance and relationship strategy
- **Target qualification (Module 13)** - strategic decision under your career thesis
- **Intake + matrix (Module 01)** - structured JD decomposition + framing_delta detection
- **Scoring (Module 02)** - analytical (numbers, weights)
- **Interrogation (Module 03)** - conversational (probing)
- **Content build (Module 04)** - creative-constrained (rules-following bullet writing)
- **QA (Module 06)** - mechanical (checklist) plus the persona review panel
- **Closeout (Module 12)** - reconciliation (alignment + saving your files)

Each module is focused. The orchestrator sequences them; modules can be invoked alone for surgical re-runs.

## Module library (15 modules)

Location: `prompts/`

| Module | Version | Purpose |
|---|---|---|
| `00_orchestrator` | v1.0 | Master sequencer; Step 0.5 reconciliation; 13 gates the run; Strategy Gate Step 2a (single decision card, Module 14 inside); ends in saving your files |
| `01_intake_and_matrix` | v1.0 | JD to requirements matrix + framing_delta_report; flags degree-knockout risk |
| `02_rubric_score` | v1.0 | Scoring engine; exact-literal vs synonym keyword reporting; MUST-HAVE verbatim check |
| `03_proactive_interrogation` | v1.0 | Gap-closing Q&A; quantification harvest; mandatory transcript |
| `04_content_build` | v1.0 | PRINT + ATS dual build; 2-page standard; FAST donor path; character scrub at build |
| `05_cross_document_alignment` | v1.0 | Resume to cover letter to ATS coherence; full locked-framing verification |
| `06_qa_gate` | v1.0 | QA battery incl. scripted heading whitelist; FULL panel = recruiter/ATS/HM; FAST panel = recruiter/ATS/targeted HM (unconditional); human-voice check |
| `07_fact_check` | v1.0 | Anti-hallucination audit; trace every claim to your fact registry |
| `08_cover_letter_build` | v1.0 | 4-section structure; COLD PORTAL MODE; tightened credential-gap rules; zero prose colons |
| `09_company_research` | v1.0 | Company context; DEFAULT ON for serious targets |
| `10_interview_prep` | v1.0 | Per-target defense scripts; internal-application coherence note |
| `11_output_packaging` | v1.0 | final/ destination; HANDOFF_MANIFEST.md; PDF renders; submission filenames; document metadata |
| `12_session_closeout` | v1.0 | Closeout checklist; health check; periodic doctrine revalidation (optional) |
| `13_target_qualification` | v1.0 | Classify against your career thesis; reads current role from the registry |
| `14_network_pathway` | v1.0 | Runs inside the Strategy Gate; warm/hybrid/cold track + auditable visibility move |

Reference docs (same location):

| File | Version | Purpose |
|---|---|---|
| `README.md` | v1.0 | This operating manual |
| `principles.md` | v1.0 | 15 standing principles, tiered 7/6/2 |
| `semantic_equivalence_map.md` | v1.0 | Synonym groups + [RECOGNITION-ONLY] tags |
| `ats_upload_notes.md` | v1.0 | Per-portal quirks; KNOCKOUT PLAYBOOK; education fields; ATS-vs-PRINT decision tree |

## Before your first run

1. Copy `templates/fact_registry_template.json` to `my-data/fact_registry.json` and fill it in. This is the evidence base every claim must trace to. Keep it private.
2. Copy `templates/career_thesis_template.md` to `my-data/` and define your own career thesis (see below).
3. Optionally start `my-data/lessons_learned.md` to record reusable patterns across sessions.

## How to use

**New target (any priority):**
Run `00_orchestrator`. Paste the module into a new AI chat, and make sure your fact registry (my-data/fact_registry.json) is pasted into or attached to the chat. After Module 13 classifies, the STRATEGY GATE emits one decision card - tier, portfolio band, proposed build mode, network track (Module 14 runs inside the gate; a warm path may pause the pipeline for the intro response and SUSPENDS the timebox), readiness status, single timebox. You make one decision on the card; the chosen mode runs. Cold senior-leadership-track submissions get a recorded visibility move or a named blocker. Module 09 stays ON for serious targets.

**New target exploratory:**
Skip Module 14. Paste `00_orchestrator` into a new chat. Paste the JD. Run. Module 13 will classify the target after intake; a DON'T PURSUE or HOLD result ends the run before any build effort is spent.

**Surgical (single module):**
Paste just the module you need. Examples:
- `06_qa_gate` to QA an existing draft
- `13_target_qualification` to evaluate fit before committing tailoring effort
- `14_network_pathway` to check warm-intro paths for a target
- `12_session_closeout` to wrap up mid-session after a milestone

**Closeout trigger phrases:**
- "Are we done with X" | "Can we move on" | "Clean slate" | "Close this out" | "Wrap up"

**Network pathway trigger phrases:**
- "Who do I know there" | "Network check on this one" | "Any warm intro paths"

## Saving your work (source of truth)

Your kit folder on your computer is the source of truth.

- **Your data files** live in `my-data/`: `fact_registry.json` (required) and `lessons_learned.md` (optional). At closeout, Module 12 walks you through updating them. Keep `my-data/` out of any public location.
- **Saving your updated files at closeout is the durable record.** Any session that ships a package or changes your standing rules is not closed until the files are saved. If you use git, commit at closeout (optional).
- **Deliverables** ship to `final/[target-name]/` via Module 11, each package carrying a `HANDOFF_MANIFEST.md` (target metadata, files inventory with ATS-vs-PRINT usage, submission guidance, thesis classification, rubric estimate, positioning highlights, submission decisions, build provenance) plus the PRINT/ATS/CoverLetter documents and PDF renders.

## What every module assumes

1. Make sure your fact registry (my-data/fact_registry.json) is pasted into or attached to the chat, along with `principles.md` and `semantic_equivalence_map.md`, plus your session notes if you keep them.
2. All claims reflect actual decision-making authority and involvement (Principle #1, anti-hallucination).
3. Locked framing decisions in your notes are non-negotiable (Principle #10).
4. Output respects the Action, Scope, Outcome, Evidence, Tech/Method bullet rubric with the 40-word hard limit (Principle #5).
5. Senior-level bullets demonstrate leveling markers (Principle #8).
6. Sessions end with explicit closeout via Module 12 (Principle #12).
7. The system extends itself per role context within fact-registry traceability bounds (Principle #13).
8. Deliverables are ASCII-clean and PDF-verified (Principle #14) and honor the identity standards - full name, header location, contact block (Principle #15).

## Career thesis (north star)

Define your own career thesis: 2 or 3 legitimate destination paths. Every target gets classified against them by Module 13. All framing extensions ladder up to at least one path.

EXAMPLE - replace with your own paths:

- **Path A: Senior People Leadership** (Director, then VP / SVP)
- **Path B: Senior Technical Authority** (Director, then Principal / Distinguished IC)
- **Path C: Independent Consulting / Practice Leadership**

Use `templates/career_thesis_template.md` to write yours, and keep it in `my-data/`.

## Standing review discipline

- **Persona review panel (Module 06, mode-aware).** FULL builds get three independent simulated reads (recruiter 6-second skim, ATS parse simulation, hiring-manager read); FAST builds get recruiter + ATS + the targeted HM risk pass, unconditionally. Unresolved HIGH findings block packaging in every mode.
- **Workspace health check** at session start and closeout: every `final/[target-name]/` has a HANDOFF_MANIFEST.md; no shipped package exists on disk that your session notes don't know about; `my-data/` is current. Fast and silent unless something fails.
- **Doctrine revalidation** every 5th closeout or monthly, whichever comes first: pipeline coherence review + persona-panel doctrine review + structure audit. (OPTIONAL - becomes useful once you are juggling multiple applications.)

## Cold submissions

Most targets go through a portal with no referral. The discipline that substitutes for warmth:

- **Knockout questions.** The playbook lives in `ats_upload_notes.md` (degree fields, salary fields, education presentation). Module 01 flags degree-knockout risk at intake; check the JD for knockouts before building.
- **MUST-HAVE keywords appear verbatim in the ATS version.** Synonym coverage is not enough for parser-side filters; Module 02 runs the verbatim check.
- **Cover letter is a tie-breaker on cold portals.** Built when the portal has a field for it (Module 08 COLD PORTAL MODE); company research (Module 09, default ON) feeds it and the screening answers.
- **Submission filenames:** "[Your Full Name] Resume - [Target Role].docx" - handled by Module 11.

## File locations

| Purpose | Path (relative to the kit root) |
|---|---|
| Module library + reference docs | `prompts/` |
| Operating manual | `prompts/README.md` (this file) |
| Templates | `templates/` (fact_registry_template.json, career_thesis_template.md) |
| Your private data | `my-data/` (fact_registry.json, career thesis, session notes, optional lessons_learned.md) - keep OUT of any public location |
| Active drafts | `drafts/[target-name]/` |
| Shipped packages | `final/[target-name]/` with HANDOFF_MANIFEST.md |

## Your data files

- `my-data/fact_registry.json` - the evidence base. Every resume claim must trace to an entry here. Start from `templates/fact_registry_template.json`.
- `my-data/lessons_learned.md` (optional) - reusable patterns you confirm at closeout.
- Session notes (optional) - active targets, locked framing decisions, network registry, outcome ledger. OPTIONAL - becomes useful once you are juggling multiple applications.

## Operating principle headlines (principles.md)

15 principles: 7 Tier 1 / 6 Tier 2 / 2 Tier 3. Tier 1 wins over Tier 2 wins over Tier 3.

**Tier 1 (non-negotiable):**
- **#1 Anti-hallucination** (supreme) - claims trace to your fact registry; registry verification before lock; claim-specific confirmation
- **#2 Accuracy over inflation** - honest scoping language
- **#10 Locked framing non-negotiable** - can extend, never violate or loosen
- **#12 Closeout discipline** - no silent state transitions; sessions end via Module 12
- **#13 Role-driven framing adaptation** - system extends per role within anti-hallucination bounds
- **#14 Output cleanliness discipline** - no em/en dashes, arrows, curly quotes; PDF-verified page counts; no orphans
- **#15 Document standards and identity** - "[YOUR FULL NAME]" full name; "[CITY, STATE]" header; "[PHONE]"; [Optional: one line for an active clearance or headline certification, if you have one]; ATS-vs-PRINT usage rules

**Tier 2 (process):**
Evidence-backed claims (#4), bullet rubric with 40-word hard limit (#5), cross-doc alignment (#6), proactive interrogation (#7), senior-level leveling (#8), walk-before-confirming (#9)

**Tier 3 (preference):**
Hireability over aesthetics (#3), engagement style (#11)

## Maintenance

**Modules and reference docs (low churn):** Edit in place and bump the version header. If you use git, old versions live in history; otherwise keep a dated backup copy if you want one.

**Your data files (high churn):** Module 12 walks you through the updates at closeout. Save the files when done.

**semantic_equivalence_map (medium churn):** Updates accumulate in a pending list in your session notes. Committed to the map when 5+ pending.

**Major reworks** get a note in your session notes, and the session that makes them ends with saving your updated files.
