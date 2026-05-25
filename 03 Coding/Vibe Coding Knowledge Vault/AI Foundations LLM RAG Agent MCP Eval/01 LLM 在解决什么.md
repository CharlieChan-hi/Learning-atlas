> 📌 **一句话版本：** 如果把现代 AI 应用看成一条链，那么 `LLM` 是大脑，`RAG` 是补资料，`Agent` 是会做事的流程层，`MCP` 是把外部工具和上下文接进来的标准化接口层。

---

## 📖 这一节在讲什么

很多人会把这些词混在一起说，但它们解决的不是同一个问题。搞清楚这四个概念，你后面看 AI 产品、工具工作流、Agent 编排时就不会乱。

## 🧠 LLM 在解决什么

`LLM` 本质上是一个能理解和生成语言、代码与多模态内容的通用推理与生成模型。它擅长总结、解释、改写、生成和推理，但它并不天然拥有最新外部知识和真实执行能力。

## 🧠 RAG 在解决什么

`RAG` 是让模型在回答前先查外部资料，再结合资料生成答案。它解决的是“模型记忆不全、知识过旧、需要基于私有资料回答”的问题。

## 🧠 Agent 在解决什么

`Agent` 更像“带流程的模型使用方式”。它不只是回答一次，而是可以规划步骤、调用工具、读取上下文、连续推进任务。

## 🧠 MCP 在解决什么

`MCP` 可以理解成让模型标准化访问外部工具和上下文的一层协议或接口方式。它让设计、文档、浏览器、数据库、搜索等能力更容易接进 agent 工作流。

> 🌐 **In English:**
> LLMs generate and reason, RAG adds external knowledge, agents add workflow and tool use, and MCP standardizes how tools and context are connected.

## 🎯 对 PM 最重要的理解

- 不是每个 AI 功能都需要 Agent
- 不是每个问答都需要 RAG
- 不是接了工具就一定更可靠
- 真正关键的是：问题场景和系统结构是否匹配

## 🧩 这四个词最容易被混用的原因

因为它们经常同时出现在同一个产品里。

例如一个 AI coding 工具可能同时具备：

- 一个强大的 `LLM`
- 从代码仓或文档里检索资料的能力
- 连续执行任务的 Agent 工作流
- 通过 `MCP` 接浏览器、设计稿和文档工具

这时候如果不把层次分清，你就很容易把“模型强”误以为“整个系统设计就对了”。

## 🎯 怎么用“问题导向”区分它们

### 如果问题是“模型不知道最新资料”

你更应该想到 `RAG`。

### 如果问题是“模型不会实际做事”

你更应该想到 `Agent` 和工具调用。

### 如果问题是“工具不好接、上下文源不统一”

你更应该想到 `MCP` 这类接入层。

### 如果问题是“生成质量本身不够好”

你更应该回到 `LLM`、Prompt 和 Eval。

> 🌐 **In English:**
> A useful way to separate these concepts is to ask which problem you are solving: weak knowledge, lack of action, poor tool integration, or poor generation quality.

## 💡 一个更贴近产品设计的理解

你可以把这四层想成：

- `LLM`：能力核心
- `RAG`：外部知识补给
- `Agent`：任务编排与执行
- `MCP`：工具与上下文接入标准

这样你在评估一个 AI 产品方案时，就更容易知道它缺的是哪一层。

## ⚠️ 最容易产生的误判

### 误判一：用了 Agent 就一定更高级

很多简单问题，直接问答或结构化输出就够了，Agent 反而会增加复杂度。

### 误判二：接了很多工具就一定更强

工具越多，噪音、权限、上下文污染和验证成本也会变大。

### 误判三：RAG 等于“答案一定正确”

RAG 只能补资料，不自动保证理解、筛选和最终输出都正确。

## 🧪 一个很好用的评估问题

你以后看到一个 AI 功能时，可以快速问：

1. 它主要靠什么层在工作
2. 它最核心的短板在知识、执行、接入，还是质量
3. 如果要优化，应该优先补哪一层

这个问题框架，会让你看 AI 产品时更像在拆系统，而不是在看热闹。

## 📝 记住这些

- `LLM`、`RAG`、`Agent`、`MCP` 是一条能力链，不是同义词。
- 你越会区分它们，越能在做产品方案时少走弯路。
- 工具越多，系统越强，但也越需要控制复杂度和风险。

## 📚 延伸阅读

- [01_Prompt_上下文_记忆与工具调用.md](01_prompts_context_memory_and_tool_use.md)
- [03_JSON_Schema_结构化输出与工作流编排.md](03_json_schema_structured_output_and_workflow_orchestration.md)
- [02_MCP_工具调用_上下文与记忆.md](../10_ai_coding_tools_codex_cli_claude_code/02_mcp_tool_use_context_and_memory.md)
