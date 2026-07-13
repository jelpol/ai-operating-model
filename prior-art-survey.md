# Prior-art survey - 2026-07-12

Run under this project's research rules: live web search, every source a
URL the researcher actually saw, borrowed ideas credited. Condensed
findings; the thesis's prior-art section, "Where this sits among what is
already public," derives from this file.

Method note (added after the round 1 outside audit; scope tightened after
round 2). This is a bounded, structured scan, not a systematic or
reproducible survey: the original search queries were not preserved, so
the record below is the sources reviewed and the judgments made, bounded
to this date. Searches ran on 2026-07-12 via general web search across
several angles: public GitHub
repositories sharing Claude Code setups and curated "awesome" lists,
practitioner "how I work with AI" write-ups, and the named-concept
literature (context engineering, LLM-as-judge, AI maturity models, golden
paths, context rot). Selection was the researcher's judgment of the most
relevant results per angle, not an exhaustive census, and no negative claim
in this file extends beyond these searches on this date. Comparative labels
such as widely referenced are descriptive impressions from the search
results, marked as judgment where they matter.

## What exists publicly

- [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code)
  - a widely referenced curated directory of Claude Code resources, the
  largest found in this search. Breadth, no methodology. Also the natural
  place to get this thesis listed.
- [awesome-claude-md](https://github.com/josix/awesome-claude-md) - exemplary
  CLAUDE.md files and templates. Single-file focus, no layered loading.
- [claude-failures](https://github.com/ctoth/claude-failures) - dated
  post-mortems of real Claude Code incidents with preventive rules. Evidence
  the honest-failure genre is publicly practiced; that it earns credibility
  is this author's judgment. Failures are not wired into a governing system.
- [carls-product-os](https://github.com/carlvellotti/carls-product-os) - a
  PM's personal workspace OS. Clean architecture, no verification,
  measurement, or maintenance.
- [lifeos-template](https://github.com/seandavi/lifeos-template) - closest
  neighbor on maintenance: an /audit skill scoring the vault, decision
  revisits, forced quarterly rewrites. Personal-life scope, no verification
  layers or maturity model.
- [life-system](https://github.com/davidhariri/life-system) - CLAUDE.md as
  "constitution," drift-catching. No verification or ratification gates.
- [Andrews, Claude Code for Non-Coders](https://medium.com/@k3vin.andrews1/claude-code-for-non-coders-by-a-non-coder-a7a67fcce236)
  - a lawyer's two-role system with PRIMARY/SECONDARY/INFERENCE/UNVERIFIED
  claim labels; verification framed as professional duty. Nearest peer to the
  layered-verification framing. No measurement or doctrine maintenance.
- [Harper Reed](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/)
  and [Simon Willison](https://simonwillison.net/2025/Feb/21/my-llm-codegen-workflow-atm/)
  - widely cited examples of the "how I work with AI" credibility genre
  (author's judgment). Codegen workflows, not operating models.

## Named concepts to cite

- Context engineering - [Anthropic's essay](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  ("smallest possible set of high-signal tokens"); the layered root/loader
  design is a direct application. Also [Claude Code best practices](https://code.claude.com/docs/en/best-practices).
- Context rot - [now a named practitioner problem](https://www.mindstudio.ai/blog/what-is-context-rot-claude-code);
  hook for the doctrine-maintenance story.
- LLM-as-judge in layered evaluation - [Braintrust](https://www.braintrust.dev/articles/what-is-llm-as-a-judge),
  [DeepEval](https://deepeval.com/blog/llm-as-a-judge).
- Defense in depth for AI outputs - guardrails literature
  ([Patronus](https://www.patronus.ai/ai-reliability/ai-guardrails)), framed
  for products, not personal practice.
- AI maturity models - [MITRE](https://aimaturitymodel.mitre.org/) and
  [Microsoft](https://learn.microsoft.com/en-us/agents/adoption-maturity-model/),
  both organization-level. Nobody found scores their own individual practice.
- Golden paths - [platformengineering.org](https://platformengineering.org/blog/what-are-golden-paths-a-guide-to-streamlining-developer-workflows),
  [Red Hat](https://www.redhat.com/en/topics/platform-engineering/golden-paths);
  the skeleton is a golden path for workspaces.

## The gap (not found in this search; bounded per the method note)

Each piece of the system has a nearest neighbor somewhere, but no found
source closes the loop in one practitioner system: doctrine maintained
against rot, a maturity model and monthly scorecard applied to an individual
practice, failure modes fed back into the governing rules, and a formal
human-authority model (validate before building, ratification gates,
author-auditor separation). The individual-scorecard move was not found in
any source this search reviewed. The security-leader framing (defense in
depth and honest control assessment applied to one's own AI outputs) was
likewise not found in the sources reviewed. Both negative statements are
bounded to the searches described in the method note, as of 2026-07-12.
