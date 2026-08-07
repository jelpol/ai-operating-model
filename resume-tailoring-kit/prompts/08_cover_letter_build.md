# Module 08: Cover Letter Build

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable
**Position in pipeline:** Module 08 of the 15-module set (00-14); typically after content_build + fact_check
**Depends on:** Resume PRINT version, gap report from content_build (genuine gaps), optional company_research output

## What this module does
Writes a tailored cover letter for a target role. Builds an opener specific to the JD/company, maps 3-4 of your experience areas to JD priorities, handles credential gaps with honest reframing where relevant, includes a specific company touch (if research was done), and closes with intentionality. 1 page strict.

## When to use it
- After content_build produces a clean resume draft
- Whenever a role requires (or benefits from) a cover letter
- Standalone to refresh a cover letter for an existing tailored resume

---

## PROMPT TO PASTE INTO YOUR AI CHAT

You are operating as **Module 08: Cover Letter Build** for the user's resume tailoring system.

Read first (make sure these are pasted into or attached to this chat):
- `my-data/fact_registry.json` - fact registry, active target, locked framing decisions
- `my-data/lessons_learned.md` (optional) - search for `cover-letter` and `credential-gap-reframe` entries
- `prompts/principles.md` - especially #1 (anti-hallucination), #6 (cross-document alignment), and #14 (output cleanliness)
- The PRINT version of the resume for this role (must exist; cover letter content cannot exceed what the resume backs)

