> 📌 **一句话版本：** `JSON`、`YAML`、`TOML` 都是结构化文本格式，本质是在用人和程序都能读懂的方式表达“配置”和“数据”。

---

## 📖 这一节在讲什么

你今天听到的 `JSON` 非常重要，因为它几乎无处不在：前后端接口返回值、AI 工具结构化输出、配置文件、日志、埋点、工作流参数、MCP 工具输入输出，经常都和它有关。理解它以后，你会更容易看懂接口、调试工具、读懂报错。

## 🧠 什么是 JSON

`JSON` 的全称是 `JavaScript Object Notation`。虽然名字里有 JavaScript，但它早就变成了一种跨语言、跨工具的通用数据交换格式。

它最大的价值是两点：

1. 人能读
2. 程序也容易解析

一个最简单的例子：

```json
{
  "name": "Daily Summary",
  "enabled": true,
  "retry_count": 3
}
```

## 🎯 为什么 JSON 对产品经理特别重要

- 看接口文档时，经常看到请求体和响应体是 JSON。
- 看 AI 输出时，经常需要它返回结构化 JSON，方便后续程序处理。
- 看埋点、配置、自动化任务时，经常碰到键值结构。
- 你以后写脚本、调试接口、检查日志时，JSON 都是高频材料。

> 🌐 **In English:**
> JSON is a structured text format used to exchange data between systems. It matters because APIs, AI tool outputs, configs, and logs often rely on JSON-shaped data.

## 🧱 JSON 的基础组成

### 对象 Object

对象是一组 `键:值` 的集合，外层用花括号包起来。

```json
{
  "title": "Weekly Report",
  "owner": "PM"
}
```

### 数组 Array

数组是一组有顺序的值，外层用方括号包起来。

```json
["todo", "doing", "done"]
```

### 常见值类型

- 字符串：`"hello"`
- 数字：`42`
- 布尔值：`true` / `false`
- 空值：`null`
- 对象：`{}`
- 数组：`[]`

## ⚠️ JSON 最常见的坑

### 坑一：键必须是双引号

很多语言里你可能见过单引号，但标准 JSON 的键和字符串都应该用双引号。

### 坑二：最后一项后面不能多逗号

```json
{
  "a": 1,
  "b": 2
}
```

最后一个字段后面多一个逗号，很多解析器就会报错。

### 坑三：JSON 和“长得像 JSON 的对象”不是一回事

有些编程语言或工具展示的数据结构，长得像 JSON，但不一定是合法 JSON。比如单引号、注释、尾逗号，都可能让它无法被标准解析器读取。

## ⚖️ JSON、YAML、TOML 的区别

| 格式 | 适合什么 | 你会在哪看到 |
|------|---------|--------------|
| JSON | 数据交换 | API、日志、AI 输出 |
| YAML | 人工配置 | CI、部署、应用配置 |
| TOML | 规则清晰的配置 | 工具配置、项目设置 |

### YAML 的感觉

YAML 更像“缩进驱动”的配置描述，比较适合人手写，但也更容易因为缩进出错。

### TOML 的感觉

TOML 比 YAML 更规整，适合写项目配置，比如工具参数、环境设置。

> 🌐 **In English:**
> JSON is great for machine-friendly data exchange, YAML is common for human-edited configuration, and TOML is often used for structured tool settings.

## 💡 在真实工作里怎么理解 JSON

### 场景一：看接口返回

你打开浏览器开发者工具或接口测试工具，经常会看到：

```json
{
  "code": 0,
  "message": "ok",
  "data": {
    "id": 101,
    "title": "April Plan"
  }
}
```

这里的重点不是背格式，而是会看：

- 哪些字段是元信息
- 哪个字段是真正业务数据
- 字段名和含义是否稳定

### 场景二：让 AI 按结构输出

你可以要求 AI：

“请返回合法 JSON，字段包括 `summary`、`risks`、`next_actions`。”

这样做的好处是，后续脚本或系统更容易继续处理结果。

### 场景三：看配置文件

你经常会遇到：

- `package.json`
- `tsconfig.json`
- `settings.json`
- `config.toml`

它们不是业务代码，却会直接影响项目怎么运行。

## 🧪 最小练习

