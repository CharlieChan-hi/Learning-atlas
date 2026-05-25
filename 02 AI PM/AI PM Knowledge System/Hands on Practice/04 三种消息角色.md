📌 **一句话版本**
学会用System/User消息分层、控制JSON输出、
调整温度参数，让AI每次都输出你想要的格式。

> 🌐 **In English:**
> Learn to use System/User message layers, control JSON output, and adjust temperature to get AI to output exactly the format you need — every time.

---

## 📖 这一节在讲什么

上一节你学会了怎么调用API。
这一节更进一步：学会**精确控制**AI的输出。

在真实的AI产品里，你不能让AI随便输出，
必须让它按照固定格式输出，
这样才能把结果塞进数据库、显示在界面上。

这一节的核心是三件事：
1. 理解消息角色（System / User / Assistant）
2. 让AI输出JSON格式
3. 用温度参数控制输出的"随机性"

> 🌐 **In English:**
> In real AI products, you can't let AI output randomly — it must follow a fixed format so results can be stored in databases and displayed on screen. This section covers three key skills: message roles, JSON output control, and temperature tuning.

---

## 🧠 三种消息角色

在API调用里，消息分三种角色，
每种角色的用途不同：

### System（系统消息）

给AI设定"人设"和行为规则，用户看不到这条消息。
相当于你在幕后给AI发了一份工作说明书。

```python
{
    "role": "system",
    "content": "你是一位资深产品经理助手，
    专注于分析用户需求。
    请始终用中文回答，
    输出简洁、结构清晰。"
}
```

### User（用户消息）

用户（或程序代码）发出的问题和请求。

```python
{
    "role": "user",
    "content": "分析一下微信读书的核心用户需求"
}
```

### Assistant（助手消息）

AI之前回复的内容，用于实现多轮对话。
在请求里带上历史的Assistant消息，
AI就能"记住"之前说过什么。

```python
{
    "role": "assistant",
    "content": "微信读书的核心用户需求有三点..."
}
```

---

## 🏗️ 完整的多轮对话示例

```python
from openai import OpenAI

client = OpenAI(api_key="YOUR_API_KEY")

messages = [
    {
        "role": "system",
        "content": "你是一位产品分析专家，
        回答简洁专业，用中文。"
    },
    {
        "role": "user",
        "content": "分析一下微信读书的用户需求"
    }
]

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=messages
)

ai_reply = response.choices[0].message.content

# 把AI的回复加入对话历史
messages.append({
    "role": "assistant",
    "content": ai_reply
})

# 继续追问
messages.append({
    "role": "user",
    "content": "那它的商业模式呢？"
})

response2 = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=messages
)

print(response2.choices[0].message.content)
```

注意：每次请求都要把完整的消息历史带上，
AI本身不存储记忆，记忆是由你的代码维护的。

> 🌐 **In English:**
> Memory in AI chat is maintained by your code, not the AI itself. You pass the full conversation history with each request — that's how multi-turn dialogue works.

---

## 📋 让AI输出JSON格式

在产品里，我们通常需要AI输出结构化数据，
比如JSON，这样才能解析和存储。

### 方法1：在Prompt里要求JSON

```python
messages = [
    {
        "role": "system",
        "content": """你是产品分析助手。
        始终以JSON格式输出，结构如下：
        {
          "product_name": "产品名",
          "core_users": ["用户类型1"],
          "key_features": ["功能1", "功能2"],
          "business_model": "商业模式描述"
        }"""
    },
    {
        "role": "user",
        "content": "分析：微信读书"
    }
]
```

### 方法2：使用response_format参数

OpenAI支持直接指定JSON输出模式：

```python
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=messages,
    response_format={"type": "json_object"}
)
```

使用这个参数后，AI的输出一定是合法的JSON，
可以直接用 `json.loads()` 解析，不会出错。

---

**解析JSON输出的完整示例：**

```python
import json
from openai import OpenAI

client = OpenAI(api_key="YOUR_API_KEY")

response = client.chat.completions.create(
    model="gpt-4o-mini",
    response_format={"type": "json_object"},
    messages=[
        {
            "role": "system",
            "content": "输出JSON，
            包含name和summary两个字段"
        },
        {
            "role": "user",
            "content": "分析微信读书"
        }
    ]
)

result = json.loads(
    response.choices[0].message.content
)
print(result["name"])
print(result["summary"])
```

---

## 🌡️ 温度参数（Temperature）

温度参数控制AI输出的"随机性"，取值范围0到2。

| 温度值 | 输出特点 | 适合场景 |
|--------|---------|---------|
| 0 | 几乎不变，非常确定 | 结构化数据提取 |
| 0.7 | 平衡，默认值 | 通用对话 |
| 1.5+ | 创意十足，更发散 | 头脑风暴 |

