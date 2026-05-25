📌 **一句话版本**
Agent不只是"回答问题"，而是能"主动规划并执行多步任务"——
这一节让你亲眼看到AI是怎么拆解任务的。

> 🌐 **In English:**
> An Agent doesn't just answer questions — it actively plans and executes multi-step tasks. This section lets you watch how AI breaks down and completes complex goals.

---

## 📖 这一节在讲什么

你用过ChatGPT回答问题，但你有没有见过AI：
- 先搜索信息
- 再写代码
- 然后运行代码
- 最后把结果整理成报告

这种"自主完成多步任务"的能力，
就是Agent（智能体）的核心特征。

这一节不要求你开发一个Agent，
而是让你用现有的产品**亲眼观察**
Agent是怎么工作的——
这对你设计AI产品、评估AI能力，都非常有价值。

> 🌐 **In English:**
> This section doesn't ask you to build an Agent. Instead, use existing products to **observe** how an Agent plans, reasons, and executes — invaluable context for designing and evaluating AI products.

---

## 🧠 什么是Agent（智能体）

传统AI（就像你用ChatGPT问一个问题）：

```
用户输入 → AI输出
（单步，被动）
```

Agent的模式：

```
用户给目标
    ↓
Agent分析目标，制定计划
    ↓
执行步骤1（可能调用工具）
    ↓
基于结果，执行步骤2
    ↓
……持续循环……
    ↓
完成目标，输出结果
```

核心区别：**Agent能自己决定下一步做什么**，
而不是每一步都等你告诉它。

> 🌐 **In English:**
> Traditional AI: user input → AI output (single step, passive). Agent: user gives a goal → Agent plans → executes step by step → achieves the goal. The key: **Agents decide their own next steps.**

---

## 🛠️ 用现有工具体验Agent（不需要写代码）

### 体验平台1：Claude Artifacts

**适合体验：** 自主生成并运行代码的能力

```
1. 打开 claude.ai
2. 输入这个任务：
   "帮我做一个互动的数据可视化，
   展示5个城市的GDP对比，
   用户可以点击切换不同年份"
3. 观察Claude：
   - 是否自动写了代码（HTML/JS）？
   - 是否直接生成了可预览的结果？
   - 有没有调试和修改的过程？
```

**观察重点：**
Claude会自动生成完整的代码，
并在侧边栏显示运行结果。
这个"写代码+运行+展示"的过程，
就是最基础的Agent行为：规划→执行→呈现。

---

### 体验平台2：GPTs（自定义GPT）

**适合体验：** 工具调用和多步骤任务

```
1. 打开 chat.openai.com
   （需要Plus账号）
2. 点击"探索GPT"
3. 找一个有工具调用能力的GPT，
   比如"Code Interpreter"或
   数据分析类的GPT
4. 上传一个Excel文件（比如销售数据）
5. 输入任务：
   "分析这份数据，找出销量最高的
   前5个产品，并画出趋势图"
6. 观察AI是否自动：
   - 读取文件
   - 运行分析代码
   - 生成图表
   - 解读结果
```

---

### 体验平台3：Coze（扣子）

**适合体验：** 多工具编排的工作流Agent

Coze是字节跳动推出的Agent编排平台，
支持把多个工具连接成工作流，
适合体验"Agent调用外部工具"。

```
1. 访问 coze.cn（国内）
   或 coze.com（海外）
2. 注册账号
3. 创建一个新Bot
4. 在"工作流"里添加几个工具：
   - 网络搜索
   - 代码执行
   - 文件处理
5. 设定一个任务：
   "搜索今天的AI行业新闻，
   总结成3条摘要，
   分别写上来源和链接"
6. 观察工作流的执行过程
```

> 🌐 **In English:**
> Use Coze (coze.com) to experience multi-tool Agent workflows: chain together web search, code execution, and file processing to complete compound tasks automatically.

---

## 👁️ 观察Agent行为的关键角度

当你在体验Agent时，用以下几个视角来观察：

### 角度1：任务分解

Agent把你给的大任务拆成了哪几个小步骤？
写下来，和你预想的步骤对比一下。

