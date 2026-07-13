# Rollout guide: stand the framework up in one guided session

What you need. Claude Code installed and signed in, git installed, and a
new PRIVATE repository (a private GitHub repo is simplest; a local-only
repo works, you just skip the pushes). Nothing else. The prompts below
do the building; you make the decisions they ask you for.

A rule before you start, because it is the one that makes everything else
work: you are the ratifier. The AI will propose; nothing becomes a rule of
your system until you say yes. If you keep only one habit from this guide,
keep that one.

## Step 1. Create the home

Make a private repository and open Claude Code inside it. Copy the three
template files from this kit (`skeleton-template.md`,
`workspace-loader-template.md`, `intake-command-template.md`) into a
`templates/` folder in your repo.

## Step 2. Paste Prompt One, the foundation

```
Read the three files in templates/. You are helping me stand up a governed
AI operating system in this repository, modeled on the frame those
templates describe. First interview me, one question at a time: what
domains of work I want to run here (start with one or two), who I am, and
what my honesty non-negotiables are. Then create: (1) a root CLAUDE.md
that loads every session, carrying only the always-true rules - git is the
source of truth, commit every session and push whenever a remote is
configured, validate the approach with
me before building anything, present every open decision in a numbered
"Waiting on you" block at the end of your responses, and never state a
vendor, version, price, or time-dependent fact from memory without live
verification; (2) a MAINTENANCE.md with an empty catch register (every
time I catch you in an error, it gets a row here paired with the standing
rule that prevents the class) and a five-number monthly scorecard
template. Show me both files before writing them. Nothing is final until
I approve the exact text.
```

## Step 3. Paste Prompt Two, your first workspace

```
Now stand up my first workspace using templates/skeleton-template.md as
the frame. Interview me one question at a time to fill in all seven parts
for this domain: the lenses to apply while building, the personas the work
is for, the grading rubric, the error controls, the learning loop and
where lessons get routed, the honest stated limit, and the verification
gate with my high-stakes triggers. Any part that genuinely does not apply
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

## Step 5. Prove it works

Drop any real file into a session and say "run intake on this." Catch the
AI in one mistake, any mistake, and watch whether it offers a standing
rule for the register. Ask it "what is in the decision queue" at the end
of a session. If all three behave, the loop is alive, and the system will
grow every time you correct it.

What good looks like after a month: your root file is still short, your
register has rows, your scorecard has its first honest numbers, and you
have said no to at least one of the AI's proposals. The no is how you know
the governance is real.
