> **阅读时间**：9 分钟 | **难度**：⭐⭐ 入门 | **前置知识**：了解 LLM、Agent、MCP、Skills 基本概念
>
> **一句话摘要**：这些产品把前面所有概念串在一起——不只是聊天，而是 AI 直接操作你的工作环境完成任务。

---

## 📌 本篇定位

前几篇我们分别聊了 LLM、Function Calling、Agent、MCP、Skills。
现在是时候把它们串起来了。

Claude Code、OpenAI Codex、Cursor 这类产品，
就是**所有这些概念的集大成者**：

```
LLM（语言理解） + Function Calling（工具调用）
    + Agent（自主规划） + MCP（标准化连接） + Skills（模块化能力）
    = 能直接帮你干活的 AI 产品
```

> 🌐 **In English:** Products like Claude Code, OpenAI Codex, and Cursor combine all the concepts we've covered — LLM understanding, function calling, agent planning, MCP connectivity, and modular skills — into AI products that directly operate on your work environment.

---

## 🔑 三款代表产品速览

| 维度 | Claude Code | OpenAI Codex | Cursor |
|:---|:---|:---|:---|
| 开发商 | Anthropic | OpenAI | Anysphere |
| 产品形态 | CLI 命令行工具 | 云端 Agent + CLI | AI-first 代码编辑器 |
| 核心定位 | 终端里的 AI 编程伙伴 | 云端并行编程 Agent | 智能代码编辑器 |
| 适合谁 | 喜欢终端的开发者 | 需要并行处理多任务的团队 | 偏好 GUI 的开发者 |

> 🌐 **In English:** Claude Code is a CLI-based AI programming partner. OpenAI Codex is a cloud-based parallel coding agent. Cursor is an AI-first code editor with a GUI. Each targets different developer workflows.

---

## 🔍 Claude Code：终端里的 AI 编程伙伴

**Claude Code** 是 Anthropic 推出的 CLI（Command-Line Interface，命令行界面）工具，
直接运行在你的终端里。

### 它能做什么

- **读写文件**：直接编辑你项目中的代码文件
- **执行命令**：运行测试、构建、Git 操作等
- **搜索代码**：在整个代码库中查找模式和引用
- **理解上下文**：通过 MCP 连接数据库、API 文档、项目管理工具等
- **Skills 系统**：通过 SKILL.md 定义可复用的工作流

### 设计哲学

Claude Code 的核心理念是**"在你的环境中工作"**——
它不要求你把代码复制到某个网页上，
而是直接在你的项目目录里操作，就像一个坐在你旁边的同事。

### 安全机制

- 默认在沙箱环境中运行，网络访问受限
- 危险操作（如删除文件）需要用户确认
- 所有操作都有审计日志

> 🌐 **In English:** Claude Code operates directly in your terminal and project directory — reading/writing files, running commands, searching code, and connecting to external tools via MCP. It works like a colleague sitting next to you, with built-in safety mechanisms.

---

## 🔍 OpenAI Codex：云端并行编程 Agent

**OpenAI Codex** 是一个云端软件工程 Agent，
最大特点是**可以同时处理多个任务**。

### 它能做什么

- **并行工作**：同时开多个任务线程，互不干扰
- **独立沙箱**：每个任务在独立的云端环境中运行
- **长时间执行**：复杂任务可以持续运行数小时（最长记录 7 小时+）
- **自适应推理**：简单任务快速响应，复杂任务深度思考
- **提交 PR**：直接为你的仓库提交 Pull Request

### 模型演进

Codex 背后的模型在 2025 年经历了快速迭代：

| 模型 | 时间 | 特点 |
|:---|:---|:---|
| codex-1 | 2025.04 | 基于 o3 优化，首个专注编程的 Agent 模型 |
| GPT-5-Codex | 2025.09 | 基于 GPT-5，支持更复杂的工程任务 |
| GPT-5.2-Codex | 2025 年底 | 上下文压缩、大规模重构、网络安全能力 |
| GPT-5.3-Codex | 2026 年初 | 最强编程模型，可在执行中实时交互 |

### 典型使用场景

