> **阅读时间**：12 分钟
> **适合人群**：零基础传统互联网产品经理
> **前置知识**：了解 API 调用的基本概念即可

---

## 📌 导读

做传统产品，你关心的是功能做没做、Bug 多不多。

做 AI 产品，你每天要做的核心决策变了——**在成本、延迟和质量之间，选哪两个？**

这三者构成了一个"不可能三角"（Impossible Triangle），就像项目管理中的"快、好、便宜只能选两个"一样。理解这个框架，是 AI PM 最基本的日常决策能力。

> 🌐 **In English:** In AI products, the daily core decision shifts to choosing between **Cost, Latency, and Quality** — you can optimize for two, but rarely all three. This is the "Iron Triangle" every AI PM must master.

---

## 🔺 第一节：什么是"不可能三角"

### 三个顶点的含义

| 维度 | 含义 | 类比 |
|:---|:---|:---|
| **质量（Quality）** | 模型回答的准确性、完整性、相关性 | 餐厅菜品口味 |
| **延迟（Latency）** | 用户从发起请求到看到结果的等待时间 | 上菜速度 |
| **成本（Cost）** | 每次 API 调用（API Call）的费用 | 菜品价格 |

### 为什么不能三者兼得

大模型（LLM, Large Language Model）的基本规律：

- **模型越大** → 质量越高，但推理（Inference）越慢、费用越贵
- **模型越小** → 速度越快、越便宜，但回答质量可能下降
- **Prompt 越长** → 上下文越丰富、质量越好，但延迟越高、Token 费用越多

> 🌐 **In English:** Larger models yield higher quality but cost more and run slower. Smaller models are fast and cheap but may sacrifice accuracy. Longer prompts improve context but increase latency and token costs.

---

## 📊 第二节：真实数据感知

下表帮你建立直觉——同一个问题，不同模型的表现差异有多大：

| 模型级别 | 代表模型 | 单次调用成本 | 响应延迟 | 质量水平 |
|:---|:---|:---|:---|:---|
| 旗舰级 | GPT-4 / Claude Opus | ¥0.3-1.0 | 3-15 秒 | 极高 |
| 平衡级 | GPT-4o-mini / Claude Sonnet | ¥0.02-0.1 | 1-5 秒 | 高 |
| 轻量级 | GPT-3.5 / 开源小模型 | ¥0.001-0.01 | 0.3-2 秒 | 中等 |

> **换算一下**：如果你的产品日活 10 万用户，每人每天调用 5 次：
>
> - 用旗舰级：日成本约 ¥15万-50万
> - 用轻量级：日成本约 ¥500-5000
>
> **差距可达 100-1000 倍。**

> 🌐 **In English:** The cost difference between flagship and lightweight models can be 100-1000x. For a product with 100K DAU and 5 calls per user per day, flagship models could cost ¥150K-500K/day vs ¥500-5K/day for lightweight models.

---

## 🎯 第三节：不同场景如何取舍

**核心原则：先明确场景的第一优先级，再选模型策略。**

### 场景取舍决策表

| 场景 | 第一优先 | 第二优先 | 可牺牲 | 推荐策略 |
|:---|:---|:---|:---|:---|
| 智能客服 | 延迟 | 成本 | 质量（可接受80分） | 小模型 + 缓存 |
| 法律合同审查 | 质量 | — | 延迟、成本 | 旗舰模型 + 长上下文 |
| 实时翻译 | 延迟 | 质量 | 成本（单次低） | 中等模型 + 流式输出 |
| 内容创作辅助 | 质量 | 延迟 | 成本 | 旗舰模型 + 流式输出 |
| 商品推荐文案 | 成本 | 延迟 | 质量（模板化即可） | 轻量模型 + 模板 |

### 取舍背后的逻辑

**智能客服**：用户等 10 秒就会离开，80 分的回答比没回答好。质量不够可以转人工兜底。

**法律审查**：一个漏洞可能造成百万损失。用户愿意等 30 秒，也愿意付费。质量是底线。

**实时翻译**：会议场景下 0.5 秒的延迟和 3 秒的延迟，体验天壤之别。

> 🌐 **In English:** Customer service prioritizes speed (users leave after 10s wait). Legal review prioritizes quality (one mistake = huge loss). Real-time translation prioritizes latency (0.5s vs 3s is a totally different experience).

---

## 🛠 第四节：六大优化策略

当你理解了三角关系，接下来是——**如何在不牺牲太多的情况下，尽量把三角形撑大？**

### 策略一：模型路由（Model Routing）

根据请求的复杂度，自动分配到不同级别的模型。

> 简单问题 → 小模型处理（便宜、快）
> 复杂问题 → 大模型处理（贵、但保证质量）

**PM 需要做的**：定义"简单"和"复杂"的分类标准。

### 策略二：语义缓存（Semantic Cache）

相似的问题，直接返回之前的答案，不再重复调用模型。

> 例：100 个用户问"怎么退款"，只需要调用 1 次模型。

**PM 需要做的**：确定哪些场景适合缓存、缓存多久过期。

### 策略三：流式输出（Streaming）

不等全部生成完再展示，而是像打字一样逐字输出。

> 实际延迟没变，但**用户感知延迟**大幅降低。

**PM 需要做的**：在需求文档中注明"支持流式输出"。

### 策略四：Prompt 优化

用更短、更精准的 Prompt 达到同样效果，减少 Token 消耗。

> Token 数减半 = 成本减半 + 延迟降低。

**PM 需要做的**：和工程师一起迭代 Prompt，跟踪优化效果。

