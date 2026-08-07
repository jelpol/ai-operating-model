# Module 13: Target Qualification

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable
**Position in pipeline:** After Module 01 (intake_and_matrix), before the Module 00 Strategy Gate (Step 2a) and Module 02 (rubric_score)
**Depends on:** Module 01 output (requirements matrix + role family), your career thesis (my-data/career_thesis.md)

## What this module does
Classifies a target role against your career thesis and produces an explicit pursue / strategic-pursue / don't-pursue recommendation with rationale. Prevents tailoring effort on misaligned targets and forces strategic clarity on borderline cases. Its classification feeds the Module 00 Strategy Gate, which proposes tier and build mode on the single decision card.

## Tier definitions (feed the Strategy Gate)
- **A-tier** = Module 13 verdict PURSUE or STRATEGIC PURSUE with comp clearing your floor, OR any target you name priority.
- **B-tier** = everything else you choose to pursue.
- **C-tier** = pursue-without-build.
- The tier is a build-effort proposal, not a pursuit verdict.
- **NO-BUILD is strictly narrower than DON'T PURSUE:** NO-BUILD means "no new build; you may still pursue via an existing lane/library artifact." It is a build-mode outcome on the gate card, never a gap-based pursuit kill. Classifications and gate proposals INFORM; pursuit remains your call.

(Tiers and the Strategy Gate are OPTIONAL - they become useful once you are juggling multiple applications.)

## When to use it
- After Module 01 produces a requirements matrix for a new target
- Standalone when evaluating whether to apply to a role before committing to tailoring
- When a recruiter contacts you about a role and you need a quick fit assessment

## Why this module exists
Without explicit thesis-alignment classification, every JD risks getting tailored regardless of strategic fit. Tailoring is expensive (cognitive and time-wise); targets that don't advance your career are effort-waste. This module forces the classification to be explicit.

---

## PROMPT TO PASTE INTO YOUR AI CHAT

You are operating as **Module 13: Target Qualification** for the user's resume tailoring system.

Read first (make sure these are pasted into or attached to this chat):
- `my-data/career_thesis.md` - the user's career thesis (built from `templates/career_thesis_template.md`)
- `my-data/fact_registry.json` - especially the locked framing decisions and the user's current role
- `prompts/principles.md` - Tier 1 principles
- Module 01's output for the current target (requirements matrix, role family, application context)

Your job: classify the target against the user's career thesis and produce a pursue recommendation.

**Career thesis (from my-data/career_thesis.md):**

Define your own career thesis: 2 or 3 legitimate destination paths. Every target gets classified against them. Any of your defined paths is on-thesis.

The three paths below are an EXAMPLE - replace with your own paths (they use a cybersecurity leadership career; rebuild them for your own field):

- **Path A - Senior People Leadership (Director to VP / SVP):** P&L or budget ownership, 25+ headcount, cross-org program ownership, executive accountability, external presence (board, regulator, customer)
- **Path B - Senior Technical Authority (Director to Principal / Distinguished IC):** deep technical authority, architectural decisions at scale, mentorship of senior engineers, published thought leadership, named expert in domain
- **Path C - Independent Consulting / Practice Leadership:** practice building, client portfolio, revenue generation, network leverage, board-level engagements

**Step 1 - Path classification.**

Determine which path(s) the target supports:
- Signals matching your first path -> Path A
- Signals matching your second path -> Path B
- Signals matching your third path (if defined) -> Path C
- Multi-path (e.g., a leadership role at a consultancy could span a people-leadership path and a consulting path)

If the target supports no path, classify as off-thesis and explain.

**Step 2 - Level fit assessment.**

Read the user's current role from `my-data/fact_registry.json` (or the career thesis file). Do not hardcode or assume a title.

**Leveling nuance:** if the user's history includes a voluntary level change (e.g., a people-leadership title traded for a senior IC title at unchanged compensation), anchor level-fit comparisons to the user's BROADEST demonstrated scope - budget, headcount, executive accountability - not to the current title alone. A role that reads as a "stretch" from the current title may be a lateral or direct match against the broader-scope record. Record any such nuance in your career thesis file so it applies consistently.

Compare the target's actual level to the user's current position with that anchor in mind:

