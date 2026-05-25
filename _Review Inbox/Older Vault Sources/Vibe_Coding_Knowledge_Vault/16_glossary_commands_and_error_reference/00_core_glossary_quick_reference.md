> 📌 **一句话版本：** 这一页把整套知识库里最高频、最容易混淆的核心术语用最短路径串起来，方便你随时查和快速回忆。

---

## 📖 这一节在讲什么

学到后面你会发现，自己不一定是不懂，很多时候只是“术语暂时卡住了”。所以这一模块的价值不是教学，而是高频速查。

## 🧠 高频术语

- `JSON`：结构化数据格式
- `API`：系统之间约定的交互接口
- `HTTP`：客户端和服务端通信协议
- `State`：页面或系统当前状态
- `RAG`：先取资料再生成
- `Agent`：可连续规划和调用工具的 AI 使用方式
- `MCP`：标准化工具和上下文接入方式
- `CI/CD`：自动化集成与发布流程
- `Token`：常见身份凭证
- `Cache`：用来加速读取的缓存层

> 🌐 **In English:**
> This glossary helps you quickly reconnect key terms to their practical meaning in engineering and AI workflows.

## 🎯 怎样更有效地使用术语表

术语表最怕被当成“背定义”的材料。更有效的用法是：

- 遇到陌生词时先查它
- 但不要停在定义
- 继续追问它在流程里解决什么问题

例如你查到 `RAG`，真正重要的不是记住全称，而是知道它是在补外部资料能力。

## 💡 再补一批高频术语

### `Prompt`

给模型的任务说明，不只是问题本身，还可能包括目标、边界、输出格式和验证要求。

### `Schema`

一套结构约束规则，帮助你定义数据应该长什么样。

### `Token`

在不同上下文里可能表示不同东西，但在这套资料里你最常碰到的是：

- 身份凭证
- 模型计费和上下文长度单位

### `Diff`

改动前后差异的对比视图，是读 Git 和 AI 改动时非常重要的东西。

### `Rollback`

把系统尽量带回更稳定状态的动作，不只是“撤销代码”这么简单。

### `Idempotency`

幂等性，意思是同一个操作重复执行，不应产生重复副作用。这在接口、支付、重试和异步任务里特别重要。

> 🌐 **In English:**
> A glossary becomes useful when each term is connected to a system role, not just to a short definition.

## ⚠️ 最容易混淆的几组词

### `Authentication` vs `Authorization`

- 前者是你是谁
- 后者是你能做什么

### `Concurrency` vs `Parallelism`

- 并发强调多任务交错推进
- 并行强调真实同时执行

### `RAG` vs `Agent`

- RAG 更偏“查资料再回答”
- Agent 更偏“规划步骤并调用工具做事”

## 🧪 一个很好用的术语学习方法

每次遇到术语时，用一句话补完整：

“这个词在系统里，是用来解决 ______ 问题的。”

只要你能把空填上，术语就不容易再次变成空壳。

## 📝 记住这些

- 术语的价值不在定义本身，而在你能不能把它和真实场景连起来。
- 以后查术语时，优先问自己“它在流程里解决什么问题”。

## 📚 延伸阅读

- [00_总目录与文件清单.md](../00_directory_index_and_file_list.md)
- [00_LLM_RAG_Agent_MCP全景图.md](../09_ai_foundations_llm_rag_agent_mcp_eval/00_llm_rag_agent_mcp_overview.md)
