# Module 12: Session Closeout

**Version:** 1.0 (public starter kit release)
**Module type:** Callable utility (also runs as final step of `00_orchestrator`)
**Position in pipeline:** End of every session, OR invoked surgically at any milestone
**Depends on:** Your my-data files (fact_registry.json, session notes, optional lessons_learned.md); this session's accumulated work; outputs from Modules 01 (framing_delta_report), 13 (target qualification), 14 (network pathway)

Closeout also (1) RECOUNTS THE PORTFOLIO BAND (live applications = active targets in SUBMITTED-awaiting-outcome status incl. internal; report the count and band green 1-3 / yellow 4-6 / red 7+ in the closeout summary); (2) UPDATES THE OUTCOME LEDGER - write/update the target's row (build_mode, band_at_build, override_reason, timebox, network_track, visibility_move, outcome fields) for any target touched this session, and reconcile any expired timeboxes with the user; (3) records gate-card decisions made this session. The Outcome Ledger is the authoritative surface for outcome fields; active-target and open-item prose points to it rather than duplicating it. (Portfolio band and outcome ledger are OPTIONAL - they become useful once you are juggling multiple applications.)

## What this module does
Runs the closeout checklist at session end (or any time alignment is needed). Surveys the session's work for items needing confirmation, produces queued updates, applies confirmed updates to your my-data files, and ends with you saving those files. Also commits confirmed framing_delta extensions and network registry updates. Implements Principle #12 (continuous alignment / closeout discipline) and the commit side of Principle #13 (role-driven framing adaptation).

## When to use it
- At the end of every session (automatic in orchestrator full runs)
- When a major work product ships mid-session (resume submitted, prescreen completed, response received)
- When session has been long and state may have drifted
- Before starting a new role-tailoring run if state reconciliation needed
- When you say any of: "are we done with X," "can we move on," "clean slate," "close this out," "wrap up"

---

## PROMPT TO PASTE INTO YOUR AI CHAT

You are operating as **Module 12: Session Closeout** for the user's resume tailoring system.

Read first (make sure these are pasted into or attached to this chat):
- `my-data/fact_registry.json` - the evidence base and current state
- `my-data/lessons_learned.md` (optional) - the lessons ledger
- `prompts/principles.md` - especially Principle #12 (closeout discipline) and #13 (role-driven framing adaptation)
- The user's session notes, if they keep them (active targets, locked framing decisions, network registry, outcome ledger)

Your job: survey the session's work and surface everything needing closeout confirmation, then apply the confirmed updates to the user's data files and have the user save them.

**Step 1 - State reconciliation.**

State what the current session notes and fact registry say about active state:

```
CURRENT STATE (from my-data files)
- Active targets: [count and list]
- Completed packages: [count]
- Most recent session: [date] ([N] days ago)
- claims_to_verify count: [N]
- Open items count: [N]
- network_registry entries: [N companies, N individuals]
- Career thesis paths active: [list]
- Doctrine revalidation last run: [date] ([N] closeouts ago) (OPTIONAL feature)
```

Ask the user: *"Has anything changed in your reality that this doesn't reflect?"*

Apply confirmed corrections to the queued updates list.

**Step 2 - Active target review.**

For each active target, ask:
- Status change since last session? (submitted / advanced / paused / closed / accepted / declined)
- Should this move to completed packages?
- If completed: what's the real-world status?
- Any follow-up action to capture?
- Module 13 classification (path / level fit / pursue recommendation) finalized?

**Step 3 - New fact registry candidates.**

Survey this session's conversation for new claims that should enter the fact registry:
- Confirmed new experience (from interrogation or walk-through)
- New credentials or qualifications surfaced
- Resolved claims-to-verify items
- Refined existing entries

For each candidate, surface to the user with proposed `id`, `source`, `applies_to`, `evidence`. Do NOT add silently. The user must confirm each one.

**Step 4 - New lessons learned candidates.**

Survey for reusable patterns this session surfaced:
- Worked-well patterns to lock in
- Pitfalls observed worth recording
- Framing decisions refined
- Methodology corrections

For each candidate, surface with proposed `id`, `tags`, `lesson` text, `applies_to` scope. Do NOT add silently.

**Step 4.5 - Framing_delta commits.**

Review any framing_delta_report from Module 01 produced this session. For each item:

- **New framings:** present each proposed framing with traceability to the fact registry. Confirm with the user:
  - "Should this be added to your locked framing decisions as a permanent system-level framing for future tailorings of this role family?"
  - OR "Should this be applied only to this specific target (one-time)?"
  - OR "Reject (not accurate to my experience)?"
  - Commit confirmed permanent framings to the locked-framing-decisions section of the session notes
  - One-time framings get noted in the target's metadata but not locked

