# skill-enhance Changelog

## Version

- `1.0.1`
- Release date: `2026-05-12`

---

## 中文版本

### 描述

本 changelog 记录的是相对于上一版的增量变化，而不是 `skill-enhance` 的完整功能介绍。

这一版的重点不是继续扩展能力边界，而是把已有能力表达得更清楚、更利于展示和发布，并把与该 skill 强绑定的变更说明收回到 skill 包内部维护。

### 变更说明

相对于上一版，本次主要变更包括：

- 调整 skill 的对外描述，使其更明确地覆盖 skill 创建、skill 增强、发布前审查以及本地 skill 定向优化四类核心场景。
- 强化 metadata 中的定位表达，突出这是一个以质量优先为目标的 skill，而不是只生成一个最小可用草稿。
- 优化 `README.md` 的展示结构，使其更适合作为 GitHub 首页说明，先回答“它是什么、解决什么问题、适合谁、如何使用、会产出什么”。
- 将 changelog 从项目级 `docs/` 目录迁移到 `.codex/skills/skill-enhance/CHANGELOG.md`，让 `skill-enhance` 的开发材料在 skill 目录内集中维护。
- 更新文档索引，使 `docs/README.md` 改为指向 skill 包内部的 changelog，减少文档位置分散带来的维护成本。

---

## English Version

### Description

This changelog describes incremental changes from the previous version rather than serving as a full product overview of `skill-enhance`.

This release is not mainly about expanding the capability surface. Its focus is to present the existing capability set more clearly for discovery and publishing, and to keep the skill-specific changelog inside the skill package itself.

### Change Log

Compared with the previous version, this release includes:

- Refined the public-facing description so the skill more clearly covers four core scenarios: skill creation, skill enhancement, publish-readiness review, and local skill customization.
- Strengthened the metadata positioning so the skill is framed as a quality-first skill package hardener rather than a minimal draft generator.
- Reworked `README.md` so it reads more like a GitHub project overview, answering what the skill is, what problem it solves, who it is for, how it is used, and what it produces.
- Moved the changelog from the project-level `docs/` directory to `.codex/skills/skill-enhance/CHANGELOG.md` so skill-specific development materials are maintained alongside the skill package.
- Updated the documentation index so `docs/README.md` now points to the changelog inside the skill package, reducing maintenance overhead caused by split document locations.
