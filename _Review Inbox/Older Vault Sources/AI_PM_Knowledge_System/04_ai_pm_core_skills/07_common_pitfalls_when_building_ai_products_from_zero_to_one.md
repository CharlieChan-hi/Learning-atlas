> **阅读时间**：15 分钟 | **难度**：入门 | **前置知识**：了解 AI 基本概念（见 01-06 篇）
>
> 💡 **一句话摘要**：AI 产品的坑，不踩不知道，一踩一个准。这篇帮你提前避开。

---



## 📑 目录

1. [坑1：把 Demo 当产品](#-坑1把-demo-当产品)
2. [坑2：高估模型能力](#-坑2高估模型能力)
3. [坑3：忽视成本](#-坑3忽视成本)
4. [坑4：没有评测体系就上线](#-坑4没有评测体系就上线)
5. [坑5：忽视人工兜底](#-坑5忽视人工兜底)
6. [坑6：把模型问题当交互问题改](#-坑6把模型问题当交互问题改)
7. [坑7：数据问题后知后觉](#-坑7数据问题后知后觉)
8. [坑8：过度承诺交付时间](#-坑8过度承诺交付时间)
9. [避坑 Checklist](#-避坑-checklist一页纸打印版)
10. [英文 Key Takeaways](#-english-key-takeaways)

---



## 🕳️ 坑1：把 Demo 当产品

**Demo Looks Great ≠ Product Ready**



### 发生了什么

很多 AI 产品在演示阶段效果惊艳——输入几个精心挑选的例子，AI 对答如流。

老板看了拍板："太好了，下周上线！"

然后上线后……

> 🔥 **真实案例**：2023-2024 年大量 AI Agent 产品，Demo 视频在社交媒体疯传，上线后用户留存率不到 10%。因为 Demo 只展示了 5 个精选 case，而真实用户会输入上万种千奇百怪的问题。



### 为什么是坑

| Demo | 产品 |
|:---|:---|
| 处理 5-10 个精选 case | 处理上万种边界情况 |
| 不考虑响应速度 | 用户期望 3 秒内响应 |
| 不考虑成本 | 每天数万次调用要花真金白银 |
| 不考虑错误处理 | 必须处理 AI 答错、答不上来的情况 |



### PM 怎么避免

1. **要求看"坏 case"**，不只看"好 case"
2. 内测阶段让**真实用户**（不是团队成员）试用
3. 统计**边界情况的覆盖率**，不只看核心场景

> 🌐 **In English:** A demo only needs to handle 5 perfect cases. A product must handle 10,000 edge cases. Always test with real users, not cherry-picked examples.

---



## 🕳️ 坑2：高估模型能力

**GPT-4 Is Powerful, But Not Omnipotent**



### 发生了什么

PM 看了 GPT-4 的发布会，觉得 AI 无所不能。

于是写了一个 PRD："AI 自动分析用户所有数据，生成完美的个性化报告。"

算法工程师看了 PRD 沉默了三分钟。

> 🔥 **类比**：这就像看到博尔特跑百米 9.58 秒，就认为他能一直跑马拉松还保持同样速度。模型有擅长的，也有做不到的。



### 常见的能力误判

| 你以为能做 | 实际情况 |
|:---|:---|
| 100% 准确率 | 顶级模型也有 5-20% 的错误率 |
| 完美理解长文档 | 超长文本理解质量明显下降 |
| 实时获取最新信息 | 模型知识有截止日期 |
| 精确数学计算 | 大模型做复杂计算经常出错 |



### PM 怎么避免

1. 在写 PRD **之前**，先做一轮**能力测试（Capability Assessment）**
2. 准备 50-100 个真实场景的测试用例，让算法跑一遍
3. 用测试结果来**校准 PRD 的期望值**

> 🌐 **In English:** Before writing the PRD, run a capability assessment with 50-100 real test cases. Let the data calibrate your expectations, not the marketing demo.

---



## 🕳️ 坑3：忽视成本

**Prototype Is Cheap, Production Is Expensive**



### 发生了什么

原型阶段，团队用 GPT-4 跑了几百次测试，花了几十块钱，觉得"成本可以忽略"。

上线后，每天 5 万次调用，每月 API 费用六位数。

老板问："这个月怎么多了 30 万支出？"



### 成本速算表

| 模型 | 单次调用成本（约） | 日均 5 万次 / 月 |
|:---|:---|:---|
| GPT-4o | ¥0.05-0.15 | ¥7.5-22.5 万 |
| GPT-4o-mini | ¥0.005-0.02 | ¥0.75-3 万 |
| Claude 3.5 Sonnet | ¥0.03-0.10 | ¥4.5-15 万 |
| 国产大模型 | ¥0.001-0.01 | ¥0.15-1.5 万 |

> ⚠️ 以上为粗略估算，实际成本取决于输入输出 token 数量。



### PM 怎么避免

1. 在 PRD 阶段就做**成本估算**：预计用户量 × 平均调用次数 × 单次成本
2. 设计**分级策略**：简单问题用小模型，复杂问题用大模型
3. 写入 PRD：**月度成本上限**和**成本超标预警机制**

> 🌐 **In English:** Estimate API costs in the PRD phase: user volume × calls per user × cost per call. Design a tiered model strategy — small models for simple tasks, large models only when needed.

---



## 🕳️ 坑4：没有评测体系就上线

**No Evaluation = Flying Blind**



### 发生了什么

团队忙着赶工期，AI 功能"看起来能用"就上线了。

上线两周，客服收到大量投诉："AI 回答的内容是错的！"

PM 去查数据，发现根本没有监控 AI 回答质量的指标。

> 🔥 **类比**：这就像开一家餐厅，菜做好了直接端上桌，没人试吃过。



### 评测体系的最低标准

| 阶段 | 必须做的 |
|:---|:---|
| 上线前 | 用 200+ 测试用例建立准确率基线（Baseline） |
| 上线时 | 监控每日准确率、用户满意度、转人工率 |
| 上线后 | 每周抽样人工审核 AI 回答质量 |



### PM 怎么避免

1. **上线标准写进 PRD**："准确率 ≥ 90% 才能上线"
2. 搭建**自动化评测流水线（Eval Pipeline）**，持续跑测试
3. 设计**用户反馈机制**：点赞/点踩，收集真实满意度

> 🌐 **In English:** Define launch criteria in the PRD (e.g., accuracy ≥ 90%). Build an eval pipeline before launch, and monitor quality metrics continuously after.

---



## 🕳️ 坑5：忽视人工兜底

**AI Cannot Handle 100% of Cases**



### 发生了什么

PM 规划了一个"全自动 AI 客服"，宣称"零人工成本"。

上线后发现 30% 的用户问题 AI 根本答不上来，用户原地爆炸。



### 为什么需要人工兜底

> 💡 **Human-in-the-loop（人机协同）** 是 AI 产品的标配设计模式，不是可选项。

即使最好的 AI，也有答不上来的时候。关键是：

| 情况 | 正确做法 |
|:---|:---|
| AI 有信心的回答 | 直接展示给用户 |
| AI 不确定的回答 | 标注"仅供参考"，提供反馈入口 |
| AI 完全答不上来 | 自动转人工 / 给用户其他选择 |



### PM 怎么避免

1. 在 PRD 中设计完整的**兜底链路（Fallback Flow）**
2. 定义**转人工的触发条件**：AI 置信度低于 X 时自动转人工
3. 给人工客服提供 **AI 对话上下文**，让接手更顺畅

> 🌐 **In English:** Human-in-the-loop is not optional — it's standard. Design fallback flows in the PRD: when AI confidence is low, automatically escalate to human agents with full conversation context.

---



## 🕳️ 坑6：把模型问题当交互问题改

**Don't Fix a Model Problem with a UI Change**



### 发生了什么

用户反馈："AI 回答不好。"

PM 第一反应：让设计师优化界面——加个引导语、改个排版、美化一下回答的展示。

改完了，用户还是说"AI 回答不好"。

因为问题出在**模型能力不足**，不是界面不好看。



### 怎么区分问题来源

| 症状 | 可能是模型问题 | 可能是产品/交互问题 |
|:---|:---|:---|
| "答案是错的" | ✅ 模型输出不准确 | |
| "答案不相关" | ✅ 模型理解错了意图 | |
| "不知道怎么提问" | | ✅ 引导设计不够 |
| "回答太长看不完" | | ✅ 展示方式需要优化 |
| "等太久了" | 可能是模型太大 | 也可能是工程优化不够 |



### PM 怎么避免

1. 收到"AI 不好"的反馈时，先做**归因分析（Root Cause Analysis）**
2. 区分清楚：是模型输出的内容有问题？还是展示的方式有问题？
3. **模型问题找算法，产品问题找设计**，对症下药

> 🌐 **In English:** When users say "AI is bad," first do root cause analysis. Is the model output wrong (fix the model) or is the presentation confusing (fix the UI)? Misdiagnosis wastes weeks.

---



## 🕳️ 坑7：数据问题后知后觉

**Garbage In, Garbage Out**



### 发生了什么

团队花了两个月搭建 RAG 系统，接入了公司知识库。

上线后 AI 经常给出过时或错误的答案。

排查发现：知识库里 40% 的文档是三年前的，很多已经失效。

> 🔥 **记住这句话**："Garbage in, garbage out"（垃圾进，垃圾出）。AI 的输出质量，永远不会超过输入数据的质量。



### 常见数据问题

| 问题 | 后果 |
|:---|:---|
| 数据过时 | AI 给出过期信息 |
| 数据有错 | AI 给出错误答案并且很自信 |
| 数据缺失 | AI 对部分问题完全答不上来 |
| 数据格式混乱 | AI 理解错误，回答文不对题 |



### PM 怎么避免

1. 项目启动时就做**数据质量审计（Data Quality Audit）**
2. 建立**数据更新机制**：谁负责更新、多久更新一次
3. 在 PRD 中明确**数据源（Data Source）和数据维护计划**

> 🌐 **In English:** "Garbage in, garbage out." Audit data quality at project kickoff. Define who owns data updates and how often they happen — write it into the PRD.

---



## 🕳️ 坑8：过度承诺交付时间

**AI Development Timelines Are Unpredictable**



### 发生了什么

PM 按照传统产品经验排了 4 周的开发计划。

第 2 周，算法工程师说："模型效果没达标，需要换方案重新测。"

第 3 周，后端说："API 供应商限流了，得加缓存层。"

项目延期了 6 周。



### 为什么 AI 产品更不可预测

| 传统产品 | AI 产品 |
|:---|:---|
| 需求明确 → 开发 → 上线 | 需求明确 → 实验 → 可能要换方案 → 再实验 → 开发 → 上线 |
| 确定性流程 | 包含大量"实验-失败-重来"的循环 |
| 工期相对可控 | 模型效果不达标就得返工 |



### PM 怎么避免

1. AI 项目排期**至少加 50% 缓冲时间**
2. 拆分为**小里程碑**：先做 MVP（最小可行产品），再迭代
3. 和老板沟通时说"预计 X 周，但如果模型效果不达标可能需要 Y 周"
4. 设置**阶段性检查点**：如果第 N 周效果没达标，触发备选方案

> 🌐 **In English:** Add at least 50% buffer to AI project timelines. Break work into small milestones with go/no-go checkpoints. Communicate uncertainty upfront — not after delays happen.

---



## 📋 避坑 Checklist（一页纸打印版）

> **适合打印出来贴在工位旁边，每次启动新 AI 项目时对照检查。**

| # | 检查项 | 状态 |
|:--|:---|:---:|
| 1 | Demo 跑通后，用 200+ 边界 case 测试了吗？ | ☐ |
| 2 | 在写 PRD 前，做了模型能力评估了吗？ | ☐ |
| 3 | PRD 中包含了月度 API 成本估算吗？ | ☐ |
| 4 | 定义了上线准确率标准（如 ≥ 90%）吗？ | ☐ |
| 5 | 搭建了评测流水线和质量监控吗？ | ☐ |
| 6 | 设计了人工兜底机制（Fallback）吗？ | ☐ |
| 7 | 用户说"AI 不好"时，先做了归因分析吗？ | ☐ |
| 8 | 做了数据质量审计，明确了数据更新机制吗？ | ☐ |
| 9 | 项目排期加了 ≥ 50% 缓冲时间吗？ | ☐ |
| 10 | 设置了阶段性检查点和备选方案吗？ | ☐ |



> 💡 **打分规则**：勾选 8 个以上 = 准备充分；5-7 个 = 有风险；5 个以下 = 建议重新评估。

---



## 📝 要点总结

> **八大坑，一句话总结：**

| 坑 | 一句话 |
|:---|:---|
| 把 Demo 当产品 | Demo 是精装样板间，产品是毛坯交付 |
| 高估模型能力 | 先测能力，再写 PRD |
| 忽视成本 | API 不免费，PRD 要算账 |
| 没有评测体系 | 不评测 = 蒙眼上线 |
| 忽视人工兜底 | AI 不是万能的，必须有 Plan B |
| 模型问题当交互改 | 先归因，再开药 |
| 数据问题后知后觉 | 垃圾进，垃圾出 |
| 过度承诺时间 | AI 项目 = 传统排期 × 1.5 |

---



## 🌐 English Key Takeaways

> **Common Pitfalls in Building AI Products from Scratch**
>
> 1. **Demo ≠ Product.** Test with 200+ edge cases before committing to launch.
>
> 2. **Assess model capability first.** Run real test cases before writing the PRD.
>
> 3. **Estimate costs early.** API calls add up — budget them in the PRD.
>
> 4. **Build evaluation before launch.** Define accuracy baselines and monitor continuously.
>
> 5. **Design for human fallback.** AI can't handle 100% of cases — plan for the rest.
>
> 6. **Diagnose before fixing.** Is it a model problem or a product problem? The fix is completely different.
>
> 7. **"Garbage in, garbage out."** Audit data quality at project start, not after launch.
>
> 8. **Add 50% time buffer.** AI development is experimental — timelines are inherently uncertain.

---



> 📖 **下一篇预告**：[00_ChatGPT为什么能成为现象级产品](../05_cases_and_breakdowns/00_why_chatgpt_became_a_breakout_product.md)
>
> ⬅️ **上一篇回顾**：[06_和算法_工程_设计协作时要懂什么](06_what_to_understand_when_collaborating_with_ml_engineering_and_design.md)

---

*Charlie's AI PM Knowledge System · 04 AI产品经理核心能力 · 第7篇*
