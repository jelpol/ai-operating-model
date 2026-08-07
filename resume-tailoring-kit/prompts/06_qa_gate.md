# Module 06: QA Gate

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable
**Position in pipeline:** Module 6 of 15 (after cross_document_alignment, before output_packaging)
**Depends on:** Resume drafts (PRINT, ATS, cover letter as relevant)

## What this module does
Mechanical final-pass quality gate. Checks page count, bullet length, voice/tense consistency, ATS parseability, formatting hygiene, character cleanliness (Principle #14 multi-pass battery), contact block completeness, date validity, and consolidates claim-trace status from fact_check. Runs a persona adversarial review panel before packaging (composition varies by build mode - see the panel section). Acts as a hard gate before output packaging - blocks if any critical issue found.

## When to use it
- After cross-document alignment passes
- Standalone QA on any draft (even one not built through this system)
- Final pre-submission check

---

## PROMPT TO PASTE INTO CLAUDE

You are operating as **Module 06: QA Gate** for the candidate's resume tailoring system. You are the last quality gate before output.

Read first:
- The candidate's fact registry and locked framing decisions. Make sure your fact registry (my-data/fact_registry.json) is pasted into or attached to this chat, along with the active target context and locked framing decisions from your session notes.
- `prompts/principles.md` - especially #14 (output cleanliness) and #15 (document standards and identity)
- `prompts/semantic_equivalence_map.md`

Inputs:
- Resume draft (PRINT or ATS or both), cover letter if in scope
- (If available) Most recent fact_check audit results
- (If available) Most recent cross-document alignment results
- The JD requirements matrix from Module 01 (for the keyword verbatim check)

**QA dimensions (run all that apply).**

### 1. Principle #14 verification battery (ALL versions: PRINT, ATS, cover letter)

This battery applies to every deliverable, not just the ATS version. Run all five passes. Any failure = BLOCKED, rebuild required.

**Pass 1 - Pre-build source-string scrub.** Confirm Module 04's build-time scrub ran: all source strings audited for em-dashes, en-dashes, curly quotes, arrows, ellipsis characters, non-standard bullets, replaced with straight ASCII.

**Pass 2 - Build, validate, render.** Build the docx, validate it opens cleanly, render to PDF (e.g., via LibreOffice).

**Pass 3 - Rendered page-count check (on the PDF, not word-count estimates).**
- PRINT: 2 pages (a 3-page depth variant is acceptable ONLY when explicitly warranted and approved by the user in advance)
- ATS: target 2 pages, hard limit 3
- Cover letter: exactly 1 page. An orphan signature on page 2 is a build failure.

**Pass 4 - Post-build scrub on the EXTRACTED text (authoritative gate).** Extract text via pdftotext or docx XML extraction. Grep the extracted text for: em-dash, en-dash, curly double quotes, curly single quotes, arrows, ellipsis character. Zero occurrences required. This pass is authoritative - a clean pass 1 does not excuse a dirty pass 4 (templates and styles can inject characters the source strings never contained).
- Cover letters additionally get a colon audit: zero prose colons. Colons inside official certification names (e.g., "CompTIA Security+") are allowed.

**Pass 5 - Visual orphan/balance check on tail pages.** No orphan section headers at page-end or alone on a final page. The last page must carry substantive content, not a 2-3 line remnant.

Make these checks SCRIPTED wherever possible: unzip the docx, inspect document.xml, and assert - do not rely on judgment-based reading of a rendered preview for character and structure checks. If you are running in a plain chat without file tooling, run the same checks by careful direct inspection of the full document text and say so in the report.

### 2. Contact block and identity (BLOCKING)
- Phone number PRESENT: [PHONE], and consistent across all versions. Missing phone = BLOCKED.
- Contact line: `[CITY, STATE] | [PHONE] | [EMAIL] | [LINKEDIN URL]`
- Headline title line PRESENT under the contact block (mirrors target JD title vocabulary; role-family title for lane resumes). Missing headline = BLOCKED.
- [Optional: one line for an active clearance or headline certification, if you have one.] If your header standard includes such a line, it renders as its own standalone line - never a pipe-token inside the contact line - and its absence or inlining = BLOCKED.
- Principle #15 verified explicitly: your name renders consistently as [YOUR FULL NAME] (never a nickname or shortened form) and the location header renders your chosen [CITY, STATE] exactly.
- Email and LinkedIn URL match across versions.

### 3. Page count governance
Covered mechanically by battery Pass 3 above. For quick pre-render estimates only, word count may be used, but the rendered-PDF count is the gate. Do not apply folklore page targets (e.g., "some ATS truncate at 4 pages"); the targets in Pass 3 are the rule.

### 4. Bullet structure and length governance
- Bullets must be real Word list numbering (native docx list paragraphs). Pasted glyph characters (bullet dots, hyphens, or any marker typed into run text) = FAIL. Verify by inspecting document.xml: list paragraphs carry numbering properties; run text starts with the first word.
- Bullet length: hard limit 40 words (all versions). Over-limit bullets get reworked or split - this aligns with principles.md #5.
- Flag every bullet over 40 words with its word count.

### 5. Date validation
- MMM YYYY format everywhere, including condensed early-career entries. Year-only ranges = FAIL.
- No overlapping full-time role date ranges: transitions present sequentially, successor start month governs predecessor end month (the date_presentation_sequential rule).
- Dates and titles identical across PRINT, ATS, and cover letter.

### 6. Voice and tense consistency
- All bullets for the CURRENT role should be present tense (e.g., "Own", "Lead", "Define")
- All bullets for PAST roles should be past tense (e.g., "Led", "Directed", "Established")
- First-person pronouns should not appear in resume bullets (implied first person)
- Cover letter is first-person, present tense, conversational

Flag every voice/tense mismatch by line.

### 7. Verb diversity (final check)
- Use semantic_equivalence_map.md to verify verb substitutions are accurate
- Verify diversity ratio meets 0.6 target from rubric_score
- Flag if any verb starts more than 3 bullets

### 8. ATS parseability (ATS version only)
- No tables (single column layout)
- No text boxes
- No images, icons, or logos
- No headers/footers with critical info
- Hyperlinks present but in plain-text-readable form
- **Section-heading whitelist.** Allowed headings: SUMMARY, CORE COMPETENCIES (or SKILLS), EXPERIENCE (or PROFESSIONAL EXPERIENCE), CERTIFICATIONS, EDUCATION, COMMUNITY LEADERSHIP, LANGUAGES. Anything else (e.g., "EARLIER CAREER", "CERTIFICATIONS AND CLEARANCE") = FAIL. Parsers cannot classify nonstandard headings and the content under them vanishes from computed experience. This whitelist check is a SCRIPTED check run on extracted ATS text in the standard QA battery of every build - a whitelist that exists only in prose gets missed.
- Employer normalization: use one consistent company token per employer (e.g., "[Company]", with org units or divisions in the title line or first bullet), so employer-entity matching aggregates tenure.
- Keyword verbatim check: every MUST-HAVE requirement's literal JD phrase appears verbatim at least once (per the Module 01 matrix). Synonyms are additive, never a substitute for the last verbatim occurrence.

### 9. Formatting hygiene (all versions)
- Consistent spacing between sections
- Consistent bullet treatment within each version (all native list paragraphs)
- No orphan widows (last line of a paragraph alone at the top of a page)
- No double spaces after periods
- No trailing whitespace

### 10. Claim-trace consolidation
Reference the most recent fact_check audit:
- UNSUPPORTED count: must be 0 to pass
- CONFLICTED count: must be 0 to pass
- INVENTED CREDENTIAL flags: must be 0 to pass
- FABRICATED NUMBER flags: must be 0 to pass
- SCOPE INFLATION flags: must be 0 to pass

Any non-zero count is a BLOCKING issue.

### 11. Locked framing final check
Verify against the FULL locked framing decisions list in your current session notes / fact registry (my-data/). Do not rely on any enumeration in this module - your own list is the source of truth and it grows over time.

Illustrative examples only (NOT the full list; cybersecurity examples - rebuild for your own field):
- Zero Trust: "principles applied" (not "implemented")
- [Past role] dates: [locked MMM YYYY - MMM YYYY range]

In addition, explicitly verify the two Principle #15 identity locks: consistent full-name rendering and the [CITY, STATE] location header (also gated under dimension 2).

### 12. Section completeness
- All standard sections present per version type
- No "[PLACEHOLDER]" or "[TODO]" or "[UNCONFIRMED]" tags remaining in final draft

### 13. PERSONA REVIEW PANEL (mandatory before packaging)

Run three adversarial passes over the near-final draft. This encodes a standing review discipline: no draft ships without an adversarial read.

**Panel composition by build mode.**
- FULL builds: the complete panel below (recruiter / ATS / hiring-manager independent cold reads; numeric scorer per Module 02).
- FAST builds: reduced panel = recruiter skim + ATS parse simulation + TARGETED HIRING-MANAGER RISK PASS, unconditionally - the hiring-manager pass is never dropped in FAST; the numeric scorer is optional and is the first thing cut. The targeted hiring-manager pass is scoped to the flagged risk areas and locked-framing-sensitive claims (not a full cold read): its brief is "which of these claims fails a probing phone screen?"
- OPTIONAL - build modes become useful once you are juggling multiple applications; if you run every build the same way, use the FULL panel.

Unresolved HIGH findings block packaging in every mode.

**Independence mechanic.** Each persona runs as a SEPARATE subagent, given ONLY the rendered deliverables (plus the JD requirements matrix for the ATS persona) and its persona brief below - no build-conversation context, no access to the builder's reasoning or intent. These are cold reads, like the real recruiter's. The orchestrator consolidates findings without softening them. One model wearing three hats inside the build context is not independent review. If subagents cannot be spawned in the current environment (e.g., a plain chat), run the personas in three separate passes and SAY SO in the report - never silently degrade to a single blended pass.

Each persona reports findings with severity (HIGH / MEDIUM / LOW). Unresolved HIGH findings BLOCK packaging.

**(a) Recruiter 6-second skim.** Read only what a recruiter sees in six seconds: headline, summary opening, above-the-fold content. Check: does the headline match the target role? Do scale signals (team size, geography, org level) surface in the summary? Is the flagship metric above the fold? Does the tenure math add up at a glance? Is anything confusing or burying the lede? Competitive-standout question: does the top third carry what the other qualified candidates' resumes will not (the candidate's own differentiators per the fact registry - e.g., a clearance or headline certification, named-brand leadership, unusual scale, a flagship improvement arc), or does it merely match the JD? Report STANDOUT / COMPETENT-BUT-GENERIC / BURIED alongside the findings.

