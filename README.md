# Operating an AI

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
to one seven-part frame. Every substantive answer passes a risk-tiered
verification gate, and high-stakes work gets the full adversarial stack.
Every substantive build opens with the plan and the criteria it will be
judged by, agreed before the work starts. Every open decision sits in a
queue until the human rules.

Every human correction becomes a standing mechanism, logged in a register
that pairs each catch with the rule it produced and exposes repeat
failures; a rule that fails twice as memory gets pushed down to the tool
layer as a mechanical guard that cannot forget. The register grew from 21
rows to 28 in the four days since first publication, and the newest row is
the first found by a routine machine pass in ordinary operation rather
than by the human.

And the whole thing grades itself on five numbers a month, starting from
an honestly embarrassing baseline; the first monthly reading comes due in
August 2026 and publishes either way. On day one, the human caught flaws
before the AI's own reviews did, twice. The system published that number
and built the machinery to invert it.

It recently proved itself on real work. Given a compliance tracker for a
second opinion, it verified every control weight against the official
government scoring source and found a defect affecting roughly one in six
controls, with the math to defend the fix.

## If I applied to a role with you, read this first

Here is the translation into hiring terms. This repository is a security
program applied to AI. Written doctrine and governance. Layered controls
of different kinds, designed so no single failure is silent. Separation of
duties, no implementer audits its own work. Measurable outcomes with honestly
embarrassing baselines published on purpose. A cross-vendor audit protocol.
Documented failure handling that turns every incident into a control. That
is the same discipline I have run in security operations and incident
response for nearly two decades, pointed at a new class of system. The
work it governs spans technical implementation, business frameworks, and
compliance execution, and the same gates are built to govern technical
design. If your role
involves adopting AI safely, building or running security programs, or
making operations measurable, this repository is a working sample, not a
claim.

## Read in this order

1. **[The thesis](thesis.md)**. The full argument. The architecture, the
   verification stack, the human's job, the measurement, what broke, and
   how it scales.
2. **[The examples](examples.md)**. One worked vignette per domain,
   fictionalized, real events.
3. **[The starter kit](starter-kit/)**. The seven-part skeleton, the
   workspace loader, and the intake protocol as reusable templates. MIT
   licensed. Take them.
4. **[The prior-art survey](prior-art-survey.md)**. Where this sits among
   published practice, every source verified live, credit where ideas were
   borrowed.

## The honest fine print

Examples use a demonstration environment. Parties are fictionalized,
identifying figures rounded, real events recorded privately, and the
package was red-teamed for re-identification by a cross-vendor auditor
with access to the private records; participants in real events may
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
published trends can be checked right here; the register, the audit
records, and the git history that back the other claims live in the
private repository, and they are available as a live walkthrough rather
than a download.

This page is the two minute rendition of the thesis, derived from version
2, 2026-07-16.

Jason Lopez
[linkedin.com/in/jaylpz](https://www.linkedin.com/in/jaylpz)
