# Craft suite validation

Date: 2026-09-15 Asia/Shanghai

- 18 new skill directories validated with the bundled `quick_validate.py` using an isolated Python environment with PyYAML.
- Every new `SKILL.md` has valid frontmatter and a unique name.
- Relative references to sibling Craft skills resolve.
- `craft-project-setup` assets and `project-contract.md` exist.
- Each skill has UI metadata.
- Isolated forward test: existing AGENTS + GitHub issue tracker produced only `docs/agents/craft.md` and one managed AGENTS block; no parallel kanban queue or empty context/finding/task. Second run was idempotent.
- Isolated read-only discovery test: no files were created.
- Scenario review covered explicit small change with tracker, read-only production-log diagnosis without reproduction, and a required integration check blocked by environment. The suite was adjusted to keep task-owner semantics, forbid read-only harness creation, and report blocked/not-run accurately.

Limitations: no real remote issue mutation, release publication, signing, merge continuation, or production traffic was performed. Runtime behavior depends on each project's tools and authorization. Source drift should be rechecked before major updates.