**设置温度的方法：**

```python
response = client.chat.completions.create(
    model="gpt-4o-mini",
    temperature=0,
    messages=[...]
)
```

💡 **提示：** 需要稳定可重复输出时（比如提取数据），
用 `temperature=0`。
需要创意发散时（比如生成文案方案），
用 `temperature=1.0` 左右。

> 🌐 **In English:**
> Temperature controls randomness. Use 0 for deterministic tasks (data extraction), 0.7 for general use, and 1.0+ for creative brainstorming.

---

## 📏 Token限制控制

每个模型都有最大token限制，
你也可以通过 `max_tokens` 参数控制输出长度。

```python
response = client.chat.completions.create(
    model="gpt-4o-mini",
    max_tokens=200,
    messages=[...]
)
```

常见token数量参考：

| 内容 | 大约token数 |
|------|-----------|
| 1个中文字 | 约1.5 token |
| 1个英文单词 | 约1 token |
| 一篇PRD | 1000-3000 token |
| 一本小说章节 | 3000-8000 token |

⚠️ **注意：** 输入和输出都计入token消耗。
System消息越长，每次调用成本越高。

---

## 🎯 综合示例：让AI输出结构化产品分析

这是一个完整的实用示例，
把本节所有知识点都用上了：

```python
import json
from openai import OpenAI

client = OpenAI(api_key="YOUR_API_KEY")

def analyze_product(product_name):
    response = client.chat.completions.create(
        model="gpt-4o-mini",
        temperature=0,
        max_tokens=500,
        response_format={"type": "json_object"},
        messages=[
            {
                "role": "system",
                "content": """你是产品分析专家。
                输出严格的JSON格式：
                {
                  "product": "产品名",
                  "users": ["目标用户"],
                  "value": "核心价值一句话",
                  "risks": ["风险1", "风险2"]
                }"""
            },
            {
                "role": "user",
                "content": f"分析产品：{product_name}"
            }
        ]
    )
    return json.loads(
        response.choices[0].message.content
    )

result = analyze_product("得物App")
print(result)
```

---

## 🧪 试试看：实践练习

**练习1：对比不同温度的输出**
用同一个Prompt，分别设置 `temperature=0`
和 `temperature=1.2`，运行5次，
观察每次输出有多大差异。
用表格记录结果。

**练习2：写一个结构化产品分析器**
参考上面的示例，把产品名换成你熟悉的App，
让AI输出JSON格式的分析结果。
尝试增加一个字段（比如"竞品"或"核心功能"）。

**练习3：实现一个简单的多轮对话**
让AI先分析一个产品的用户需求，
然后追问"这个产品的变现方式是什么"，
确认AI能记住第一次的分析内容来回答。

---

## ⚠️ 常见误解

**误解1：System消息是强制规则，AI一定会遵守。**
不对。System消息只是优先级更高的指令，
但AI并非100%服从，
特别是当任务复杂时可能会"忘记"格式要求。
需要在User消息里再次强调格式。

**误解2：temperature=0 的输出完全一致。**
不完全对。大多数情况下几乎一样，
但底层随机性没有完全消除，
极少数情况下还是可能有微小差异。

**误解3：JSON输出不需要验证。**
不对。即使用了 `response_format=json_object`，
字段内容还是可能不对（比如该是数组却输出了字符串）。
生产代码里要加 try/except 来处理解析错误。

---

## 🎯 AI产品经理视角

工程师在实现AI功能时，
一定会遇到"怎么让AI稳定输出结构化数据"的问题。
你现在理解了System消息、温度、JSON模式，
就能在需求评审会上说：

"AI提取用户意图时，建议用temperature=0
确保稳定性，System消息里规定JSON格式，
这样前端就能直接解析不用再做清洗。"

这样的需求描述，
会让工程师觉得你真的懂技术。

> 🌐 **In English:**
> When you understand system messages, temperature, and JSON mode, you can write requirements like: "Use temperature=0 for stable output; enforce JSON format in the system message so the frontend can parse directly without cleaning." That's the kind of PM engineers love.

---

## 📚 延伸阅读

- OpenAI JSON Mode 文档：
  [platform.openai.com/docs/guides/structured-outputs](https://platform.openai.com/docs/guides/structured-outputs)
- OpenAI API 参数参考：
  [platform.openai.com/docs/api-reference/chat](https://platform.openai.com/docs/api-reference/chat)

---

📝 **记住这些**

- System = 给AI的幕后指令，User = 用户输入
- 多轮对话靠代码维护消息历史
- `response_format=json_object` 强制JSON输出
- 温度0=稳定确定，温度高=创意发散
- token输入+输出都计费，System消息要精简

---
*模块：08_动手实践 | 文件：03_结构化Prompt与输出控制*
