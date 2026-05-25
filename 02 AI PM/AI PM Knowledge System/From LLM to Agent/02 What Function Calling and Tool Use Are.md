> **适读人群**：零基础产品经理 · 无需编程经验
> **阅读时间**：8 分钟
> **前置知识**：了解 LLM（大语言模型）能"对话"即可

---

## 📌 一句话版本

**Function Calling 就是让 LLM 不只"会说"，还"能做事"的机制。**

> 🌐 **In English:**
> Function Calling allows an LLM to invoke external tools
> — turning a chatbot into an assistant that takes action.

---

## 📖 在讲什么

你用过 ChatGPT，知道它很能聊。
但你有没有发现——它聊得再好，也不能帮你真的查天气、订机票、改数据库？

**Function Calling（函数调用 / 工具调用）** 就是解决这个问题的：

它让 LLM 在"说话"之外，获得一种新能力——
**向外部工具发出结构化请求，让系统代替它去"做事"。**

打个比方：LLM 以前是一个只能写纸条的秘书；
Function Calling 给了它一部电话，现在它能打电话叫外卖、叫快递、查快递单号了。

> 🌐 **In English:**
> LLMs can only generate text. Function Calling gives them
> the ability to request structured actions — like calling
> an API, querying a database, or sending an email —
> through external tools.

---

## 💡 人话解释

想象你有一个超级聪明的实习生小 A：

| 场景 | 没有 Function Calling | 有了 Function Calling |
|------|----------------------|----------------------|
| 你问天气 | 小 A 猜一个答案给你 | 小 A 打电话问气象台 |
| 你让发邮件 | 小 A 把邮件内容写好给你看 | 小 A 直接帮你把邮件发出去 |
| 你查数据 | 小 A 凭记忆编一个数字 | 小 A 去数据库跑一条查询 |

**关键区别：从"只能说"变成"能做"。**

更准确地说：

- LLM 自己 **并不执行** 工具，它只是 **告诉系统** "我需要调用哪个工具、传什么参数"
- **系统负责真正执行**，然后把结果还给 LLM
- LLM 拿到结果后，再组织成自然语言回复你

> 🌐 **In English:**
> The LLM doesn't run the tool itself. It outputs a
> structured request ("call weather API, city=Beijing").
> The system executes it, returns the result, and the LLM
> composes a final answer for the user.

---

## 📐 正式定义

**Function Calling** 是大语言模型（LLM, Large Language Model）
的一种能力，指模型在对话过程中，根据用户意图，
**输出结构化的工具调用请求**（通常为 JSON 格式），
由外部系统执行后将结果返回模型，
模型再据此生成最终回答。

> 该能力由 OpenAI 于 2023 年 6 月首次发布，
> 随后 Anthropic（Claude）、Google（Gemini）等主流模型跟进支持。

> 🌐 **In English:**
> Function Calling is the LLM's ability to output
> structured tool-invocation requests (typically JSON)
> during a conversation. The external system executes the
> request and feeds the result back to the model.

---

## 🔍 怎么出现的

### 1. LLM 的先天局限

LLM 的训练数据有截止日期，它不知道"今天天气"；
它也没有手和脚，不能操作数据库、不能发邮件。

### 2. 早期的"土方法"

开发者曾经用 Prompt 让 LLM 输出特定格式的文本，
然后自己写正则表达式去解析——脆弱、容易出错。

### 3. 官方标准化

2023 年，OpenAI 率先在 API 中加入 Function Calling 功能：

- 开发者预先定义好"工具清单"（名称 + 参数格式）
- LLM 在需要时，直接输出标准 JSON 调用请求
- 不再需要手动解析，稳定性大幅提升

### 4. 成为行业标准

目前主流 LLM 均支持 Function Calling，
它是 **Agent（智能体）** 和 **MCP（模型上下文协议）** 的基石。

> 🌐 **In English:**
> LLMs have no real-time data and cannot perform actions.
> Early hacks used regex to parse model output.
> In June 2023, OpenAI standardized Function Calling in
> its API, and it quickly became an industry standard.

