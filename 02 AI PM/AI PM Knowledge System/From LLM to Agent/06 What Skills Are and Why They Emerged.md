> **阅读时间**：7 分钟 | **难度**：⭐⭐ 入门 | **前置知识**：了解 Agent 和 MCP 基本概念
>
> **一句话摘要**：Skills 是 Agent 的"模块化技能包"——让 AI 的能力变得可复用、可组合、可共享。

---

## 📌 本篇定位

上一篇我们聊了 MCP 如何让 AI 连接外部工具。
但连接工具只是第一步，Agent 还需要知道 **"怎么用好这些工具"**。

Skills（技能）就是在 Agent 和 MCP 基础上出现的更高层概念——
它不只是一个工具调用，而是**一整套完成特定任务的能力包**。

> 🌐 **In English:** Skills are a higher-level concept built on top of Agents and MCP. They are modular capability packages that bundle instructions, tools, strategies, and memory — enabling AI agents to perform complex tasks reliably and repeatably.

---

## 🔑 核心概念速览

| 概念 | 类比 | 一句话解释 |
|:---|:---|:---|
| Skill | 员工的一项专业技能 | Agent 会做的一件具体的事 |
| SKILL.md | 技能说明书 | 描述技能何时触发、怎么执行 |
| Skill 调用 | 派活给专业人员 | Agent 识别场景后自动/手动加载技能 |

> 🌐 **In English:** A Skill is like a professional competency — it includes when to activate, what tools to use, and how to execute. SKILL.md is its instruction manual.

---

## 🤔 为什么会出现 Skills？

想象一个场景：你有一个 Agent，它能通过 MCP 连接 GitHub、数据库、邮件系统。
但每次你让它"帮我做一次代码审查"，它都要**从头推理该怎么做**：

1. 先读哪些文件？
2. 用什么标准审查？
3. 结果输出成什么格式？
4. 要不要自动提交评论？

**每次都从零开始推理，效率低、结果不稳定。**

Skills 的出现就是为了解决这个问题：
把"做代码审查"这件事**封装成一个技能包**，
包含完整的策略、工具组合、输出格式——Agent 下次直接调用，不用重新推理。

> 🌐 **In English:** Without Skills, an agent must reason from scratch every time it performs a task. Skills package proven strategies, tool combinations, and output formats into reusable modules — making agents more efficient and consistent.

---

## 🆚 Skills vs Function Calling：关键区别

很多人会问："这和 Function Calling（函数调用）有什么区别？"

| 维度 | Function Calling | Skills |
|:---|:---|:---|
| 粒度 | 单个工具调用 | 完整能力包（多个工具 + 策略） |
| 上下文 | 无记忆 | 可携带记忆和上下文 |
| 复用性 | 每次需重新编排 | 封装好，一次定义反复使用 |
| 触发方式 | 模型自动决定调单个工具 | 基于场景匹配加载整套能力 |

**简单类比：**
- Function Calling = 你告诉员工"帮我打个电话"（单个动作）
- Skill = 你告诉员工"帮我处理客户投诉"（一整套流程：接听 → 记录 → 分类 → 回复 → 归档）

> 🌐 **In English:** Function Calling is a single tool invocation. A Skill is a complete capability package — it may involve multiple tools, carry context and memory, and encapsulate an entire workflow. Think of it as "make a phone call" vs. "handle a customer complaint end-to-end."

---

## 🛠️ 实际例子：Claude Code 的 Skills 系统

Claude Code 是目前 Skills 概念落地最完整的产品之一。
以下是它的 Skills 系统运作方式：

### 技能结构

每个 Skill 是一个目录，核心文件是 `SKILL.md`，包含两部分：

```yaml
---
name: review-pr          # 成为 /review-pr 斜杠命令
description: 审查 Pull Request 的代码质量和安全性
---
```

```markdown
# 审查步骤
1. 读取 PR 的 diff 内容
2. 检查代码风格、安全漏洞、性能问题
3. 生成结构化审查报告
4. 在 PR 中提交评论
```

### 触发方式

| 方式 | 说明 | 适用场景 |
|:---|:---|:---|
| 用户调用 | 输入 `/review-pr` | 明确想执行某技能 |
| 模型调用 | Agent 自动识别场景并加载 | 上下文匹配时自动触发 |
| 禁止模型调用 | 设置 `disable-model-invocation: true` | 有副作用的操作（如部署） |

### Token 效率设计

这是一个精妙的工程细节：

- **元数据扫描**：每个 Skill 仅消耗约 100 tokens（只读名称和描述）
- **完整加载**：被激活时加载完整内容，通常 < 5,000 tokens
- **按需资源**：附带的模板、脚本等仅在需要时才加载

