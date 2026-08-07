# Learning Artifact Template

Copy into each new file in `my-data/learnings/` or `my-data/validations/`. The front-matter keeps a flat folder searchable and makes each artifact's lifecycle legible.

```yaml
---
title:        # human-readable
type:         # explanation | reference  (learnings only; explanation is durable, reference expires)
domain:       # e.g., identity, detection-eng, ai-ml, networking
tags:         # [free, tags, for, retrieval]
date:         # YYYY-MM-DD created
updated:      # YYYY-MM-DD last edited in place
confidence:   # established-fact | consensus-best-practice | judgment-call
sources:      # [urls / docs verified against]
expires:      # YYYY-MM-DD  (reference types and vendor-fact validations only; omit for durable explanation)
---
```

Body for a Module 01 (research anchoring) artifact - five sections:

1. Framework mapping
2. Framework gap analysis
3. My gap read (owned / adjacent-new / new, with drill order and checks)
4. Leverage read
5. Linking pass ([[wikilinks]] to related artifacts, both directions)

Body for a Module 02 (validation) artifact:

1. Verdict (Sound / Sound with caveats / Flawed)
2. Six-dimension findings table
3. Caveats or required fixes
4. Expiry note if the verdict rests on vendor or version facts

Versioning: edit artifacts in place and let git history (or a dated change line inside the file) record what was believed when. No dated sibling copies. A [[wikilink]] to a file that does not exist yet is a fine to-do marker.
