> 📌 **一句话版本：** 一个 AI 功能能不能稳定工作，关键往往不在“模型答得多聪明”，而在于输入结构、输出结构、任务状态和错误处理有没有设计好。

---

## 📖 这一节在讲什么

案例第二步，是把“AI 生成周报”背后的结构设计清楚。因为只要结构没定住，后面前端、后端、AI 和测试都会反复返工。

## 🧠 至少需要哪些结构

- 用户输入结构
- 任务记录结构
- AI 输出结构
- 状态枚举
- 错误结构

## 🎯 状态设计特别重要

这个功能很适合异步处理，所以常见状态可能有：

- `idle`
- `submitting`
- `processing`
- `success`
- `failed`

这些状态会直接影响前端展示和用户体验。

## 🎯 AI 输出为什么尽量结构化

因为结构化输出更适合：

- 页面展示
- 存储历史
- 重试和审计
- 后续自动化处理

> 🌐 **In English:**
> AI features become much more reliable when input schema, output schema, task states, and failure handling are designed explicitly.

## 🧩 为什么很多 AI 功能一做就乱

最常见的原因，不是模型不够聪明，而是结构没定住。具体表现经常是：

- 输入参数今天一套、明天一套
- 输出格式一会儿是段落，一会儿是列表
- 页面不知道什么时候该显示“处理中”
- 历史记录里没有稳定字段

这会直接导致：

- 前端展示越来越难
- 后端存储越来越乱
- 测试很难写
- 后续自动化没法接

## 🎯 先把输入结构定清楚

针对周报案例，输入至少要区分：

- 用户原始内容
- 时间范围
- 模板或风格选项
- 是否需要重点风险提示

如果这些输入不稳定，后面你很难判断生成结果变差到底是模型问题还是输入不一致问题。

## 🎯 输出结构最好提前面向消费方设计

不要只想“模型能不能生成一段好文案”，还要想：

- 页面怎么展示
- 历史记录怎么保存
- 是否支持复制到别的系统
- 后续能不能做二次处理

例如，你可以把输出拆成：

- `summary`
- `highlights`
- `risks`
- `next_week_focus`

这样后面页面、导出、脚本都更容易处理。

> 🌐 **In English:**
> Good schema design starts from downstream use. Structure outputs for UI, storage, history, and automation, not just for model readability.

## 💡 状态设计为什么直接决定体验质量

如果这个功能是异步生成，用户体验几乎完全依赖状态设计。

例如：

- 点击后有没有立即反馈
- 处理中是否可离开页面
- 失败后能否重试
- 成功后结果是否可追踪

这说明状态不是“工程补充”，而是产品体验的一部分。

## ⚠️ 常见结构设计错误

### 错误一：所有内容都塞进一个长字段

短期看简单，长期几乎无法复用和校验。

### 错误二：没有错误结构

一旦失败，你只能弹一句模糊报错，后面什么都很难分析。

### 错误三：没有历史记录主键和状态字段

这样前端和后端都没法稳定追踪任务生命周期。

## 🧪 可以怎么练这一页

你可以自己尝试写一个最小 JSON 结构：

- 输入对象一份
- 输出对象一份
- 状态枚举一份
- 失败响应一份

只要你把这四份结构写出来，你对 AI 功能的“工程感”就会明显增强。

## 📝 记住这些

- 结构是 AI 功能稳定性的基础。
- 状态设计会直接决定体验是否清晰。
- JSON 结构和 Schema 设计，是 AI 产品落地的关键中间层。

## 📚 延伸阅读

- [03_JSON_Schema_结构化输出与工作流编排.md](../09_ai_foundations_llm_rag_agent_mcp_eval/03_json_schema_structured_output_and_workflow_orchestration.md)
- [03_同步_异步_并发_队列与任务系统.md](../06_backend_foundations_http_api_auth_and_services/03_sync_async_concurrency_queues_and_task_systems.md)
