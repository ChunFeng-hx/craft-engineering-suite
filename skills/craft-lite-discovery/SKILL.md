---
name: craft-lite-discovery
description: "Turn an unclear software requirement into a confirmed design by checking repository facts, resolving domain language, and asking only implementation-changing questions."
---

# Craft Lite Discovery

Use for unclear behavior, competing designs or overloaded domain language. Do not modify production code.

## Inspect before asking

Read relevant code, tests, project rules, current Kanban task, `CONTEXT.md`, ADRs and findings. Facts available from the repository are the agent's job; ask the user for product decisions, priorities and trade-offs.

## Interview in dependency order

Map a decision tree. In each round ask the whole current frontier: decisions whose prerequisites are settled. Number the questions, explain why each changes the implementation, and give a recommended answer. Use concrete edge cases. Challenge terms such as “user”, “delete”, “active” or “permission” against the existing glossary and code. Continue until no implementation-changing decision remains silently assumed.

Record a resolved domain term in `CONTEXT.md` only when it will be reused. Record an ADR only when the choice is hard to reverse, surprising without context and selected among real alternatives. Put current scope, acceptance and open choices in the Kanban task, not in the glossary.

If a runnable answer is needed, hand the question to `craft-lite-build` only after a small prototype or experiment is explicitly authorized; keep the experiment isolated.

## Finish

Produce a decision summary, non-goals, important scenarios and remaining uncertainty. Wait for the user's confirmation before implementation unless the user already authorized implementation of this exact resolved design.

## Shared project frame

Use the repository as the durable project memory. The fixed owners are:

- `AGENTS.md` or `CLAUDE.md`: entrypoint and pointers; keep it short.
- `checklist/`: stable project rules and validation SOPs.
- `shared-context/findings/`: reusable evidence with source anchors.
- `CONTEXT.md`: domain terms and relationships.
- `docs/adr/`: rare, durable trade-off decisions.
- `kanban/`: the only persistent task/progress record: `discussion/` → `planning/` → `executable/` → `done/`.

External Issues and PRs are intake links, never a second task body. Drafts and task state are not authorization. Create records lazily; a small task may stay in the conversation.
