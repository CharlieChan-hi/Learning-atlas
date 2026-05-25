> **阅读时间**：8 分钟 | **难度**：⭐⭐ 入门 | **前置知识**：了解 API 基本概念
>
> **一句话摘要**：MCP 是 AI 世界的 USB-C 接口——让任何 AI 应用用同一套协议连接任何外部工具。

---

## 📌 本篇定位

在上一篇我们了解了 Agent 的概念。Agent 要"做事"，就需要调用工具。
但问题来了——**每个 AI 应用和每个工具之间的对接方式都不一样**。
MCP（Model Context Protocol，模型上下文协议）就是为了解决这个"碎片化对接"问题而诞生的。

> 🌐 **In English:** MCP is an open protocol by Anthropic that standardizes how AI applications connect to external tools and data sources — like a universal adapter for the AI ecosystem.

---

## 🔑 核心概念速览

| 概念 | 类比 | 一句话解释 |
|:---|:---|:---|
| MCP Server | USB 设备 | 工具提供方，把能力暴露出来 |
| MCP Client | 电脑的 USB 接口 | AI 应用端，负责发起连接 |
| Protocol | USB 标准协议 | 双方沟通的规则和格式 |

> 🌐 **In English:** MCP has three core concepts — Server (tool provider), Client (AI application), and Protocol (communication rules between them).

---

## 🤔 MCP 之前：M×N 问题

在 MCP 出现之前，AI 生态面临一个经典的"组合爆炸"问题：

```
10 个 AI 应用 × 100 个工具 = 1,000 种定制对接
```

每个 AI 应用想连接外部工具（比如读文件、查数据库、发邮件），
都需要**自己写一套连接代码**。
这就像早年每个手机品牌都有自己的充电口——诺基亚、三星、摩托罗拉各不相同。

**MCP 做的事，就像 USB-C 统一了充电接口：**

```
10 个 AI 应用 × 1 次 MCP 对接 + 100 个工具 × 1 次 MCP 对接 = 110 次对接
```

从 1,000 次降到 110 次，这就是标准化的力量。

> 🌐 **In English:** Before MCP, connecting M AI apps to N tools required M×N custom integrations. MCP reduces this to M+N by providing a single universal protocol — just like USB-C unified charging cables.

---

## 📖 MCP 的诞生与演进

MCP 由 Anthropic 工程师 David Soria Parra 和 Justin Spahr-Summers 主导开发，
于 **2024 年 11 月**正式发布。以下是关键时间线：

| 时间 | 事件 | 意义 |
|:---|:---|:---|
| 2024.11 | Anthropic 发布 MCP 开源标准 | 协议诞生，附 Python/TypeScript SDK |
| 2025.03 | OpenAI 宣布采用 MCP | 竞争对手也用，说明协议真的有价值 |
| 2025.04 | Google DeepMind 确认支持 | 三大巨头全部站队 |
| 2025.05 | 微软/GitHub 加入指导委员会 | 生态进一步扩大 |
| 2025.11 | 重大规范更新（异步、无状态等） | 协议走向成熟 |
| 2025.12 | 捐赠给 Linux 基金会 | 成为真正的行业公共标准 |

截至 2025 年底，MCP 生态已有 **5,800+ Server、300+ Client**，
SDK 月下载量超过 **9,700 万次**。

> 🌐 **In English:** MCP was released by Anthropic in Nov 2024. By late 2025, OpenAI, Google, and Microsoft had all adopted it. It was donated to the Linux Foundation with 5,800+ servers and 97M+ monthly SDK downloads.

---

## 🆚 MCP vs 传统 API vs 插件系统

很多人第一反应是："这不就是 API 吗？"
不完全是。下面是关键区别：

| 维度 | 传统 REST API | 插件系统（如 ChatGPT Plugins） | MCP |
|:---|:---|:---|:---|
| 标准化程度 | 每家各写各的 | 平台私有标准 | 开放行业标准 |
| 发现机制 | 需要文档手动查 | 平台商店 | 协议内置发现能力 |
| 双向通信 | 通常单向请求 | 单向 | 支持双向实时通信 |
| 跨平台 | 取决于实现 | 锁定单一平台 | 一次实现，到处可用 |

MCP 底层使用 **JSON-RPC 2.0** 进行消息传输，
设计思路借鉴了编程领域成熟的 **LSP（Language Server Protocol，语言服务协议）**。

> 🌐 **In English:** MCP differs from traditional APIs and proprietary plugin systems by being an open, bidirectional, cross-platform standard with built-in tool discovery — built on JSON-RPC 2.0 and inspired by the Language Server Protocol.