### 策略五：预处理与后处理

在调用大模型之前，先用规则或小模型做初步筛选；大模型返回后，再做格式化和过滤。

**PM 需要做的**：设计前置规则，减少无效调用。

### 策略六：异步处理（Async Processing）

非实时场景下，允许后台处理、稍后通知用户结果。

> 例："您的报告正在生成，预计 3 分钟后发送到邮箱。"

**PM 需要做的**：设计等待状态的用户体验。

> 🌐 **In English:** Six optimization strategies: Model Routing (route by complexity), Semantic Cache (reuse answers), Streaming (show tokens as generated), Prompt Optimization (shorter prompts = lower cost), Pre/Post Processing (filter before calling LLM), and Async Processing (background tasks for non-real-time needs).

---

## 📝 第五节：PM 视角——如何写进 PRD

在你的产品需求文档（PRD, Product Requirements Document）中，应该新增一个"AI 约束"章节：

> ### AI 约束 / AI Constraints
>
> | 约束项 | 要求 | 备注 |
> |:---|:---|:---|
> | 质量下限 | 准确率 ≥ 90% | 低于此转人工 |
> | 延迟上限 | 首字输出 ≤ 2秒 | 支持流式 |
> | 单次成本上限 | ≤ ¥0.05 | 日调用量约50万次 |
> | 降级策略 | 大模型超时5秒后切换小模型 | — |

**关键提醒**：这些数字不是拍脑袋定的，而是需要和工程团队一起，基于测试数据来确定。PM 的责任是**提出合理的目标范围**，工程负责达成。

> 🌐 **In English:** Add an "AI Constraints" section to your PRD, specifying quality floor, latency ceiling, cost cap per call, and fallback strategy. These numbers should be data-driven, not guesses.

---

## 📋 第六节：场景决策模板

当你面对一个新的 AI 功能需求时，用这个模板做决策：

> ### AI 功能决策卡片
>
> **功能名称**：_______________
>
> **Step 1：明确优先级**
>
> | 优先级 | 维度 | 目标值 |
> |:---|:---|:---|
> | 第一优先 | _______ | _______ |
> | 第二优先 | _______ | _______ |
> | 可接受牺牲 | _______ | 底线值：_______ |
>
> **Step 2：选择模型策略**
>
> - [ ] 旗舰模型直接调用
> - [ ] 中等模型 + Prompt 优化
> - [ ] 小模型 + 缓存
> - [ ] 模型路由（混合方案）
>
> **Step 3：配套优化**
>
> - [ ] 流式输出
> - [ ] 语义缓存
> - [ ] 异步处理
> - [ ] 降级兜底方案
>
> **Step 4：验证指标**
>
> | 指标 | 基线值 | 目标值 | 测量方式 |
> |:---|:---|:---|:---|
> | 质量 | ____% | ____% | 评测集 |
> | 延迟 P95 | ____s | ____s | 监控 |
> | 单次成本 | ¥____ | ¥____ | 账单 |

> 🌐 **In English:** Use this decision card for every new AI feature: (1) Set priority among cost/latency/quality, (2) Choose model strategy, (3) Add optimizations like streaming or caching, (4) Define measurable validation metrics.

---

## 💡 第七节：常见误区

| 误区 | 正确认知 |
|:---|:---|
| "直接用最好的模型就行" | 最好的模型 ≠ 最合适的模型，场景匹配才是关键 |
| "延迟优化是工程师的事" | PM 需要定义延迟目标，影响架构选型 |
| "先上线再优化成本" | 错误的成本结构上线后很难改，提前规划很重要 |
| "质量越高越好" | 过高质量 = 过高成本，够用就好 |

> 🌐 **In English:** Common mistakes: using the best model for everything, leaving latency to engineers, deferring cost optimization, and over-engineering quality. The right model is the one that fits the scenario.

---

## 🧪 试试看：做一次取舍决策

> **场景**：你负责一款电商 App 的"AI 商品问答"功能。用户在商品详情页可以问任何关于商品的问题，AI 实时回答。
>
> 请思考：
> 1. 质量、延迟、成本，你的优先级排序是？
> 2. 你会选择什么模型策略？
> 3. 你会采用哪些优化手段？
> 4. 在 PRD 中，你会写什么约束条件？
>
> **参考思路**：电商场景用户耐心低（延迟优先），错误回答可能导致退货（质量不能太低），日调用量巨大（成本敏感）。推荐：中等模型 + 商品信息缓存 + 流式输出 + 兜底转人工。

> 🌐 **In English:** Try it: For an e-commerce "AI product Q&A" feature, rank your priorities, choose a model strategy, pick optimizations, and draft PRD constraints. Hint: users are impatient, wrong answers cause returns, and call volume is massive.

---

## 📚 本章小结

| 要点 | 一句话总结 |
|:---|:---|
| 不可能三角 | 成本、延迟、质量只能同时优化两个 |
| 场景决定取舍 | 先定优先级，再选模型策略 |
| 优化策略 | 路由、缓存、流式、Prompt 优化等可以把三角形撑大 |
| PM 的角色 | 定义约束条件、写进 PRD、推动工程落地 |

> 🌐 **In English:** Key takeaways — the iron triangle forces trade-offs; scenario determines priority; optimization strategies expand the triangle; PM's role is to define constraints and drive execution.

---

> 📖 **下一篇**：[评测体系怎么搭](05_how_to_build_an_evaluation_framework.md) — 当你做了取舍之后，如何验证你的决策是对的？
