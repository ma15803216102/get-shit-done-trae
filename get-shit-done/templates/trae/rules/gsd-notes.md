---
alwaysApply: false
description: "当你在 Trae 中使用 GSD（Get Shit Done）进行规划/执行/验证时，遵循这些简要原则。"
---

# GSD × Trae：使用说明（可选规则）

> 这是一个“按需启用”的 project rule（Apply Intelligently）。当你在 Trae 中进行 GSD 相关工作时，建议参考。

## 1. Rules 与 Skills 的分工

- **Rules**：常驻/半常驻的行为约束（简短、稳定）
- **Skills**：按需加载的具体流程（较长、包含步骤与 gating）

因此：不要把完整 workflows 内容复制到 rules 中，以免每次对话上下文膨胀。

## 2. 路径请使用项目相对路径

在 Trae rules/skills 中提到文件路径时，优先使用相对项目根目录的路径（例如 `.planning/PROJECT.md`），避免写入用户机器的绝对路径或 home 路径。

## 3. Secrets 约束

- rules/工件中 **只写环境变量名**，不要写环境变量值
- 在提交 `.planning/**` 前，应进行 secrets 扫描（项目可用脚本/CI 承担）

