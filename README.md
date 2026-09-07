# Operating an AI

**Lea esta documentación en español: [es/README.md](es/README.md)**

**I spent nearly two decades running security operations and incident response.
Now I run an AI the same way I ran security programs, as a governed
operation with written doctrine, layered verification, honest metrics, and
an audit trail, not a chat window.**

This repository is the public documentation of that system, built with
Claude and operated by a human who signs every rule.

The two minute version. The system runs six domains of work (a job search,
business consulting for managed services providers, service offering
design, technical advisory, device management, and this publication) from
one private repository, each domain under its own doctrine, all conforming
to one nine-part frame. Every substantive answer passes a risk-tiered
verification gate, and high-stakes work gets the full adversarial stack.
Every substantive build opens with the plan and the criteria it will be
judged by, agreed before the work starts. Every open decision sits in a
queue until the human rules. And more than one AI sits at the table: a
second vendor's model audits what the first one builds under a written
containment protocol, the passes run automated from the command line, a
routing table says which model gets which work, and a flip-outcome log
records what each pass caught so a pairing has to earn its cost.

Every human correction becomes a standing mechanism, logged in a register
that pairs each catch with the rule it produced and exposes repeat
failures; a rule that fails twice as memory gets pushed down to the tool
layer as a mechanical guard that cannot forget. Between first publication
and the version 2 revision, four days, the register grew from 21 rows to
28, and the newest row then was the first found by a routine machine pass
in ordinary operation rather than by the human. By early August the
register held 53 rows.

And the whole thing grades itself on five numbers a month, starting from
an honestly embarrassing baseline. The first monthly reading ran on
schedule in August 2026, unattended, and the readings it can
substantiate publicly published either way: the human still catches most
flaws first, and the thesis shows that number rather
than rounding it up to a success story, with the full board held in the
private scorecard until its trend can publish. On day one, the human caught
flaws before the AI's own reviews did, twice. The system published that
number and built the machinery to invert it, and it keeps publishing
until the trend obeys.

It recently earned its keep on real work. Given a compliance tracker for a
second opinion, it verified every control weight against the official
government scoring source and found a defect affecting roughly one in six
controls, with the math to defend the fix. One story is a data point,
not a warranty; the thesis carries the fuller record, failures included.

## If I applied to a role with you, read this first

I ran security operations and incident response for nearly two decades.
This repository is that discipline applied to an AI, and it is built to be
checked rather than believed. Four things to check, each with where to
look.

1. The rules are written and a human signs every one. The thesis, section
   2, shows the layered instruction files and the doctrine each domain runs
   under.
2. No implementer audits its own work, and scrutiny scales with risk. A
   second vendor's model reviews what the first one builds under a written
   [adversarial review protocol](starter-kit/adversarial-review-protocol.md);
   every substantive answer passes a risk-tiered gate and high-stakes work
   gets the full stack (thesis, section 4). The pass-by-pass records stay in
   the private repository and are available as a walkthrough.
3. Every correction becomes a control. Each catch gets a register row
   paired with the rule that prevents the class. The register is private;
   its growth is public: 21 rows at first publication, 53 by early August
   (thesis, section 9).
4. The numbers publish even when they embarrass. The first monthly
   scorecard reading went out in August 2026 with the human still catching
   most flaws first (thesis, section 7).

The frame is the same whether the deliverable is a tenant hardening
baseline, a pricing model, or a compliance tracker whose control weights it
checked against the official scoring source; what changes is the scrutiny,
which follows the risk (thesis, section 2). If your role involves adopting
or governing AI safely, building or running a security program, or making
operations measurable, this is a working sample. What it cannot show is
scale, the teams and incidents behind the two decades; that is on the
LinkedIn profile at the end of this page.

## Read in this order

1. **[The thesis](thesis.md)**. The full argument. The architecture, the
   verification stack, the human's job, the measurement, what broke, and
   how it scales.
2. **[The examples](examples.md)**. One worked vignette per domain,
   fictionalized, real events.
3. **[The starter kit](starter-kit/)**. The nine-part skeleton, the
   workspace loader, the intake protocol, and the cross-vendor
   adversarial review protocol as reusable templates, with a guided
   rollout that stands up the foundation and a first workspace in one
   session and says what comes after. MIT licensed. Take them.
4. **[The resume tailoring kit](resume-tailoring-kit/)**. The job-search
   domain exported whole: the fifteen-module tailoring pipeline, the fact
   registry that keeps the AI honest, and a guided first session, sanitized
   for anyone to run in a plain AI chat. MIT licensed. Take it.
5. **[The technical advisory kit](technical-advisory-kit/)**. The
   advisory domain exported whole: a research anchoring protocol that
   makes the gap list the deliverable, a six-dimension design verdict
   engine, and a session-wide verification gate, sanitized for anyone to
   run in a plain AI chat. MIT licensed. Take it.
6. **[The prior-art survey](prior-art-survey.md)**. Where this sits among
   published practice, every source verified live, credit where ideas were
   borrowed.

If you came to adopt the starter kit rather than to read: open
[starter-kit/rollout-guide.md](starter-kit/rollout-guide.md) first and run
it with your AI. The reading order above is for understanding the system;
the guide is for standing one up. This repository is documentation, not a
system, so opening it in Claude Code sets nothing up by itself.

## The honest fine print

Examples use a demonstration environment. Parties are fictionalized,
identifying figures rounded, real events recorded privately, and the
package was red-teamed for re-identification by a cross-vendor auditor
with access to the private records through version 2, with later
additions passing the staged review gates recorded in the thesis's
revision history; participants in real events may
recognize their own stories, and readers of the public material alone
should not be able to trace any example to a real person or organization.
Claims in
these documents are the author's judgment unless a source is cited; the
confidence-labeling discipline described applies to the system's working
answers. The writing is
CC BY 4.0, the templates are MIT. The system's own stated limit applies to
everything here. One model wearing all the hats is not independent review,
which is why the design leans on primary sources, human ratification, and
a cross-vendor audit protocol, and why the failures publish alongside the
wins. One more scope note: the prior-art survey, the starter kit, and the
published scorecard readings can be checked right here; the register, the audit
records, and the git history that back the other claims live in the
private repository, and they are available as a live walkthrough rather
than a download.

This page is the two minute rendition of the thesis, derived from version
4, 2026-08-02. La edición en español se traduce de esa misma versión;
comience en [es/README.md](es/README.md).

Jason Lopez
[linkedin.com/in/jaylpz](https://www.linkedin.com/in/jaylpz)
