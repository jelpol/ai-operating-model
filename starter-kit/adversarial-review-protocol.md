# Adversarial review protocol (template)

A second AI's value is highest when it is allowed to attack and forbidden
to govern. This template is model-agnostic: it assumes only that you have
an author model and an auditor model from different vendors, each
reachable in some scriptable form (a CLI, an API, or at worst a
disciplined copy-paste). The separation is the control; the tooling is
convenience.

## The eight rules

1. **One exchange folder.** The entire review lives in one dedicated
   working folder. Every other file in your repository is read-only
   input for the exchange, cited but never edited by it.
2. **Disclosure is a decision.** What the outside model may read is
   ruled explicitly by the human, per engagement, never a default.
   Client-bearing or personal material enters an exchange only by named
   decision, on the record.
3. **Different vendors, different chairs.** The model that authored the
   work never audits it. When changes are ratified, one model implements
   and the other audits the diffs against exactly what was agreed.
4. **Rounds are capped and sequential.** A debate that can grind forever
   will erode protections through repetition. Set the cap before round
   one (three to five is typical). Two round types have opposite success
   conditions, and confusing them breaks the protocol: a finding round
   that comes back empty early in the exchange is suspect, record it and
   treat it as a shallow read rather than a clean bill; a verification
   round that confirms every prior fix present by exact quote and
   raises nothing new is the
   success condition that ends the exchange.
5. **Fixes are verified with exact quotes.** Each round re-verifies the
   previous round's fixes by quoting the current file, and the finding
   count only moves down when a fix is verifiably present. A patch that
   cannot show its own text in the file did not happen; record the false
   claim in the provenance rather than rewording it away.
6. **No convergence may weaken a protection.** A midpoint between two
   models that loosens an honesty rule or the human's authority is not
   convergence, it is erosion. Protections only strengthen through an
   exchange.
7. **Output is a decision menu.** The exchange produces findings and
   options for the human to rule on. Nothing in it self-executes, and
   nothing becomes a rule of your system without the human's explicit
   ratification.
8. **Provenance is kept.** Every round's prompt and response is
   persisted in the exchange folder. The record of who found what, who
   fixed what, and who verified it IS the deliverable's audit trail.

## The run, step by step

1. Freeze the artifact set under review and list the files in scope.
2. Write the auditor's brief: the artifact list, the claims the work
   makes, and the instruction to refute, not to summarize. Name the
   finding format (file, quote, why it is wrong, severity).
3. Run the auditor round. Persist prompt and response in the exchange
   folder.
4. Triage findings with the human: accept, dispute with evidence, or
   rule out of scope. Disputes carry the evidence, not just the
   disagreement.
5. Implement accepted fixes (author model), then run the next auditor
   round to verify each fix by exact quote, plus hunt for new findings.
6. Repeat within the round cap until a clean verification round, then
   record the verdict: agreed, or not agreed with the residuals named.
7. Log what the auditor caught that the author missed. A pairing that
   catches nothing across cycles gets demoted; one that earns its cost
   becomes your default for that work class.

## Keeping a flip-outcome log

One table, append-only: date, work, author model, auditor model, what
the auditor uniquely caught. This is the evidence that decides which
model gets which chair for which work, and it is the honest answer to
"is the second model worth it" that no vendor page will give you.
