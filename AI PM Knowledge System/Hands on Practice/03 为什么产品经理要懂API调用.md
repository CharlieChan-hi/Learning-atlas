📌 **一句话版本**
API调用就是"用代码来叫AI干活"——产品经理懂这个，
才能和工程师说清楚需求、看懂技术文档。

> 🌐 **In English:**
> Calling an AI API means "asking AI to work via code." As a PM, understanding this helps you communicate with engineers and read technical documentation.

---

## 📖 这一节在讲什么

你用ChatGPT，是通过网页界面在和AI对话。
工程师把AI集成到产品里，是通过API在和AI对话。

API（Application Programming Interface，应用程序编程接口）
本质上是一个"服务窗口"：你发一个请求过去，
它返回一个结果给你。

这一节带你亲手发一次API请求，
体验AI产品"幕后"是怎么工作的。

> 🌐 **In English:**
> When you use ChatGPT via a browser, you're talking to AI through a web interface. Engineers integrate AI into products through APIs — a "service window" where you send a request and get a response back. This section walks you through making your first API call.

---

## 🎯 为什么产品经理要懂API调用

你不需要成为工程师，但懂API调用能帮你：

- **写清楚需求**：知道参数是什么，才能告诉工程师
  "我要控制输出的随机性程度"
- **看懂技术文档**：评估第三方AI服务时，
  能自己读懂接口文档
- **评估成本**：API是按token计费的，
  懂调用才能估算成本
- **理解延迟**：为什么AI回复有时快有时慢？
  看过API响应就明白了

> 🌐 **In English:**
> You don't need to become an engineer. But understanding APIs helps you write clearer requirements, read technical docs, estimate costs, and understand latency.

---

## 🧠 核心概念：请求与响应

每次API调用都包含两个部分：

**请求（Request）**：你发出去的内容
```
{
  "model": "gpt-4o-mini",
  "messages": [
    {
      "role": "user",
      "content": "你好，介绍一下自己"
    }
  ]
}
```

**响应（Response）**：AI返回给你的内容
```
{
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "你好！我是ChatGPT..."
      }
    }
  ],
  "usage": {
    "prompt_tokens": 12,
    "completion_tokens": 45,
    "total_tokens": 57
  }
}
```

注意响应里的 `usage` 字段——这就是计费依据，
`total_tokens` 就是这次调用消耗的token数量。

---

## 🔑 第一步：注册账号，获取API Key

### OpenAI（推荐新手从这里开始）

```
1. 访问 platform.openai.com
2. 注册账号（邮箱+手机验证）
3. 进入 API Keys 页面
4. 点击 "Create new secret key"
5. 复制保存这个key（只显示一次！）
```

⚠️ **注意：** API Key是私密的，不要分享给别人，
不要上传到GitHub，不要截图发朋友圈。
泄露了要立刻在控制台里撤销。

### Anthropic Claude（替代选项）

```
1. 访问 console.anthropic.com
2. 注册账号
3. 进入 API Keys 页面创建Key
```

💡 **提示：** 两个平台都需要绑定信用卡才能
使用付费API。新用户通常有一些免费额度。
如果不想绑卡，可以先跳到"用curl测试"的部分，
用别人共享的测试环境试验。

---

## 💻 第二步：用curl发第一个请求

`curl` 是系统自带的命令行工具，
不需要安装任何东西。Mac和Linux直接用，
Windows用命令提示符（CMD）也行。

打开终端（Terminal），输入以下命令：

```bash
curl https://api.openai.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "gpt-4o-mini",
    "messages": [
      {
        "role": "user",
        "content": "用一句话介绍产品经理"
      }
    ]
  }'
```

把 `YOUR_API_KEY` 替换成你自己的Key，然后按回车。

---

**你应该看到类似这样的响应：**

```json
{
  "id": "chatcmpl-abc123",
  "object": "chat.completion",
  "model": "gpt-4o-mini",
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "产品经理是连接用户需求..."
      },
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 18,
    "completion_tokens": 30,
    "total_tokens": 48
  }
}
```

恭喜！你刚刚成功调用了一次AI API。

---

## 🐍 第三步：用Python调用（推荐）

