> 📌 **一句话版本：**
> Workflow 是「人设计路线，AI 走路」；Agent 是「人给目标，AI 自己找路」。

> 🌐 **In English:** Workflow = human designs the steps, AI follows; Agent = human sets the goal, AI figures out the steps.

---

## 📖 在讲什么

这是整套 AI 产品经理知识体系中 **最关键的概念对比之一**。

当我们说"用 AI 做一件事"时，背后其实有两种截然不同的思路：

- **第一种**：把任务拆成明确的步骤，让 AI 按顺序执行 → 这就是 **Workflow（工作流）**
- **第二种**：把目标告诉 AI，让它自己决定怎么做 → 这就是 **Agent（智能体）**

理解这个区别，直接决定了你在设计 AI 产品时选择什么架构、承诺什么效果、承担什么风险。

> 🌐 **In English:** There are two fundamental approaches to building AI products — Workflow (predefined steps) and Agent (autonomous decision-making). Understanding this distinction is essential for product architecture decisions.

---

## 💡 人话解释

想象你是一个老板，要让助手帮你"订一张从北京到上海的机票"。



### 🔹 Workflow 方式：像流水线工人

你给助手一张清单：

| 步骤 | 具体操作 | 谁决定的 |
|:---:|:---|:---:|
| 第 1 步 | 打开携程搜索航班 | 你 |
| 第 2 步 | 筛选直飞 + 经济舱 | 你 |
| 第 3 步 | 选最便宜的那班 | 你 |
| 第 4 步 | 下单并付款 | 你 |

助手 **只管执行**，一步接一步，不会跳步，不会自作主张。



### 🔹 Agent 方式：像一个能独立思考的助手

你只说了一句话："帮我订一张明天北京到上海的机票。"

这个助手会 **自己思考**：

- "明天有哪些航班？我先查一下日期和价格。"
- "用户之前都坐东航，可能有偏好，我先问一句？"
- "发现明天经济舱很贵，要不要推荐后天的？主动问一下。"
- "找到了最优方案，整理好给用户确认。"

助手自己决定 **先做什么、后做什么、要不要追问**。

> 🌐 **In English:** Workflow = a checklist your assistant follows step-by-step. Agent = a smart assistant who figures out the best approach on their own, even asking clarifying questions when needed.

---

## 📐 正式定义

| 概念 | 定义 |
|:---|:---|
| **Workflow（工作流）** | 一种 **预定义执行流程** 的系统架构。由人类设计好每个节点的输入、输出和流转逻辑，AI 在每个节点内完成特定任务，但节点之间的流转顺序是固定的。 |
| **Agent（智能体）** | 一种具有 **自主决策能力** 的 AI 系统。给定目标后，Agent 自行规划步骤、调用工具、评估结果，并根据中间反馈动态调整行动策略。 |

> 🌐 **In English:** **Workflow** — a system with predefined execution flow where AI handles tasks at each node but transitions are fixed. **Agent** — an autonomous AI system that plans, executes, evaluates, and adapts its strategy dynamically given a goal.

---

## 🔍 怎么出现的

### Workflow 的由来

Workflow 并不是 AI 时代的新概念。传统软件开发中就有"工作流引擎"（如 BPMN 流程引擎）。AI 时代的 Workflow 只是把其中某些节点换成了大模型（LLM, Large Language Model）调用。

代表工具：**Dify、Coze、LangChain** 等都提供了可视化的 Workflow 搭建界面。

### Agent 的由来

Agent 的概念更早来源于人工智能学术界（如"BDI Agent"理论）。但真正让它走入大众视野的是 2023 年：

- **AutoGPT**（2023 年 3 月）：第一个爆火的开源 Agent 项目
- **GPT-4** 的推理能力提升，使得 Agent "看起来能干活"了
- **Function Calling（函数调用）** 机制成熟，让 LLM 能调用外部工具

> 🌐 **In English:** Workflows evolved from traditional BPM engines — AI just replaced some nodes with LLM calls. Agents emerged from academic AI theory but became mainstream in 2023, driven by AutoGPT, GPT-4's reasoning, and Function Calling capabilities.

---

## ⚖️ 概念对比：Workflow vs Agent

| 维度 | 🔹 Workflow（工作流） | 🔸 Agent（智能体） |
|:---|:---|:---|
| **谁决定下一步** | 人类预先设计 | AI 自主决策 |
| **可控性** | ⭐⭐⭐⭐⭐ 高 | ⭐⭐ 低 |
| **灵活性** | ⭐⭐ 低 | ⭐⭐⭐⭐⭐ 高 |
| **可预测性** | 输入相同 → 路径相同 | 输入相同 → 路径可能不同 |

| 维度 | 🔹 Workflow（工作流） | 🔸 Agent（智能体） |
|:---|:---|:---|
| **调试难度** | 低，按节点排查 | 高，链路复杂不确定 |
| **成本** | 可控（固定调用次数） | 不可控（可能反复调用） |
| **风险等级** | 低 | 中-高 |
| **适用场景** | 流程明确、容错度低 | 流程不固定、需要创造性 |



### 🏷️ 一个简单的类比

> **Workflow** = 导航地图上的固定路线（你设定起点终点和路线，它照走）
>
> **Agent** = 一个老司机（你告诉他目的地，他自己判断走哪条路，遇到堵车还会变道）

> 🌐 **In English:** Workflow is like GPS with a fixed route — predictable but rigid. Agent is like an experienced driver — flexible but unpredictable. Workflow excels in controlled, low-risk processes; Agent suits open-ended, creative tasks.

---