- **Temporal**：用 Codex 加速功能开发、调试、测试
- **Superhuman**：产品经理用 Codex 做轻量级代码修改，不需要找工程师
- **Kodiak**：用 Codex 编写自动驾驶的调试工具和测试覆盖

> 🌐 **In English:** OpenAI Codex runs as a cloud agent that can handle multiple tasks in parallel, each in its own sandbox. It evolved through four model generations in 2025, culminating in GPT-5.3-Codex which supports real-time interaction during execution.

---

## 🔍 Cursor：AI-First 的代码编辑器

**Cursor** 走了一条不同的路——
它不是 CLI 工具或云端 Agent，而是**一个完整的代码编辑器**（基于 VS Code）。

### 核心特点

- **内嵌 AI**：AI 不是插件，而是编辑器的核心能力
- **多模型支持**：可以选择 Claude、GPT 等不同模型
- **Tab 补全**：智能代码补全，理解你的项目上下文
- **Composer**：对话式编程，描述需求后 AI 直接生成/修改代码
- **代码库索引**：自动索引整个项目，AI 理解全局上下文

### 与前两者的定位差异

Cursor 更偏向**"增强现有开发体验"**，
而 Claude Code 和 Codex 更偏向**"AI 独立完成任务"**。

> 🌐 **In English:** Cursor is an AI-first code editor (based on VS Code) where AI is a core feature, not a plugin. It enhances the traditional coding experience with smart completion, multi-model support, and full codebase understanding — positioned more as "AI-enhanced editing" than "AI-independent execution."

---

## 🧩 这类产品的共同特点

虽然形态不同，但这三类产品有共同的底层逻辑：

### 1. 从"回答问题"到"完成任务"

传统 ChatGPT 对话模式：

```
用户：这段代码有什么 Bug？
AI：第 15 行有一个空指针问题，你应该加一个 null check...
用户：（自己去改代码）
```

Agent 模式：

```
用户：帮我修复这个 Bug
AI：（自动定位问题 → 读取相关文件 → 修改代码 → 运行测试 → 确认通过）
AI：已修复，修改了 2 个文件，测试全部通过。
```

**核心转变：AI 从"顾问"变成了"执行者"。**

### 2. 操作真实环境

这些产品不是在一个隔离的聊天窗口里工作。
它们直接操作你的**文件系统、终端、Git 仓库、数据库**——
这是从"模拟"到"实战"的跨越。

### 3. 安全与信任机制

因为 AI 能直接操作环境，安全变得至关重要：

| 安全机制 | 说明 |
|:---|:---|
| 沙箱隔离 | 限制 AI 的操作范围 |
| 权限确认 | 危险操作需要用户批准 |
| 审计日志 | 所有操作可追溯 |
| 网络限制 | 默认禁止外部网络访问 |

> 🌐 **In English:** These products share three common traits: they shift AI from "answering questions" to "completing tasks," they operate on real environments (files, terminals, databases), and they incorporate robust safety mechanisms (sandboxing, permission prompts, audit logs, network restrictions).

---

## 📊 三款产品深度对比

| 维度 | Claude Code | OpenAI Codex | Cursor |
|:---|:---|:---|:---|
| 交互方式 | 终端对话 | 云端任务分发 | GUI 编辑器 |
| 执行位置 | 本地机器 | 云端沙箱 | 本地机器 |
| 并行能力 | 单线程 | 多任务并行 | 单线程 |
| MCP 支持 | 原生支持 | 支持 | 通过插件 |
| Skills 系统 | SKILL.md 原生 | 兼容 SKILL.md | 无原生支持 |
| 长任务能力 | 中等 | 强（数小时） | 弱（交互式） |
| 学习曲线 | 中等（需会终端） | 低 | 低（类似 VS Code） |
| 适合场景 | 深度编程、项目管理 | 批量任务、代码审查 | 日常编码、快速原型 |

> 🌐 **In English:** Claude Code excels at deep local programming tasks with native MCP/Skills support. Codex shines at parallel cloud execution for hours-long tasks. Cursor offers the most accessible experience for everyday coding with its familiar VS Code interface.

---

## 📈 它们代表的趋势

这类产品揭示了 AI 产品发展的一个关键方向：

### "AI Agent as Product"（AI Agent 即产品）

过去几年 AI 产品的演变路径：