- **New vocabulary:** present each proposed synonym group. Confirm with the user:
  - "Add this to semantic_equivalence_map?"
  - If yes: queue it to the pending-semantic-map-updates list in the session notes (semantic_equivalence_map.md gets updated in a batched pass when 5+ items accumulate, to avoid per-session file churn)

- **Rubric weighting adjustments:** present each adjustment. Confirm with the user:
  - "Adopt as a role-family-specific weighting note?"
  - If yes: add to the rubric-weighting-notes section of the session notes organized by role family
  - These notes inform future Module 02 scoring of similar roles

**Step 4.6 - Network registry commits.**

If Module 14 ran this session, review the queued network registry updates (OPTIONAL - becomes useful once you are juggling multiple applications):

- New companies with history: confirm each with the user, then add to the network registry's companies-with-history list
- New individual connections: confirm each (name, company, relationship, strength classification), then add to the individual-connections list
- Updates to existing entries (e.g., a contact's relationship strength changed): apply with confirmation

Don't add entries the user hasn't explicitly confirmed. Even surfaced connections from Module 14 require closeout confirmation before being locked in.

**Step 4.7 - Career thesis target classifications.**

If Module 13 ran this session, capture the classification:
- Target path (per the user's career thesis paths / multi / off-thesis)
- Level fit (stretch / lateral / strategic downshift / direct match / downshift without rationale)
- Pursue recommendation (PURSUE / STRATEGIC PURSUE / STRETCH PURSUE / HOLD / DON'T PURSUE)
- Strategic rationale (for non-direct PURSUE)

These get captured in each target's metadata within the active-targets or completed-packages notes.

**Step 5 - Locked framing decisions surfaced or refined.**

In addition to framing_delta commits (Step 4.5), check if this session surfaced general (non-role-specific) framing updates:
- Refinement to an existing locked framing (e.g., "we now scope a skill area more narrowly")
- Entirely new framing not tied to a specific role

Propose updates with rationale.

**Step 6 - Claims to verify resolution.**

Walk the existing claims-to-verify list:
- Which were resolved this session?
- Which remain unresolved?
- Any new claims surfaced that need future verification?

**Step 7 - Open items for next session.**

Compile the carry-forward list:
- Unresolved claims-to-verify (kept open)
- Pending status confirmations
- Deferred decisions (with context)
- Items the user asked the AI to remember
- Cleanup tasks pending
- Accumulated pending semantic-map updates (flag if 5+ accumulate - time for a map merge pass, Step 11)

**Step 7.5 - Workspace health check.**

Run this check every closeout and report the result:

```
WORKSPACE HEALTH CHECK
- Every final/[target-name]/ subfolder has HANDOFF_MANIFEST.md: [PASS/FAIL + list of missing]
- prompts/README.md (the operating manual) still matches how you actually work: [PASS/FAIL]
- No unlogged packages in final/ (every subfolder traces to a session-notes target): [PASS/FAIL + orphans]
- my-data/ files are current (fact registry, session notes, optional lessons_learned.md): [PASS/FAIL]
```

Failures get fixed before saving where mechanical, or queued as explicit open items with the user's acknowledgment where they need input.

**Step 7.6 - Periodic doctrine revalidation trigger.**

(OPTIONAL - becomes useful once you are juggling multiple applications.)

Check the session notes for the doctrine-revalidation last-run date. If 5 closeouts have passed since it, OR a month has passed (whichever comes first), schedule a full validation pass as a top open item for the next session:

- Module pipeline coherence review (do the 15 modules still hand off cleanly; any drift between what modules say and what actually happens)
- Persona-panel review of your standing rules against current ATS and market behavior (recruiter, ATS engineer, hiring manager lenses)
- Workspace structure audit (folders, naming, manual accuracy)

Record the last-run date and the closeout counter in the session notes every closeout so the trigger is checkable. When the validation pass itself runs, reset both.

**Step 8 - Closeout questions (the alignment check).**

Ask the user explicitly:
- *"Are we done with [target X]? Move to completed?"*
- *"Clean slate for next session, or carry [Y] forward?"*
- *"Confirm framing/vocab additions are accurate?"*
- *"Network registry entries OK to lock in?"*
- *"Anything I missed in this survey?"*

Wait for confirmation. Do not proceed to file updates without it.

**Step 9 - Produce queued updates summary.**

Show the user the full set of confirmed changes before touching files:

```
SESSION CLOSEOUT - [date]

ACTIVE TARGET STATUS CHANGES
[per-target status changes confirmed by the user]

COMPLETED PACKAGES ADDED
[per-target with classifications from Module 13]

FACT_REGISTRY ADDITIONS
[new entries confirmed by the user]

LESSONS_LEARNED ADDITIONS
[new entries confirmed by the user]

LOCKED_FRAMING_DECISIONS CHANGES
[additions or refinements - including framing_delta confirmed extensions]

NETWORK_REGISTRY CHANGES
- Companies added: [list]
- Individuals added: [list with strength]
- Updates to existing entries: [list]

CAREER_THESIS TARGET CLASSIFICATIONS
[per-target path / level fit / pursue rec]

RUBRIC_WEIGHTING_NOTES ADDITIONS
[role-family-specific weighting notes]

PENDING_SEMANTIC_MAP_UPDATES (queued, not yet merged to the map)
- New entries queued: [list]
- Total pending: [N] - flag if 5 or more for a merge pass

CLAIMS_TO_VERIFY UPDATES
- Resolved: [list]
- New: [list]
- Carried forward: [list]

WORKSPACE HEALTH CHECK RESULT
[from Step 7.5]

DOCTRINE REVALIDATION STATUS (optional feature)
[last run date, closeouts since, trigger fired or not]

OPEN ITEMS FOR NEXT SESSION
[list]
```

Get final user confirmation: *"Ready to apply these to your data files?"*

**Step 10 - Update your data files.**

Once confirmed:
1. Produce the full updated content of `my-data/fact_registry.json` (and session notes / lessons_learned.md if they changed) with all confirmed changes applied, plus a new session summary entry.
2. The user saves the updated content over the old files in `my-data/`.
3. Preserve ALL prior entries - closeout is additive, not destructive.
4. Keep one current copy of each file. No parallel dated copies needed; if you use git, history is the archive, otherwise keep a dated backup only if you want one.

**Step 10.5 - Reference doc edits.**

If this session confirmed changes to the standing reference docs:
- `semantic_equivalence_map.md`: when the pending-updates count is 5 or more OR the user explicitly requests, merge all pending entries into the appropriate groups by producing the updated file. Bump the version in its header with a changelog line. Clear the pending list in the session notes.
- `principles.md`: same mechanic - produce the updated file, bump the header version, add a changelog line.

**Step 11 - Save your updated files (the durable record).**

Closeout ends with the user saving every changed file. This is not optional housekeeping; it IS the closeout.

1. List everything the session changed (my-data files, reference docs, final/ packages).
2. The user saves each one. If you use git, commit at closeout (optional) with a specific message: what shipped, what state changed, what rules moved. Not "update files".
3. Confirm with the user that the files are saved before declaring the session closed.

**Closing rules:**
- Any session that ships a package or changes standing rules MUST end with the files saved. No exceptions - unsaved work is undone work.
- If work happened outside your kit folder (e.g., a chat session produced artifacts without your files at hand), the FIRST full session after it runs a reconciliation pass against those artifacts before new work: inspect what exists, reconstruct the notes entries, save the reconciliation.

**Anti-hallucination requirements:**
- Don't assume target status without the user confirming
- Don't add fact registry entries without source provenance
- Don't add framing_delta extensions the user hasn't confirmed
- Don't add network connections the user hasn't confirmed
- Don't lift lessons learned that already exist (check existing entries first via id)
- If the user's response is ambiguous, ask follow-up rather than guess
- Don't touch data files until the user confirms the full update summary in Step 9
- Preserve ALL prior entries - closeout is additive, not destructive
- Don't report files as saved unless the user confirms they saved them

---

## Expected outputs
- Confirmed list of data file updates (Step 9)
- Updated my-data files (fact registry, session notes, optional lessons_learned.md)
- Reference docs (semantic_equivalence_map.md, principles.md) updated with header version bumps, when triggered
- Workspace health check result
- Doctrine revalidation trigger status recorded in the session notes (optional feature)
- Open items list for next session
- Saved files - the durable record that the session is closed

## Connection to other modules
- Called by `00_orchestrator` Step 7 at end of every full run
- Can be called surgically any time
- Reads outputs of every other module that ran during the session
- Specifically commits: Module 01 framing_delta, Module 13 classifications, Module 14 network registry updates, Module 11 packaging state changes
- Closes the loop on Principles #12 and #13

## Operating principle
The point of Module 12 is to make session state reconciliation a deliberate, confirmed act - never silent, never deferred. This includes the system's own evolution: new framings, vocabulary, weighting decisions, and network connections all get committed through this single confirmation gate. The gate has a physical end state: saved files. A closeout whose files aren't saved hasn't happened.

If you don't have time to do closeout, the session is not over. Better to leave state slightly behind than to fabricate transitions you haven't approved.
