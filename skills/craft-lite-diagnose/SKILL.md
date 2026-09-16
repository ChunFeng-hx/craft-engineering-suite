---
name: craft-lite-diagnose
description: "Diagnose a non-obvious bug, regression, flaky failure or performance problem with evidence before theorizing, then lock the cause down at a valid seam."
---

# Craft Lite Diagnose

Use when a first-glance fix is unreliable. For read-only requests, inspect existing logs, traces, commands and tests first; do not create a harness, test or debug logging.

## Establish evidence

Build or reuse one feedback loop that goes red on the actual symptom. Confirm it reproduces the user's problem, then minimize load-bearing inputs. If the environment prevents a red loop, continue useful source/log analysis and report the evidence gap as blocked or not-run; do not invent a confirmed cause.

Use these result states precisely: `blocked` means an external prerequisite or environment boundary prevents the discriminating check; `not-run` means a relevant check was identified but intentionally could not be attempted in this run. Keep both separate from “passed” and “failed”, name the missing evidence, and state what would unblock or run it. Do not turn a missing reproduction into a confirmed root cause.

Rank a small number of evidence-backed competing hypotheses. For each, state a prediction and run one discriminating probe. Control time, randomness, seeds, scheduling and environment at boundaries when relevant. Measure a performance baseline instead of broad logging.

## Fix and verify

At the correct public seam, turn the minimized repro into a regression test when implementation is authorized. Apply the smallest cause-level fix, rerun the original loop and relevant broader checks. Remove only temporary instrumentation created for this task; retain a useful reproducible test or harness.

Record the confirmed cause, limitations and durable lesson in the fixed project owners. A missing architectural seam is a separate architecture task, not a reason to write a misleading test.

## Shared project frame

Use the repository as the durable project memory. The fixed owners are:

- `AGENTS.md` or `CLAUDE.md`: entrypoint and pointers; keep it short.
- `checklist/`: stable project rules and validation SOPs.
- `shared-context/findings/`: reusable evidence with source anchors.
- `CONTEXT.md`: domain terms and relationships.
- `docs/adr/`: rare, durable trade-off decisions.
- `kanban/`: the only persistent task/progress record: `discussion/` → `planning/` → `executable/` → `done/`.

External Issues and PRs are intake links, never a second task body. Drafts and task state are not authorization. Create records lazily; a small task may stay in the conversation.