这意味着即使你有 100 个 Skills，待机开销也只有约 10,000 tokens。

> 🌐 **In English:** Claude Code's skill system uses SKILL.md files with YAML frontmatter. Skills can be user-invoked (slash commands) or model-invoked (auto-triggered by context). The token-efficient design costs only ~100 tokens per skill for scanning, with full content loaded on demand.

---

## 🌍 Skills 的行业发展

Skills 概念正在快速标准化：

| 时间 | 事件 |
|:---|:---|
| 2025 年中 | Claude Code 推出 Skills 系统 |
| 2025.12 | Anthropic 将 Skills 规范开源 |
| 2025.12 | OpenAI 的 Codex CLI 和 ChatGPT 采用相同的 SKILL.md 格式 |
| 2026 年初 | 生态已有 50 万+ 兼容 Skills |

**跨平台兼容**是 Skills 的一个重要特性——
同一个 Skill 可以在 Claude.ai、Claude Code、API 以及 OpenAI Codex 上运行，
无需为每个平台做适配。

> 🌐 **In English:** The SKILL.md format became an open standard in late 2025. Both Anthropic and OpenAI adopted it, creating a cross-platform ecosystem with 500,000+ compatible skills by early 2026.

---

## 🧩 Skills 的层级与优先级

在实际使用中，Skills 有清晰的层级系统：

```
企业级 Skills（Enterprise）    ← 最高优先级
    ↓
个人级 Skills（Personal）
    ↓
项目级 Skills（Project）       ← 最低优先级
```

当多个同名 Skill 存在时，高优先级的会覆盖低优先级的。
项目子目录中还可以有自己的 Skills（适合 Monorepo 场景）。

> 🌐 **In English:** Skills follow a priority hierarchy: Enterprise > Personal > Project. Same-named skills at higher levels override lower ones. Subdirectories can have their own skills, supporting monorepo setups.

---

## 🎯 PM 视角：Skills 意味着什么？

**1. 渐进式增强能力**

传统软件的功能是开发团队一次性内置的。
有了 Skills，AI 产品可以**像安装 App 一样逐步扩展能力**。
用户甚至可以自己创建 Skills，定制专属工作流。

**2. 新的分发渠道**

Skills 正在形成类似"App Store"的生态。
已经出现了 Skills 市场（如 SkillsMP），
**"AI 技能开发者"可能成为一个新职业。**

**3. 用户粘性重新定义**

当用户在你的平台上积累了大量定制 Skills，
迁移成本就会变高。**Skills 库可能成为新的用户粘性来源。**

> 🌐 **In English:** For PMs, Skills enable progressive capability enhancement (like installing apps), create a new distribution channel (Skills marketplaces are emerging), and redefine user stickiness (accumulated custom Skills increase switching costs).

---

## ⚠️ 常见误解

> **误解 1**："Skills 就是 Prompt 模板"
>
> **澄清**：Prompt 模板只是文本替换。Skills 可以包含多个工具调用、
> 条件逻辑、外部脚本、上下文记忆——是完整的执行方案。

> **误解 2**："Skills 只适合开发者"
>
> **澄清**：Skills 的应用范围包括创意设计、内容写作、数据分析、
> 项目管理等各领域。技术背景不是必须的。

> 🌐 **In English:** Skills are not just prompt templates — they include multi-tool orchestration, conditional logic, scripts, and memory. They apply far beyond coding: design, writing, data analysis, and project management all benefit.

---

## 📝 本篇小结

| 要点 | 内容 |
|:---|:---|
| Skills 是什么 | Agent 的模块化、可复用的能力包 |
| 为什么出现 | 避免 Agent 每次从头推理，提升效率和一致性 |
| 和 Function Calling 的区别 | 单个调用 vs 完整工作流封装 |
| 标准化现状 | SKILL.md 已成跨平台开放标准 |
| PM 关注点 | 渐进增强、新分发渠道、用户粘性 |

---

## 🔗 延伸阅读

- [Claude Code Skills 官方文档](https://code.claude.com/docs/en/skills)
- [Anthropic 官方 Skills 仓库](https://github.com/anthropics/skills)
- [Claude Code Skills 深度解析](https://mikhail.io/2025/10/claude-code-skills/)
- [Awesome Claude Skills 社区合集](https://github.com/travisvn/awesome-claude-skills)

---

> **下一篇**：[06 Claude Code、Codex 这类产品在做什么](06_what_claude_code_and_codex_style_tools_do.md)
>
> **上一篇**：[04 什么是 MCP？它想解决什么问题](04_what_mcp_is_and_what_problem_it_solves.md)

---

*最后更新：2026-03 | 作者：Charlie FocusLab*
