> 📌 **一句话版本：** AI 产品没有标准答案，PM 必须学会搭一套评测体系来定义"什么算好"。

---

## 📖 这一节在讲什么

传统产品的质量保障逻辑很清晰：写测试用例 → QA 测试 → Bug 修复 → 上线。功能要么对，要么错，黑白分明。

AI 产品不一样。模型的回答没有标准答案，同一个问题问两次可能得到不同结果。**"好"和"不好"之间是一道光谱，不是一条线。**

这意味着，AI PM 需要掌握一套全新的质量保障方法——**评测体系（Evaluation System）**。

> 🌐 **In English:** Traditional products have binary test results (pass/fail). AI products exist on a quality spectrum — the same question may yield different answers each time. AI PMs need a new quality framework: an **Evaluation System**.

---

## 🔄 第一节：思维转变——从"测试"到"评测"

| 对比维度 | 传统产品测试 | AI 产品评测 |
|:---|:---|:---|
| 答案 | 唯一正确答案 | 多个可接受答案 |
| 判断标准 | 对/错 | 好/中/差（打分） |
| 可复现性 | 完全可复现 | 有随机性 |
| 覆盖方式 | 用例覆盖功能 | 测试集覆盖场景 |

**一个关键概念**：在 AI 产品中，我们不说"测试通过率"，而说"评测得分"。这个思维转变非常重要。

> 🌐 **In English:** Shift your mindset: traditional testing checks pass/fail against a single correct answer. AI evaluation scores outputs on a spectrum (good/medium/poor) across diverse scenarios, acknowledging randomness in results.

---

## 🏗 第二节：评测四层次

AI 产品的评测体系分为四个层次，从自动到人工、从离线到线上，层层递进：

### 四层架构总览

| 层次 | 名称 | 执行者 | 速度与成本 |
|:---|:---|:---|:---|
| L1 | 自动化评测 | 代码规则 | 极快、极低成本 |
| L2 | LLM-as-Judge | AI 模型 | 快、低成本 |
| L3 | 人工评测 | 人类评审 | 慢、高成本 |
| L4 | 线上评测 | 真实用户 | 最慢、中等成本 |

> 🌐 **In English:** Four evaluation layers: L1 Automated (code rules, fastest), L2 LLM-as-Judge (AI scores AI, fast), L3 Human Review (experts, slow but reliable), L4 Online Metrics (real users, post-launch).

---

### 🔹 L1：自动化评测（Automated Evaluation）

**原理**：用代码规则检查模型输出，不需要人参与。

**适合检查的内容**：

- 格式是否正确（JSON 格式、字数限制）
- 是否包含敏感词或违禁内容
- 关键字段是否存在（如必须包含价格、日期）
- 回答长度是否在合理范围内

**优点**：速度快、成本低、可大规模运行

**局限**：只能检查"表面特征"，无法判断内容是否真正"好"

> 举个例子：自动化评测能发现"回答是空的"，但发现不了"回答跑题了"。

> 🌐 **In English:** L1 uses code rules to check format, forbidden words, required fields, and length. It's fast and cheap but can only catch surface-level issues, not content quality.

---

### 🔹 L2：LLM-as-Judge（用 AI 评价 AI）

**原理**：用一个更强的大模型（如 GPT-4）来给另一个模型的输出打分。

**具体做法**：

> 写一个评分 Prompt（Evaluation Prompt），告诉评价模型：
> "请根据以下标准，对这段回答打 1-5 分……"

**优点**：

- 能理解语义，判断内容质量
- 速度比人工快几百倍
- 成本比人工低很多

**局限**：

- 评价模型本身也有偏见（Bias）
- 对模棱两可的情况判断不稳定
- 需要精心设计评分标准

**PM 需要做的**：定义清晰的评分标准（Rubric），比如：

> | 分数 | 含义 | 示例 |
> |:---|:---|:---|
> | 5 分 | 完全准确、全面、有帮助 | 回答正确且有额外建议 |
> | 4 分 | 基本准确，有小瑕疵 | 回答正确但缺少细节 |
> | 3 分 | 部分正确，有遗漏 | 答对了一半 |
> | 2 分 | 大部分错误 | 核心信息错误 |
> | 1 分 | 完全错误或有害 | 瞎编或有害内容 |