```
2022  ChatGPT        → AI 能聊天
2023  GPT-4 + Plugins → AI 能用工具
2024  Agent 框架兴起   → AI 能规划和执行
2025  Claude Code/Codex → AI 能独立完成复杂任务
2026  ???             → AI 能自主管理项目？
```

**我们正在经历从"AI 作为功能"到"AI 作为产品"的转变。**

> 🌐 **In English:** These products represent the "AI Agent as Product" trend — a shift from AI-as-a-feature (chatbots, copilots) to AI-as-a-product (autonomous task completion). The trajectory points toward AI independently managing entire projects.

---

## 🎯 PM 视角：这类产品揭示了什么？

**1. AI 产品的下一个方向**

不再是"在现有产品里加个 AI 聊天框"。
而是**围绕 AI Agent 的能力重新设计产品形态**。

**2. 用户角色的变化**

用户从"操作者"变成"指挥者"。
PM 需要重新思考：当用户只需要描述意图，**产品的"界面"是什么？**

**3. 商业模式的启示**

这些产品的定价通常按"Agent 使用量"计费，
而不是传统的按席位/功能收费。
**"AI 完成的工作量"可能成为新的价值衡量标准。**

> 🌐 **In English:** For PMs, these products reveal three insights: AI products should be designed around agent capabilities (not just adding a chat box), user roles shift from "operator" to "director," and business models may evolve from per-seat pricing to per-task or per-agent-usage pricing.

---

## 💡 为什么 PM 需要亲自体验这些产品

> "你不需要会写代码，但你需要理解 AI 能做到什么。"

作为产品经理，亲手使用这些产品的价值在于：

1. **建立直觉**：知道 AI Agent 目前的能力边界在哪里
2. **发现机会**：你所在行业的哪些工作流可以被 Agent 化？
3. **理解用户**：你的开发者用户可能已经在用这些工具了
4. **预判趋势**：今天编程领域发生的事，明天会扩展到所有知识工作

**建议体验路径：**

| 步骤 | 行动 | 时间 |
|:---|:---|:---|
| 1 | 安装 Cursor，用 AI 写一个简单网页 | 30 分钟 |
| 2 | 试用 Claude Code，让它帮你管理一个小项目 | 1 小时 |
| 3 | 体验 Codex，给它一个代码审查任务 | 30 分钟 |

> 🌐 **In English:** PMs should experience these products firsthand — not to write code, but to build intuition about AI agent capabilities, discover automation opportunities in their industry, understand developer users, and anticipate how agent-based workflows will expand beyond coding to all knowledge work.

---

## 📝 本篇小结

| 要点 | 内容 |
|:---|:---|
| 这类产品是什么 | LLM + Agent + MCP + Skills 的集大成者 |
| 核心转变 | 从"AI 回答"到"AI 执行" |
| 共同特点 | 操作真实环境、安全机制、任务导向 |
| 代表趋势 | AI Agent as Product |
| PM 行动项 | 亲自体验，建立对 AI 能力的直觉 |

---

## 🔗 延伸阅读

- [Claude Code 官方文档](https://code.claude.com/docs/en/skills)
- [OpenAI Codex 官方介绍](https://openai.com/index/introducing-codex/)
- [OpenAI Codex 开发者平台](https://developers.openai.com/codex)
- [Codex 如何改变软件开发](https://devops.com/openai-codex-transforming-software-development-with-ai-agents-2/)

---

## 🗺️ 系列导航

本篇是"从 LLM 到 Agent"系列的第六篇，
让我们回顾一下整个知识链路：

```
00 LLM 到底改变了什么
    ↓
02 什么是 Workflow？什么是 Agent？
    ↓
04 什么是 MCP？它想解决什么问题        ← 连接标准
    ↓
05 什么是 Skills？为什么会出现这个概念   ← 能力模块化
    ↓
06 Claude Code、Codex 这类产品在做什么  ← 你在这里 ✦
```

每一层概念都在前一层的基础上构建，
最终汇聚成了我们今天看到的 AI Agent 产品形态。

---

> **上一篇**：[05 什么是 Skills？为什么会出现这个概念](05_what_skills_are_and_why_they_emerged.md)

---

*最后更新：2026-03 | 作者：Charlie FocusLab*
