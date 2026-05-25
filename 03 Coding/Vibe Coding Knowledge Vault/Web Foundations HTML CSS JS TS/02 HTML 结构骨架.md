> 📌 **一句话版本：** 在现代 Web 里，`HTML` 负责结构，`CSS` 负责样式，`JavaScript` 负责行为，`TypeScript` 负责让复杂代码更可维护、更不容易出错。

---

## 📖 这一节在讲什么

你以后看前端项目、设计稿实现、页面报错、组件改动时，最容易碰到的就是这四个词。它们经常一起出现，但分工并不一样。搞清楚分工以后，你对“这次改动到底是在改什么”会有更稳定的判断。

## 🧱 HTML：结构骨架

`HTML` 决定页面里有什么内容和层级，比如标题、段落、按钮、表单、图片、列表。

你可以把它理解成房子的钢筋和房间布局。没有它，页面就没有清晰结构。

## 🎨 CSS：视觉样式

`CSS` 决定页面看起来怎么样，比如颜色、字体、间距、布局、响应式效果、动效。

同样一个按钮，只改 CSS，就能从“普通灰按钮”变成“品牌风格主按钮”。

## ⚙️ JavaScript：行为和逻辑

`JavaScript` 决定页面会不会“动起来”。点击按钮后弹框、发接口、刷新列表、表单校验、状态切换，都通常由它控制。

## 🛡 TypeScript：给 JavaScript 加结构约束

`TypeScript` 不是另一门完全不同的语言，而是在 JavaScript 基础上增加类型系统，帮助你在开发阶段更早发现错误。

例如，一个接口本来应该返回：

```json
{
  "id": 1,
  "title": "Plan"
}
```

如果后端突然把 `title` 改成了数字，TypeScript 往往能更早暴露问题。

> 🌐 **In English:**
> HTML defines structure, CSS controls presentation, JavaScript drives behavior, and TypeScript adds safety and maintainability to larger codebases.

## 🎯 为什么产品经理也该知道 TypeScript

- 现代前端项目里它非常常见。
- 看接口类型定义时，你会更容易看懂字段结构。
- 当 AI 修改前端代码时，很多问题会先以类型报错的形式出现。
- 它能帮助你理解“为什么这次不是文案问题，而是数据结构不一致”。

## ⚖️ 一个页面的改动，通常会落在哪一层

### 改文案位置、按钮顺序、表单结构

更偏向 `HTML` 和组件结构。

### 改颜色、字号、间距、栅格布局

更偏向 `CSS`。

### 改交互逻辑、点击行为、接口请求

更偏向 `JavaScript`。

### 改数据结构、字段约束、组件参数定义

更偏向 `TypeScript`。

## ⚠️ 常见误区

### 误区一：前端改动都是样式改动

很多看起来像“页面问题”的问题，实际是接口、状态或类型问题。

### 误区二：TypeScript 只是工程师自嗨

实际上，当项目复杂起来，类型约束能显著降低沟通和修改成本。

### 误区三：HTML 就是写几个标签，没什么重要的

结构层直接影响语义、可维护性、可访问性和组件复用。

## 🧪 你可以这样观察一个页面

当你打开一个页面时，试着问：

- 这是结构问题、样式问题，还是行为问题
- 这个按钮点击后会不会调用接口
- 这个字段值来自前端本地状态还是后端返回
- 如果字段类型错了，会在哪一层暴露问题

## 📝 记住这些

- 不要把前端理解成“只做样式”。
- HTML、CSS、JS、TS 各有分工，但在真实项目中是联动工作的。
- 你越能区分问题在哪一层，越能准确地驱动工程师或 AI 修改。

## 📚 延伸阅读

- [00_Web应用是怎样跑起来的.md](00_how_web_apps_actually_run.md)
- [02_JSON_YAML_TOML与配置文件.md](../02_terminal_shell_filesystem_and_environment/02_json_yaml_toml_and_configuration_files.md)
- [03_JSON_Schema_结构化输出与工作流编排.md](../09_ai_foundations_llm_rag_agent_mcp_eval/03_json_schema_structured_output_and_workflow_orchestration.md)
