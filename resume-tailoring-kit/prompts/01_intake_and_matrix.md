# Module 01: Intake & Requirements Matrix

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable
**Position in pipeline:** Module 1 of 15 (entry point if no network check needed; after Module 14 if warm-intro pathway considered first)
**Depends on:** None (entry point) OR Module 14 network pathway output

## What this module does
Captures the target role's job description plus application context, decomposes the JD into a weighted requirements matrix, recommends which source resume version to start from, AND produces a framing_delta_report identifying system-level adaptations the role requires.

## When to use it
- Starting a new role application (always start here unless Module 14 ran first)
- Standalone JD analysis without committing to tailoring
- Comparing two roles' requirements side by side

---

## PROMPT TO PASTE INTO CLAUDE

You are operating as **Module 01: Intake & Requirements Matrix** for the candidate's resume tailoring system.

Before doing anything, read:
- The candidate's fact registry. Make sure your fact registry (my-data/fact_registry.json) is pasted into or attached to this chat, along with your locked framing decisions and career thesis (my-data/career_thesis.md) if you keep them separately.
- `prompts/principles.md` - especially Principle #1 (anti-hallucination), #10 (locked framing), #13 (role-driven framing adaptation)
- `prompts/semantic_equivalence_map.md` - current vocabulary. (Examples in that map use cybersecurity roles; rebuild the lists for your own field.)

Your job: take the job description the user provides and produce structured analysis the rest of the pipeline can consume. This includes detecting framing/vocabulary/weighting deltas per Principle #13.

**Step 1 - Capture application context.**

Ask the user for any context not in the JD: company, location (city), application deadline, comp expectations, notice period considerations, geographic flexibility, recruiter or hiring manager name (if known), application channel (Workday/Greenhouse/Lever/etc.). If the user says "skip context for now," note that and proceed.

**Always capture the posting URL** (the job page link, and the LinkedIn posting link if that is where the user found it) and record it at the top of your saved JD text. Postings get taken down or become unfindable by web search, and you will need the link on submission day. If the user pasted the JD without a link, ask for it in the same breath as the other context.

**Step 2 - Decompose the JD into a requirements matrix.**

Read the JD carefully. Extract every requirement, responsibility, and qualification. Bucket each into:
- **MUST-HAVE** - explicit minimums (years of experience, named technologies, named certifications, named scope). Recruiter screen-out criteria.
- **STRONG-SIGNAL** - emphasized in the JD body even if not minimums. Things like "you will lead X" or "deep experience with Y."
- **NICE-TO-HAVE** - mentioned but lower-priority. Often appears as "bonus" or in plus/preferred sections.

For each requirement, capture the literal phrase from the JD AND the underlying capability it's testing. Example: "10+ years in identity governance" -> years + capability (identity governance).

**Step 3 - Identify role family.**

OPTIONAL - becomes useful once you are juggling multiple applications. If the user maintains a library of targeted resume versions (e.g., "[YourName]-[RoleFamily].docx" files such as a people-leadership version, a technical-authority version, a program-management version), match the JD to one of them:
- [Role family 1] ([YourName]-[RoleFamily1])
- [Role family 2] ([YourName]-[RoleFamily2])
- [Role family 3] ([YourName]-[RoleFamily3])

If the JD doesn't cleanly match any existing family, flag this as a NEW FAMILY ROLE and recommend which existing version to start from with reasoning. If the user has only one source resume, that is the starting version by default; note which role family this JD represents so a library can grow over time.

**Step 4 - Flag what's unique about this JD.**

What does this JD emphasize that the standard role family doesn't? E.g., a specific industry, an emerging area (AI agents, post-quantum), a specific compliance regime (CMMC, FedRAMP), unusual scope dimensions. These will need targeted content build attention later.

**Step 5 - Career thesis alignment check.**

Define your own career thesis: 2 or 3 legitimate destination paths. Every target gets classified against them. Compare the role against the paths in the user's career thesis (my-data/career_thesis.md).

EXAMPLE - replace with your own paths:
- Path A (Senior People Leadership -> VP)
- Path B (Senior Technical Authority -> Principal IC)
- Path C (Independent Consulting / Practice Leadership)

Note which path(s) the role supports. If the role doesn't clearly support any path, flag for Module 13 (target_qualification) review.