> 🌐 **In English:** L2 uses a stronger LLM to score another model's output. It understands semantics and is much faster/cheaper than humans, but has its own biases. PM's job: define a clear scoring rubric (1-5 scale with examples).

---

### 🔹 L3：人工评测（Human Evaluation）

**原理**：让人类专家或标注员对模型输出进行评分。

**适用场景**：

- 产品上线前的关键节点
- 涉及安全、合规的高风险场景
- 需要校准 LLM-as-Judge 的评分标准

**具体做法**：

1. 准备 50-200 条测试样本
2. 制定评分指南（Annotation Guideline）
3. 每条样本至少 2 人评分
4. 计算评分者一致性（Inter-Annotator Agreement）

**优点**：最可靠、最能反映真实质量

**局限**：慢、贵、难以大规模执行

> 🌐 **In English:** L3 involves human experts scoring outputs. It's the most reliable method, used at critical milestones and for safety-critical scenarios. Requires 50-200 samples, 2+ raters per sample, and consistency checks.

---

### 🔹 L4：线上评测（Online Evaluation）

**原理**：产品上线后，用真实用户行为数据来评估质量。

**关键指标**：

| 指标 | 含义 | 采集方式 |
|:---|:---|:---|
| 用户满意度 | 用户对回答的评价 | 点赞/点踩按钮 |
| 任务完成率 | 用户是否达成目标 | 行为埋点 |
| 二次提问率 | 用户是否需要追问 | 对话轮次统计 |
| 转人工率 | 用户是否转了人工 | 客服系统数据 |

**优点**：最真实，反映实际用户体验

**局限**：反馈滞后、样本有偏差、难以精确归因

> 🌐 **In English:** L4 tracks real user behavior post-launch: satisfaction (thumbs up/down), task completion rate, follow-up question rate, and human handoff rate. Most authentic but feedback is delayed and hard to attribute.

---

## 📏 第三节：核心评测指标

不同场景需要关注不同指标。以下是 AI PM 最常用的六大指标：

| 指标 | 英文 | 含义 | 适用场景 |
|:---|:---|:---|:---|
| 准确率 | Accuracy | 回答是否正确 | 问答、搜索 |
| 相关性 | Relevance | 回答是否切题 | 对话、推荐 |
| 完整性 | Completeness | 回答是否全面 | 报告生成、摘要 |
| 有害性 | Harmfulness | 是否包含有害内容 | 所有场景 |
| 延迟 | Latency | 响应时间 | 实时交互 |
| 用户满意度 | User Satisfaction | 用户主观评价 | 所有场景 |

### 指标之间的关系

- **准确率和完整性**经常冲突——回答越全面，越容易出错
- **延迟和质量**经常冲突——参考上一篇"不可能三角"
- **有害性**是底线指标——必须优先保障

> 🌐 **In English:** Six key metrics: Accuracy (is it correct?), Relevance (is it on-topic?), Completeness (is it thorough?), Harmfulness (is it safe?), Latency (how fast?), User Satisfaction (do users like it?). Harmfulness is always the non-negotiable baseline.

---

## 🔧 第四节：搭建评测体系的五个步骤

### Step 1：建立黄金测试集（Golden Dataset）

**什么是黄金测试集**：一组精心准备的"问题 + 参考答案"，作为评测的标准。

**怎么建**：

1. 从真实用户问题中采样 100-500 条
2. 覆盖常见场景、边界场景、容易出错的场景
3. 为每条问题编写参考答案（Reference Answer）
4. 标注难度级别（简单/中等/困难）

**PM 需要做的**：

- 定义采样标准（哪些场景必须覆盖）
- 审核参考答案的质量
- 持续维护和更新测试集

> 🌐 **In English:** Step 1: Build a Golden Dataset — 100-500 curated question-answer pairs from real user queries, covering common cases, edge cases, and known failure modes. PM defines sampling criteria and reviews answer quality.

---

### Step 2：定义评分标准（Scoring Rubric）

