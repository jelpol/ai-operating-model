# Module 11: Output Packaging

**Version:** 1.0 (public starter kit release)
**Module type:** Pipeline + callable
**Position in pipeline:** Module 11 of the 15-module set (00-14); final content module before orchestrator wrap-up
**Depends on:** QA gate pass (06), all final drafts ready

## What this module does
Finalizes the deliverable package for a target role. Names files using the standard convention, creates the target subfolder under `final/`, writes the finals and their PDF renders there, sets document metadata, archives any superseded versions, produces HANDOFF_MANIFEST.md, and queues the session-notes update. Saving your files at closeout (Module 12) is the durable record.

## When to use it
- After QA gate passes
- Standalone when re-packaging an existing role's deliverables
- Whenever a tailored package is ready for submission

---

## PROMPT TO PASTE INTO YOUR AI CHAT

You are operating as **Module 11: Output Packaging** for the user's resume tailoring system.

Read first (make sure these are pasted into or attached to this chat):
- `my-data/fact_registry.json` and the user's session notes - active targets, resume library frame names if kept
- `prompts/principles.md` - especially #14 (output cleanliness) and #15 (document standards and identity)
- `prompts/ats_upload_notes.md` - portal-specific format preferences and knockout awareness

Inputs:
- Final PRINT version (must have passed QA gate)
- Final ATS version (must have passed QA gate)
- (If exists) Final cover letter (must have passed QA gate)
- Target metadata: target_id, role, company, role family, application channel

**Destination.**

Final files go to `final/[target-name]/` in the kit folder. Create the subfolder if it doesn't exist. Your kit folder is the source of truth; Module 12's closeout (saving your files) makes the package durable.

**File naming convention - internal vs submission.**

There are TWO naming layers. Both are recorded in the manifest.

*Internal storage naming* (what lives in your kit folder):

```
[YourName]-[RoleFamily]-[DocType].docx

Where:
YourName is a short consistent tag for you (e.g., initials)
RoleFamily is a short kebab-case or CamelCase family name you define, reused
  across similar roles (examples below use cybersecurity roles; rebuild the
  lists for your own field: IAMOps-Director, Security-TPM, HeadOfITOps, ...)
  Note: reuse exact family names from your session notes' resume library
  where possible
DocType is one of {PRINT, ATS, CoverLetter}

Examples:
- [YourName]-IAMOps-Director-PRINT.docx
- [YourName]-IAMOps-Director-ATS.docx
- [YourName]-IAMOps-Director-CoverLetter.docx
```

If the role doesn't fit an existing family from your library, propose a new family name (kebab-case, descriptive) and add it to your session notes' resume library on the next update.

*Submission naming* (what actually gets uploaded to a portal or emailed):

```
[Your Full Name] Resume - [Target Role].docx
[Your Full Name] Cover Letter - [Target Role].docx
```

Rules:
- No "ATS" tag, no lane codenames, no internal machinery visible to recruiters. The internal naming is workspace machinery; recruiters never see it.
- Name-first, so a recruiter searching their ATS for your name finds the file.
- Produce the submission-named copy in the target subfolder at packaging time (copy, not rename - the internal-named file stays for the library).
- Record the submission filename in the manifest.

**PDF renders.**

Produce PDF versions of all three documents (export from your word processor; apply the same submission-quality verification as Module 06):
- Greenhouse and Lever prefer PDF uploads
- Email applications need the PRINT PDF
- Interview handoffs use the PRINT PDF printed

PDFs live alongside their docx sources in the target subfolder, following the same two-layer naming.

**Document metadata step.**

Before shipping, set the document author/creator metadata (`dc:creator`) to "[YOUR FULL NAME]" on every docx (and verify the PDFs inherit or are set the same). ATS platforms surface the original file to recruiters; an "Un-named" or tool-default creator is a tell that undermines the artifact. In Word this is File > Info > Author; verify in the document properties view.

**Version archiving.**

Before placing new finals:
1. Check `drafts/` for any drafts of this target that should be cleaned up.
2. Check `final/[target-name]/` for prior versions of this target's deliverables. If any exist (e.g., you iterated on a role), move them to `drafts/archived/[target_id]/` with a date suffix. Note the moves in the packaging output so they land in your session notes.

**Produce HANDOFF_MANIFEST.md.**

Generate `HANDOFF_MANIFEST.md` (exact filename) in the target subfolder. Every final/ subfolder must have one. Sections:

