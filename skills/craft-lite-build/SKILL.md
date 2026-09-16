---
name: craft-lite-build
description: "Implement an authorized software change through small behavior-focused slices, using tests and the single Kanban task without unnecessary process overhead."
---

# Craft Lite Build

Use for an explicit, authorized change or a confirmed task. If a material design decision is open, return to `craft-lite-discovery`.

## Establish the slice

Read the current Kanban task, relevant checklist, context, ADRs and findings. State the bounded outcome, non-goals, first vertical slice and completion check. For a tiny change, keep this in the conversation; do not create ceremony.

## Implement

For behavior changes, use the smallest useful red-green-clean cycle:

1. Test one observable behavior through a stable public seam with an independently known expected result.
2. Run it red for the intended reason.
3. Write the smallest implementation that makes it green.
4. Clean up only what keeps the slice clear, then repeat.

Do not test private implementation details, internal call counts or tautological calculations. Mock system boundaries only when needed. Keep unrelated refactors out of scope.

## Verify and close

Run focused tests and relevant type, lint, build, integration or migration checks. Inspect the diff against two contracts: requested behavior and project craft (rules, boundaries, compatibility, maintainability). Record passed, failed, blocked and not-run accurately. Update the canonical Kanban task after material progress; preserve reusable findings and decisions in their fixed owners. Move to `done/` only when every acceptance criterion and required check is satisfied.

## Shared project frame

Use the repository as the durable project memory. The fixed owners are:

- `AGENTS.md` or `CLAUDE.md`: entrypoint and pointers; keep it short.
- `checklist/`: stable project rules and validation SOPs.
- `shared-context/findings/`: reusable evidence with source anchors.
- `CONTEXT.md`: domain terms and relationships.
- `docs/adr/`: rare, durable trade-off decisions.
- `kanban/`: the only persistent task/progress record: `discussion/` → `planning/` → `executable/` → `done/`.

External Issues and PRs are intake links, never a second task body. Drafts and task state are not authorization. Create records lazily; a small task may stay in the conversation.
