> 📌 **一句话版本：** 一个 Agent 工作流真正成熟，不是它永远不失败，而是它失败时能不能被看见、被收口，并在必要时顺利交还给人来接管。

---

## 📖 这一节在讲什么

很多 AI 工作流只讲“自动化能做什么”，却不讲失败时怎么办。现实里，真正决定工作流是否能上线的，往往就是失败收口能力。

## 🧠 为什么 Agent 比单轮问答更需要失败设计

因为它通常会：

- 执行多个步骤
- 调用多个工具
- 依赖多份上下文
- 影响真实系统状态

只要中间某一步失败，影响就可能一路往后传。

> 🌐 **In English:**
> Agent systems need strong failure handling because they chain multiple steps, tools, and state changes rather than producing a single isolated answer.

## 🎯 一个成熟 Agent 工作流至少要考虑什么

- 哪些失败要自动重试
- 哪些失败应该立即停止
- 哪些失败需要人工接管
- 失败后怎么留下足够线索

## 💡 什么叫“人工接管友好”

这意味着当工作流卡住时，人能快速知道：

- 卡在哪一步
- 用了哪些输入
- 当前状态是什么
- 下一步最该怎么接

如果这些信息都没有，自动化就会从“省时间”变成“浪费时间”。

## ⚠️ 最容易被忽略的失败场景

### 场景一：工具调用成功，但结果不可用

### 场景二：模型生成了结构，但值是错的

### 场景三：任务部分完成，状态却标成成功

### 场景四：失败后没有重新进入人工流程的入口

## 🧪 一个很实用的收口问题模板

看一个 Agent 工作流时，你可以问：

1. 最容易失败的是哪一步
2. 失败了系统会不会知道
3. 失败了人能不能接上
4. 接上以后有没有足够线索继续处理

## 📝 记住这些

- 自动化成熟的标志不是“永不失败”，而是“失败可控”。
- 人工接管不是自动化的失败，而是自动化设计的一部分。
- PM 很适合推动这类失败收口设计，因为它直接决定真实可用性。

## 📚 延伸阅读

- [10_AI_Coding工具_Codex_CLI_Claude_Code/03_并行协作_上下文控制与安全边界.md](../10_ai_coding_tools_codex_cli_claude_code/03_parallel_collaboration_context_control_and_safety_boundaries.md)
- [14_安全_权限_密钥_成本与风控/02_AI成本_模型选择与风险权衡.md](../14_security_permissions_keys_cost_and_risk_control/02_ai_costs_model_selection_and_risk_tradeoffs.md)
