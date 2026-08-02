# Starter kit

Reusable, sanitized templates from the operating model described in the
thesis. Take them, adapt them, keep the honesty rules intact. The
templates are MIT; the rollout guide's prose, like the other written
works in this repository, is CC BY 4.0. Templates current as of thesis
version 4, 2026-08-02.

Contents.

- `rollout-guide.md`. Start here. Step-by-step instructions and three
  copy-paste prompts that stand the whole framework up in one guided
  session.
- `skeleton-template.md`. The nine-part frame every workspace is built
  from. Start any new AI-managed domain of work by filling this in.
- `workspace-loader-template.md`. The thin on-demand loader file that
  makes a workspace self-loading without bloating the always-on context.
- `intake-command-template.md`. The artifact intake protocol. Drop any
  file, reverse-engineer it, interrogate the framing, and leave behind both
  an instance and a reusable template.
- `adversarial-review-protocol.md`. The cross-vendor review protocol,
  model-agnostic: author-auditor separation, a contained exchange, rounds
  that verify each other's fixes, and a decision menu that keeps the human
  in charge.

Two concepts these templates reference without providing, because they are
one-per-system rather than one-per-workspace. The always-loaded global
layer (the thin root instruction file) and the cross-domain lesson inbox
are both described in the thesis, the global layer in its architecture
section and lesson routing in its skeleton section; build yours once and
every workspace shares them.

Scope, stated plainly. The templates as delivered target Claude Code,
which supplies folder-triggered context loading, file imports, and custom
commands; porting to another harness needs equivalents of those three.
And the skeleton governs how AI work is produced and verified. It does not
supply threat modeling, data classification, secrets handling, access
control, incident response, backup testing, retention and deletion rules,
prompt-injection boundaries, rollback, control ownership, exception expiry,
evidence standards, or automated enforcement; bring your own, or run the
system inside an environment that already has them.

None of these contain anything from the private repository beyond
structure. Fill them with your own doctrine. The frame is the gift, the
content is yours.
