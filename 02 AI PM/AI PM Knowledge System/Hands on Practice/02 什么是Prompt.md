📌 **一句话版本**
Prompt就是你给AI的"任务描述"，写得越清楚，AI的输出就越好用。

> 🌐 **In English:**
> A prompt is the instruction you give to an AI. The clearer you write it, the better the output you get.

---

## 📖 这一节在讲什么

很多人第一次用AI的感受是："这玩意儿怎么这么蠢？"
然后另一些人的感受是："卧槽，这也太厉害了！"

区别通常不在AI，而在于**你怎么说话**。

Prompt（提示词）就是你输入给AI的那段文字。
AI不会猜你的想法，它只能根据你给的信息来工作。
这一节教你怎么写一个让AI真正有用的Prompt。

> 🌐 **In English:**
> The difference between "this AI is useless" and "this AI is amazing" usually comes down to **how you talk to it.** A prompt is what you type to the AI. It can only work with the information you provide — it won't guess your intent.

---

## 🧠 什么是Prompt

Prompt，直译是"提示"，在AI语境里就是**你给AI的输入文字**。

一个Prompt可以是：
- 一句话的问题
- 一段详细的任务描述
- 包含背景、要求、格式的完整指令

AI根据你的Prompt来生成回答。
Prompt越清晰、越具体，回答质量通常越高。

> 🌐 **In English:**
> A prompt is the text you give to an AI model. It can be a simple question, a detailed task description, or a full instruction with context, requirements, and format guidelines.

---

## 🎯 好Prompt vs 差Prompt

### 对比示例1：写一份产品分析

**差Prompt：**
```
帮我分析一下这个产品。
```

**好Prompt：**
```
你是一位有10年经验的产品经理。
请从用户价值、商业模式、竞争壁垒三个维度，
分析"得物"App的产品策略。
每个维度写2-3句话，用中文输出。
```

---

**差Prompt的问题：**
- "这个产品"是哪个产品？AI不知道
- 要分析什么角度？不清楚
- 输出多长？什么格式？没说

**好Prompt做对了什么：**
- 给了AI一个角色（有经验的产品经理）
- 明确了分析对象（得物App）
- 规定了分析维度（3个维度）
- 控制了输出格式（每维度2-3句，中文）

---

### 对比示例2：写用户故事

**差Prompt：**
```
写个用户故事。
```

**好Prompt：**
```
请帮我写一个用户故事，格式如下：
作为[用户角色]，我希望[功能]，
以便[获得的价值]。

背景：我们在做一个外卖App的评价功能，
目标用户是25-35岁的都市白领。
请写3个不同场景的用户故事。
```

---

## 🏗️ 好Prompt的四个要素

一个高质量的Prompt通常包含以下四个部分，
不一定每次都要全部用上，但越完整越好：

| 要素 | 说明 | 示例 |
|------|------|------|
| 角色 | 让AI扮演什么身份 | "你是一位资深产品经理" |
| 背景 | 提供必要的上下文 | "我们在做B端SaaS产品" |
| 任务 | 具体要做什么 | "分析以下3个竞品" |
| 格式 | 期望的输出形式 | "用表格输出，3列" |

> 🌐 **In English:**
> A high-quality prompt typically includes four elements:
> **Role** (who AI should act as), **Context** (background info),
> **Task** (what to do), **Format** (how to output).

---

## 🎭 角色设定技巧（Role Prompting）

告诉AI扮演一个特定角色，能显著提升输出质量。
这是因为角色设定帮助AI激活相关的知识和表达风格。

**常用角色模板：**

```
你是一位有[N]年经验的[职业]，
专注于[领域]。
请用专业但易懂的方式回答我的问题。
```

**产品经理常用角色：**
- 用户研究员
- 竞品分析师
- 增长黑客
- UX设计师
- 技术架构师（帮你理解技术）

💡 **提示：** 角色设定不是万能的，
AI还是可能给出错误信息。
记得用批判性思维审查输出结果。

---

## 🔢 Few-Shot（举例示范）

