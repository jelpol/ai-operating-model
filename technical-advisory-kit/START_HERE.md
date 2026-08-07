# Start Here

This kit makes an AI assistant useful for real technical work: studying material until you are actually proficient, and reviewing designs without the AI flattering you. It was built and battle-tested inside a working security practice, then stripped of the owner's data so anyone can run it.

It assumes you work in or near a technical field. If the resume kit next door is about getting the job, this one is about being good at it.

## The two rules that make this work

1. **The AI never gets to answer from memory on anything that changes.** Versions, features, licensing, CVEs, framework IDs: verified live or labeled unverified. Module 03 enforces this for a whole chat session.
2. **You track what you actually know.** The knowledge registry is an honest map of your expert domains, your working proficiency, and your named open gaps. The AI reads it and calibrates: no re-teaching what you own, no assuming depth you lack. Study sessions exist to move items across that map, and the gap list, not the reading, is the deliverable.

## Session 1: set up (20 minutes)

1. Copy `templates/knowledge_registry_template.md` to `my-data/knowledge_registry.md` and fill it in honestly. Inflating the expert list buys you unchecked wrong answers in exactly the places you can least afford them.
2. Skim `prompts/principles.md` so you know the standing rules.
3. Create `my-data/learnings/` and `my-data/validations/` folders. **`my-data/` stays private, always.**

## Every working session after that

1. Open an AI chat, paste `prompts/03_verification_gate.md` first. It governs every answer for the rest of the chat.
2. Studying something? Paste `prompts/01_research_anchoring.md` plus the material plus your registry. Save the five-output artifact to `my-data/learnings/`, add the new gap rows to your registry.
3. Deciding something? Paste `prompts/02_validate_a_design.md` plus the design. Sound, Sound with caveats, or Flawed, scored across failure modes, attack surface, scale, operations, cost, and compliance. Keep the verdict in `my-data/validations/` if future-you will cite it.
4. Close by updating the registry if your level moved.

## Monthly, fifteen minutes

Re-check anything past its expiry date, reconcile contradictions, confirm the registry still matches reality. Skip this and the knowledge base silently rots.

## Privacy

Same deal as every kit here: prompts are public, your data is not. Your registry is a map of your professional strengths and weaknesses; your learnings may reference your employer's environment. `my-data/` ships empty and gitignored. Pasting a registry into an AI chat sends it to that provider, so use one you trust and check its retention settings.
