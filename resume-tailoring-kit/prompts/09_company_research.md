# Module 09: Company Research

**Version:** 1.0 (public starter kit release)
**Module type:** Callable; DEFAULT ON for serious targets
**Position in pipeline:** Runs before cover_letter_build, or before interview_prep
**Depends on:** Target company name

## What this module does
Light, targeted research pass on a target company to inform cover letter specificity and interview prep. Captures current leadership, recent news relevant to your target function, structural signals (M&A, layoffs, reorgs), regulatory context, and any prior interaction you have had with the company. Output is ~1 page of useful context - not an industry report.

This module is ON BY DEFAULT for serious targets (see prompts/README.md, the operating manual; the orchestrator must not skip it for any target you genuinely intend to pursue). Skip only for low-stakes or exploratory runs. For cold portal submissions the research matters even more, not less: it feeds the cover letter and the screening-question answers that substitute for a referral's warmth.

Examples below use cybersecurity roles; rebuild the relevance filters for your own field.

## When to use it
- Before cover_letter_build if you want specific company-anchored language
- Before cold portal submissions - the research feeds the cover letter and screening-question answers that substitute for a referral's warmth
- Before interview_prep - context-rich responses land better
- Standalone to refresh research between application and interview

---

## PROMPT TO PASTE INTO CLAUDE

You are operating as **Module 09: Company Research** for the user's resume tailoring system.

Read first (make sure these are pasted into or attached to this chat):
- `my-data/fact_registry.json` - check for any prior interaction with this company
- `my-data/lessons_learned.md` (optional) - search for the company name

Inputs:
- Target company name
- Target role (for relevance filtering)

**Default behavior.**

This module is ON by default for serious targets. Do not treat it as optional overhead when the user genuinely intends to pursue the role; only skip for low-stakes or exploratory runs.

**Research scope (light, targeted).**

You have web search and web fetch available. Use them for:

1. **Current leadership** - the executives most relevant to the target role family (for a security/IAM director hire that means CEO, CISO, CIO, CHRO; adjust for your field). Confirm names and recency.
2. **Recent function-relevant news** - last 6-12 months: incidents, major hires in the target function, technology adoption, regulatory issues.
3. **Company structure signals** - public M&A activity, divestitures, layoffs, reorganizations (relevant to whether the role is in a stable or churning environment).
4. **Industry/regulatory context** - what regulatory regime (FFIEC, SEC, HIPAA, etc.) and primary risk profile.
5. **Culture signals from public sources** - high-level only. Avoid Glassdoor specifics; cite company press, leadership public statements, reputable industry coverage.
6. **Prior interaction** - check the fact registry: has the user worked with or for this company before (as an employer, customer, client, or vendor)? If unclear, ask the user directly.

**Scope discipline.**

This is a 5-10 minute research pass, not Wall Street equity research. The deliverable is 1 page of useful context. If you can't find something material in 2-3 searches, move on.

**Output structure:**

```
COMPANY RESEARCH - [Company]
Target role: [role]
Research date: [date]

LEADERSHIP (last verified [date], cite source for each)
- CEO: [name]
- [Function head, e.g., CISO]: [name or "not publicly named"]
- [Other relevant executive]: [name or "not publicly named"]
- Other relevant: [...]

RECENT FUNCTION-RELEVANT NEWS (last 12 months, sources cited)
1. [date - 1-line summary] - source: [URL or publication]
2. ...

COMPANY STRUCTURE & STABILITY SIGNALS
- M&A activity: [...]
- Reorganization signals: [...]
- Hiring momentum in the target function (if findable): [...]

REGULATORY/INDUSTRY CONTEXT
- Primary regime: [FFIEC / SEC / HIPAA / etc.]
- Recent regulatory events: [...]

CULTURE SIGNALS (high-level, public sources only)
- [observation with source]
- Note: avoid Glassdoor specifics; use company press, leadership statements

PRIOR INTERACTION (from the fact registry)
- [yes/no + details if yes; ask the user if unclear]

KEY CONTEXT FOR COVER LETTER
- Specific company quality worth referencing: [...]
- Recent event the candidate could acknowledge: [...]
- Language the company uses about itself worth echoing: [...]

KEY CONTEXT FOR SCREENING QUESTIONS (cold portal submissions)
- Company facts that strengthen "why us" answers: [...]
- Specifics that make portal answers read warm rather than generic: [...]

KEY CONTEXT FOR INTERVIEW PREP
- Likely interviewer focus areas given recent news: [...]
- Topics to research deeper before interview: [...]
- Red flags worth asking about: [...]

LESSONS_LEARNED TO APPEND
- [if any reusable patterns surface]

RECOMMENDED NEXT MODULE
- 08_cover_letter_build (use research for specificity) OR
- 10_interview_prep (use research for context)
```

**Anti-hallucination requirements:**
- Cite sources for every news item (URL or publication + date)
- Don't infer leadership changes from old data - confirm current state
- Don't make up culture claims. If you can't find a specific source, omit
- If prior interaction can't be confirmed from the fact registry, ask the user directly - don't assume
- If research turns up nothing material on a section, say so. Don't pad.

---

## Expected outputs
- 1-page company context document
- Specific items for cover letter and screening-question answers
- Specific items for interview prep
- Optional lessons_learned entries

## Connection to other modules
- Output -> `08_cover_letter_build` (specific company touch; screening-question warmth for cold portal submissions)
- Output -> `10_interview_prep` (context for scenario responses)
- New patterns -> `my-data/lessons_learned.md` (optional)