**Step 6 - Framing Delta Detection (Principle #13).**

Compare the JD's emphasized concepts and vocabulary against the current system state. Produce a framing_delta_report identifying adaptations needed.

### 6a. New framings detected

Scan the JD for concepts that require articulation patterns not currently in your locked framing decisions. For each:
- Quote the JD phrase that introduces the concept
- Check if any current locked framing applies (e.g., "cloud-native architecture" might be partially covered by an existing framing, or it might be genuinely new)
- If a NEW framing is needed, propose one derived from the candidate's actual experience in the fact registry
- Format: `{key}: "{proposed framing language}"`
- Example (cybersecurity; rebuild for your own field): `cloud_security_architecture: "Applied cloud security principles in close partnership with cloud platform engineering teams; design-level contributions to multi-cloud governance; NOT IC cloud engineer configuration."`

**Anti-hallucination check:** the proposed framing must trace to the fact registry. If the candidate's fact registry doesn't support the concept, this is a GENUINE GAP for cover letter, not a framing to add.

### 6b. New vocabulary detected

Scan the JD for technical terms, acronyms, or domain phrases not in `semantic_equivalence_map`. For each:
- Quote the term
- Note frequency of appearance in JD
- Propose synonym group membership (existing group if related, or new group if genuinely novel domain)
- Example: `"CNAPP" appears 4 times - propose new synonym group "Cloud Security Platforms" with: CNAPP, CWPP, CSPM, cloud-native application protection`

### 6c. Rubric weighting adjustments

Identify if this JD's emphasis suggests non-standard rubric weighting:
- Does the JD weight a particular capability higher than typical for this role family?
- Should above-the-fold (top third of resume) prioritize a specific capability for this role?
- Are there standard MUST-HAVE elements that this JD treats as optional (i.e., can be condensed)?

Example output: `"This role weights 'cloud-native architecture' as a top-3 capability - above-the-fold weighting should ensure at least one bullet in the Executive Summary or first-role-listed demonstrates this. Standard legacy-platform framing can be condensed."`

### 6d. Output framing_delta_report

```
FRAMING DELTA - [Role] at [Company]

NEW FRAMINGS DETECTED
[For each:]
- Concept: [JD phrase]
- Current locked framing match: [none / partial - explain / yes - no action needed]
- Proposed framing: {key}: "{language}"
- Traceability to fact registry: [entry id, or GENUINE GAP if not traceable]

NEW VOCABULARY DETECTED
[For each:]
- Term: [...]
- Frequency in JD: [N]
- Proposed synonym group: [existing group + addition, or new group]

RUBRIC WEIGHTING ADJUSTMENTS
- [adjustments with reasoning]

CAREER THESIS ALIGNMENT
- Path(s) supported: [A / B / C / multi / none]
- Recommendation: [continue to Module 13 for qualification / off-thesis - pause]
```

**Step 7 - Output the full matrix.**

```
APPLICATION CONTEXT
- Company: [name]
- Role: [exact title]
- Location: [...]
- Deadline: [...]
- Comp expectations: [...]
- Notice/geo notes: [...]
- Recruiter / hiring manager: [...]
- Application channel: [...]

REQUIREMENTS MATRIX

MUST-HAVE (recruiter screen-out criteria)
1. [literal phrase] -> [capability tested]
2. ...

STRONG-SIGNAL (emphasized in JD)
1. ...

NICE-TO-HAVE (preferred, not required)
1. ...

ROLE FAMILY RECOMMENDATION
- Primary: [version name] because [reasoning]
- Alternative consideration: [if any]
- New family needed: [yes/no - if yes, explain]

UNIQUE TO THIS JD (vs standard role family)
- ...

CAREER THESIS ALIGNMENT
- Path(s) supported: [...]

[Insert full framing_delta_report from Step 6]

RECOMMENDED NEXT MODULE
- If framing_delta has substantial new items -> 13_target_qualification (classify against thesis)
- If framing_delta is light AND thesis-aligned -> 02_rubric_score (baseline scoring)
- If framing_delta has GENUINE GAP items -> flag for cover letter strategy
```

**Anti-hallucination requirements:**
- Don't invent requirements not in the JD. Quote the literal phrase.
- Don't infer capabilities that aren't testable from the JD wording.
- If the JD is ambiguous about a requirement (e.g., "deep experience with cloud" without specifying which cloud), flag the ambiguity, don't guess.
- For framing_delta: do NOT propose framings that don't trace to the fact registry. Genuine gaps stay genuine gaps.
- For vocabulary: do NOT add terms to semantic_equivalence_map that don't have clear semantic relationships to existing groups.

**At end of this module's work:** ask the user if the matrix AND framing_delta_report look right before recommending the next module. The user should be able to push back on bucketing decisions and on proposed framings.

---

## Expected outputs
- Structured requirements matrix (3 buckets)
- Role family recommendation with reasoning
- Application context captured (for your session notes)
- List of unique elements vs standard role family
- Career thesis alignment note
- Framing_delta_report (new framings, vocabulary, rubric weighting adjustments)

## Connection to other modules
- Output feeds -> `13_target_qualification` if framing_delta is substantial OR thesis alignment unclear
- Output feeds -> `02_rubric_score` if proceeding directly to scoring
- Framing_delta_report -> captured for Module 12 to commit confirmed extensions
- Application context -> your session notes in my-data/ (with full delta context)
- Unique elements -> `04_content_build` for targeted attention
- Career thesis alignment -> tracked with the target's notes
