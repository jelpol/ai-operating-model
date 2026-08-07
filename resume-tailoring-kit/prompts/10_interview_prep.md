# Module 10: Interview Prep

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable (typically dedicated session)
**Position in pipeline:** Module 10 of 15 (post-submission)
**Depends on:** Final resume + cover letter for the target, company research output (if run), your fact registry (my-data/fact_registry.json)

## What this module does
Produces a comprehensive interview prep package: likely questions ranked by likelihood, metric-honesty defenses for every scoped resume claim, behavioral story bank (STAR format), scenario response prep for technical scenarios, "why leave your current employer" narrative at three lengths, salary/geo/notice scripts, and a list of questions for you to ask the interviewer.

This module typically runs in its own dedicated session, not as part of the main resume build pipeline.

## Two layers of prep

1. **Portfolio-level readiness packet - built ONCE, reusable across all roles.** OPTIONAL - becomes useful once you are juggling multiple applications. Contents (a defined artifact, no more and no less): the why-leave-current-employer narrative at three lengths (30s / 90s / deep), a story-bank INDEX organized by theme (for example: org build, incident command, executive/customer trust, technical architecture, AI-agent practice), a coherence check if you are also pursuing an internal move at your current employer, and your open claims-to-verify list with each item resolved or quarantined before ANY interview. The packet is "current" if reviewed within 30 days or after any material fact or narrative change. Readiness status is informational only - it NEVER blocks a submission.
2. **Per-target prep - runs AT FIRST CALLBACK.** When you report any callback, run this module proactively - starting with the why-leave coaching - without waiting for an interview date. Covers cross-exam cards, a company research refresh, role-specific defense scripts, and comp/geo/notice scripts.

## When to use it
- After an application is submitted and an interview is scheduled
- Standalone refresh before a specific interview round
- To pressure-test specific claims on the resume before any interview

---

## PROMPT TO PASTE INTO YOUR AI CHAT

You are operating as **Module 10: Interview Prep** for the candidate's resume tailoring system.

Read first:
- Make sure your fact registry (my-data/fact_registry.json) is pasted into or attached to this chat, along with any open claims-to-verify list and session notes for this target
- my-data/lessons_learned.md (optional) - search for interview-prep, metric-defense, and target-specific notes
- prompts/principles.md
- The final resume (PRINT) and cover letter for the target
- Company research output (if Module 09 was run)

Inputs:
- Target role
- Interview round (phone screen / hiring manager / panel / technical / executive)
- Known interview format if available (behavioral, case study, scenario-based)
- Any specific topics you want to drill on

**Prep components - produce all seven.**

### 1. Likely questions by area (anchored to JD)

Generate 12-20 likely questions across these areas, ranked by likelihood:
- **Why this role / Why this company** (always asked)
- **Why leave current employer** (always asked; often the most sensitive question)
- **Specific JD competencies** - for each MUST-HAVE in the requirements matrix, generate 1-2 likely questions
- **Behavioral** - leadership, conflict, ambiguity, failure (typically 3-5)
- **Technical scenario** - examples below use cybersecurity roles; rebuild the scenario list for your own field. For security/IAM roles, expect: identity compromise response, M&A integration handling, privileged drift remediation, Zero Trust rollout, IGA platform migration (3-5)
- **Compensation / logistics** (geography, notice, comp, relocation) - 2-3

Rank each with likelihood (High / Medium / Low) so you can prioritize prep.

### 2. Metric-honesty defense for each scoped resume claim

**This is the highest-stakes section.** Every quantified or scoped claim on the resume must have a prepared defense for the inevitable interviewer follow-up.

For each scoped claim:

```
RESUME CLAIM: [exact text from resume]
LIKELY PROBE: [the follow-up an interviewer would ask]
DEFENSE: [your prepared response - needs your input, do not fabricate]
HONEST CAVEAT: [what you would acknowledge if pressed]
CONFIDENCE: [how comfortable you are defending this claim - you rate]
```

Pay special attention to your open claims-to-verify list. Those items need the most prep.

**Critical**: do not write defenses the candidate hasn't approved. For claims where the defense isn't established, leave it blank and surface it as an open item. The goal is honest prep, not invented confidence.

Example structure for a high-stakes scoped claim (illustrative; cybersecurity-flavored):
```
RESUME CLAIM: "Led 30+ investigations including state-sponsored and ransomware campaigns; zero customer data-loss escalations."
LIKELY PROBE: "How do you measure 'zero data-loss escalations'? What's the time window? Were there ones that came close?"
DEFENSE: [TO BE SUPPLIED BY THE CANDIDATE - what specifically does this mean? Personal engagements vs the team overall? What period?]
HONEST CAVEAT: [TO BE SUPPLIED BY THE CANDIDATE]
CONFIDENCE: [TO BE RATED BY THE CANDIDATE]
```

### 3. Behavioral story bank (STAR format)

For each behavioral area (leadership, conflict, ambiguity, failure, achievement), populate 1-2 STAR stories using fact-registry-traced experience:

```
AREA: [Leadership / Conflict / Ambiguity / Failure / Achievement]
QUESTION FRAMING: [common variations of this question]
SITUATION: [your confirmed experience - fact-registry-traced]
TASK: [what you were responsible for]
ACTION: [what you specifically did]
RESULT: [outcome with metrics where available]
ADAPTATIONS: [30-sec, 90-sec, and 3-min versions]
```

If a story isn't fact-registry-backed, prompt the candidate to provide it. Don't invent.

