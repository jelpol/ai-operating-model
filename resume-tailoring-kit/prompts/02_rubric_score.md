# Module 02: Rubric Score

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable
**Position in pipeline:** Module 2 of 15 (also run after content_build for final score)
**Depends on:** Requirements matrix from Module 01, semantic_equivalence_map.md

## What this module does
Scores a resume version against a requirements matrix. Produces a weighted % effectiveness score, per-bucket breakdown, ATS keyword density check, verb diversity check, above-the-fold weighting, and categorized gap report. Used for both baseline and final scoring. Also reports a competitive-standout verdict on whether the top third differentiates against the qualified-candidate pool. Rationale: fit gets a resume past the parser; differentiation gets the callback.

## When to use it
- After intake to baseline an existing source version
- After content_build to score the tailored draft
- Standalone to audit any resume against a JD

---

## PROMPT TO PASTE INTO CLAUDE

You are operating as **Module 02: Rubric Score** for the candidate's resume tailoring system.

Read first:
- The candidate's fact registry. Make sure your fact registry (my-data/fact_registry.json) is pasted into or attached to this chat.
- `prompts/principles.md`
- `prompts/semantic_equivalence_map.md` - for synonym recognition. (Examples in that map use cybersecurity roles; rebuild the lists for your own field.)

Inputs you need:
1. The requirements matrix from Module 01 (or paste-in)
2. The resume version to score (file path or paste-in)
3. Whether this is BASELINE or FINAL scoring

**Scoring method - 0/1/2/3 scale.**

For each requirement in the matrix, score the resume content:
- **0 points** - absent
- **1 point** - mentioned but generic, no specifics
- **2 points** - addressed adequately with named tools, scope, or evidence
- **3 points** - strongly demonstrated with quantified evidence, named artifacts, or scoped impact

Apply bucket weights:
- MUST-HAVE: weight x3
- STRONG-SIGNAL: weight x2
- NICE-TO-HAVE: weight x1

**Above-the-fold weighting.**

The top third of the resume - Executive Summary, Selected Leadership Highlights (or equivalent), and the first listed job description - gets a 1.5x weight multiplier on its content. Recruiters and ATS engines both weight placement.

Identify the top third by content position, not page position. Then for any requirement scored using content from the top third, multiply that requirement's score by 1.5.

**Second-pass stricter check.**

After completing the first scoring pass, do a SECOND pass with explicitly stricter criteria:
- A "2" only counts as "2" if at least two of {named tool, scope, quantified result} are present
- A "3" requires at least three of the four: named tool, scope, quantified result, named artifact
- Demote anything that doesn't meet the stricter bar

Report the delta between the lenient and strict scores. If delta > 5 percentage points, flag the score as "uncertain - wide spread." This approximates multi-run averaging in a single pass.

Compute: weighted_score / max_possible x 100 = effectiveness %. Report both lenient and strict.

**Verb diversity sub-score.**

Verb diversity is a HUMAN-readability metric, not an ATS metric. ATS engines do not score verb variety. The honest rationale: a recruiter or hiring manager reading ten bullets that all open with "Led" registers it as padding and stops absorbing the content. Vary verbs for the human reader - but never sacrifice a required literal keyword to improve this ratio.

Count action verbs at the start of each bullet across the entire resume. Compute:
- unique_verbs / total_bullets = verb_diversity_ratio

Targets:
- >= 0.6 = [PASS] good diversity
- 0.4 - 0.6 = [WARN] some repetition, consider varying
- < 0.4 = [FAIL] heavy repetition, reads as monotonous to a human reviewer

List the 5 most-repeated verbs.

**Keyword density check.**

For each MUST-HAVE requirement, check whether its key terms (named technologies, certifications, frameworks) appear >= 2 times in the resume. Report EXACT-literal-phrase matches and synonym matches SEPARATELY - recruiter-facing ATS search (Workday, iCIMS) is literal boolean, so only verbatim occurrences of the JD's phrase are guaranteed to surface in a recruiter's keyword search. Use the semantic_equivalence_map.md to identify synonym matches (e.g., "JML" and "joiner-mover-leaver" both count as identity-lifecycle synonyms), but never merge the two counts into a single number.

Flag any must-have keyword that appears:
- 0 times verbatim, 0 synonyms -> [FAIL] absent (critical gap)
- 0 times verbatim, synonyms present -> [FAIL] literal miss (recruiter boolean search will not find it)
- 1 time verbatim -> [WARN] under-emphasized
- 2+ times verbatim -> [PASS] adequate

**MUST-HAVE verbatim rule.**

Every MUST-HAVE requirement's literal JD phrase must appear verbatim at least once in the ATS version (twice preferred), wherever it is honest to include it. Semantic-map synonyms count toward density but may never replace the last verbatim occurrence of the phrase.

**Competitive-standout check.**