**(b) ATS parse simulation.** Walk the document as a parser would: section classification against the whitelist, contact tokenization (does line 2 tokenize into location / phone / email / LinkedIn cleanly? is any clearance/certification line safely separate?), keyword verbatim check against the JD matrix, employer normalization (does tenure aggregate under one company token?), date computability.

**(c) Hiring-manager read.** Full read as a skeptical hiring manager: outcome density (results, not activity), decode-ability of internal terms (would an internal project codename or team name mean anything to an outsider without a decode clause?), and any claim that would not survive a probing phone screen. Flag every claim that invites a question the candidate cannot answer with specifics.

**(d) Human-voice / executive point-of-view check (PRINT versions and cover letters, every mode).** As part of the panel: (1) Does the first half-page sound like a person with a specific career thesis? (2) Could a recruiter summarize the profile in one sentence? (3) Does the document choose a clear winning axis, or try to win every row? A failing read is a panel finding at the reviewer's assessed severity.

**Output structure:**

```
QA GATE - [Role] [Version]

OVERALL STATUS: [PASS / PASS WITH WARNINGS / BLOCKED]

PRINCIPLE #14 BATTERY
- Pass 1 (pre-build scrub): [PASS/FAIL]
- Pass 2 (build + render): [PASS/FAIL]
- Pass 3 (rendered page count): PRINT [n] / ATS [n] / CL [n] - [PASS/FAIL]
- Pass 4 (extracted-text scrub, authoritative): [PASS/FAIL] [offending chars + locations if any]
- Pass 4a (cover letter colon audit): [PASS/FAIL/N-A]
- Pass 5 (orphan/balance): [PASS/FAIL]

CONTACT BLOCK AND IDENTITY (BLOCKING)
- Phone present + consistent: [PASS/FAIL]
- Headline title line present: [PASS/FAIL]
- Clearance/certification line standalone (if used): [PASS/FAIL/N-A]
- Principle #15 (naming, location header): [PASS/FAIL]

BULLET STRUCTURE AND LENGTH
- Native list numbering (document.xml verified): [PASS/FAIL]
- Total bullets: [N]
- Over 40-word hard limit: [n] [list with counts]

DATE VALIDATION
- MMM YYYY everywhere: [PASS/FAIL]
- No overlapping ranges (sequential transitions): [PASS/FAIL]
- Cross-version date/title identity: [PASS/FAIL]

VOICE/TENSE CONSISTENCY
- Mismatches found: [n]
- [details with line references]

VERB DIVERSITY
- Ratio: [X.XX]
- Status: [PASS / WARN / FAIL]
- Most-used verbs: [list]

ATS PARSEABILITY (ATS version only)
- Tables/text boxes/images: [PASS/FAIL]
- Section-heading whitelist: [PASS/FAIL] [nonstandard headings found]
- Employer normalization: [PASS/FAIL]
- Keyword verbatim vs JD matrix: [PASS/FAIL] [missing MUST-HAVE phrases]

FORMATTING HYGIENE
- Issues found: [n]
- [details]

CLAIM-TRACE STATUS (from latest fact_check)
- UNSUPPORTED: [n] [BLOCKING if > 0]
- CONFLICTED: [n] [BLOCKING if > 0]
- INVENTED CREDENTIAL: [n] [BLOCKING if > 0]
- FABRICATED NUMBER: [n] [BLOCKING if > 0]
- SCOPE INFLATION: [n] [BLOCKING if > 0]

LOCKED FRAMING
- Verified against your full locked-framing list in [my-data file]: [all respected / violations: ...]

PERSONA REVIEW PANEL
- Independence mechanic: [independent subagents / three separate passes (subagents unavailable)]
- Recruiter skim: [findings with severity]
- Competitive-standout verdict: [STANDOUT / COMPETENT-BUT-GENERIC / BURIED]
- ATS parse simulation: [findings with severity]
- Hiring-manager read: [findings with severity]
- Human-voice check (PRINT/CL): [findings with severity, or N-A]
- Unresolved HIGH findings: [n] [BLOCKING if > 0]

REMAINING PLACEHOLDERS
- [n] tags still present: [list]

BLOCKING ISSUES (must resolve before output_packaging)
1. ...
2. ...

WARNINGS (recommend fix, not blocking)
1. ...
2. ...

RECOMMENDED NEXT MODULE
- If blocked: back to 04_content_build or 07_fact_check
- If pass with warnings: 11_output_packaging (the user decides whether to address warnings first)
- If clean pass: 11_output_packaging
```

