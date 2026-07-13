# The system at work: one example per domain

Companion to "Operating an AI." Jason Lopez. Version 1, 2026-07-12.

Same convention as the thesis. These are real, recorded events presented as
a demonstration environment. Parties are fictionalized, identifying figures
are rounded, and machine and product names are blurred where they could
identify anyone or anything but me. The set was red-teamed for
re-identification by a cross-vendor auditor with access to the private
records; the honest residual is that people who participated in the
underlying events may recognize their own stories, and readers of this
public material alone should not be able to trace any example to a real
person or organization. The underlying records live in the private
repository with
dates and commits attached.

## The job search workspace

This is the strictest domain in the system. Every claim destined for a
resume must trace to a fact registry entry with provenance, meaning a
record of when I confirmed it and in what words. When the AI drafts a
bullet using language I have not confirmed, the claim gets flagged and
surfaced, never silently shipped and never silently dropped. Locked framing
decisions, the agreed honest wording for sensitive scope, can be added to
but never loosened. And a finished package cannot ship until a multi-pass
check renders the actual PDF, extracts the text back out, and proves the
formatting and the content both survived. The lesson that built all this is
simple. A resume that cannot survive cross-examination is worse than no
resume.

## The chief of staff workspace

The AI runs a living tracker of open business items for the consulting
work, reconciled each session against the business's live systems. The best example of the discipline is
a failure it caught in its own files. An always-loaded instruction still
described an event as the active top priority nearly two weeks after the
event had happened and closed. A context-isolated audit agent caught it, because the
rule here is that current-state files are never allowed to carry history,
and history is never allowed to impersonate current state. The fix took a
minute. The point is that something was hunting for the problem.

## The offerings workspace

Pricing and scoping work runs on a ledger where every figure that drives a
decision records its value, its date, its source, and whether it is an
actual or an estimate. The standing rule is that an estimate never appears
in anything client-facing dressed up as a validated number. Before any
document leaves the building it passes a pre-flight check, and if any input
is still an estimate, the document stays internal until the real number
exists. A number has a date and a source, or it does not ship.

## The advisor workspace

Technical questions pass through a tiered gate before the answer reaches
me. A cheap factual lookup needs one authoritative source and a confidence
label. Anything that is a judgment call, touches production, or carries
security weight gets a second adversarial pass whose only job is to refute
the draft. A calibration registry tracks which domains I am expert in,
where the AI validates at peer level and never explains fundamentals, and
which I am deliberately learning, where it teaches. The same question gets
a different answer shape depending on who is asking, and the system knows
who I am.

## The device workspace

A canonical settings file and a tool manifest define what every machine I
work from must look like. When one machine fell behind the standard, an
audit stamped its record as behind and predicted what would be missing,
including a stub that masquerades as a real runtime. The next session on
that machine ran the check, found the predicted gaps, installed the tools
with my approval, synced the settings, and replaced the stamp with a dated
record. The recorded machines were reconciled to the same declared
standard, and any new device is intended to walk the same check to the
same declared state, however many there are, because the standard is
written for the fleet and not for the devices that happened to exist
first. No human memory is involved in keeping any of it true.

## The publication workspace

The workspace this very document stages in runs the same rules on itself,
and its best example is a near miss. A heavily revised draft of the public
thesis once slipped toward approval without fresh review, because the
review gate had no rule for re-running after edits. The human caught it and
asked the obvious question, and the answer became mechanism within the
hour. A materially edited draft is a new draft, and no draft reaches the
human without a context-isolated cold-read panel. That panel has since caught a
count error, a metric inconsistency, and a privacy soft spot before any of
them reached the public. The document you are reading was audited by
machinery that does not care that it is describing itself.

## The thread through all six

Every one of these domains, including the workspace this document stages
in, now conforms to the same seven-part skeleton described in the thesis,
one born from it and the rest assessed against it with the found gaps
closed and deviations named, and every one of
these examples is the same pattern wearing different clothes.
Write the rule down where it loads. Verify against a source, not a memory.
Let machinery hunt for drift. And when the human catches something anyway,
turn the catch into a mechanism.
