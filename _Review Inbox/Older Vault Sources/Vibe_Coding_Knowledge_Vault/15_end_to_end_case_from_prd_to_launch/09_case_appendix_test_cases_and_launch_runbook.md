> 📌 **一句话版本：** 这页把完整案例最后一公里补齐：给你一份测试用例视角和一份上线前 Runbook，让“做完功能”真正过渡到“能稳上线”。

---

## 📖 这一节在讲什么

很多人做案例做到这里就停了，但如果你想把它真的学成工作能力，就必须连“怎么测、怎么发、怎么观测”一起练。

## 🧪 测试用例视角

### 正常路径

- 输入正常内容
- 生成成功
- 结果区显示完整
- 历史记录新增一条

### 异常路径

- 输入为空
- 输入超长
- 模型超时
- 生成失败
- 历史记录加载失败

### 状态路径

- 提交中按钮是否禁用
- 处理中状态是否持续可见
- 成功后状态是否正确收口
- 失败后是否允许重试

## 🚀 上线前 Runbook

你可以把它理解成一份最小上线操作清单：

1. 确认环境变量
2. 确认接口和日志可观测
3. 确认最小验证动作
4. 确认异常处理与回滚方案
5. 上线后观察成功率、错误率和用户反馈

> 🌐 **In English:**
> A strong case study should include both test thinking and a release runbook so the feature can move from “implemented” to “reliably shippable.”

## ⚠️ Runbook 为什么特别值得 PM 学

因为它不是工程手册那么复杂，但足够让你在上线讨论里知道：

- 哪些准备还没做
- 哪些风险还没收口
- 哪些验证必须先过

## 📝 记住这些

- 测试用例和 Runbook，是把案例从“演示”变成“交付训练”的关键。
- PM 很适合用清单方式参与上线和验收。
- 真正可交付的能力，总是要走到最后一公里。

## 📚 延伸阅读

- [03_从开发联调到测试上线.md](03_from_development_integration_to_testing_and_launch.md)
- [06_案例验收_发布与复盘清单.md](06_case_acceptance_release_and_retrospective_checklist.md)
