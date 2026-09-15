# Craft Engineering Suite

A focused suite of independent coding skills that combines structured project memory with practical engineering methods.

## What is included

- `craft-suite-router`: choose the smallest current method
- discovery and context modeling
- task planning and wayfinding
- implementation and testing
- debugging and review
- research and prototypes
- handoff and merge resolution
- project setup, release verification, architecture, triage and learning loop

Each skill is independently invocable. The router loads one primary method at a time; it does not run the entire suite. Project setup records one canonical task owner and document layout so the skills do not create duplicate queues or duplicate decisions.

## Install

Copy the directories under `skills/` into your Codex skills directory, for example:

```sh
cp -R skills/craft-* ~/.codex/skills/
```

Then use `$craft-suite-router` when you do not know which method fits, or invoke a specialist directly, such as `$craft-discovery`, `$craft-implementation`, `$craft-debugging`, or `$craft-review`.

## Sources and design

This suite is a selective fusion of Matt Pocock-style engineering workflows and Stream29's checklist/kanban/shared-context project workflow. It keeps the useful methods, removes private environment assumptions, and gives each capability one clear owner. See [`使用说明与来源对照.md`](使用说明与来源对照.md), [`SOURCE-MANIFEST.json`](SOURCE-MANIFEST.json), and [`VALIDATION.md`](VALIDATION.md).

## Attribution and license

The instructions in this repository are new, selective rewrites. They were informed by the public Stream29 checklist/kanban workflow and the locally installed Matt Pocock skill snapshot; see the source notes for the exact mapping. This repository is offered under MIT for the original material here. It does not relicense third-party repositories or trademarks.
