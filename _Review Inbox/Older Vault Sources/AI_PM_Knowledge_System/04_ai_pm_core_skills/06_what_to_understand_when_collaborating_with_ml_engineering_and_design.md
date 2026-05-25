> **阅读时间**：15 分钟 | **难度**：入门 | **前置知识**：了解 AI 基本概念（见 01-03 篇）
>
> 💡 **一句话摘要**：AI PM 不需要比每个人更专业，但需要能和每个人「说上话」。

---



## 📑 目录

1. [为什么协作方式不同了](#-1-为什么协作方式不同了)
2. [和算法工程师协作](#-2-和算法工程师ml-engineer协作)
3. [和后端/全栈工程师协作](#-3-和后端全栈工程师协作)
4. [和设计师协作](#-4-和设计师协作)
5. [完整协作案例：AI 客服产品](#-5-完整协作案例做一个-ai-客服产品)
6. [PM 的桥梁角色](#-6-pm-的桥梁角色)
7. [常见误解](#-7-常见误解)
8. [要点总结](#-8-要点总结)
9. [英文 Key Takeaways](#-english-key-takeaways)

---



## 🔍 1. 为什么协作方式不同了

在传统互联网产品中，PM 主要协调的是 **前端 → 后端 → 设计** 三方。

AI 产品多了一个关键角色——**算法工程师（ML/AI Engineer）**，而且后端和设计的工作内容也发生了变化。

| 角色 | 传统产品关注点 | AI 产品关注点 |
|:---|:---|:---|
| 算法工程师 | ——（通常没有） | 模型选择、训练、评测 |
| 后端工程师 | 数据库、接口、逻辑 | + API 调用、成本、延迟 |
| 设计师 | 确定性界面 | + 不确定性状态设计 |

> 🌐 **In English:** AI products add a new collaborator — the ML Engineer — and change the focus areas for backend engineers and designers.

---



## 🤖 2. 和算法工程师（ML Engineer）协作

### 他们关心什么

算法工程师每天打交道的是：

- **模型选择（Model Selection）**——用哪个模型、用多大的模型
- **训练数据（Training Data）**——数据够不够、质量好不好
- **评测指标（Evaluation Metrics）**——准确率、召回率等量化数字
- **性能优化（Performance Optimization）**——推理速度、资源消耗



### PM 需要懂的最低限度

你不需要自己训练模型，但至少要知道这四个词：

| 概念 | 一句话解释 | PM 需要关注 |
|:---|:---|:---|
| 模型（Model） | AI 的"大脑" | 选什么模型影响效果和成本 |
| 训练（Training） | 教 AI 学知识 | 需要多少数据、多长时间 |
| 推理（Inference） | AI 给出答案的过程 | 每次调用都有延迟和成本 |
| 评测（Evaluation） | 考试，看 AI 答得好不好 | 上线标准是什么 |



### 常见沟通场景和话术

在和算法工程师沟通时，掌握几句「内行话」，效率翻倍：

> 📌 **场景 1：选型讨论**
> "这个场景用什么模型比较合适？我们的数据量大概是 XX，期望的响应时间是 XX 秒以内。"

> 📌 **场景 2：目标对齐**
> "现在准确率 85%，目标是多少才能上线？用户可以接受的错误率大概是多少？"

> 📌 **场景 3：方案选择**
> "用 RAG（检索增强生成）还是微调（Fine-tuning）？各自的成本和开发周期是什么？"



### ⚠️ 踩坑点

| 错误说法 | 为什么有问题 | 正确说法 |
|:---|:---|:---|
| "把 AI 做得更准" | 没有具体场景和指标 | "在XX场景下，准确率从85%提到92%" |
| "能不能让 AI 不犯错" | 100%不犯错不现实 | "关键场景的错误率控制在5%以内" |
| "越快越好" | 速度和效果常常矛盾 | "响应时间3秒以内，准确率不低于XX" |

> 🌐 **In English:** Don't say "make AI more accurate" — give specific scenarios and measurable targets. ML Engineers need concrete goals, not vague demands.

---



## 🛠️ 3. 和后端/全栈工程师协作

### 他们关心什么

在 AI 产品中，后端工程师除了传统的数据库和接口外，还要操心：

- **API 接入（API Integration）**——对接大模型的调用接口
- **系统架构（System Architecture）**——怎么把 AI 能力嵌入产品
- **并发处理（Concurrency）**——多人同时用时系统撑不撑得住
- **稳定性（Reliability）**——AI 接口挂了怎么办



### 常见讨论话题

| 话题 | PM 需要了解的 |
|:---|:---|
| 缓存策略（Caching） | 相同问题可以缓存答案，省钱又快 |
| 兜底机制（Fallback） | AI 挂了给用户看什么？不能白屏 |
| 成本控制（Cost Control） | 每次 API 调用都花钱，要设计限流策略 |
| 流式输出（Streaming） | 让用户看到"AI正在打字"，体验更好 |



### PM 需要记住的一件事

> 💡 **大模型是通过 API 调用的（API Call）。每次调用都有两个代价：**
>
> 1. **成本**——按 token（大约每 750 个汉字）计费
> 2. **延迟**——通常 1-10 秒不等

这意味着你在写 PRD 时，必须考虑：
- 每个功能大概要调用几次 API？
- 每月预计调用量是多少？
- 预算能不能覆盖？

> 🌐 **In English:** Every LLM API call costs money and takes time. PMs must estimate call volume and budget during PRD planning, not after launch.

---



## 🎨 4. 和设计师协作

### AI 产品设计的特殊挑战

传统产品的界面是**确定性**的——用户点按钮，出固定结果。

AI 产品的界面充满**不确定性**——同样的输入，可能给出不同的输出。

这给设计带来了新挑战：

| 状态 | 传统产品 | AI 产品 |
|:---|:---|:---|
| 加载中（Loading） | 转圈等一下 | 可能要等 5-10 秒，需要特殊设计 |
| 错误态（Error） | "网络错误，请重试" | "AI 暂时无法回答"，要引导用户 |
| 空状态（Empty） | "暂无数据" | "试试问我这些问题？"引导交互 |
| 结果展示 | 固定格式 | 长短不一、格式多变 |



### 常见讨论话题

- **Loading 状态**：是用骨架屏、还是流式输出、还是进度条？
- **错误态**：AI 出错时给用户什么提示？能不能重试？
- **引导式交互（Guided Interaction）**：新用户不知道怎么用 AI，需要引导
- **结果反馈（Feedback Loop）**：让用户"点赞/点踩"来改善 AI



### PM 需要桥接的认知差

> 🎯 **这是 PM 最独特的价值：**

| 认知鸿沟 | PM 怎么桥接 |
|:---|:---|
| 设计师不懂 AI 的局限 | 告诉设计师"AI 可能答错、答慢、答不上来"，提前设计这些状态 |
| 工程师不懂用户预期 | 告诉工程师"用户期望3秒内响应"、"用户不接受完全错误的答案" |
| 算法不懂产品优先级 | 告诉算法"先把核心场景做到90%，长尾场景后面再优化" |

> 🌐 **In English:** The PM bridges the gap: designers don't know AI limitations, engineers don't know user expectations, and ML engineers don't know product priorities. You connect all three.

---



## 📋 5. 完整协作案例：做一个 AI 客服产品

下面用一个完整案例，串联 PM 与三方的协作全流程。



### 第一步：需求定义（PM 主导）

> PM 输出 PRD，明确目标：
> - 替代 60% 的重复人工客服问题
> - 平均响应时间 < 3 秒
> - 回答准确率 > 90%
> - 月预算 < 5 万元



### 第二步：技术方案讨论（PM + 算法 + 后端）

| 讨论项 | 算法工程师的视角 | 后端工程师的视角 | PM 需要做的 |
|:---|:---|:---|:---|
| 用什么方案 | "用 RAG，接企业知识库" | "我来做检索服务和 API 网关" | 对齐两边方案，确认可行 |
| 数据准备 | "需要整理历史客服对话" | "我提供数据导出接口" | 推动数据整理，确认时间线 |
| 评测标准 | "我测准确率和召回率" | "我监控响应时间和错误率" | 定义上线标准，写进文档 |



### 第三步：交互设计讨论（PM + 设计师）

> PM 和设计师一起确认：
> - 用户输入框 + 流式输出的聊天界面
> - AI 回答后附"是否解决了您的问题？"反馈按钮
> - AI 无法回答时，展示"转人工客服"按钮
> - 首次进入时展示 3 个推荐问题引导用户



### 第四步：开发与迭代（PM 协调三方）

```
Week 1-2: 算法搭建RAG管线 + 后端搭建基础服务
Week 3:   设计师出交互稿 → PM Review → 修改
Week 4:   前后端联调 + 算法接入
Week 5:   内测 + PM组织评测
Week 6:   修复问题 → 灰度上线
```



### 第五步：上线后（PM 持续跟进）

- 看每日指标：响应时间、准确率、转人工率
- 收集用户反馈中的"高频差评"场景
- 推动算法优化差评集中的场景

> 🌐 **In English:** Building an AI customer service product requires the PM to coordinate ML Engineers (RAG pipeline), Backend Engineers (API & infra), and Designers (chat UI & error states) across a 6-week sprint.

---



## 🎯 6. PM 的桥梁角色

> 💡 **核心观点：AI PM 是团队的"翻译官"和"优先级裁判"。**

你的价值不在于比算法更懂模型、比工程更懂架构、比设计更懂美学——

你的价值在于：

1. **翻译需求**：把用户需求翻译成技术语言
2. **对齐目标**：让三方朝同一个方向使劲
3. **排列优先级**：资源有限时决定先做什么
4. **管理预期**：告诉老板 AI 不是万能的，告诉用户 AI 正在变好



| 能力 | 具体表现 |
|:---|:---|
| 和算法对话 | 能用准确率、召回率讨论问题 |
| 和工程对话 | 能理解 API 成本和系统瓶颈 |
| 和设计对话 | 能描述 AI 的不确定性对交互的影响 |
| 和业务对话 | 能用 ROI 来论证 AI 投入是否值得 |

> 🌐 **In English:** The AI PM is a translator and priority judge. Your value is not in outperforming each specialist, but in enabling them to work together effectively.

---



## ⚠️ 7. 常见误解

> 以下是产品经理在跨角色协作中最容易踩的认知坑：

| # | 误解 | 现实 |
|:--|:---|:---|
| 1 | "PM 需要会写代码/训练模型" | 不需要。你需要的是理解概念，能提出正确的问题 |
| 2 | "算法工程师会替我做产品决策" | 他们做技术决策，产品决策还是你的事 |
| 3 | "AI 功能做好了就不用迭代了" | AI 产品需要持续优化，比传统产品更需要 |
| 4 | "设计师自己能设计好 AI 交互" | 设计师需要你告诉他 AI 的能力边界 |
| 5 | "后端接个 API 就行了，很简单" | 稳定性、成本、并发都是大问题 |

> 🌐 **In English:** PMs don't need to code or train models. They need to ask the right questions, make product decisions, and communicate AI's boundaries to every team member.

---



## 📝 8. 要点总结

> **一页纸速览——AI PM 跨角色协作核心要点**

| 协作对象 | 你要懂的核心词 | 你要问的核心问题 |
|:---|:---|:---|
| 算法工程师 | 模型、训练、评测、RAG | "准确率多少？上线标准是什么？" |
| 后端工程师 | API、成本、延迟、兜底 | "每次调用多少钱？挂了怎么办？" |
| 设计师 | 不确定性、Loading、引导 | "AI 出错时用户看到什么？" |



**记住三条原则：**
1. 给技术人员**具体**的目标，不要给**模糊**的方向
2. 在 PRD 阶段就把**成本**和**评测标准**写进去
3. 你是桥梁——确保每个人理解**彼此的约束**

---



## 🌐 English Key Takeaways

> **Collaborating with AI Engineers, Developers, and Designers**
>
> 1. **With ML Engineers:** Speak in metrics — accuracy, recall, latency. Give specific scenarios, not vague requests like "make it better."
>
> 2. **With Backend Engineers:** Understand that every API call costs money and time. Plan for caching, fallback, and cost control from day one.
>
> 3. **With Designers:** Communicate AI's uncertainty. Help them design for loading, errors, empty states, and guided interactions.
>
> 4. **Your role as PM:** You are the translator between three worlds. You don't need to be the expert — you need to ask the right questions and align everyone toward the same goal.
>
> 5. **Key principle:** Write evaluation criteria and cost estimates into your PRD before development starts.

---



> 📖 **下一篇预告**：[07_AI产品从0到1常见坑](07_common_pitfalls_when_building_ai_products_from_zero_to_one.md) —— 从 Demo 到产品的路上，有哪些坑在等你？
>
> ⬅️ **上一篇回顾**：[05_评测体系怎么搭](05_how_to_build_an_evaluation_framework.md)

---

*Charlie's AI PM Knowledge System · 04 AI产品经理核心能力 · 第6篇*
