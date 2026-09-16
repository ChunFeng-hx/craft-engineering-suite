---
name: craft-lite-setup
description: "Initialize one practical repository-centered engineering workflow with Kanban as the sole persistent task truth and fixed document responsibilities."
---

# Craft Lite Setup

Run once when a repository lacks the Craft Lite frame. This is an inspection and setup method, not a template copier.

## Inspect

Read Git status/remotes, `AGENTS.md`/`CLAUDE.md`, existing `checklist/`, `shared-context/`, `CONTEXT.md`, ADRs, `kanban/`, and links to Issues/PRs. Preserve user text and existing history.

## Establish the fixed frame

Persistent tasks always use repository Kanban:

```text
kanban/discussion/ → kanban/planning/ → kanban/executable/ → kanban/done/
```

External trackers remain intake/evidence links. They never own a duplicate task body. Fixed document owners are: rules → `checklist/`; findings → `shared-context/findings/`; domain language → `CONTEXT.md`; durable trade-offs → `docs/adr/`; task state → `kanban/`.

Create only missing files that contain useful content. Add one concise `## Craft Lite` pointer block to the actual loaded `AGENTS.md` or `CLAUDE.md`; if neither exists, ask which entrypoint to create. Do not create empty glossaries, ADRs, findings or tasks.

For generated-code repositories, mark files containing the project's generator warning (for example `Easy生成，平台修改本地 update 会更新此文件`) as generated ownership. Do not hand-edit those files; locate the generator, schema or source template instead. Record the boundary in the project entrypoint or checklist. Treat migrations, generated models and platform registration as separate responsibilities: inspect existing commands and ownership before creating or moving any of them. Do not migrate user code, change repository layout, or introduce a Build wrapper unless the boundary is confirmed and authorized.

## Build wrapper

Use `Build<ProjectName>` only when independent Git history or an external workflow boundary requires it and the user confirms. The same fixed memory and Kanban model applies in either layout. Never reparent a dirty checkout, copy credentials or create a second task system.

## Verify

Check paths, links, one entrypoint block, preserved text, Kanban ownership and Git status. A dry second run must propose no duplicate block or competing queue. Report created/changed files and the next method.

## Shared project frame

Use the repository as the durable project memory. The fixed owners are:

- `AGENTS.md` or `CLAUDE.md`: entrypoint and pointers; keep it short.
- `checklist/`: stable project rules and validation SOPs.
- `shared-context/findings/`: reusable evidence with source anchors.
- `CONTEXT.md`: domain terms and relationships.
- `docs/adr/`: rare, durable trade-off decisions.
- `kanban/`: the only persistent task/progress record: `discussion/` → `planning/` → `executable/` → `done/`.

External Issues and PRs are intake links, never a second task body. Drafts and task state are not authorization. Create records lazily; a small task may stay in the conversation.