---

## ⚠️ 常见误解

> **误解 1**："MCP 就是另一种 API"
>
> **澄清**：API 是具体的接口实现，MCP 是一套协议标准。
> 就像 HTTP 是协议，而某个网站的接口才是 API。

> **误解 2**："MCP 只有 Anthropic 在用"
>
> **澄清**：截至 2025 年底，OpenAI、Google、微软、AWS、Cloudflare
> 等都已采用或参与治理。MCP 已捐赠给 Linux 基金会下的 Agentic AI Foundation。

> **误解 3**："MCP 会取代现有 API"
>
> **澄清**：MCP 是在现有 API 之上的一层标准化封装。
> 已有的 API 可以通过 MCP Server 暴露出来，两者是互补关系。

> 🌐 **In English:** MCP is not "just another API" — it's a protocol standard (like HTTP vs. a specific endpoint). It doesn't replace APIs but wraps them in a standardized layer. All major AI companies now support it.

---

## 🏢 实际案例：谁在用 MCP？

- **Notion** — 构建了 MCP Server，让 AI 助手直接管理笔记和文档
- **Stripe** — 通过 MCP 暴露支付工作流，AI 可以自动化收款操作
- **GitHub** — 用 MCP 封装工程流程，AI Agent 可自动创建 PR、管理 Issue
- **Hugging Face** — 模型管理和数据集搜索通过 MCP 提供
- **Postman** — API 测试工作流通过 MCP 对外开放

这些案例说明一个趋势：**SaaS 产品正在把自己变成 AI 可调用的工具**。

> 🌐 **In English:** Major SaaS companies like Notion, Stripe, GitHub, and Hugging Face have built MCP servers — signaling a trend where products expose their capabilities as AI-callable tools.

---

## 🎯 PM 视角：MCP 可能改变什么？

作为产品经理，MCP 带来三个值得关注的变化：

**1. 生态格局重塑**
以前，平台通过"独家插件生态"锁定开发者（想想 ChatGPT Plugins）。
MCP 让工具的"可连接性"变成通用能力，**平台的护城河从"生态锁定"转向"体验差异化"**。

**2. 产品能力边界扩展**
你的 AI 产品不再需要内置所有功能。
通过 MCP，可以**按需连接外部能力**，像搭积木一样组合产品功能。

**3. 新的竞争维度**
未来可能出现一个问题：你的产品有 MCP Server 吗？
**没有 MCP 接口的 SaaS 工具，可能会被 AI 生态排除在外。**

> 🌐 **In English:** For PMs, MCP reshapes platform competition (from ecosystem lock-in to experience differentiation), expands product capability boundaries (plug-and-play tools), and creates a new competitive dimension (products without MCP may be excluded from the AI ecosystem).

---

## 🧪 动手试试

如果你想亲手体验 MCP 的工作方式：

1. **最简单的方式**：安装 Claude Desktop，在设置中启用一个 MCP Server（如文件系统）
2. **开发者方式**：用 TypeScript/Python SDK 写一个简单的 MCP Server
3. **观察方式**：注意 Claude Code 中的工具调用——每个 `mcp__` 前缀的工具就是一个 MCP Server 提供的

---

## 📝 本篇小结

| 要点 | 内容 |
|:---|:---|
| MCP 是什么 | AI 工具连接的开放协议标准 |
| 核心价值 | 把 M×N 问题简化为 M+N |
| 三个核心概念 | Server、Client、Protocol |
| 行业地位 | 三大 AI 巨头 + 微软/AWS 等全部采用 |
| PM 关注点 | 生态格局、能力边界、竞争维度 |

---

## 🔗 延伸阅读

- [Anthropic 官方 MCP 介绍](https://www.anthropic.com/news/model-context-protocol)
- [MCP 官方规范](https://modelcontextprotocol.io/specification/2025-11-25)
- [MCP 一周年回顾](http://blog.modelcontextprotocol.io/posts/2025-11-25-first-mcp-anniversary/)
- [MCP 企业采用指南](https://guptadeepak.com/the-complete-guide-to-model-context-protocol-mcp-enterprise-adoption-market-trends-and-implementation-strategies/)

---

> **下一篇**：[05 什么是 Skills？为什么会出现这个概念](05_what_skills_are_and_why_they_emerged.md)
>
> **上一篇**：[02 什么是 Workflow？什么是 Agent？](02_workflows_vs_agents.md)

---

*最后更新：2026-03 | 作者：Charlie FocusLab*