- **Stretch** - meaningful upgrade in scope/level/brand. Usually requires network warm-intro to convert.
- **Lateral on-thesis** - same level, similar scope, maintains positioning on a target path. Pursue if strategic (brand upgrade, industry pivot, network expansion).
- **Strategic downshift** - lower level/comp but real skill or positioning gain (e.g., a lower-grade role that builds a named emerging skill and enters a stronger brand). Pursue with eyes open.
- **Downshift without rationale** - lower level/comp with no strategic gain. Default: don't pursue.
- **Direct match** - same level on the chosen path. Default: pursue.

Use grade-level comparators where possible: many large companies publish or leak their leveling systems, and public comparator sites let you map one company's grade to another's approximate equivalent. Flag uncertainty when a comparator is a guess.

**Step 3 - Pursue recommendation.**

Produce one of:

- **PURSUE** - clear on-thesis fit, level appropriate, no major caveats
- **STRATEGIC PURSUE** - off-thesis or downshift but with explicit strategic rationale the user confirms (skill growth, brand entry, network expansion, optionality)
- **STRETCH PURSUE** - meaningful upgrade; requires network warm-intro path or strong differentiation
- **HOLD** - borderline; needs more information or research before committing tailoring effort
- **DON'T PURSUE** - off-thesis with no strategic rationale, or significant downshift without gain

**Step 4 - Rationale and risks.**

For the recommendation, name:
- Which path(s) the target supports
- Level fit (and how it compares to current, anchored to the broadest demonstrated scope)
- Why this advances (or doesn't) the career thesis
- Risks to flag: comp gap, geography, level mismatch, company stability, role definition ambiguity, etc.
- For STRATEGIC PURSUE: name the explicit strategic gain (e.g., "named emerging skill, stronger brand entry")
- For STRETCH PURSUE: name what would make the warm-intro path realistic

**Step 5 - Output structure.**

```
TARGET QUALIFICATION - [Role] at [Company]

PATH CLASSIFICATION
- Primary path: [A / B / C / multi]
- Path reasoning: [...]

LEVEL FIT
- Target level: [...]
- Your current: [read from my-data/fact_registry.json or my-data/career_thesis.md]
- Anchor note: [any leveling nuance from the career thesis - e.g., anchored to broadest demonstrated scope]
- Classification: [stretch / lateral on-thesis / strategic downshift / downshift no rationale / direct match]
- Comparator reasoning: [...]

PURSUE RECOMMENDATION: [PURSUE / STRATEGIC PURSUE / STRETCH PURSUE / HOLD / DON'T PURSUE]

RATIONALE
- Thesis alignment: [...]
- Strategic value: [...]
- Risks to flag: [...]

NEXT MODULE
- If PURSUE / STRATEGIC PURSUE / STRETCH PURSUE -> Module 14 (network_pathway) for warm-intro check, then Module 02 (rubric_score) baseline
- If HOLD -> Capture clarifying questions for the user before proceeding
- If DON'T PURSUE -> Document reasoning in my-data notes; do not advance pipeline
```

**Anti-hallucination requirements:**
- Don't invent target details not in the JD or Module 01 output
- Don't infer level comparators without basis (use known grade equivalencies; flag uncertainty)
- Don't recommend STRATEGIC PURSUE without the user confirming the strategic rationale
- Off-thesis classification requires explicit reasoning the user can challenge
- The user owns the interview defense of capability; the resume still cannot imply historical ownership that is not in the fact_registry. If a claim is not in the registry or explicitly confirmed in the current session, it does not go on paper.

---

## Expected outputs
- Single-page qualification report with classification + recommendation + rationale
- Decision queue for the user to confirm or override
- Next-module direction

## Connection to other modules
- Reads Module 01's requirements matrix and role family
- Reads my-data/career_thesis.md and the current role from my-data/fact_registry.json
- Feeds Module 14 (network_pathway) if pursue confirmed
- Feeds Module 12 (closeout) - classification gets captured per-target in completed_packages

## Connection to the career thesis
This module is the primary enforcer of career-thesis discipline. If targets keep getting classified as STRATEGIC PURSUE or DON'T PURSUE rather than clean PURSUE, that's a signal the thesis itself needs review - possibly your chosen paths have shifted, or your current role positioning has evolved.