Few-Shot是指在Prompt里提供几个示例，
让AI按照你的例子来生成内容。

**示例：**

```
请帮我给用户通知消息写文案，
风格要简洁、友好。

示例1：
输入：用户完成了首次购买
输出：🎉 恭喜完成第一笔订单！

示例2：
输入：用户的积分快过期了
输出：⏰ 你有120积分将于7天后到期

现在请写：
输入：用户关注的商品降价了
输出：
```

提供了两个示例之后，AI会学习你的风格和格式，
生成风格一致的第三条文案。

> 🌐 **In English:**
> Few-shot prompting means providing example inputs and outputs in your prompt, so the AI learns your style and format before generating new content.

---

## ⚠️ 常见误解

**误解1：Prompt越长越好。**
不对。Prompt要清晰，不是要长。
无关信息会分散AI的注意力，降低输出质量。

**误解2：AI会记住上一次对话。**
不一定。大多数API调用没有记忆功能。
如果需要上下文连贯，要把背景信息重新放进Prompt里。

**误解3：Prompt写好了就万事大吉。**
不对。Prompt Engineering是迭代的过程。
第一版不满意，修改重试，找到效果最好的版本。

---

## 🧪 试试看：写3个不同场景的Prompt

**练习目标：** 亲手写3个Prompt，体验不同写法的效果差异

**场景1：产品需求分析**
为你当前负责的一个功能，
写一个让AI帮你分析用户需求的Prompt。
要包含：角色、背景、任务、格式。

**场景2：会议纪要整理**
你有一段会议录音的文字版，
写一个让AI帮你整理成结构化会议纪要的Prompt。
用Few-Shot，提供一个示例格式。

**场景3：竞品对比**
选2个你熟悉的App（比如微信和钉钉），
写一个让AI从3个维度对比的Prompt。
要求输出表格格式。

---

**练习步骤：**

```
第一步：写出你的Prompt（先别管好不好）
第二步：在ChatGPT或Claude里运行
第三步：看输出，问自己：
  - 这是我想要的吗？
  - 哪里不符合预期？
第四步：修改Prompt，再试一次
第五步：记录你改了什么、效果如何
```

---

## 📝 Prompt迭代记录模板

每次练习后，用这个表格记录：

| 版本 | 我的Prompt | AI输出 | 问题 | 改进方向 |
|------|-----------|--------|------|----------|
| v1 | ... | ... | 太笼统 | 加具体维度 |
| v2 | ... | ... | 格式不对 | 指定表格输出 |
| v3 | ... | ... | 满意 | — |

---

## 🎯 AI产品经理视角

作为产品经理，你在工作中可以用Prompt做这些事：

- 快速起草PRD框架（让AI先生成结构）
- 分析用户反馈（让AI归类和总结）
- 生成会议纪要（输入录音文字，输出结构化摘要）
- 竞品分析初稿（让AI先做功能对比表）
- 写用户故事（批量生成，人工筛选）

关键是：**AI是你的初稿生成器，你是最终决策者。**
不要直接用AI输出，要用批判性眼光审查。

> 🌐 **In English:**
> As a PM, use prompts to generate first drafts of PRDs, analyze user feedback, create meeting notes, and compare competitors. Remember: **AI is your draft generator; you are the final decision-maker.**

---

## 📚 延伸阅读

- OpenAI Prompt Engineering Guide:
  [platform.openai.com/docs/guides/prompt-engineering](https://platform.openai.com/docs/guides/prompt-engineering)
- Anthropic Prompt Library:
  [docs.anthropic.com/claude/prompt-library](https://docs.anthropic.com/claude/prompt-library)
- Learn Prompting（免费教程）:
  [learnprompting.org](https://learnprompting.org)

---

📝 **记住这些**

- Prompt = 你给AI的任务描述，越清晰越好
- 好Prompt包含：角色、背景、任务、格式
- Few-Shot：用示例告诉AI你想要什么风格
- Prompt需要迭代，第一版不好是正常的
- AI输出要审查，不要直接使用

---
*模块：08_动手实践 | 文件：01_第一次和AI对话_理解Prompt*