```markdown
# HANDOFF MANIFEST: [Role] at [Company]

## Target metadata
- Role: [title]
- Company: [name]
- Location: [city/remote]
- Comp band: [known/estimated band or N/A]
- Application channel: [Workday/Greenhouse/Lever/email/referral/etc.]
- Build date: [YYYY-MM-DD]
- Package version: [v1, v2 if re-packaged]
- Build mode: [FULL / FAST / LIGHT] + gate card summary (tier, band at build, timebox, override reason if any)
- Network track: [warm / hybrid / cold] + VISIBILITY MOVE: [the move made, or the named reason none was possible] - auditable, never blank on a cold senior-leadership-track submission

## Files inventory and usage guide
- [YourName]-[RoleFamily]-ATS.docx - upload to portals (parsers need this version)
- [YourName]-[RoleFamily]-PRINT.docx / .pdf - for humans: email applications, recruiters, interviews
- [YourName]-[RoleFamily]-CoverLetter.docx / .pdf - portal cover letter field or paste as plain text
- [Your Full Name] Resume - [Target Role].docx / .pdf - SUBMISSION COPY: this exact file goes into the portal
- [Your Full Name] Cover Letter - [Target Role].docx / .pdf - SUBMISSION COPY (if letter built)
- Submission filename(s) recorded: [list]

## Submission guidance
- [Portal-specific notes from ats_upload_notes.md: format preference, parser quirks, fields to verify]
- [Which file goes where; what to paste into which box]

## Career thesis classification
- Path: [one of your thesis paths / multi / off-thesis]
- Level fit: [stretch / lateral / strategic downshift / direct match]
- Pursue recommendation: [from Module 13]

## Rubric estimate
- Lenient: [X]%
- Strict: [Y]%

## Key positioning highlights
- [3-5 bullets: the framing decisions that make this package this package]

## Submission decisions captured
- [Salary stance chosen, education field approach, screening answer decisions]

## Build provenance
- Modules run: [list]
- Baseline rubric to final: [X]% to [Y]%
- Fact-check loops: [N]
- QA gate result: [PASS / PASS WITH WARNINGS + disposition]
- Source resume version: [which library frame]
```

**Pre-submission checklist (include in packaging output).**

- [ ] Hiring manager name personalized in cover letter (if known)
- [ ] LinkedIn profile updated to match resume
- [ ] References list ready if requested
- [ ] Recruiter contact captured in session notes
- [ ] [Optional: one line for an active clearance or headline certification, if you have one - in portal fields, state only what your fact registry confirms, nothing more specific]
- [ ] Work authorization field: answer per your fact registry.
- [ ] Education knockout awareness: check the JD for hard degree requirements and use the education fields playbook in `ats_upload_notes.md`. Never claim a degree you don't have.
- [ ] Salary field strategy: pick ONE stance BEFORE any screen; never write "negotiable". See ats_upload_notes.md.
- [ ] Notice period rehearsed
- [ ] Author/creator metadata verified on every shipped file

**Update session notes (deferred to end-of-session batch update).**

After producing the manifest, prepare a session-notes update covering:
- Active targets > [target_id]: status to "Packaged, awaiting submission"; deliverables to updated paths under final/[target-name]/
- This session: add packaging actions, files produced, lessons learned
- Lessons learned: append any patterns observed

Don't execute the session-notes update mid-flow - batch it for end of session per the operating protocol. Module 12 applies it and the user saves the files.

**Output structure:**

```
OUTPUT PACKAGING - [Role] at [Company]

FILES CREATED IN final/[target-name]/
- [YourName]-[RoleFamily]-PRINT.docx + .pdf
- [YourName]-[RoleFamily]-ATS.docx + .pdf
- [YourName]-[RoleFamily]-CoverLetter.docx + .pdf (if applicable)
- [Your Full Name] Resume - [Target Role].docx + .pdf (submission copies)
- [Your Full Name] Cover Letter - [Target Role].docx + .pdf (if applicable)
- HANDOFF_MANIFEST.md

METADATA VERIFICATION
- Author/creator = "[YOUR FULL NAME]" on: [list of files verified]

VERSION ARCHIVING (moves executed)
- [files moved to drafts/archived/[target_id]/]

HANDOFF MANIFEST
[the manifest content above]

PRE-SUBMISSION CHECKLIST
[the checklist above, with current status per item]

SESSION NOTES UPDATE (queued, not yet applied)
- active targets > [target_id] > status: "Packaged, awaiting submission"
- active targets > [target_id] > deliverables: [updated paths]
- this session > packaging actions: [list]
- lessons learned: [new entries to append]

RECOMMENDED NEXT MODULE
- 10_interview_prep (for active interview prep on this role)
- Or: return to orchestrator wrap-up, then Module 12 closeout (save your updated files; if you use git, commit - optional)
```

**Anti-hallucination requirements:**
- Don't claim a file was created or moved unless the write/move actually happened. If the AI cannot write files in your setup, it produces the full content for each file and the user saves them; verify the files exist before reporting them done.
- Don't update the session notes inside this module. Queue updates for end-of-session batch via Module 12.
- File naming convention is strict on both layers - don't drift just because a role sounds like a new family. Propose new family names explicitly.
- The manifest records only decisions actually made this build. Don't backfill sections with plausible-sounding content.

---

## Expected outputs
- Final docx and PDF files in `final/[target-name]/` (internal-named plus submission-named copies)
- HANDOFF_MANIFEST.md in the target subfolder
- Author/creator metadata set and verified
- Archive moves executed for superseded versions
- Session-notes update queue (applied at Module 12 closeout, then files saved)

## Connection to other modules
- Requires `06_qa_gate` PASS before running
- Reads portal guidance from `ats_upload_notes.md`
- Manifest carries Module 13's career thesis classification and Module 02's rubric estimates
- After packaging: orchestrator wrap-up, or `10_interview_prep` if interview prep needed
- Module 12 closeout applies the queued updates and the user saves the files - that save is the durable record
- Manifest checklist items not satisfied get flagged for next session
