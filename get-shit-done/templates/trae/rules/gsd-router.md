---
alwaysApply: true
description: "GSD（Get Shit Done）在 Trae 中的项目规则：命令别名、路由与基本约束。"
---

# GSD × Trae：命令路由与约束（Project Rules）

本项目使用 GSD 作为“流程/工件驱动”的开发系统。在 Trae 中：

- **Skills（技能）**按需加载（位于 `.trae/skills/`）
- **Project Rules（项目规则）**常驻生效（位于 `.trae/rules/`）

参考：Trae Rules / Skills 官方文档  
- https://docs.trae.ai/ide/rules  
- https://docs.trae.ai/ide/skills

---

## 目录约定（相对项目根目录）

安装到项目后，GSD 的 Trae 资产应存在：

- `.trae/skills/`：Trae skills（每个 skill 一个目录）
  - `.trae/skills/gsd-new-project/SKILL.md`
  - `.trae/skills/gsd-map-codebase/SKILL.md`
- `.trae/get-shit-done/`：GSD engine（workflows/templates/tools）
  - `.trae/get-shit-done/bin/gsd-tools.cjs`

GSD 在项目内生成的工件目录：

- `.planning/`：项目工件（PROJECT/REQUIREMENTS/ROADMAP/STATE/phases…）
- `.planning/codebase/`：代码库映射文档（STACK/ARCHITECTURE/…）

---

## 命令别名与路由（重要）

Trae 的 skills 目录采用 **dash 命名**（例如 `gsd-new-project`），避免在文件系统层面使用 `:`。

因此我们约定：

- 你可以输入 **colon 风格**（更接近 GSD 原始命令名）：
  - `/gsd:new-project`
  - `/gsd:map-codebase`
- 也可以输入 **dash 风格**（Trae 实际 skill 名）：
  - `/gsd-new-project`
  - `/gsd-map-codebase`

两者语义等价。遇到 colon 风格时，请将其视为 dash 风格 skill 来执行：

| 用户输入 | 等价执行的 Trae skill |
|---|---|
| `/gsd:new-project` | `/gsd-new-project` |
| `/gsd:map-codebase` | `/gsd-map-codebase` |

---

## 最小闭环：你应该期望的结果

### 1) `/gsd:map-codebase`（或 `/gsd-map-codebase`）

应生成（示例）：

- `.planning/codebase/STACK.md`
- `.planning/codebase/INTEGRATIONS.md`
- `.planning/codebase/ARCHITECTURE.md`
- `.planning/codebase/STRUCTURE.md`
- `.planning/codebase/CONVENTIONS.md`
- `.planning/codebase/TESTING.md`
- `.planning/codebase/CONCERNS.md`

### 2) `/gsd:new-project`（或 `/gsd-new-project`）

应生成（示例）：

- `.planning/PROJECT.md`
- `.planning/config.json`
- `.planning/REQUIREMENTS.md`
- `.planning/ROADMAP.md`
- `.planning/STATE.md`

