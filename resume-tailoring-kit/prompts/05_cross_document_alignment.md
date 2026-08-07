# Module 05: Cross-Document Alignment

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable
**Position in pipeline:** Module 5 of 15 (after content_build and cover_letter_build, before qa_gate)
**Depends on:** PRINT version, ATS version, and (if it exists) cover letter

## What this module does
Audits PRINT, ATS, and CoverLetter versions for the same role to ensure content consistency. Catches drift in dates, titles, headline metrics, named entities, and factual claims. Tone differences across formats are accepted; factual mismatches are blocking.

## When to use it
- After content_build + cover_letter_build, before qa_gate
- Standalone whenever multiple versions exist for the same role and you suspect drift
- Before any final submission to a target

---

## PROMPT TO PASTE INTO CLAUDE

You are operating as **Module 05: Cross-Document Alignment** for the user's resume tailoring system.

Read first (make sure these are pasted into or attached to this chat):
- `my-data/fact_registry.json` - fact_registry, locked_framing_decisions, active target
- `prompts/principles.md` - especially Principle #6 (cross-document alignment)
- `prompts/semantic_equivalence_map.md` - to recognize when synonymous terms across docs are still consistent

Inputs:
- PRINT version (file path or paste-in)
- ATS version (file path or paste-in)
- (Optional) Cover letter

**Alignment checks.**

For each pair of documents, run these checks:

### 1. Dates and titles
- Every role's start/end dates match across all docs
- Every role's title matches across all docs
- Earlier Career section dates match where roles appear

### 2. Headline metrics
- Direct report counts (e.g., "[X]+" vs "a handful" = misalignment)
- Years of experience (e.g., "[X]+ years" vs "nearly two decades" - flag if drift)
- Project counts, case counts, team scale
- All quantified evidence claims

### 3. Named entities
- Customer/client descriptors mentioned (e.g., "Fortune 100", "government agencies" - must match)
- Tool/platform names (examples below use cybersecurity roles - e.g., SailPoint, Entra ID; rebuild the lists for your own field)
- Compliance/framework names (e.g., SOX, ISO 27001 - same set referenced)
- Certifications listed (must be identical across resumes; the cover letter doesn't need to list them, but if it does, they must match)

### 4. Locked framing decisions
Verify against the FULL locked_framing_decisions list in your fact registry (my-data/fact_registry.json). Every locked framing must be respected consistently across all documents. Examples (illustrative only, not the full list):
- Platform work you supported but did not own = "in close partnership with platform owners"
- Zero Trust = "contributed to" or "co-designed", never unqualified "implemented"

### 5. Factual claims
For each substantive claim in one doc, check that any related claim in another doc:
- Doesn't contradict
- Doesn't significantly inflate or deflate
- Uses semantically consistent language (semantic_equivalence_map.md applies)

### 6. Cover letter specific (when present)
- Any claim made in the cover letter must be supported by resume content
- The cover letter cannot introduce experience NOT shown in the resume
- Credential gaps acknowledged in the cover letter should align with reality (no fake humility about credentials the user actually holds, no false confidence about credentials they don't)

**Tone differences that are OK (not flagged):**
- Cover letter is conversational; resume is direct
- Cover letter uses first person; resume uses implied first person
- Cover letter explains "why this role"; resume doesn't
- Cover letter can name a company-specific detail (e.g., "the balance of rigor and pragmatism at [Company]") that wouldn't appear in the resume

**Output structure:**

```
CROSS-DOCUMENT ALIGNMENT AUDIT - [Target role]

DOCUMENTS COMPARED:
- PRINT: [path]
- ATS: [path]
- Cover Letter: [path or "N/A"]

ALIGNMENT STATUS: [ALIGNED / MINOR DRIFT / BLOCKING MISALIGNMENT]

DATES & TITLES
- [PASS: all match / WARN: drift on ... / FAIL: mismatch on ...]

HEADLINE METRICS
- [PASS: all consistent / WARN: variation: [doc A: "X", doc B: "Y"]]

NAMED ENTITIES
- [PASS: consistent / WARN: drift: [details]]

LOCKED FRAMING DECISIONS (full list from the fact registry)
- [PASS: respected / FAIL: violation: [doc: ..., text: ..., lock violated: ...]]

FACTUAL CLAIMS
- Total claims compared: [N]
- Aligned: [n]
- Drift (semantic): [n]
- Contradictions: [n]

COVER LETTER -> RESUME BACKING (when CL present)
- Claims in CL: [n]
- Backed by resume: [n]
- Unsupported by resume: [n] - must resolve

BLOCKING ISSUES (must fix before submission)
1. [specific mismatch with doc references]
2. ...

MINOR DRIFT (recommend fix, not blocking)
1. ...

RECOMMENDED NEXT MODULE
- If blocking issues: back to 04_content_build or 08_cover_letter_build to resolve
- If clean: 06_qa_gate
```

**Anti-hallucination requirements:**
- Don't infer alignment when the documents are genuinely silent. If one doc mentions "[N]+ cases" and another doesn't mention cases at all, that's not a misalignment - it's just absence.
- Don't manufacture drift to seem thorough. Report only actual differences.
- Quote literal text when reporting mismatches; don't paraphrase the apparent drift.

---

## Expected outputs
- Alignment status (ALIGNED / MINOR DRIFT / BLOCKING MISALIGNMENT)
- Per-check pass/fail with specifics
- Blocking issues list (if any)
- Minor drift list (recommendations)
- Recommended next module

## Connection to other modules
- If blocking -> back to `04_content_build` or `08_cover_letter_build`
- If clean -> `06_qa_gate`
- Drift patterns observed -> append to `my-data/lessons_learned.md` (optional) if reusable
