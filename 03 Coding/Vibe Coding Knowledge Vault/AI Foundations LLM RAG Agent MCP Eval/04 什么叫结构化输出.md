> 📌 **一句话版本：** 当你要求 AI 输出 `JSON Schema` 约束下的结构化结果时，你得到的不再只是“好看的文字”，而是更容易被程序继续处理和验证的工作材料。

---

## 📖 这一节在讲什么

很多人用 AI 时，只把它当成聊天工具。但一旦你开始做自动化、Agent 工作流、工具调用、批量处理，就会发现“结构化输出”才是关键能力之一。因为系统真正需要的，不是漂亮段落，而是稳定字段。

## 🧠 什么叫结构化输出

结构化输出就是：你不只是让模型“说点什么”，而是明确要求它按固定字段、固定层级、固定类型返回结果。

例如，你不是说：

“帮我总结这段需求。”

而是说：

“请返回一个 JSON，对象包含 `summary`、`risks`、`open_questions`、`next_steps` 四个字段。”

## 🎯 为什么这很重要

- 方便程序直接读取
- 减少人工二次整理
- 降低输出格式漂移
- 更容易校验缺字段、错字段、空字段
- 更适合进入多步工作流

> 🌐 **In English:**
> Structured outputs make AI results easier to validate, parse, and reuse in downstream workflows. This is essential for automation and agent-based systems.

## 🧱 JSON Schema 是什么

你可以把 `JSON Schema` 理解成“对 JSON 输出结构的合同说明”。它能定义：

- 需要哪些字段
- 每个字段是什么类型
- 哪些字段必填
- 哪些字段是数组、对象或枚举值

这能帮助模型更稳定地按你想要的格式返回结果，也能帮助程序更可靠地检查结果是否合格。

## ⚖️ 普通文本输出和结构化输出的区别

| 类型 | 优点 | 风险 |
|------|------|------|
| 普通文本 | 自然、灵活 | 难解析、格式飘 |
| 结构化输出 | 易校验、易编排 | 需要前期定义结构 |

## 💡 一个典型场景

假设你要做“需求审查助手”，你可以让 AI 返回：

```json
{
  "summary": "简要总结",
  "risks": ["风险1", "风险2"],
  "open_questions": ["待确认点1"],
  "priority": "high"
}
```

这样后面你就能：

- 把 `risks` 单独显示在页面
- 把 `open_questions` 发送给协作同学
- 按 `priority` 做排序或过滤

## 🔧 它和工具调用、MCP 的关系

当模型调用工具时，往往也需要结构化参数。比如：

- 工具名称是什么
- 需要哪些参数
- 参数类型是什么
- 返回结果应该长什么样

这就是为什么你理解 `JSON` 和 `Schema` 后，再看 `MCP`、AI agent、多工具编排，会清楚很多。

> 🌐 **In English:**
> Tool calling depends on structured inputs and outputs. Once you understand JSON and schemas, concepts like MCP and agent workflows become much easier to reason about.

## ⚠️ 常见误区

### 误区一：只要写“请输出 JSON”就够了

如果没有约束字段名、字段类型和必填项，模型仍然可能给你不稳定的结构。

### 误区二：结构化输出就不会出错

结构更稳定，不代表内容一定正确。字段可能齐了，但值仍可能是错的、空的或误导的。

### 误区三：结构化输出只适合工程师

其实产品经理也非常适合使用它，因为你经常需要让 AI 返回“可继续处理”的结果，而不是只能人工阅读的文字。

## 🧪 一个实战思路

当你下次让 AI 帮你做需求分析时，可以试着要求它返回：

- `summary`
- `user_value`
- `implementation_risks`
- `metrics`
- `open_questions`

然后你再观察：

- 字段是不是稳定
- 有没有缺项
- 哪些值还需要人工补充

## 🎯 结构化输出和并发工作流

当一个系统里有多个 agent 或多个工具并行工作时，结构化输出会更关键。因为这时不只是“给人看”，而是“给下一个工具继续处理”。输出越规整，工作流越稳定。

## 📝 记住这些

- 普通文本适合阅读，结构化输出适合自动化。
- `JSON Schema` 是定义输出合同的关键概念。
- 即使有了结构化输出，你也仍然需要验证内容是否真实、完整、可执行。

## 📚 延伸阅读

- [02_JSON_YAML_TOML与配置文件.md](../02_terminal_shell_filesystem_and_environment/02_json_yaml_toml_and_configuration_files.md)
- [03_同步_异步_并发_队列与任务系统.md](../06_backend_foundations_http_api_auth_and_services/03_sync_async_concurrency_queues_and_task_systems.md)
- [00_Codex_CLI与Claude_Code全景.md](../10_ai_coding_tools_codex_cli_claude_code/00_codex_cli_and_claude_code_overview.md)