**为什么重要**：没有清晰的评分标准，不同人打分结果天差地别。

**怎么定义**：

> 以"智能客服回答质量"为例：
>
> | 维度 | 5 分（优秀） | 3 分（及格） | 1 分（不合格） |
> |:---|:---|:---|:---|
> | 准确性 | 信息完全正确 | 核心正确，细节有误 | 核心信息错误 |
> | 相关性 | 精准回答用户问题 | 回答相关但不够精准 | 跑题或答非所问 |
> | 完整性 | 涵盖所有必要信息 | 涵盖主要信息 | 关键信息缺失 |
> | 安全性 | 无任何有害内容 | — | 包含误导或有害信息 |

**PM 需要做的**：针对你的产品场景，定义具体的评分维度和标准。

> 🌐 **In English:** Step 2: Define a Scoring Rubric with clear criteria per dimension (accuracy, relevance, completeness, safety). Use a scale with concrete examples for each score level. PM owns the rubric definition.

---

### Step 3：搭建评测流水线（Evaluation Pipeline）

**流程**：

```
黄金测试集 → 模型生成回答 → 自动化检查(L1)
                              → LLM 评分(L2)
                              → 人工抽检(L3)
                              → 汇总评测报告
```

**关键配置**：

| 配置项 | 建议值 |
|:---|:---|
| L1 自动化覆盖率 | 100%（所有样本） |
| L2 LLM 评分覆盖率 | 100%（所有样本） |
| L3 人工抽检比例 | 10-20% |
| 每条样本 L3 评审人数 | 2-3 人 |

> 🌐 **In English:** Step 3: Build an Evaluation Pipeline — run all samples through L1 (automated) and L2 (LLM-as-Judge) at 100% coverage, then human-review 10-20% of samples with 2-3 reviewers each. Aggregate into a report.

---

### Step 4：分析结果与迭代

**看什么**：

- **整体得分趋势**：版本迭代是否在进步
- **分场景得分**：哪些场景是弱项
- **失败案例分析**：低分回答的共性是什么
- **评分一致性**：L2 和 L3 的评分是否吻合

**PM 需要做的**：

- 每次评测后出一份简报
- 把低分场景转化为具体优化需求
- 推动工程团队迭代 Prompt 或模型

> 🌐 **In English:** Step 4: Analyze results — track score trends across versions, identify weak scenarios, study failure patterns, and check L2-L3 consistency. PM produces a brief after each evaluation and converts findings into optimization tasks.

---

### Step 5：建立持续评测机制

**不是评测一次就完了**。AI 产品需要持续评测，因为：

- 模型升级可能导致表现变化
- 用户行为会随时间变化
- 新场景会不断出现

**建议节奏**：

| 评测类型 | 频率 | 触发条件 |
|:---|:---|:---|
| L1 + L2 自动评测 | 每次部署 | 模型/Prompt 变更 |
| L3 人工评测 | 每 2-4 周 | 定期 + 重大变更 |
| L4 线上指标监控 | 实时 | 持续运行 |
| 黄金测试集更新 | 每月 | 新场景、新问题 |

> 🌐 **In English:** Step 5: Make evaluation continuous. Run L1+L2 on every deployment, L3 every 2-4 weeks, monitor L4 in real-time, and update the Golden Dataset monthly. AI models change, user behavior evolves, and new scenarios emerge.

---

## 🎯 第五节：PM 视角——你不需要写代码，但你需要定义"什么算好"

作为 AI PM，你的评测职责是：

| PM 的职责 | 不是 PM 的职责 |
|:---|:---|
| 定义评分标准和维度 | 编写评测代码 |
| 审核黄金测试集 | 搭建评测工具 |
| 分析评测报告 | 调试模型参数 |
| 推动优化迭代 | 训练模型 |
| 设计线上反馈机制 | 维护数据管道 |

**记住这句话**：

> PM 不需要会开车（写代码），但需要会看地图（评测报告）、会指路（定义标准）、会验收（判断达标）。

> 🌐 **In English:** AI PM's evaluation role: define what "good" means (rubric), curate the test set, analyze reports, drive iterations, and design feedback mechanisms. You don't write evaluation code — you define the standard and verify the outcome.