找一个你现在机器上的 JSON 文件，比如 `package.json` 或某个接口返回，试着回答：

1. 最外层是对象还是数组
2. 里面有哪些关键字段
3. 哪些字段是配置，哪些字段是内容
4. 如果少一个字段，会影响什么

## 🎯 JSON 和 Vibe Coding 的关系

你以后会在这些地方反复遇到 JSON：

- 接口请求与响应
- AI 的结构化输出
- 工具调用参数
- 自动化脚本输入输出
- 配置文件
- 日志和调试信息

如果你看不懂 JSON，很多 AI 和工程工具都会像“有字天书”。

## 🧩 怎样真正读懂一个 JSON

很多人以为“看懂 JSON”就是看懂括号，其实真正难的是看懂结构关系。你可以按下面顺序读：

### 第一步：看最外层

先判断最外层是对象还是数组。

- 如果是对象，通常代表“一个整体实体”
- 如果是数组，通常代表“多个同类项”

### 第二步：找核心业务字段

不是每个字段都同样重要。很多接口会有：

- `code`
- `message`
- `data`

这时候真正有业务意义的内容，往往藏在 `data` 里。

### 第三步：看字段类型

字段名一样，不代表类型一定稳定。你要看：

- 是字符串还是数字
- 是单个对象还是数组
- 会不会是 `null`

这直接决定前端、脚本、AI 工作流后面能不能稳定处理。

> 🌐 **In English:**
> Reading JSON is about understanding structure, field importance, and data types, not just recognizing braces and brackets.

## 💡 一个更真实的接口例子

```json
{
  "code": 0,
  "message": "ok",
  "data": {
    "user": {
      "id": 12,
      "name": "Chen"
    },
    "permissions": ["read", "write"],
    "is_new_user": false
  }
}
```

你可以这样拆：

- `code`：这次请求是否成功
- `message`：服务端给的说明
- `data.user.name`：真正要显示给用户的信息
- `permissions`：后面可能决定按钮是否可点
- `is_new_user`：可能决定是否展示新手引导

这就说明，JSON 不只是“数据长什么样”，而是直接连接业务逻辑。

## ⚠️ 字段变化为什么会引发线上问题

当系统升级时，最常见的问题之一就是字段变化，比如：

- 字段名变了
- 类型变了
- 可空性变了
- 嵌套层级变了

这些变化看起来像“小改动”，但前端、脚本、AI 自动化、报表逻辑都可能因此失效。所以你以后只要听到“接口字段调整”，就要立刻想到影响范围。

## 🎯 为什么 AI 工作流特别依赖 JSON

当你让 AI 输出自由文本时，人看得懂，但程序不一定好接。

当你让 AI 输出 JSON 时：

- 后面的脚本更容易解析
- 字段缺失更容易发现
- 多步骤 agent 工作流更稳定
- 可以做结构校验

这也是为什么现在很多 tool calling、structured output、MCP 参数都围绕 JSON 展开。

## 🧭 PM 看 JSON 时要养成的习惯

- 先找业务核心字段
- 再看字段是否稳定
- 再看异常情况怎么表示
- 最后再想它怎么被页面、脚本或 AI 工具消费

## 🧪 一个很有用的练习方式

以后你看到一个接口返回时，试着口头把它翻译成一句人话：

“这个接口告诉我，本次请求成功了，用户叫 Chen，有读写权限，不是新用户。”

当你能把 JSON 稳定翻译成人话，说明你已经开始真正理解它了。

## 📝 记住这些

- JSON 是“结构化数据”的通用语言。
- 它最重要的不是语法，而是你能不能读懂字段结构和数据边界。
- 一旦你学会看 JSON，看接口、看 AI 输出、看工具配置都会轻松很多。

## 📚 延伸阅读

- [00_Web应用是怎样跑起来的.md](../04_web_foundations_html_css_js_ts/00_how_web_apps_actually_run.md)
- [02_用Python处理文件_JSON_Excel与接口.md](../08_python_foundations_and_automation/02_using_python_for_files_json_excel_and_apis.md)
- [03_JSON_Schema_结构化输出与工作流编排.md](../09_ai_foundations_llm_rag_agent_mcp_eval/03_json_schema_structured_output_and_workflow_orchestration.md)