**Blocking criteria.**
A draft is BLOCKED if any of these are true:
- Any Principle #14 battery pass fails (character contamination in extracted text, page count over limit, orphan signature/section, cover letter prose colon)
- Phone number missing or inconsistent; headline title line missing; clearance/certification line (if part of your header standard) missing or not standalone
- Any UNSUPPORTED, CONFLICTED, INVENTED CREDENTIAL, FABRICATED NUMBER, or SCOPE INFLATION flags from fact_check
- Any locked framing violation (including the naming and location-header identity locks)
- Nonstandard ATS section heading; pasted glyph bullets; missing MUST-HAVE verbatim keyword
- Date format violation, overlapping ranges, or cross-version date/title mismatch
- Any [UNCONFIRMED] or [PLACEHOLDER] or [TODO] tags remaining
- Any unresolved HIGH finding from the persona review panel

Any failure = BLOCKED, rebuild required. Warnings don't block but should be raised clearly so the user can decide.

**Anti-hallucination requirements:**
- Don't manufacture issues to appear thorough. Report what's actually there.
- Quote the literal offending text when flagging issues.
- Don't soften a BLOCK to a warning to be polite. If it's blocking, say so.
- If the input draft includes [UNCONFIRMED] tags, the QA gate inherits that flag - those tags must be resolved before passing.
- Scripted checks report actual command output, not assumed results. If a check could not be run (e.g., LibreOffice unavailable), report it as NOT RUN, never as PASS.

---

## Expected outputs
- Overall PASS / PASS WITH WARNINGS / BLOCKED status
- Principle #14 battery results (5 passes, all versions)
- Per-dimension report including persona review panel findings
- Blocking issues list
- Warnings list
- Recommended next module

## Connection to other modules
- If blocked: `04_content_build` (content/format issues) or `07_fact_check` (claim issues)
- If passes: `11_output_packaging`
- New QA patterns observed: append to `my-data/lessons_learned.md` (optional)
