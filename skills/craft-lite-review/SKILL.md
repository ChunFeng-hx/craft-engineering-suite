---
name: craft-lite-review
description: "Review a diff, branch or completed change against the requested behavior and project rules, with evidence-first findings and explicit limits."
---

# Craft Lite Review

Use for independent assessment. Establish the fixed base and reviewed head, read the request/spec, relevant project rules, context and decisions, then inspect the complete relevant diff and nearby code.

Review two contracts separately:

- **Contract**: requested behavior, edge cases, errors, compatibility and non-goals.
- **Craft**: repository rules, boundaries, tests, security, performance, duplication and maintainability.

Trace each finding to an exact path/line or reproducible behavior. Say “不明确” when the source does not establish intent. Compare neighboring implementations before calling a convention defective. Do not edit, commit, merge or publish comments during review.

For state-changing or retryable operations, check idempotency across processes and instances, not only a local mutex or in-memory flag. Identify the idempotency key, durable store, uniqueness constraint or atomic operation and the behavior after timeout, retry and crash. For auditable behavior, verify that audit records are durable, permissioned and queryable by the operators who need them; a log line alone is not a queryable audit trail. For schema or persistence changes, trace the migration from file to registration, execution, deployed schema and rollback/compatibility path. A migration file that is never wired into the runner is incomplete.

Report actionable findings first using:

```text
结论
证据
影响
建议
原文出处
```

State checks actually run, remaining risks and review limits. Suggest a single update to `checklist/` or `shared-context/findings/` only when a finding is durable; do not copy the review report into project memory automatically.

## Shared project frame

Use the repository as the durable project memory. The fixed owners are:

- `AGENTS.md` or `CLAUDE.md`: entrypoint and pointers; keep it short.
- `checklist/`: stable project rules and validation SOPs.
- `shared-context/findings/`: reusable evidence with source anchors.
- `CONTEXT.md`: domain terms and relationships.
- `docs/adr/`: rare, durable trade-off decisions.
- `kanban/`: the only persistent task/progress record: `discussion/` → `planning/` → `executable/` → `done/`.

External Issues and PRs are intake links, never a second task body. Drafts and task state are not authorization. Create records lazily; a small task may stay in the conversation.
