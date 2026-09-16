# Craft Lite Engineering Suite

Craft Lite 是一套面向日常软件开发的精简 Skill 套件。它把项目长期上下文、任务状态和工程方法收束到一个模型里：

- 持久任务唯一真源是仓库内的 `kanban/`，状态为 `discussion/ → planning/ → executable/ → done/`。
- `checklist/` 保存稳定规则和验证清单。
- `shared-context/findings/` 保存可复用的证据和排查结论。
- `CONTEXT.md` 保存会反复使用的领域术语和关系。
- `docs/adr/` 只保存少量难以逆转的决策。
- `AGENTS.md` 或 `CLAUDE.md` 只做短入口和指针。

Issue、PR 和外部报告可以作为入口或证据链接，但不建立第二份任务正文。

## 六个 Skill

| Skill | 用途 |
| --- | --- |
| [`craft-lite-router`](skills/craft-lite-router/SKILL.md) | 判断当前阶段并加载一个主要方法 |
| [`craft-lite-setup`](skills/craft-lite-setup/SKILL.md) | 为已有仓库建立一次统一的项目框架 |
| [`craft-lite-discovery`](skills/craft-lite-discovery/SKILL.md) | 澄清含糊需求和领域决策 |
| [`craft-lite-build`](skills/craft-lite-build/SKILL.md) | 实现已确认且获授权的改动 |
| [`craft-lite-diagnose`](skills/craft-lite-diagnose/SKILL.md) | 诊断难 Bug、回归、性能和间歇性故障 |
| [`craft-lite-review`](skills/craft-lite-review/SKILL.md) | 审查变更是否符合需求和项目规则 |

路由器只选择当前阶段的一个主要方法；同一任务进入下一阶段时，按顺序加载下一个方法。小改动可以直接使用 `craft-lite-build`，无需先创建完整文档。

## 安装

把 `skills/` 下需要的 Skill 目录复制到 Codex 的技能目录，例如：

```text
~/.codex/skills/
```

也可以下载仓库中的 [`craft-lite-engineering-suite-2026-09-15.zip`](craft-lite-engineering-suite-2026-09-15.zip) 后解压。

## 来源与许可证

本套件是对 Stream29 checklist/shared-context/kanban 工作流和 Matt Pocock 工程 Skill 方法的重新组织与改写。具体来源、改写范围和验证边界见 [`SOURCE-MANIFEST.json`](SOURCE-MANIFEST.json) 与 [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md)。

仓库中的原创改写部分采用 MIT 许可证；第三方项目的名称、商标、原始文本和许可证权利仍归各自权利人所有。详见 [`LICENSE`](LICENSE)。
