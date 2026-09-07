# Rollout guide: stand up the foundation and your first workspace in one guided session

What you need. Claude Code installed and signed in, git installed, and a
new PRIVATE repository (a private GitHub repo is simplest; a local-only
repo works, you just skip the pushes). Nothing else. The prompts below
do the building; you make the decisions they ask you for. If you already
have a repository with work in it, read "If you already have a
repository" at the end of this guide before Step 1.

A rule before you start, because it is the one that makes everything else
work: you are the ratifier. The AI will propose; nothing becomes a rule of
your system until you say yes. If you keep only one habit from this guide,
keep that one.

## What this session builds, and what it does not

Built by the end of Step 5: a root instruction file that loads in every
session, a maintenance file with an empty catch register and a monthly
scorecard template, one workspace built from the nine-part skeleton, and
the intake command. That is the foundation and one domain of work, and
it completes the kit's governance loop for that domain. It does not
supply the controls this kit's README lists as out of scope (threat
modeling, secrets handling, access control, and the rest); those still
come from your environment.

Not built here, each with the trigger that makes it worth building:

- A second workspace, when a second domain of work arrives. The
  procedure is at the end of this guide; it is Prompt Two again.
- A layer above the workspaces (a shared board, registers that more than
  one domain writes to), when threads start crossing domains. The thesis
  describes it in its architecture section.
- A second machine. Claude Code's own memory is stored per machine and
  does not travel in a clone; only what you commit travels. Decide what
  stays local (memory, credentials) before you clone to a second computer.
- A second model, running the adversarial review protocol, on the day
  you want a review that does not share the author's blind spots.

Harness check. The three behaviors this guide relies on were checked
against the Claude Code documentation (the pages on memory files and on
skills at code.claude.com/docs) on 2026-09-06, with Claude Code 2.1.224
installed at the time; they were read from the documentation, not
exercised in a recorded run. They are: a CLAUDE.md at the repository
root loads at session start; a CLAUDE.md in a subfolder loads when the
AI reads files there; and a command you invoke by name is created either
by a file at .claude/commands/<name>.md or by a folder at
.claude/skills/<name>/ containing a SKILL.md. Re-check those three when
Claude Code changes how it loads instruction files, imports, or skills,
and update this paragraph.

## Step 1. Create the home

Make a private repository and open Claude Code inside it. Copy the three
template files from this kit (`skeleton-template.md`,
`workspace-loader-template.md`, `intake-command-template.md`) into a
`templates/` folder in your repo. The fourth template,
`adversarial-review-protocol.md`, joins later, on the day you add a
second model; the guided session below only needs the three.

## Step 2. Paste Prompt One, the foundation

```
Read the three files in templates/. You are helping me stand up a governed
AI operating system in this repository, modeled on the frame those
templates describe. First interview me, one question at a time: what
domains of work I want to run here (start with one or two), who I am, and
what my honesty non-negotiables are. Then create: (1) a root CLAUDE.md
that loads every session, carrying only the always-true rules - git is the
source of truth, commit every session and push whenever a remote is
configured unless I have told you that pushing needs my go each time,
validate the approach with me before building anything, present every open decision in a numbered
"Waiting on you" block at the end of your responses, never state a
vendor, version, price, or time-dependent fact from memory without live
verification, and when I correct an error, propose a catch-register row
and the standing rule that prevents the class; (2) a MAINTENANCE.md with an empty catch register (every
time I catch you in an error, it gets a row here paired with the standing
rule that prevents the class) and a five-number monthly scorecard
template. Show me both files before writing them. Nothing is final until
I approve the exact text.
```

## Step 3. Paste Prompt Two, your first workspace

```
Now stand up my first workspace using templates/skeleton-template.md as
the frame. Interview me one question at a time to fill in all nine parts
for this domain: the lenses to apply while building, the personas the work
is for, the grading rubric, the error controls, the learning loop and
where lessons get routed, the honest stated limit, the verification
gate with my high-stakes triggers, whether this domain runs enough
parallel threads to need a standing workboard, and which document classes
will repeat and need a class-level standard. Any part that genuinely does not apply
gets a named deviation with a reason, never silently skipped. Then create
the workspace folder with a thin loader built from
templates/workspace-loader-template.md, an index, the doctrine file, and a
State folder with a genesis entry. Show me everything before writing.
Commit when I approve, and push if a remote is configured.
```

## Step 4. Paste Prompt Three, the intake protocol

```
Install the artifact intake protocol from
templates/intake-command-template.md as a custom command in this
repository, adapted to my workspace names. From now on, when I drop any
file and ask you to make sense of it, run that protocol: read it fully,
interrogate the framing with me, file the instance with its owner, and
leave behind a reusable template. Confirm the command is installed and
show me how I trigger it.
```

In current Claude Code, custom commands and skills are one mechanism
with two supported formats: a single file at `.claude/commands/<name>.md`,
or a folder at `.claude/skills/<name>/` containing a `SKILL.md`. Either
creates a command you invoke by name. The AI should install in the
format its version documents.

## Step 5. Prove it works

Drop a file into a session and say "run intake on this." Use a file that
is safe to share with your AI provider: nothing confidential, regulated,
or credential-bearing, and check your own data-handling rules before
using real material. Catch the
AI in one mistake, any mistake, and watch whether it offers a standing
rule for the register. Ask it "what is in the decision queue" at the end
of a session. If all three behave, the loop is alive, and the system will
grow every time you correct it.

What good looks like after a month: your root file is still short, your
register has rows, your scorecard has its first honest numbers, and you
have said no to at least one of the AI's proposals. The no is how you know
the governance is real.

## When the second domain arrives

Paste Prompt Two again with "my first workspace" changed to "my next
workspace" and the new domain named. Keep the shape identical to the
first: a thin loader, an index, the doctrine file, a State folder. The
sameness is what keeps several workspaces navigable; the doctrine inside
each one is what keeps them distinct. The root file stays short. If it is
growing, something that belongs in a workspace has drifted up.

## If you already have a repository

The prompts above assume an empty repository. In one that already holds
working projects, run the session as an adaptation, not a build. Start
from a clean working tree on a disposable branch. Two rules bind from
here whether or not you paste the paragraph below: nothing is created,
copied, or changed in this repository until you have approved that path by
name, and nothing is pushed until you say so. Before copying anything,
check whether `templates/`, `CLAUDE.md`, or `MAINTENANCE.md` already
exist; if any does, decide now whether it is merged or the new material
goes under a different name, and do not overwrite it. Then, with your
approval, copy the same three template files from Step 1 into `templates/`
(or the folder name you chose). Paste this paragraph before Prompt One,
and again before Prompt Two:

```
This repository already contains working projects. Before creating
anything, inventory the tree, list every file or folder you would create
that already exists, and propose a merge for each. Change nothing until I
approve each path by name. Do not push until I say so, and in the root
instruction file make pushing require my explicit go each time, not
"whenever a remote is configured"; I will loosen that myself later if I
choose to.
```

Require the first pass to produce a proposal and no changes, and check
that yourself with `git status` and the diff before approving anything.
Approve each change to an existing file by name, then let the prompts
run. Existing projects are mapped onto the nine-part frame, not rebuilt.
When the session ends, run whatever checks your projects already had;
they should pass exactly as they did before.