---

## 🔧 技术流程（简化版）

以"帮我查北京明天天气"为例，完整流程只有 5 步：

```
用户："帮我查北京明天天气"
         │
         ▼
┌──────────────────────────┐
│  ① LLM 理解意图          │
│  判断：需要调用天气工具   │
└──────────┬───────────────┘
           ▼
┌──────────────────────────┐
│  ② LLM 输出调用请求      │
│  {                       │
│    "tool": "get_weather", │
│    "city": "北京",        │
│    "date": "明天"         │
│  }                       │
└──────────┬───────────────┘
           ▼
┌──────────────────────────┐
│  ③ 系统执行真正的 API    │
│  调用天气服务 → 拿到结果  │
└──────────┬───────────────┘
           ▼
┌──────────────────────────┐
│  ④ 结果返回给 LLM        │
│  {"天气":"晴","温度":22}  │
└──────────┬───────────────┘
           ▼
┌──────────────────────────┐
│  ⑤ LLM 生成自然语言回复  │
│  "北京明天晴，22℃，适合  │
│   出门~"                  │
└──────────────────────────┘
```

> **PM 要记住的重点：LLM 只负责"判断"和"表达"，不负责"执行"。**

> 🌐 **In English:**
> 1. User asks → 2. LLM outputs a structured tool call →
> 3. System executes the real API → 4. Result returns to
> LLM → 5. LLM composes a natural-language answer.

---

## ⚖️ 概念对比

### 纯 LLM 对话 vs Function Calling

| 维度 | 纯 LLM 对话 | LLM + Function Calling |
|------|------------|----------------------|
| 能力边界 | 只能生成文本 | 可调用外部工具 |
| 实时性 | 知识有截止日期 | 可查询实时数据 |
| 准确性 | 可能"幻觉"编造 | 基于真实数据回答 |
| 行动力 | 不能执行操作 | 能触发真实动作 |

### 相关概念关系

| 概念 | 一句话说明 | 与 FC 的关系 |
|------|----------|-------------|
| Function Calling | LLM 调用单个工具 | 本篇主角 |
| Agent（智能体） | LLM 自主规划 + 多步调用 | FC 是 Agent 的基础能力 |
| MCP | 工具接入的统一标准 | 规范 FC 的"电话簿"格式 |
| Workflow（工作流） | 预设的固定流程 | 可包含 FC 作为某个步骤 |

> 🌐 **In English:**
> Pure LLM = text only. Function Calling = text + action.
> FC is the foundation for Agent, MCP, and Workflow.

---

## 🎯 PM 视角：这跟我有什么关系？

### 1. 设计 AI 产品时，你要决定"给 LLM 哪些工具"

这就像给实习生列一张"你可以打这些电话"的清单：

| 工具名称 | 功能说明 | 使用场景 |
|---------|---------|---------|
| `search_product` | 搜索商品信息 | 用户问"有没有红色连衣裙" |
| `check_order` | 查询订单状态 | 用户问"我的快递到哪了" |
| `create_ticket` | 创建工单 | 用户要求"帮我投诉" |

> **PM 的核心工作：定义工具清单 + 每个工具的触发条件。**

### 2. 你要理解"LLM 可能调错工具"

就像实习生可能理解错意思，打错电话。
所以你需要：

- 工具命名清晰，避免歧义
- 给每个工具写明确的描述（Description）
- 设计兜底方案：调错了怎么办？

### 3. 你要规划"哪些功能需要 Function Calling"

一个简单的判断标准：

> **如果用户的需求需要"查真实数据"或"触发真实操作"，**
> **那就需要 Function Calling。**

- 闲聊、写文案、翻译 → 不需要
- 查库存、下单、发通知 → 需要

### 4. 你要关注安全边界

给 LLM 工具，就像给员工权限：

- 只读操作（查询）→ 风险低
- 写操作（下单、删除）→ 需要二次确认机制
- 敏感操作（付款、修改密码）→ 必须人工审批