Fit gets a resume past the parser; differentiation gets the callback. After scoring fit, evaluate the TOP THIRD against the qualified-candidate pool for this role family: what does this resume carry that the other plausible candidates' resumes will not?

Build the differentiator list from the candidate's own fact registry; verify each item against the current fact registry before crediting it. Generic examples of what qualifies (rebuild for your own field and history): an active clearance or headline certification, named-brand leadership experience, a flagship quantified improvement arc (e.g., cycle time cut from months to days), unusual scale or geographic scope (global build-outs, large org growth), promotions delivered for direct reports, rare cross-domain combinations.

Report a verdict:
- **STANDOUT** - two or more differentiators surface in the top third
- **COMPETENT-BUT-GENERIC** - fit is present but the top third reads like the rest of the pool
- **BURIED** - differentiators exist in the document but sit below the fold

The verdict reports ALONGSIDE the effectiveness % - it never adjusts the mechanical score (scores stay comparable across the package history). A BURIED verdict routes back to 04_content_build for top-third rework.

**Gap report.**

For each requirement scoring 0 or 1:
- Quote the JD phrase
- Show what's currently in the resume (or "absent")
- Categorize the gap as one of:
  - **EVIDENCE-PRESENT-BUT-UNDER-SURFACED** - the candidate has the experience per the fact registry or source resume; the current draft just doesn't surface it well
  - **EVIDENCE-LIKELY-UNDOCUMENTED** - the candidate probably has this but it's not in the resume or fact registry. Candidate for interrogation.
  - **GENUINE-GAP** - the candidate doesn't have this experience. Acknowledge and address in cover letter.

Use the fact registry to inform the categorization. Don't classify as GENUINE-GAP without first checking the fact registry.

**Output structure:**

```
RUBRIC SCORE - [Resume version] vs [Target role]
Scoring type: [BASELINE / FINAL]

OVERALL EFFECTIVENESS
- Lenient pass: [X]% ([weighted] / [max])
- Strict pass: [Y]%
- Delta: [Z] pp [STABLE / UNCERTAIN]

PER-BUCKET BREAKDOWN
- MUST-HAVE: [X]% lenient | [Y]% strict
- STRONG-SIGNAL: [X]% lenient | [Y]% strict
- NICE-TO-HAVE: [X]% lenient | [Y]% strict

ABOVE-THE-FOLD CONTRIBUTION
- Top-third content contributed: [X] points of total weighted score
- Top-third effectiveness: [X]% of available top-third weight captured

VERB DIVERSITY (human-readability metric)
- Ratio: [X.XX] [PASS / WARN / FAIL]
- Most-repeated verbs: [verb1 (n), verb2 (n), ...]

KEYWORD DENSITY (must-have keywords; verbatim and synonym counts reported separately)
- [keyword]: verbatim [count] | synonyms [count] [PASS / WARN / FAIL]

MUST-HAVE VERBATIM CHECK (ATS version)
- [JD literal phrase]: [n] verbatim occurrences [PASS >= 1, prefer 2 / FAIL 0]

COMPETITIVE-STANDOUT CHECK
- Differentiators in top third: [list]
- Verdict: [STANDOUT / COMPETENT-BUT-GENERIC / BURIED]

GAP REPORT
1. [JD phrase] | Current: [resume excerpt or "absent"] | Score: [0-3] | Category: [...]
2. ...

PRIORITY GAPS FOR NEXT MODULE
- Top 3-5 gaps that would move the score most if addressed

RECOMMENDED NEXT MODULE
- If baseline + score < 75%: 03_proactive_interrogation
- If baseline + score >= 75%: 04_content_build
- If final + score >= 90%: 05_cross_document_alignment then 06_qa_gate
- If final + score < 85%: another pass of 04_content_build
- If delta > 5pp (uncertain): re-score with even stricter criteria before deciding
```

**Anti-hallucination requirements:**
- Don't credit a bullet for evidence that isn't actually there.
- Use the semantic_equivalence_map.md as the AUTHORITY on what counts as a synonym. Don't invent equivalences not in the map.
- The score is mechanical; don't soften it to encourage the user. If it's 61%, say 61%.
- Cite fact registry IDs when crediting a bullet for evidence the registry confirms.
- If the lenient and strict scores diverge significantly, the honest report includes BOTH and acknowledges the uncertainty.

---

## Expected outputs
- Lenient + strict effectiveness % (with delta and stability flag)
- Per-bucket breakdown
- Above-the-fold contribution
- Verb diversity sub-score
- Keyword density check (verbatim and synonym counts separate) + must-have verbatim check
- Categorized gap report
- Specific recommended next module

## Connection to other modules
- EVIDENCE-LIKELY-UNDOCUMENTED gaps -> `03_proactive_interrogation`
- Priority gaps -> `04_content_build`
- Score deltas (baseline to final) capture this module's value in your session notes
- New synonyms discovered during scoring -> add to `semantic_equivalence_map.md`
