> 📌 **阅读对象**：传统互联网产品经理，零 AI 基础
> ⏱ **建议阅读时长**：20 分钟
> 🎯 **读完你能获得**：一套可直接打印使用的 AI 需求分析 Checklist

---



## 📖 目录

1. [为什么需要额外的问题](#-为什么需要额外的问题)
2. [第一组：这个需求真的需要 AI 吗](#-第一组这个需求真的需要-ai-吗)
3. [第二组：需要什么级别的 AI 能力](#-第二组需要什么级别的-ai-能力)
4. [第三组：失败了怎么办](#-第三组失败了怎么办)
5. [第四组：成本和性能能接受吗](#-第四组成本和性能能接受吗)
6. [第五组：数据从哪来](#-第五组数据从哪来)
7. [实战模板：AI 需求分析 Checklist](#-实战模板ai-需求分析-checklist)
8. [PM 视角：如何把这套方法融入日常工作](#-pm-视角如何把这套方法融入日常工作)
9. [常见误解](#️-常见误解)
10. [本章小结](#-本章小结)
11. [延伸阅读](#-延伸阅读)

---



## 💡 为什么需要额外的问题

传统 PM 的需求分析方法论已经很成熟了——用户画像、场景分析、竞品调研、优先级排序……这些在 AI 产品中**依然重要**。

但 AI 产品有一组**传统需求分析不会覆盖的问题**。如果不问这些问题，你可能会：

- 🚫 用 AI 解决一个 if-else 就能搞定的问题（浪费钱）
- 🚫 选了一个太大的模型（成本爆炸）
- 🚫 没考虑 AI 出错时的用户体验（用户骂街）
- 🚫 上线后才发现没有可用的训练数据（项目推倒重来）



> 🌐 **In English:**
> Traditional PM analysis methods remain essential, but AI products require an additional set of questions. Skipping them leads to over-engineering, cost overruns, poor error handling, or data availability issues discovered too late.

---



## 🤔 第一组：这个需求真的需要 AI 吗？

> **核心原则：规则能解决的问题，不要用模型。**

这是 AI PM 最重要的判断力。不是所有看起来"智能"的功能都需要 AI。



### 判断框架

| 问自己 | 如果答案是…… | 建议 |
|---|---|---|
| 这个问题有明确的规则吗？ | 有 → 如"年龄 ≥ 18" | 用规则，不用 AI |
| 输入和输出的对应关系固定吗？ | 固定 → 如"状态码 → 错误提示" | 用映射表 |
| 需要"理解"自然语言吗？ | 需要 → 如"理解用户投诉的情绪" | 考虑用 AI |
| 需要"生成"新内容吗？ | 需要 → 如"写一封回复邮件" | 适合用 AI |



### 举几个例子

> ✅ **需要 AI 的场景**
> - "根据用户的聊天记录，判断他是否有购买意向" → 需要理解语义
> - "自动为商品写营销文案" → 需要创作能力
> - "将用户上传的合同翻译成英文" → 需要语言理解

> ❌ **不需要 AI 的场景**
> - "判断用户是否满 18 岁" → 一个 if 判断
> - "根据订单状态显示不同的提示文字" → 一张映射表
> - "计算购物车总金额" → 基础数学运算



> 🌐 **In English:**
> The first question: Does this really need AI? If a problem can be solved with simple rules, lookup tables, or basic logic — don't use AI. AI is for understanding natural language, generating content, or handling fuzzy/complex reasoning.

---



## 📊 第二组：需要什么级别的 AI 能力？

> **核心原则：杀鸡不用牛刀，选对模型规模能省一大笔钱。**

AI 模型的能力差异巨大，成本差异也巨大。选对级别至关重要。



### 三个级别对照表

| 级别 | 能力范围 | 典型模型 | 单次调用成本 |
|---|---|---|---|
| **轻量级** | 分类、提取关键词、情感判断 | 小型模型 / 专用模型 | ¥0.001 - ¥0.01 |
| **中等级** | 摘要、简单问答、翻译 | 中型通用模型 | ¥0.01 - ¥0.1 |
| **重量级** | 复杂推理、长文创作、代码生成 | 大型语言模型（LLM） | ¥0.1 - ¥1+ |



### 怎么选？问这几个问题

1. **任务复杂度**：是简单分类，还是需要深度推理？
2. **输出长度**：输出几个字（分类标签）还是几百字（文章）？
3. **质量要求**：允许偶尔出错，还是必须高准确率？
4. **是否需要多模态（Multimodal）**：只处理文字，还是图片+文字+音频？



> **💰 成本对比（直观感受）**：
> 假设每天处理 10,000 次请求——
> - 轻量级模型：每天 ¥10 ~ ¥100
> - 重量级模型：每天 ¥1,000 ~ ¥10,000
>
> **差 100 倍！** 这就是为什么选对级别很重要。



> 🌐 **In English:**
> AI models range from lightweight (classification, extraction — cheap) to heavyweight (complex reasoning, long-form generation — expensive). Choosing the right level can mean a 100x cost difference. Ask: How complex is the task? How long is the output? What quality is required? Is multimodal needed?

---



## 🛡 第三组：失败了怎么办？

> **核心原则：AI 一定会出错，提前设计好"出错时的用户体验"。**

这是传统 PM 最容易忽略的问题。传统产品的"错误处理"是处理系统异常（网络超时、服务器崩溃）。AI 产品的"错误处理"要多考虑一层——**AI 本身输出了错误内容**。



### 必须回答的三个问题



**问题 1：AI 出错时，用户体验怎么办？**

| 策略 | 适用场景 | 示例 |
|---|---|---|
| 标注"AI 生成，仅供参考" | 辅助决策场景 | AI 写的会议纪要 |
| 提供"换一个回答"按钮 | 创作类场景 | AI 生成的文案 |
| 自动转人工处理 | 高准确率要求场景 | AI 客服无法解答时 |
| 要求用户确认后生效 | 操作类场景 | AI 代填表单 |



**问题 2：是否需要人工兜底（Human-in-the-loop, HITL）？**

人工兜底的意思是：当 AI 不确定自己的回答是否正确时，把任务转交给人类处理。

> 判断标准很简单——**看错误的代价有多大**：
> - AI 推荐一首歌推荐错了 → 用户最多觉得"不好听"，无所谓 → **不需要兜底**
> - AI 自动回复客户邮件内容有误 → 客户可能投诉 → **需要兜底**
> - AI 辅助医疗诊断出错 → 可能危及生命 → **必须强兜底**



**问题 3：错误的代价到底有多大？**

| 错误代价 | 场景举例 | 建议策略 |
|---|---|---|
| **低** | 推荐歌曲、生成表情包 | AI 直接输出，无需确认 |
| **中** | 回复客户邮件、生成报告 | AI 输出 + 人工审核 |
| **高** | 医疗建议、法律文书、金融交易 | AI 仅辅助，人工最终决策 |



> 🌐 **In English:**
> AI will make mistakes — plan for it. Three key questions: (1) What's the UX when AI fails? (2) Is human-in-the-loop needed? (3) How costly are errors? Low-stakes = AI auto-output. Medium-stakes = AI + human review. High-stakes = AI assists, human decides.

---



## 💰 第四组：成本和性能能接受吗？

> **核心原则：AI 的成本不是一次性的，而是持续的、随用量增长的。**

传统产品的成本主要在开发阶段。AI 产品的成本分三层：



### AI 产品成本三层模型

| 成本层级 | 内容 | 特点 |
|---|---|---|
| **一次性成本** | 模型选型、Prompt 开发、评测体系搭建 | 与传统开发成本类似 |
| **持续推理成本** | 每次 API 调用的费用 | 随用户量线性增长 |
| **运营调优成本** | Bad case 分析、Prompt 迭代、数据更新 | 长期持续投入 |



### 必须算清的三笔账

**1. 每次调用多少钱？**

> 计算公式：输入 Token 数 × 输入单价 + 输出 Token 数 × 输出单价
> Token 是 AI 处理文本的基本单位，大约 1 个中文字 ≈ 1.5 个 Token



**2. 响应延迟能接受吗？**

| 场景 | 用户可接受延迟 | 注意事项 |
|---|---|---|
| 实时对话 | ≤ 3 秒 | 可用流式输出（Streaming）缓解 |
| 后台处理 | ≤ 30 秒 | 可异步处理 |
| 批量任务 | 分钟级 | 可用队列排队 |



**3. 并发量扛得住吗？**

> 大模型 API 通常有**调用频率限制**（Rate Limit）。
> 如果你的产品有突发高并发场景（如双十一），需要提前跟 API 提供商确认配额，或准备降级方案。



> 🌐 **In English:**
> AI costs have three layers: one-time (setup), recurring inference (per API call, scales with users), and ongoing optimization. Calculate per-call cost, verify latency is acceptable, and confirm rate limits can handle your peak traffic.

---



## 🗄 第五组：数据从哪来？

> **核心原则：AI 的能力上限 = 模型能力 + 可用数据的质量。**

很多 AI 产品失败不是因为模型不行，而是**没有合适的数据**。



### 三个关键数据问题



**问题 1：是否需要 RAG（Retrieval-Augmented Generation，检索增强生成）？**

> **通俗解释**：RAG 就是"让 AI 先查资料，再回答问题"。

| 场景 | 是否需要 RAG | 原因 |
|---|---|---|
| 通用闲聊 | 不需要 | 模型自身知识够用 |
| 回答公司产品问题 | 需要 | 模型不知道你公司的产品信息 |
| 基于最新文档回答 | 需要 | 模型训练数据有截止日期 |

如果你的产品需要 AI 基于**公司私有数据**或**实时更新的信息**来回答，就需要 RAG。



**问题 2：是否需要记忆（Memory）？**

> **通俗解释**：Memory 就是让 AI 记住之前的对话内容或用户偏好。

| 场景 | 是否需要记忆 | 类型 |
|---|---|---|
| 一次性翻译 | 不需要 | 每次独立处理 |
| 多轮客服对话 | 需要短期记忆 | 记住这一次对话上下文 |
| 个性化助手 | 需要长期记忆 | 记住用户的偏好和历史 |



**问题 3：数据隐私和合规怎么办？**

这是最容易被忽略但最致命的问题：

- 📋 用户数据是否会被发送到第三方 API？
- 📋 数据存储是否符合 GDPR（通用数据保护条例）等法规？
- 📋 是否需要数据脱敏处理？
- 📋 AI 生成的内容涉及版权问题吗？



> 🌐 **In English:**
> Three data questions: (1) Do you need RAG to provide the AI with company-specific or real-time data? (2) Does the AI need memory — short-term (conversation context) or long-term (user preferences)? (3) What about data privacy — will user data go to third-party APIs? Is it GDPR-compliant?

---



## 📋 实战模板：AI 需求分析 Checklist

> 以下 Checklist 可直接打印，在每次 AI 需求评审时使用。



### AI 需求分析 Checklist v1.0

| 序号 | 检查项 | 回答 | 备注 |
|---|---|---|---|
| **第一组：是否需要 AI** | | | |
| 1.1 | 这个需求能用规则/逻辑解决吗？ | ☐ 能 / ☐ 不能 | |
| 1.2 | 需要理解自然语言吗？ | ☐ 是 / ☐ 否 | |
| 1.3 | 需要生成新内容吗？ | ☐ 是 / ☐ 否 | |
| **第二组：AI 能力级别** | | | |
| 2.1 | 任务复杂度？ | ☐ 低 / ☐ 中 / ☐ 高 | |
| 2.2 | 是否需要多模态？ | ☐ 是 / ☐ 否 | |
| 2.3 | 推荐模型级别？ | ☐ 轻量 / ☐ 中等 / ☐ 重量 | |
| **第三组：失败处理** | | | |
| 3.1 | 错误代价等级？ | ☐ 低 / ☐ 中 / ☐ 高 | |
| 3.2 | 是否需要人工兜底？ | ☐ 是 / ☐ 否 | |
| 3.3 | 出错时的 UX 方案？ | ___________ | |
| **第四组：成本与性能** | | | |
| 4.1 | 预估单次调用成本？ | ¥_________ | |
| 4.2 | 预估日均调用次数？ | _________ 次 | |
| 4.3 | 预估月度推理成本？ | ¥_________ | |
| 4.4 | 可接受的响应延迟？ | _________ 秒 | |
| 4.5 | 峰值并发量？ | _________ 次/秒 | |
| **第五组：数据** | | | |
| 5.1 | 是否需要 RAG？ | ☐ 是 / ☐ 否 | |
| 5.2 | 是否需要记忆功能？ | ☐ 短期 / ☐ 长期 / ☐ 不需要 | |
| 5.3 | 数据来源是什么？ | ___________ | |
| 5.4 | 数据隐私是否合规？ | ☐ 已确认 / ☐ 待确认 | |



> **使用方法**：
> 1. 在 AI 需求评审会议上，逐项过一遍
> 2. 任何一项回答不出来的，标记为待调研
> 3. 所有项填完后，才算需求分析完成



> 🌐 **In English:**
> This printable checklist covers all five question groups. Use it during AI requirement reviews. Any unanswered item should be flagged for further research before proceeding to development.

---



## 🎯 PM 视角：如何把这套方法融入日常工作



### 融入现有流程，而非替代

这套 AI 专属问题**不是替代**传统需求分析流程，而是**在传统流程基础上增加一个环节**。

建议的工作流程：

```
传统需求分析（用户画像、场景、竞品...）
         ↓
    AI 专属问题 Checklist      ← 新增环节
         ↓
    需求评审 & 技术评审
         ↓
    开发排期
```



### 什么时候拿出这份 Checklist？

| 时机 | 说明 |
|---|---|
| **需求初评** | 判断是否需要 AI，避免过度设计 |
| **技术方案评审** | 与算法工程师对齐模型选型和成本 |
| **上线前评审** | 确认兜底方案和监控指标已就绪 |



### 跟算法工程师的沟通技巧

你不需要懂算法细节，但你需要能**用业务语言翻译技术约束**：

> - 算法说"准确率只能到 85%"
>   → 你翻译成"每 100 个用户会有 15 个体验到错误回答，我们需要设计兜底方案"
>
> - 算法说"这个模型推理延迟 5 秒"
>   → 你翻译成"用户每次提问要等 5 秒才能看到回答，需要加一个加载动画和流式输出"
>
> - 算法说"需要至少 1000 条标注数据"
>   → 你翻译成"我们需要安排人力花 2 周标注数据，才能开始训练"



> 🌐 **In English:**
> Integrate the AI checklist into your existing workflow — don't replace traditional analysis, augment it. Use the checklist at initial review, technical review, and pre-launch review. Learn to translate technical constraints into business impact for stakeholder communication.

---



## ⚠️ 常见误解



> ❌ **误解 1："AI 需求分析就是写清楚让 AI 做什么"**
>
> 不够。AI 需求分析还要写清楚：AI 做不好怎么办、能花多少钱、数据从哪来、谁来兜底。光说"用 AI 自动回复邮件"是远远不够的。



> ❌ **误解 2："这些问题应该让技术团队回答"**
>
> 错了。成本预算、错误代价评估、用户体验设计——这些是**产品经理的职责**。技术团队告诉你"能不能做"和"做到什么程度"，但"值不值得做"和"出错怎么办"是 PM 要回答的。



> ❌ **误解 3："先做出来再说，上线后再调优"**
>
> 危险思维。如果没有提前设计兜底方案，上线后 AI 犯错直接影响用户体验。如果没有提前算成本，上线后发现 API 费用远超预算。**事前多花 1 小时分析，事后少花 100 小时救火。**



> 🌐 **In English:**
> Misconceptions: (1) AI requirements aren't just about what AI should do — they must cover failure handling, costs, and data sources. (2) Cost assessment and UX design for failures are PM responsibilities, not just engineering concerns. (3) "Ship first, optimize later" is dangerous without fallback plans and cost projections.

---



## 📝 本章小结



| 问题组 | 核心问题 | 一句话要点 |
|---|---|---|
| 第一组 | 需要 AI 吗？ | 规则能解决就别用模型 |
| 第二组 | 什么级别？ | 杀鸡别用牛刀 |
| 第三组 | 失败了怎么办？ | 看错误代价定兜底方案 |
| 第四组 | 成本能接受吗？ | 推理成本随用量线性增长 |
| 第五组 | 数据从哪来？ | 没有好数据就没有好 AI |



> 💡 **记住这句话**：
> 传统需求分析问"用户要什么"。
> AI 需求分析还要问"AI 做不到怎么办"。



> 🌐 **In English:**
> Traditional requirements ask "What do users want?" AI requirements additionally ask "What happens when AI can't deliver?" The five question groups cover: necessity, capability level, failure handling, cost/performance, and data availability.

---



## 📚 延伸阅读

- 上一篇：[00_AI 产品经理和传统产品经理有什么不同](00_how_ai_product_managers_differ_from_traditional_pms.md)
- 推荐概念学习：RAG / Human-in-the-loop / Token / Rate Limit / Streaming
- 推荐实践：用本章的 Checklist 分析一个你熟悉的产品功能，看看是否适合用 AI 实现

---

> 📄 *本文档为 Charlie's AI PM Knowledge System 系列教程*
> *更新日期：2026-03-26*