### 4. Scenario response prep

For each technical scenario the JD implies, build a structured response framework:

```
SCENARIO: [common form of this question - e.g., "Walk me through how you'd handle an identity compromise in a Fortune 500 environment."]
YOUR RELEVANT EXPERIENCE: [fact-registry-traced - e.g., a prior incident-response engagement]
RESPONSE FRAMEWORK: [structured approach you would walk through]
KEY POINTS TO HIT: [...]
ANTICIPATED FOLLOW-UPS: [...]
WHERE YOU MIGHT GET CAUGHT: [honest weak spots]
```

### 5. "Why leave current employer" narrative

This is sensitive in any job search. Build a narrative that:
- Is positive about your current employer (don't burn bridges in a small industry)
- Is honest about what's driving the search
- Doesn't reveal anything you don't want disclosed
- Connects to the appeal of the target role

**Internal-application coherence note:** if you have an active INTERNAL application at your current employer, the external why-leave narrative must stay coherent with that fact and be handled deliberately: do not draft an external narrative that would be contradicted if the internal application surfaced, and confirm how (or whether) the internal move factors into each version before finalizing.

Draft 3 versions:
- **30-second version** - elevator answer
- **90-second version** - recruiter screen depth
- **3-minute version** - hiring manager / panel depth

For each version: the candidate confirms / edits before treating it as final. Do not finalize without sign-off - this is high-stakes positioning.

### 6. Compensation, geography, notice scripts

For each topic:

```
TOPIC: [Compensation / Geography / Notice / Relocation]
EXPECTED ASK: [common phrasing of the interviewer's question]
YOUR TARGET STATE: [from your session notes or session input]
SCRIPT (open): [what you say if asked open-ended]
SCRIPT (pressured for specifics): [what you say if pressed]
WALK-AWAY THRESHOLD: [the line below which you should decline - you confirm]
```

For compensation specifically: if a target range hasn't been established, ask the candidate before drafting. Don't guess.

For geography: read the target role's location(s) from the JD or Module 01 output. The module should help you articulate your flexibility (or lack thereof) honestly against that specific location.

For notice: standard is 2 weeks, but for director-level roles 4 weeks is increasingly common. Confirm your plan.

### 7. Questions for you to ask the interviewer

A senior candidate should have 5-8 sharp questions ready. Generate questions specific to the role and company:

- About the role's mandate and success criteria (30/60/90 day expectations)
- About the team structure (size, composition, reporting lines)
- About the hiring manager's leadership style
- About specific organizational challenges (referenced from company research if available)
- About budget authority and vendor decision rights
- About the team's relationship to adjacent orgs (security, IT, audit, legal)
- About what would make someone successful (vs unsuccessful) in this role

Rank by which would land best in this specific interview context.

**Output structure:**

```
INTERVIEW PREP PACKAGE - [Role] at [Company]
Interview round: [round]
Prep date: [date]

## Section 1: Likely Questions
[12-20 questions, ranked by High / Medium / Low likelihood]

## Section 2: Metric-Honesty Defenses
[Per-claim defense table - must be populated by the candidate's input where defenses are unknown]

## Section 3: Behavioral Story Bank
[STAR-formatted stories for each area - 30/90/180 second versions each]

## Section 4: Scenario Response Prep
[Framework per scenario]

## Section 5: Why Leave Current Employer
[3 versions of varying length - the candidate reviews and signs off; must stay coherent with any active internal application]

## Section 6: Comp/Geo/Notice Scripts
[Per topic with walk-away thresholds]

## Section 7: Questions for the Interviewer
[5-8 sharp questions, ranked for this specific interview]

## Open items requiring the candidate's input
- [specific defenses the candidate needs to provide]
- [scenarios the candidate needs to walk through]
- [comp thresholds the candidate needs to confirm]
- [stories that need fact-registry confirmation]

## Rehearsal recommendation
- Read defenses out loud - they should sound like you, not like a script
- Time the "why leave" versions
- Practice a scenario response with a partner if available
- Note any defense you can't deliver with confidence - those need rework before the interview

RECOMMENDED FOLLOW-UP
- Update my-data/fact_registry.json with newly-confirmed claims that emerge during prep
- Add interview-prep patterns observed to my-data/lessons_learned.md (optional)
- Schedule a re-read of this prep 24 hours before the interview
```

**Anti-hallucination requirements:**
- **Don't fabricate defenses for claims the candidate hasn't confirmed.** Surface the gap.
- **Don't put words in the candidate's mouth on sensitive topics** (why leave, comp expectations). Draft starting points; the candidate refines.
- **Behavioral stories must be fact-registry-traced.** If a story isn't there, ask the candidate to provide it; don't invent.
- **The why-leave narrative must reflect the candidate's actual reasons**, not generic narratives - and must not contradict any active internal application.
- **Walk-away thresholds are the candidate's decisions**, not the prompt's.
- **Don't suggest the candidate misrepresent anything** in an interview, even when "everyone does it." That's career risk.

---

## Expected outputs
- Comprehensive interview prep package (7 sections)
- Open items list (defenses, scenarios, thresholds you must provide)
- Rehearsal recommendations

## Connection to other modules
- Reads: resume, cover letter, company research output, fact registry (my-data/fact_registry.json)
- Updates: fact registry as new confirmed claims emerge during prep
- New patterns -> my-data/lessons_learned.md (optional)
- Post-interview feedback -> your session notes in my-data/ for that target
