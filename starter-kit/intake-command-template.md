# Artifact intake protocol (template)

Save as a custom command (for Claude Code: `.claude/commands/intake.md`) or
run it as a checklist by hand. The trigger is any dropped artifact, a
spreadsheet, a document, a config, anything someone built that you want to
understand, improve, or repeat. The output is always two layers. The
instance gets filed with its owner, and the reusable template gets filed
where the next project finds it.

## Step 1. Read the artifact completely

Structure, every sheet or section, formulas, conventions, and the method
embedded in it. Verify any technical claims the artifact makes when they
are high-stakes. Surface errors and inconsistencies to the human, and never
silently fix someone else's work.

## Step 2. Framing interrogation (validate before building)

Ask the human, and get agreement before writing anything reusable. Skip a
question only by stating the assumed answer out loud.

1. Purpose and audience. Who consumes this, through which persona?
2. What good looks like. What made this artifact valuable, and what is
   wrong with it?
3. Reuse ambition. One-off, this client or family, or everywhere?
4. Owning domain. Where does the instance live, where does the template
   go, whose rules run on it?
5. Verification needs. What must be checked before anyone relies on it?
6. Sensitivities. Private data, pricing exposure, anything that must not
   leave the building.

## Step 3. File the instance

With its owner, file the artifact in its native format, a plain-text
snapshot beside it so it is diffable and reviewable, and instance notes
recording structure, findings, and verification status.

## Step 4. Build the reusable layer

In the owning domain's template location, leave a template spec covering
structure, formulas, method, design decisions, and what to adapt per use,
plus a grading rubric future instances are scored against.

## Step 5. Close out

Record the lesson in the learning loop, including the cross-domain inbox if
the lesson is system-level. Commit. The next "make one like this" should be
a one-line ask.