---

## 🧪 试试看：设计一个简单的 Prompt 评测实验

> **场景**：你负责一个"AI 读书笔记助手"，用户输入一本书的名字，AI 生成 300 字的读书笔记。
>
> **动手练习**：
>
> **第一步：准备 5 个测试问题**
>
> | 编号 | 输入（书名） | 难度 |
> |:---|:---|:---|
> | 1 | 《活着》 | 简单（知名） |
> | 2 | 《思考，快与慢》 | 中等 |
> | 3 | 《枪炮、病菌与钢铁》 | 中等 |
> | 4 | 《一本不存在的书》 | 边界（应拒绝） |
> | 5 | 《哈利波特》（不指定哪一部） | 边界（应澄清） |
>
> **第二步：定义你的评分标准**
>
> | 维度 | 5 分标准 | 1 分标准 |
> |:---|:---|:---|
> | 准确性 | 核心观点正确 | 瞎编内容 |
> | 完整性 | 涵盖主题、论点、启发 | 只有一句话 |
> | 可读性 | 流畅、有结构 | 混乱不可读 |
> | 安全性 | 不捏造书名/内容 | 伪造不存在的引用 |
>
> **第三步：把同一组问题分别用两种不同的 Prompt 跑一遍**
>
> - Prompt A："请为这本书写一份 300 字的读书笔记。"
> - Prompt B："请为这本书写一份 300 字的读书笔记。要求：包含核心主题、主要论点、个人启发三个部分。如果书名不明确，请先确认。如果书不存在，请说明。"
>
> **第四步：对比两组结果的评分差异**
>
> 你会发现，Prompt B 在"完整性"和"边界场景处理"上通常会明显优于 Prompt A。这就是评测驱动优化（Eval-Driven Optimization）的力量。

> 🌐 **In English:** Try it: Design a mini evaluation for an "AI book notes" feature. Prepare 5 test books (including edge cases), define a 4-dimension rubric, run two different prompts, and compare scores. You'll see how structured evaluation drives prompt optimization.

---

## 💡 第六节：常见误区

| 误区 | 正确认知 |
|:---|:---|
| "上线后看用户反馈就行" | 线上反馈有偏差且滞后，必须有离线评测 |
| "测试集一次建好就不用管了" | 用户行为在变，测试集必须持续更新 |
| "LLM-as-Judge 完全可靠" | LLM 评价有偏见，需要人工校准 |
| "评测是工程师的事" | PM 定义标准，工程师搭建工具，两者缺一不可 |
| "样本越多越好" | 100 条高质量样本 > 10000 条低质量样本 |

> 🌐 **In English:** Common mistakes: relying only on post-launch feedback, never updating test sets, blindly trusting LLM-as-Judge, leaving evaluation entirely to engineers, and prioritizing quantity over quality in test samples.

---

## 📚 本章小结

| 要点 | 一句话总结 |
|:---|:---|
| 思维转变 | AI 评测是"打分"而非"对错判断" |
| 四层体系 | 自动化 → LLM 评分 → 人工 → 线上，层层递进 |
| 六大指标 | 准确率、相关性、完整性、有害性、延迟、满意度 |
| 五步搭建 | 建测试集 → 定标准 → 搭流水线 → 分析迭代 → 持续运行 |
| PM 的角色 | 定义"什么算好"，不需要写评测代码 |

> 🌐 **In English:** Key takeaways — AI evaluation is scoring, not pass/fail. Build four layers (auto → LLM → human → online), track six metrics, follow five steps, and remember: PM defines "what good looks like."

---

## 📚 延伸阅读

- OpenAI Evals 开源项目 — 了解业界评测框架
- Anthropic 的模型评测方法论博客
- LangChain 评测模块文档
- 《Building LLM-Powered Applications》评测章节

---

> 📖 **上一篇**：[成本、延迟、质量：三者如何取舍](04_balancing_cost_latency_and_quality.md)
> 📖 **下一篇**：[和算法、工程、设计协作时要懂什么](06_what_to_understand_when_collaborating_with_ml_engineering_and_design.md)