curl很直接，但Python更灵活，
实际工作中大多数时候用Python。

**安装OpenAI库（只需要做一次）：**

```bash
pip install openai
```

**最简单的Python示例：**

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_API_KEY"
)

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {
            "role": "user",
            "content": "用一句话介绍产品经理"
        }
    ]
)

print(response.choices[0].message.content)
print("消耗token:", response.usage.total_tokens)
```

把这段代码保存为 `test_api.py`，然后在终端运行：

```bash
python test_api.py
```

---

## 🧠 理解响应结构：作为PM你要关注什么

看到响应后，作为产品经理，你最应该关注这几个字段：

| 字段 | 位置 | 含义 |
|------|------|------|
| `content` | choices[0].message | AI的回复内容 |
| `total_tokens` | usage | 本次消耗的token |
| `finish_reason` | choices[0] | 结束原因（stop正常） |
| `model` | 顶层 | 使用的模型版本 |

**`finish_reason` 的几种情况：**
- `stop`：正常结束
- `length`：达到token上限被截断
- `content_filter`：被内容安全拦截

💡 **提示：** 如果你的AI产品输出经常被截断，
工程师说"finish_reason是length"，
你就知道是token限制的问题了。

> 🌐 **In English:**
> As a PM, focus on: `content` (the AI's reply), `total_tokens` (cost basis), `finish_reason` (why it stopped), and `model` (which version was used).

---

## ⚠️ 常见误解

**误解1：API调用很贵。**
不对。一般的API调用非常便宜。
gpt-4o-mini大约每1000个token花费0.001-0.003美元，
一次普通对话通常不超过1分钱人民币。

**误解2：API和ChatGPT网页一样。**
不完全对。API没有记忆（无状态），
每次请求都是独立的。
要实现多轮对话，需要在每次请求里
带上历史消息记录。

**误解3：我要先学会编程再看这个。**
不对。上面的Python示例只有10行，
复制粘贴就能跑。你只需要理解每一行在做什么，
不需要自己从零写出来。

---

## 🧪 试试看：3个练习任务

**练习1（基础）：修改模型**
把代码里的 `gpt-4o-mini` 改成 `gpt-3.5-turbo`，
观察输出有什么不同，token消耗有什么变化。

**练习2（进阶）：修改消息内容**
把 `content` 改成你工作中一个真实的问题，
比如"帮我分析一下电商App评价功能的用户价值"。
观察输出质量。

**练习3（思考）：理解成本**
调用10次API，计算平均每次的token消耗。
换算成你们产品如果每天有1万用户问问题，
大概每天要花多少钱。

---

## 📊 实践记录模板

| 调用次数 | 我的Prompt | token消耗 | 模型 | 观察 |
|----------|-----------|----------|------|------|
| 第1次 | 介绍产品经理 | 48 | gpt-4o-mini | 简洁 |
| 第2次 | ... | ... | ... | ... |

---

## 🎯 AI产品经理视角

当工程师说"API调用延迟太高"，
你现在知道这是什么意思了：
从发出请求到收到响应的时间太长。

当产品负责人问"AI功能成本怎么估算"，
你可以说：按token计费，
先测平均每次对话消耗多少token，
再乘以单价和每日调用量。

这些对话，在你亲手调用过一次API之后，
就会变得自然而然。

> 🌐 **In English:**
> After you've made one real API call, conversations about "latency," "token cost," and "rate limits" will make immediate sense. That's the value of this exercise.

---

## 📚 延伸阅读

- OpenAI API 文档：
  [platform.openai.com/docs/api-reference](https://platform.openai.com/docs/api-reference)
- Anthropic API 文档：
  [docs.anthropic.com/claude/reference](https://docs.anthropic.com/claude/reference)
- OpenAI Cookbook（示例代码）：
  [cookbook.openai.com](https://cookbook.openai.com)

---

📝 **记住这些**

- API = 用代码叫AI干活的"服务窗口"
- 每次调用包含请求和响应
- Token是计费单位，要关注total_tokens
- finish_reason告诉你AI为什么停下来
- API是无状态的，不记忆上一次对话

---
*模块：08_动手实践 | 文件：02_第一次调用AI_API*
