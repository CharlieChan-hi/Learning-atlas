📌 **一句话版本**
RAG就是让AI"先查资料再回答"，
解决AI不知道你公司私有知识的问题。

> 🌐 **In English:**
> RAG (Retrieval-Augmented Generation) lets AI "look up documents before answering," solving the problem of AI not knowing your company's private knowledge.

---

## 📖 这一节在讲什么

你有没有遇到过这种情况：
把公司产品文档发给ChatGPT，让它帮你解答问题，
但它的回答和你的文档对不上号。

这是因为AI的知识是训练时"烤进去"的，
它不认识你们公司的内部资料、私有知识库、
最新的产品规格文档。

RAG（检索增强生成）就是解决这个问题的方法。
这一节用生活化的比喻帮你理解RAG，
然后用最简单的方式让你亲手体验一次。

> 🌐 **In English:**
> AI's knowledge is "baked in" during training — it doesn't know your company's internal docs or private knowledge base. RAG solves this by letting AI retrieve relevant documents before generating an answer.

---

## 🧠 用生活比喻理解RAG

想象一个场景：

你参加了一个考试，题目是关于你从没学过的领域。
普通AI的做法是：凭记忆硬答，可能答错。

**RAG的做法：**
1. 先打开一堆参考书（检索文档）
2. 找到和题目最相关的段落（向量匹配）
3. 把相关段落和题目一起给AI看
4. AI基于这些材料来回答（生成答案）

更接地气的比喻：
RAG就像一个"开卷考试"，
AI可以查资料，而不是全靠死记硬背。

> 🌐 **In English:**
> RAG is like an "open-book exam" for AI. Instead of relying on memorized training data, it can search through provided documents and use relevant passages to construct its answer.

---

## 🏗️ RAG的核心组件

一个完整的RAG系统由以下几个部分组成：

```
用户问题
    ↓
[检索模块] ← 知识库（你的文档）
    ↓
相关文档片段
    ↓
[生成模块] ← LLM（大语言模型）
    ↓
最终回答
```

**四个核心组件：**

| 组件 | 作用 | 技术实现 |
|------|------|---------|
| 文档加载 | 读入你的知识文档 | PDF/Word/网页解析 |
| 向量化 | 把文本转成数字向量 | Embedding模型 |
| 向量检索 | 找最相关的文档片段 | 向量数据库 |
| 答案生成 | 基于检索结果回答 | LLM（GPT/Claude等） |

💡 **提示：** "向量化"这个词听起来很难，
但你可以这样理解：
把每段文字变成一串数字，
语义相近的文字，数字就相近。
这样就能用数学方法找"最相关的段落"。

> 🌐 **In English:**
> Vectorization converts text into numbers. Semantically similar text produces similar numbers, allowing mathematical retrieval of the most relevant passages.

---

## 🚀 方法一：不写代码体验RAG

最简单的RAG体验方式：
**用ChatGPT的文件上传功能**。

**步骤：**

```
1. 打开 chat.openai.com（需要Plus账号）
   或使用 Claude.ai（免费版支持文件上传）

2. 点击对话框的"+"或回形针图标

3. 上传一个PDF文档
   （可以用你们产品的PRD或竞品分析报告）

4. 输入问题：
   "根据我上传的文档，
   总结这个产品的核心功能有哪些？"

5. 观察AI的回答
   - 它是否引用了文档里的具体内容？
   - 它回答的准确吗？
   - 如果你问文档里没有的内容，它怎么处理？
```

这本质上就是一个简化版的RAG体验：
你提供了"知识库"（文件），
AI在这个知识库里检索信息来回答问题。

---

## 💻 方法二：用代码搭建最简RAG

如果你想亲手用代码体验，下面是最精简的实现。
不需要向量数据库，用关键词匹配模拟检索。

**先安装依赖：**

```bash
pip install openai
```

**最简RAG示例（约30行）：**