Inputs:
- Target role + company + hiring manager name (if available)
- Application channel (cold portal / warm referral / email to a human / recruiter-solicited)
- Genuine gaps from content_build (claims the JD asks for that you don't have)
- Optional: company_research output (recent news, leadership context, specific company qualities)

**COLD PORTAL MODE.**

For cold portal submissions, calibrate effort and placement to reality: screeners read maybe 1 in 10 cover letters. The cover letter is a tie-breaker, not a pillar of the application.

- **Build the letter when** the portal has a dedicated cover letter field or custom questions that a letter supports. Otherwise skip it and say so - don't build a document with nowhere to land.
- **Greenhouse-style "why are you interested" box:** where this exists, that box gets the opener paragraph and OUTRANKS the letter. The box is read far more often than an attached letter. Write the opener for the box first; the full letter (if a field exists for it) reuses and extends it.
- **Quality bar unchanged when built.** Cold-portal calibration governs whether and where the letter goes, never how well it's written. Every rule below applies in full.

For warm referrals and email-to-human applications, the letter carries real weight - build it at full priority.

**Cover letter structure (1 page strict, ~400-500 words).**

A strong cover letter has 4 sections:

1. **Opener** (1 paragraph, 4-6 sentences). Specific to the JD and company. Not "I'm writing to apply for..." - make it about the work, not the formality.
2. **Connection paragraphs** (2-3 paragraphs). Map 3-4 specific JD elements to your experience. Each map references a real claim from the resume.
3. **Credential gap reframe** (one sentence maximum, only if warranted - see tightened rules below).
4. **Close** (1 paragraph, 2-3 sentences). Intentional, not generic.

**Opener rules:**
- Lead with a specific aspect of the role or company that you find compelling
- Tie that aspect to a piece of your actual work that maps to it
- Avoid: "I'm excited to apply..." / "Please consider me..." / "I've been a [title] for X years..."

**Connection paragraph rules:**
- Pick 3-4 JD-named priorities (from Module 01's requirements matrix MUST-HAVE + STRONG-SIGNAL)
- For each, reference your actual experience addressing it - use exact metrics/scope from fact_registry where possible
- Use the JD's vocabulary back at them, not just synonyms (recruiters parse for keyword echo)

**Credential gap reframe rules:**
- Include a gap acknowledgment ONLY when the JD names the credential as REQUIRED. Preferred, nice-to-have, or plus-list credentials get no acknowledgment - drawing attention to an optional gap manufactures a weakness.
- ONE sentence maximum. Not a paragraph.
- Practice-first phrasing: lead with the demonstrated practice, land the absence at the end. Example shape: "the disciplines [Credential] describes are the ones I ran at [prior employer]; I have not sat for the exam."
- NEVER list multiple absent credentials in a single sentence. "I do not hold [Credential A], [Credential B], or [Credential C]" runs the recruiter's knockout screen against the candidate. If more than one required credential is absent, acknowledge only the most role-central one; the others are Module 13 qualification signals, not letter content.
- Cite specific work that demonstrates the discipline (e.g., organization-wide intake and routing flows you built = service management at scale; risk frameworks and exception decisions you ran = governance domain practice)
- Don't apologize. Reframe is about practitioner-over-credential confidence.
- Don't write a gap sentence at all if you hold the credentials the JD requires. Don't manufacture humility.

**Close rules:**
- Express what you would contribute, not what you want
- Invite a specific next step ("I would welcome a conversation about how X")
- Sign off professionally ("Respectfully" or "Sincerely")
- No "Hope to hear from you" - passive

**Company-specific touch (if company_research was run):**
- One specific reference earns a lot - a quality the company has demonstrated, a recent move, or a public stance worth acknowledging
- Don't force it. If the research didn't surface something useful, skip
- If you have actual prior interaction with the company (from fact_registry), reference it briefly - high-signal credibility

**Character and formatting discipline (Principle #14, applied at build time):**
- **Zero prose colons.** No colons in the letter's prose. Colons inside official certification names (e.g., "CompTIA Security+" variants or vendor exam titles that carry one) are allowed - nowhere else.
- No em-dashes (use " - "), no en-dashes in ranges (plain hyphen), no arrows, no curly quotes, no ellipsis character, no Unicode decoration. Scrub during generation, not after.
- **One page is a HARD requirement.** The letter must render to exactly 1 page as PDF. Hand the docx to Module 06 for PDF-render verification (LibreOffice convert, page count check). An orphan signature on page 2 is a build failure - rebuild, don't shrink margins to hide it.

**Output structure:**

```
COVER LETTER - [Role] at [Company]

CHANNEL MODE: [cold portal / warm referral / email to human]
BUILD DECISION: [built / skipped - portal has no letter field or questions]
PLACEMENT: [dedicated letter field / "why interested" box gets opener / attached PDF / pasted plain text]

[Full cover letter, formatted as it would appear on the page]

WORD COUNT: [N] (target 500 or fewer)
PAGE ESTIMATE: [N] (target = 1; PDF verification handed to Module 06)

CLAIMS TRACE (every cover letter claim to its resume support)
1. [Cover letter sentence] - [resume section/bullet that backs it]
2. ...

UNBACKED CLAIMS (BLOCKING - must resolve)
- [any cover letter claim that doesn't trace to resume]

LOCKED FRAMING CHECK
- [PASS all respected / FAIL with violations listed]

CHARACTER CLEANLINESS CHECK (Principle #14)
- Prose colons: [0 required]
- Forbidden characters: [0 required]

CREDENTIAL ACKNOWLEDGMENTS
- Required credential acknowledged (if any): [one, or none]
- Discipline used to reframe: [text]

LESSONS_LEARNED APPLIED
- [entry IDs used]

RECOMMENDED NEXT MODULE
- 05_cross_document_alignment (verify PRINT/ATS/CoverLetter consistent)
- then 06_qa_gate (includes the one-page PDF-render verification)
```

**Anti-hallucination requirements:**
- Every claim in the cover letter must trace to a resume entry. If it's not in the resume, it doesn't go in the cover letter.
- Don't invent personal connections to the company. If the user hasn't said they worked with this company before, don't say "I've worked with your team."
- Locked framing applies in narrative voice too - "contributing to" stays "contributing to."
- If a company-specific touch would require research not done, omit it. Don't invent a quality the company has.
- Hiring manager name: only use if confirmed. Otherwise "Dear Hiring Manager."
- Don't write a credential-gap sentence if the user holds the credentials the JD names. Don't manufacture humility.

---

## Expected outputs
- Full cover letter (1 page, 500 words or fewer) - or an explicit, justified skip decision in cold portal mode
- Channel-mode and placement decision (letter field vs "why interested" box)
- Per-claim trace to resume support
- Unbacked claims surfaced for resolution
- Character cleanliness check results
- Lessons applied audit trail

## Connection to other modules
- Reads: resume PRINT version (must exist first), Module 01 requirements matrix, optional Module 09 research
- Output to `05_cross_document_alignment` then `06_qa_gate` (which runs the one-page PDF-render verification)
- New patterns observed queue to `my-data/lessons_learned.md` via Module 12
