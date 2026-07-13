# Workspace loader (template)

Save this as `CLAUDE.md` inside the workspace folder. It is deliberately
thin. It loads only when the AI touches this folder, pulls the full
doctrine in with imports, and states the rituals. Detail lives in the
imported files, never here, so the always-loaded global layer stays lean
and this loader keeps each domain self-contained.

```markdown
# <Workspace Name> loader

<One line: what this workspace is, and its everyday aliases.> Loads on
demand when the AI touches files in this folder. Version control is the
source of truth; canonical files are edited in place and history is the
record.

@WORKSPACE_INDEX.md
@<doctrine file, e.g. operating-model.md or principles.md>

## Session start
Read the index, then the newest State file by date. Reconcile with the
human before acting. "Has anything changed that the record does not
reflect?"

## <The workspace's operating loop>
<Two or three lines. The modes, the loop, or the pipeline this workspace
runs. Point at the doctrine file for detail.>

## Closeout
Update the State record. Route lessons per the learning loop, including
the cross-domain inbox for system-level lessons. Commit and push is the
durable record. A session that changes anything ends with both.
```

Companion files this loader expects are `WORKSPACE_INDEX.md` (the one-page
map covering purpose, layout, authoritative files, and ritual), the
doctrine file (built from the skeleton template), and a `State/` folder
holding dated records with the newest as current.