> 🌐 **In English:**
> As a PM, you define which tools the LLM can use, write
> clear descriptions, plan fallback logic, and set safety
> boundaries — especially for write/delete operations.

---

## ⚠️ 常见误解

### 误解 1："LLM 自己能执行工具"

> **事实**：LLM 只输出"我想调用什么"的 JSON，
> 真正执行的是你的后端系统。

### 误解 2："有了 Function Calling 就不会幻觉了"

> **事实**：LLM 可能"幻觉"出一个不存在的工具名，
> 或者给工具传错参数。需要系统侧做校验。

### 误解 3："Function Calling = Agent"

> **事实**：Function Calling 是单次工具调用；
> Agent 是多步骤自主规划 + 多次调用。
> FC 是 Agent 的基础零件，但不等于 Agent。

### 误解 4："所有 LLM 的 Function Calling 都一样"

> **事实**：不同厂商的实现细节不同
> （参数格式、并行调用支持等），但核心理念一致。

> 🌐 **In English:**
> Common myths: LLM does NOT execute tools itself;
> Function Calling does NOT eliminate hallucinations;
> FC is NOT the same as Agent — it's one building block.

---

## 🧪 试试看

### 练习 1：判断是否需要 Function Calling

下面哪些场景需要 Function Calling？打勾即可：

- [ ] 用户说"帮我写一封感谢邮件"
- [ ] 用户说"帮我把这封邮件发给张总"
- [ ] 用户说"今天股票涨了吗"
- [ ] 用户说"帮我总结这篇文章"
- [ ] 用户说"帮我在系统里创建一个新客户"

> **答案**：第 2、3、5 题需要。
> 写邮件和总结文章只需要生成文本；
> 发邮件、查股票、创建客户需要调用外部系统。

### 练习 2：设计工具清单

假设你在做一个"AI 客服助手"，请列出 3-5 个工具：

| 工具名称 | 功能 | 输入参数 |
|---------|------|---------|
| 例：`query_order` | 查询订单状态 | 订单号 |
| ? | ? | ? |
| ? | ? | ? |
| ? | ? | ? |

> 试着自己填完，然后想想：
> 哪些是只读的？哪些是写操作？哪些需要二次确认？

> 🌐 **In English:**
> Exercise 1: Identify which user requests need FC.
> Exercise 2: Design a tool list for an AI customer
> service assistant, and classify read vs. write tools.

---

## 📝 要点回顾

1. **Function Calling 让 LLM 从"会说"变成"能做"**
2. **LLM 只负责判断和表达，系统负责执行**
3. **流程：用户问 → LLM 判断 → 输出调用 → 系统执行 → 返回结果**
4. **PM 的工作：定义工具清单 + 触发条件 + 安全边界**
5. **FC 是理解 Agent、MCP 的基础概念**

---

### 📝 Key Takeaways

> 1. Function Calling turns LLMs from "talkers" into
>    "doers" by letting them invoke external tools.
> 2. The LLM only outputs a structured request; the
>    system executes the actual operation.
> 3. Flow: User → LLM decides → Tool call → System
>    executes → Result → LLM answers.
> 4. PM's job: define the tool list, trigger rules,
>    and safety boundaries.
> 5. Function Calling is the foundation for
>    understanding Agent, MCP, and AI workflows.

---

## 📚 延伸阅读

| 资源 | 说明 |
|------|------|
| OpenAI Function Calling 官方文档 | 最权威的技术说明 |
| Anthropic Tool Use 文档 | Claude 的工具调用实现 |
| 本系列下一篇：Workflow 与 Agent | 从单次调用到多步规划 |
| 本系列第四篇：什么是 MCP | 工具接入的统一标准 |

---

> 📎 **本篇定位**：03_从LLM到Agent 系列 · 第 1 篇
> **下一篇**：→ 02_什么是Workflow_什么是Agent
> **系列目标**：帮你从"LLM能聊天"理解到"AI能自主做事"
