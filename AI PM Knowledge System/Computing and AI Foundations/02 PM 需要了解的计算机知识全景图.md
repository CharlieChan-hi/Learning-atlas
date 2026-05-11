

> 📌 **一句话版本：** PM 不需要学会所有计算机知识，但需要知道全景图长什么样——就像你不需要会开飞机，但要看得懂航线图。



---



## 📖 这一节在讲什么

你是一个产品经理，每天要和工程师对话、评审技术方案、拍板产品决策。

但你可能经常遇到这样的场景：

- 工程师说"这个要走异步队列"，你点点头但不太确定在说什么
- 技术评审会上满屏英文缩写，你假装看得懂
- 老板问"为什么这个功能要做两周"，你答不上来

**这一节不是要把你变成工程师。** 它要做的是：给你一张地图，让你知道"计算机世界"里都有些什么，哪些和你有关，哪些可以忽略。

> 🌐 **In English:** This section provides a panoramic map of computer science knowledge. You don't need to master everything — just know what exists and what matters for your role as a PM.



---



## 🗺️ PM 需要了解的计算机知识全景图

想象计算机知识是一栋四层大楼，你作为 PM，不需要每层都住，但至少要知道每层住着谁。



### 🏢 第一层（地基）：你不需要懂的

> 底层硬件、汇编语言、电路设计、芯片架构……
>
> 这些留给硬件工程师。你只需要知道：电脑靠芯片运行，芯片越强越贵。完毕。



### 🏢 第二层（结构）：你知道就行的

> 操作系统、编译原理、算法复杂度、计算机网络底层协议……
>
> 你不需要理解内核调度，但你要知道：程序运行需要操作系统，算法有快有慢。



### 🏢 第三层（装修）：你最好懂的

> HTTP 协议、JSON 格式、版本控制（Git）、基本的命令行操作……
>
> 这些概念你几乎每天都会碰到。懂了它们，和工程师的沟通效率提升 80%。



### 🏢 第四层（你住的楼层）：你必须懂的

> API、数据库基本概念、前端与后端、云服务（Cloud）……
>
> 这些直接影响你的产品决策。不懂 API，你没法评估第三方集成；不懂数据库，你没法理解数据产品。



> 🌐 **In English:** Think of CS knowledge as a 4-story building. PMs live on the top floor (APIs, databases, frontend/backend, cloud). You should visit the 3rd floor often (HTTP, JSON, Git). Floors 1-2 are for specialists.



---



## 📊 每个知识点 PM 需要懂到什么程度



### ✅ 你必须懂的（日常工作直接用到）

| 知识点 | 你需要懂到什么程度 | 典型场景 |
|:------|:----------------|:--------|
| **API**（应用编程接口） | 知道 API 是"两个系统之间的对话方式"，能看懂 API 文档的大意 | 评估第三方服务接入、定义数据接口 |
| **数据库** | 知道数据存在"表"里，能理解"查询""字段""索引"这些词 | 设计数据产品、理解性能瓶颈 |
| **前端与后端** | 前端是用户看到的界面，后端是服务器上的逻辑和数据 | 拆分需求、分配开发资源 |
| **云服务（Cloud）** | 知道服务器不用自己买，可以"租"，按量付费 | 评估成本、选择技术方案 |



> 💡 **类比时间：** API 就像餐厅的菜单——你（前端）看着菜单点菜，厨房（后端）按菜单做菜，菜单就是 API。你不需要知道厨房怎么炒菜，但你要看得懂菜单。
>
> ⚠️ *这只是帮助理解的类比，实际 API 比"菜单"复杂得多。*



> 🌐 **In English:** APIs are like menus between systems. Databases are like organized spreadsheets. Frontend is what users see; backend is the logic behind it. Cloud means renting servers instead of buying them.



### 🟡 你最好懂的（提升沟通效率）

| 知识点 | 你需要懂到什么程度 | 典型场景 |
|:------|:----------------|:--------|
| **HTTP 协议** | 知道浏览器和服务器通过 HTTP "对话"，懂 200（成功）、404（没找到）、500（服务器出错） | 排查线上问题、理解技术方案 |
| **JSON 格式** | 知道 JSON 是一种数据格式，长得像 `{"name": "小明", "age": 25}` | 看 API 文档、理解数据结构 |
| **版本控制（Git）** | 知道代码有"版本"，可以回退、可以多人协作 | 理解发布流程、协调多人开发 |