## 🎯 PM 视角：什么时候用 Workflow，什么时候用 Agent

### ✅ 优先选 Workflow 的场景

- 业务流程 **已经很清晰**（如客服话术、合同审批、数据报表生成）
- 对结果的 **一致性要求高**（每次输出格式一样）
- 需要向客户/老板 **解释 AI 做了什么**（可追溯）
- 预算有限，需要 **成本可控**

### ✅ 考虑用 Agent 的场景

- 任务本身 **无法提前穷举所有步骤**（如开放式研究、复杂信息整理）
- 容错度较高，**错了可以重来**（如写一篇文章初稿）
- 需要 AI **主动调用多种工具**（如搜索+计算+绘图的组合）

### 🚩 PM 必须知道的真相

> **目前行业现状（2025年）：大多数真正在生产环境跑的 AI 产品，用的是 Workflow，不是 Agent。**

很多团队高估了 Agent 的能力。Agent 的 demo 演示很惊艳，但一到真实场景就暴露问题：

1. **稳定性不足**：同一个任务跑 10 次，可能有 3 次走偏
2. **成本飙升**：Agent 自主决策意味着多轮调用，API 费用可能是 Workflow 的 5-10 倍
3. **无法解释**：老板问"AI 为什么这么做"，你答不上来
4. **调试地狱**：出了 bug 你甚至不知道从哪一步开始错的

> 🌐 **In English:** Most production AI products in 2025 use Workflows, not Agents. Agents look impressive in demos but face real-world issues: inconsistency, high costs (5-10x), poor explainability, and debugging nightmares. Use Workflows for structured, low-risk tasks; reserve Agents for open-ended, fault-tolerant scenarios.

---

## ⚠️ 常见误解

| # | 误解 | 真相 |
|:---:|:---|:---|
| 1 | "Agent 一定比 Workflow 更高级、更好" | 错。大多数场景 Workflow 更靠谱、更省钱、更好维护 |
| 2 | "用了大模型就算 Agent" | 错。只有具备 **自主决策+工具调用+动态规划** 的系统才是 Agent |
| 3 | "Workflow 太简单了，没技术含量" | 错。设计一个好的 AI Workflow 需要深刻理解业务逻辑和 Prompt 工程 |
| 4 | "Agent 很快就能替代人类完成所有工作" | 过于乐观。目前 Agent 只在特定垂直领域有可靠表现 |

> 🌐 **In English:** Common myths: "Agents are always better" (wrong — Workflows are more reliable for most cases), "Any LLM usage is an Agent" (wrong — Agents require autonomous planning + tool use), "Workflows are too simple" (wrong — good Workflow design demands deep domain expertise).

---

## 🧪 试试看

### 动手练习：用"订机票"需求分别画 Workflow 和 Agent 的执行路径

**任务**：用户说"帮我订一张明天北京飞上海的机票，要最便宜的"。

**练习 1 — 画 Workflow 流程图：**

用方框和箭头画出固定步骤（建议 4-6 步），标注每步的输入和输出。

**练习 2 — 模拟 Agent 的思考过程：**

写出 Agent 可能的"内心独白"——它会怎么规划、可能在哪里追问用户、可能尝试几条路径。

**练习 3 — 对比反思：**

| 对比点 | 你的 Workflow 方案 | 你的 Agent 方案 |
|:---|:---|:---|
| 总共调用 LLM 几次？ | | |
| 能保证每次结果一样吗？ | | |
| 如果航班信息有误，谁负责？ | | |

> 🌐 **In English:** Try it yourself — for the task "Book the cheapest flight from Beijing to Shanghai tomorrow," design both a Workflow (fixed steps) and an Agent approach (autonomous reasoning). Then compare: How many LLM calls? Is the output consistent? Who handles errors?

---

## 📝 要点回顾

1. **Workflow = 人定步骤，AI 执行**；可控、可预测、成本低，适合流程明确的场景
2. **Agent = 人定目标，AI 自主规划**；灵活、智能，但不稳定、成本高、难调试
3. **不是 Agent 就一定比 Workflow 好**——选哪个取决于业务场景
4. **2025 年现状**：绝大多数落地产品用的是 Workflow
5. **PM 的核心判断力**：看清需求本质，选对技术架构



> ### 🔑 Key Takeaways
>
> 1. **Workflow** = Human designs steps, AI executes. Predictable, controllable, cost-effective.
> 2. **Agent** = Human sets goals, AI plans autonomously. Flexible but unstable and expensive.
> 3. Agent is NOT always better than Workflow — the right choice depends on the use case.
> 4. In 2025, most production AI products run on Workflows, not Agents.
> 5. A PM's core skill: match the right architecture (Workflow vs Agent) to the right problem.

---

## 📚 延伸阅读

| 资源 | 说明 |
|:---|:---|
| Anthropic — *Building effective agents*（2024） | Anthropic 官方对 Agent 设计模式的深度解析，强烈推荐 |
| LangChain 官方文档 — Agents vs Chains | 从代码层面理解 Workflow（Chain）和 Agent 的区别 |
| Dify / Coze 产品文档 | 国内主流 AI Workflow 平台，体验搭建流程 |
| Andrew Ng — *Agentic Design Patterns*（2024） | 吴恩达总结的四种 Agent 设计模式，深入浅出 |
| 《AI Agent 产品设计指南》（各社区文章） | 搜索关键词：AI Agent 产品设计、Agent 落地实践 |

---

> *本篇属于「03_从 LLM 到 Agent」系列第 2 篇。下一篇将聊聊 Agent 为什么火——以及为什么容易被吹过头。*
