# The system at work: the domains, and the moments that tested them

Companion to "Operating an AI." Jason Lopez. Version 3, 2026-08-02,
derived from thesis version 4. The structure is six domain vignettes,
one per domain of work, carried forward from version 2 with privacy
phrasing tightened, followed by three case studies from the recent
record that cut across domains.

Same convention as the thesis. These are real, recorded events presented as
a demonstration environment. Parties are fictionalized, identifying figures
are rounded, and machine and product names are blurred where they could
identify anyone or anything but me. The set was red-teamed for
re-identification by a cross-vendor auditor with access to the private
records through version 2, and later additions passed the staged review
gates recorded in the thesis's revision history; the honest residual is
that people who participated in the
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

The monthly billing run shows the same discipline from another angle.
Rates live in a configuration with two declared sides, what the engineers
cost and what the customers are billed, and every rate carries a status,
actual or needed. A needed rate is never invented. It renders as a flagged
cell and a numbered question, and each answer is recorded with who gave it
and when, so the same question never has to be asked twice and the
question list shrinks month over month. Asking the human is a designed
workflow here, not a failure mode. And when I asked whether the math was
right, the system did not re-read its own workbook. It recomputed every
figure from the raw source data with the rules applied from scratch,
scanned for duplicate entries, and only then said yes, with the remaining
risks named, including the one thing no recomputation can see, hours that
were never logged at all.

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
first. Keeping it all true is the check's job now, run when a machine
next works, rather than a memory task, with the honest limit that a
machine nobody opens is a machine nobody has checked.

The newest control in this domain was not born here. A rule about keeping
each change set scoped to its own work failed twice as a remembered rule,
so it was rebuilt as a pre-execution hook that mechanically blocks the
risky command class before it runs, and the canonical copy lives in the
device standard, so every machine inherits the guard the same way it
inherits the settings file. A control that graduated from memory to
machinery is exactly what this workspace exists to distribute.

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
machinery that does not care that it is describing itself, and the
revision you are reading walked back through that same gate.

## The commitment that never existed

A live incident at a client. A team member summarized the state of play
for a stakeholder update, including the line that the team would
continue reviewing activity across other systems, a plan. The
AI drafted the outbound message and the plan came out as "we are also
checking your other systems," work in progress. No chat, no
ticket, and no message said that work existed. The human caught it with a
single question, are we actually doing that, and the fix took a minute.
The mechanism took only a few more. Every statement that commits the team
to an action now has to trace to a recorded commitment, a chat, a ticket,
a message, or the human's own direction. No source, and the line moves out
of the draft into a labeled suggestion list. Planned actions stay in
planned tense. The lesson is that an AI drafting on a team's behalf can
invent obligations as easily as facts, with an edit as small as will to
are, and the rule landed in doctrine the same session, in the middle of
the work it came from.

## Two AIs argue until they agree

An overnight engineering build needed to ship with confidence, and the
directive was one line: make sure the two models agree. The author model
and a second vendor's auditor ran five adversarial rounds, each round
re-verifying the previous round's fixes with exact quotes from the
current files, the finding count allowed to move down only when a fix was
verifiably real. Round by round the count fell, and the discipline caught
two failures a single model would have missed. Two fixes had been
"applied" by scripts whose text match had drifted, so nothing actually
changed while the drafts claimed it had; the auditor's re-verification
exposed both, and every patch since asserts its match or fails loudly.
The auditor also corrected the implementer's own bookkeeping,
twenty-three findings where the implementer counted twenty-one. The
exchange ended in a written agreed verdict, and the false patch claims
stayed in the provenance record instead of being reworded away. Trust
came out of the arguing, which is what the arguing is for.

## The operating model leaves home

A team in the demonstration environment stood up an internal
documentation assistant, a shared AI workspace over a knowledge base,
and expected it to learn from use. Tools like that do not learn from
use. What they have is levers, and the levers are exactly the ones this
system runs on.
In a single working session, the personal operating model scaled down
into a starter
kit for the team tool: project instructions playing the role doctrine
plays here, answer only from the documentation, cite the source and its
date, refuse to guess, never emit credentials, state coverage honestly; a
context file playing the role of the reference layer, the shorthand, the
tool stack, where the documentation lives; and a gap log with a periodic
harvest playing the role of the catch register, every miss becoming a
fixed document or an instructions tweak with a dated change log. A
one-page rebuild note took the rebuild out of one person's head. The
point is that context
engineering transfers. The same discipline that runs one person's system,
curate what the model knows, build the loop that captures what it misses,
version the instructions like doctrine, stands up a team-facing assistant
in an afternoon, and guards against the same failure it guards against
at home, trusting ambient learning instead of built mechanisms.

## The thread through all of it

Every one of these domains, including the workspace this document stages
in, now conforms to the same nine-part skeleton described in the thesis,
one born from it and the rest assessed against it with the found gaps
closed and deviations named, and every one of
these examples is the same pattern wearing different clothes.
Write the rule down where it loads. Verify against a source, not a memory.
Let machinery hunt for drift. And when the human catches something anyway,
turn the catch into a mechanism.
