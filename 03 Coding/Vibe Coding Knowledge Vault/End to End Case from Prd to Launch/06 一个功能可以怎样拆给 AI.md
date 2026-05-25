> 📌 **一句话版本：** 在完整案例里，真正决定 AI coding 质量的，不是工具名字，而是你怎么拆任务、怎么控边界、怎么要求验证；这页给你一套可以直接复用的分工模板。

---

## 📖 这一节在讲什么

当一个功能真的进入实现阶段，你最需要的不是“万能 prompt”，而是一套稳定的任务拆分方式。

## 🎯 一个功能可以怎样拆给 AI

### 任务一：先分析

目标：定位相关文件、结构和影响范围。

### 任务二：出方案

目标：给出最小改动方案和验证计划。

### 任务三：局部实现

目标：只改一块，不做全局重构。

### 任务四：验证与汇报

目标：跑检查、列风险、说剩余待确认点。

> 🌐 **In English:**
> High-quality AI coding depends on staged task design: analyze first, propose a minimal plan, implement locally, then verify and report.

## 💡 为什么这种拆法更稳

因为它天然会限制 AI 常见的失控点：

- 一上来改太多
- 顺手改无关文件
- 改了但不验证
- 最后只说“修好了”

## ⚠️ 分工时最值得强调的内容

- 允许改哪些文件
- 不要动哪些内容
- 需要跑哪些验证
- 最后必须汇报哪些信息

## 🧪 一个实用模板

你可以这样说：

“请先分析这个问题，只列相关文件、影响范围和风险，不要改代码。确认后，再只修改登录流程相关文件，修复后运行测试并汇报改动、风险和待确认项。”

## 📝 记住这些

- 工具越强，任务拆分越重要。
- 先分析、再实现、再验证，是最稳的 AI coding 节奏。
- 分工模板能帮你把 AI 从“灵感工具”变成“可靠搭子”。

## 📚 延伸阅读

- [03_AI_Coding任务模板与验证清单.md](../16_glossary_commands_and_error_reference/03_ai_coding_task_templates_and_validation_checklist.md)
- [01_如何把AI变成结对工程师.md](../10_ai_coding_tools_codex_cli_claude_code/01_how_to_turn_ai_into_a_pair_engineer.md)
