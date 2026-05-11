> 📌 **一句话版本：** Code Review 不只是看代码风格，更重要的是看逻辑风险、影响范围、测试覆盖和需求契合度。

---

## 📖 这一节在讲什么

当你开始参与 PR 和 AI 改动审查后，最容易不知道“到底该看什么”。这页就是给你一个实用的 Review 观察框架。

## 🧠 Review 最值得看的四类问题

- 逻辑有没有跑偏
- 改动有没有超范围
- 边界条件是否考虑
- 有没有合适验证

## 🎯 PM 参与 Review 的价值

- 更容易识别需求是否被误实现
- 更容易发现体验层和业务层的偏差
- 能帮助团队提前暴露风险

> 🌐 **In English:**
> A useful code review checks logic, scope, edge cases, and validation, not just code style.

## 🧩 Review 为什么不是“顺手看两眼”

很多项目里，Review 如果只停留在“代码格式看起来还行”，那它的价值会非常有限。真正有效的 Review 更像一次“风险扫描”。

它至少要回答：

- 这次改动是否对准需求
- 改动范围是否受控
- 有没有明显副作用
- 验证是否充分

## 🎯 PM 最适合看什么，不适合执着看什么

### PM 特别适合看的

- 实现有没有偏离业务目标
- 页面和交互有没有跑偏
- 错误提示和状态反馈是否完整
- 风险和影响范围是否说清楚

### PM 不必执着细扣的

- 特别底层的风格细节
- 团队已有规范能自动解决的格式问题

这不是说 PM 不能看代码细节，而是你最有价值的视角在需求和风险层。

## 💡 Review 时可以顺着看的顺序

1. 先看 PR 背景和目标
2. 再看改动文件是否合理
3. 再看有没有超范围
4. 再看验证证据
5. 最后才看更细的实现质量

> 🌐 **In English:**
> The most valuable review flow is to start from purpose and scope, then move into risk, validation, and only then implementation detail.

## ⚠️ 最常见的无效 Review

### 无效一：只看代码，不看目标

你根本不知道这次改动是不是做对了事情。

### 无效二：只看 happy path

主路径没问题，不代表异常和边界就没问题。

### 无效三：只看“它说测过了”

没有验证方式或结果说明时，“测过了”几乎没有信息量。

## 🧪 一个简短但实用的 Review 清单

你可以在心里快速过这几句：

- 这次改动是为了什么
- 改了哪些核心文件
- 有没有超出需求范围
- 风险最大的是哪块
- 验证做了哪些
- 还有什么待确认

这套问题，特别适合你在 AI 改代码后也拿来用。

## 📝 记住这些

- Review 的本质是风险发现，不是找茬。
- PM 在 Review 里最有价值的视角，往往是需求契合度和用户影响。
- AI 生成代码尤其需要 Review，因为它容易“表面正确，细节跑偏”。

## 📚 延伸阅读

- [01_从需求到提交PR的协作流程.md](../03_git_github_and_collaboration_flow/01_collaboration_flow_from_requirement_to_pull_request.md)
- [01_测试为什么不是可有可无.md](01_why_testing_is_not_optional.md)