```python
from openai import OpenAI

client = OpenAI(api_key="YOUR_API_KEY")

# 模拟知识库（实际项目里是文档）
knowledge_base = [
    "产品A的目标用户是25-35岁都市白领",
    "产品A的核心功能是AI智能推荐和社交分享",
    "产品A的商业模式是订阅制，月费68元",
    "产品A的竞品是产品B和产品C",
]

def simple_retrieve(query, docs, top_k=2):
    """简单关键词匹配检索"""
    scored = []
    for doc in docs:
        score = sum(
            1 for word in query
            if word in doc
        )
        scored.append((score, doc))
    scored.sort(reverse=True)
    return [doc for _, doc in scored[:top_k]]

def rag_answer(question):
    # 第一步：检索相关文档
    relevant_docs = simple_retrieve(
        question, knowledge_base
    )
    context = "\n".join(relevant_docs)

    # 第二步：带着上下文问AI
    response = client.chat.completions.create(
        model="gpt-4o-mini",
        messages=[
            {
                "role": "system",
                "content": f"""请基于以下资料回答：
{context}
如果资料里没有答案，
请说"资料中未包含此信息"。"""
            },
            {"role": "user", "content": question}
        ]
    )
    return response.choices[0].message.content

print(rag_answer("产品A的目标用户是谁？"))
print(rag_answer("产品A的价格是多少？"))
print(rag_answer("产品A的CEO是谁？"))
```

**运行后观察：**
- 第1个问题：AI能准确回答（知识库里有）
- 第2个问题：AI能准确回答（知识库里有）
- 第3个问题：AI应该说"资料中未包含此信息"

---

## 📊 RAG效果观察表

做完练习后，用这个表格记录你的观察：

| 问题类型 | 知识库有？ | AI回答准确？ | 观察备注 |
|---------|----------|------------|---------|
| 产品核心功能 | 有 | 是/否 | ... |
| 价格信息 | 有 | 是/否 | ... |
| 公司历史 | 无 | 是/否 | ... |

---

## 🎯 AI产品经理视角：如何评估RAG效果

当工程师实现了RAG功能后，
你作为产品经理应该从以下角度评估效果：

**评估维度一：召回率**
问10个知识库里有答案的问题，
AI答对了几个？
目标：≥ 8个答对。

**评估维度二：准确率**
AI引用了知识库内容的问题里，
引用准确的有几个？
目标：100%准确引用，不能"凭空捏造"。

**评估维度三：边界处理**
问5个知识库里没有答案的问题，
AI是否正确地说"不知道"而不是乱编？
这个非常重要，乱编是最危险的情况。

**评估维度四：响应速度**
检索+生成总共花了多少秒？
用户可接受的等待通常在3-5秒以内。

> 🌐 **In English:**
> As a PM evaluating RAG: check recall rate (does it find relevant docs?), accuracy (does it cite correctly?), boundary handling (does it say "I don't know" when it should?), and response latency.

---

## ⚠️ 常见误解

**误解1：RAG可以解决所有AI幻觉问题。**
不对。RAG能减少幻觉，但不能完全消除。
AI还是可能在引用文档时断章取义，
或者把文档里的信息和自己的"记忆"混淆。

**误解2：知识库越大越好。**
不一定。知识库太大会影响检索精度，
而且每次检索出来的文档越多，
放进Prompt的内容越多，
token成本也越高，速度也越慢。

**误解3：有了RAG就不需要训练模型了。**
不对。RAG适合"需要随时更新知识"的场景，
比如公司文档库。
对于需要AI深度理解某个领域的场景，
还是需要微调（Fine-tuning）。

---

## 🧪 进阶体验：用Kimi/文心一言

国内可以用这些平台体验RAG：

```
Kimi（月之暗面）：kimi.moonshot.cn
  - 免费版支持上传文件
  - 可以上传PDF、Word、Excel

文心一言（百度）：yiyan.baidu.com
  - 支持文档解读功能

360 AI：ai.360.com
  - 支持文档问答
```

试验方法：
1. 上传你们产品的竞品分析文档
2. 问一些文档里有答案的问题
3. 问一些文档里没有答案的问题
4. 观察AI怎么处理这两种情况

---

## 📚 延伸阅读

- LangChain RAG 教程（英文）：
  [python.langchain.com/docs/use_cases/question_answering](https://python.langchain.com/docs/use_cases/question_answering)
- 什么是向量数据库（科普）：
  搜索"pinecone what is vector database"
- RAG vs Fine-tuning 对比：
  搜索"RAG vs fine-tuning when to use"

---

📝 **记住这些**

- RAG = 先检索文档，再基于文档生成回答
- 核心步骤：文档向量化 → 相似性检索 → 带上下文生成
- 不写代码：用ChatGPT/Claude的文件上传功能体验
- PM评估RAG要看：召回率、准确率、边界处理、速度
- 知识库里没有的内容，AI应该说"不知道"

---
*模块：08_动手实践 | 文件：04_搭建一个简单的RAG应用*