> 💡 **类比时间：** HTTP 状态码就像快递单号查询——200 是"已签收"，404 是"查无此单"，500 是"快递站系统崩了"。
>
> ⚠️ *这只是帮助理解的类比。*



> 🌐 **In English:** HTTP is how browsers talk to servers (200 = OK, 404 = Not Found, 500 = Server Error). JSON is a universal data format. Git tracks code versions like "Track Changes" in Word.



### ⚪ 你知道就行的（偶尔会碰到）

| 知识点 | 你需要懂到什么程度 | 典型场景 |
|:------|:----------------|:--------|
| **算法复杂度** | 知道算法有快有慢，工程师说"这个是 O(n²)"意思是"数据一多就很慢" | 理解性能优化讨论 |
| **操作系统** | 知道程序跑在操作系统上，iOS / Android / Linux 是不同的系统 | 跨平台需求评估 |
| **编译原理** | 知道代码需要"翻译"成机器能懂的语言才能运行 | 理解构建和发布流程 |



> 🌐 **In English:** Algorithm complexity = some code runs slower with more data. Operating systems = the platform software runs on. Compilation = translating code into machine-readable instructions.



### 🚫 你不需要懂的（留给专业工程师）

| 知识点 | 为什么你不需要懂 |
|:------|:---------------|
| **底层硬件设计** | 除非你做芯片产品 |
| **汇编语言** | 这是和机器直接对话的语言，离产品太远 |
| **内核开发** | 操作系统内部的事，和产品需求无关 |



---



## 🎯 AI 产品经理视角：AI 时代额外需要懂的技术概念

进入 AI 时代，产品经理的"技术地图"需要新增一块区域。以下是 AI PM 比传统 PM **额外**需要了解的概念：



| 概念 | 一句话解释 | 为什么 PM 要懂 |
|:----|:---------|:-------------|
| **模型（Model）** | AI 从数据中学到的"判断能力" | 选型、评估 AI 能力的基础 |
| **训练（Training）** | 让 AI 学习数据的过程 | 影响成本和时间规划 |
| **推理（Inference）** | AI 给出答案的过程 | 每次调用都有成本，影响定价 |
| **Prompt（提示词）** | 你给 AI 的"指令" | 直接决定 AI 产品的用户体验 |
| **Token（词元）** | AI 处理文本的最小单位 | 影响 API 调用成本的计算 |
| **幻觉（Hallucination）** | AI 编造不存在的信息 | 产品设计必须考虑的风险 |
| **RAG（检索增强生成）** | 让 AI 先查资料再回答 | 提升准确性的常见技术方案 |



> 💡 **一个比喻：** 传统 PM 像餐厅经理，管好厨师（工程师）和顾客（用户）就行。AI PM 还要管一个"会自己发挥的机器人厨师"——它有时做得好，有时乱加调料（幻觉），你必须了解它的脾气。
>
> ⚠️ *这只是帮助理解的类比。*



> 🌐 **In English:** AI PMs need additional knowledge: Models (learned capabilities), Training (learning process), Inference (generating answers), Prompts (instructions to AI), Tokens (text units that cost money), Hallucination (AI making things up), and RAG (retrieval-augmented generation).



---



## 📝 要点总结

1. **计算机知识像一栋楼** —— PM 住在顶层（API、数据库、前后端、云），偶尔下楼看看就行
2. **四个层级** —— 必须懂 → 最好懂 → 知道就行 → 不需要懂，把有限精力花在刀刃上
3. **AI 时代新增了一块地图** —— 模型、训练、推理、Prompt、Token、幻觉、RAG 是 AI PM 的必修课
4. **目标不是成为工程师** —— 而是能听懂工程师在说什么，能问出正确的问题



> 🌐 **Key Takeaways:**
>
> 1. CS knowledge is a building — PMs live on the top floor (APIs, databases, frontend/backend, cloud)
> 2. Four priority levels: Must know → Should know → Nice to know → Don't need
> 3. AI era adds new territory: Models, Training, Inference, Prompts, Tokens, Hallucination, RAG
> 4. The goal isn't to become an engineer — it's to ask the right questions



---



> 📚 **下一节预告：** [02 什么是模型、训练、推理](02_what_models_training_and_inference_are.md) —— 理解 AI 产品的三块地基。