### 角度2：工具调用

Agent调用了哪些工具？
（搜索引擎、代码执行器、计算器……）
是否合理？是否多余？

### 角度3：错误恢复

当某一步出错时（比如代码报错），
Agent是否能自动发现问题并修正，
还是直接放弃？

### 角度4：输出质量

最终结果是否达到了你的目标？
有没有幻觉（编造信息）或遗漏？

---

## 📝 Agent观察笔记模板

用这个模板记录你的每次Agent体验：

```
【观察记录】

日期：
平台：
任务描述：

Agent执行步骤：
  步骤1：
  步骤2：
  步骤3：
  ……

调用的工具：

出现的问题：

最终结果质量（1-5分）：

作为产品经理，我的思考：
  - 这个Agent的边界在哪里？
  - 什么场景下它会失败？
  - 如果我来设计这个产品，
    我会怎么改进？
```

---

## 🎯 AI产品经理视角

体验Agent之后，你需要建立一个认知框架：
**什么任务适合Agent，什么任务不适合。**

**适合Agent的任务特征：**
- 有明确的目标，但执行路径不固定
- 需要多步骤、多工具配合
- 可以接受一定的误差率
- 执行时间有弹性（不追求极速响应）

**不适合Agent的任务特征：**
- 对结果100%准确性有要求（金融交易、医疗诊断）
- 需要毫秒级响应
- 执行路径必须严格可控、可审计

**PM设计Agent产品时的关键问题：**

| 问题 | 原因 |
|------|------|
| 失败时怎么通知用户？ | Agent可能中途失败 |
| 用户能看到执行过程吗？ | 透明度影响信任 |
| 有没有人工审核节点？ | 防止错误扩散 |
| Agent的权限边界是什么？ | 防止越权操作 |

> 🌐 **In English:**
> Key PM questions when designing Agent products: How to notify users on failure? Can users see execution steps (transparency)? Are there human-review checkpoints? What are the permission boundaries?

---

## 🧪 进阶体验：设计一个Agent任务

不只是观察，试着主动"为难"Agent：

**任务1：故意给含糊的目标**
```
给Claude一个模糊任务：
"帮我整理一下我们的产品"
观察：Agent会问你澄清问题，
还是直接猜测开始执行？
```

**任务2：给一个需要多步推理的任务**
```
"假设我有10万预算，
要在上海举办一场100人的
AI产品发布会，帮我做一个预算分配表"
观察：Agent的规划逻辑是否合理？
```

**任务3：给一个超出能力边界的任务**
```
"帮我登录我们公司的内部系统
查一下上周的用户数据"
观察：Agent是否会清楚地说明
自己做不到这件事？
```

---

## ⚠️ 常见误解

**误解1：Agent越自主越好。**
不对。自主性越高，出错的风险也越大。
好的Agent产品设计要在"自主"和"可控"之间取得平衡。

**误解2：Agent能替代人类做所有决策。**
不对。目前的Agent适合处理结构化、
可验证的任务，不适合需要价值判断的复杂决策。

**误解3：Agent的每一步都是正确的。**
不对。Agent会出错、会走弯路。
好的设计要有"失败处理机制"和"回滚能力"。

---

## 📚 延伸阅读

- OpenAI Assistants API（Agent功能）：
  [platform.openai.com/docs/assistants](https://platform.openai.com/docs/assistants)
- 扣子Coze官方文档：
  [www.coze.cn/docs](https://www.coze.cn/docs)
- Anthropic的Claude Tool Use：
  [docs.anthropic.com/claude/docs/tool-use](https://docs.anthropic.com/claude/docs/tool-use)

---

📝 **记住这些**

- Agent = 能自主规划并执行多步任务的AI
- 核心能力：任务分解、工具调用、错误恢复
- 体验工具：Claude Artifacts、GPTs、Coze
- PM关注点：透明度、失败处理、权限边界、审核节点
- 不是所有任务都适合Agent，要辨别使用场景

---
*模块：08_动手实践 | 文件：05_体验一个Agent工作流*
