> 📌 **一句话版本：** 如果你想把 AI 真正用稳，一份好任务模板和一份固定验证清单，往往比再多几个“万能 prompt”更有价值。

---

## 📖 这一节在讲什么

这一页给你一个可反复复用的 AI Coding 任务模板，以及一套简洁验证清单。

## 🧠 任务模板

你可以尽量包含：

- 背景
- 目标
- 范围
- 禁止项
- 验证方式
- 最终汇报格式

## 💡 一个更完整的任务模板长什么样

你以后可以直接按这个思路去写：

- 背景：当前问题或目标是什么
- 目标：希望最终得到什么结果
- 范围：允许改哪些文件、模块或页面
- 禁止项：哪些东西绝对不要动
- 约束：是否允许跑测试、装依赖、联网、改配置
- 验证：执行后要检查什么
- 汇报：最后要输出哪些结论

例如：

“请分析登录页重复请求问题，只修改登录流程相关文件，不要动样式和文案。修复后运行相关检查，并告诉我改动文件、原因、风险、验证结果和待确认点。”

## 🎯 为什么这个模板有效

因为它同时解决了 AI coding 最容易失控的几个地方：

- 任务太模糊
- 范围太大
- 顺手乱改
- 不做验证
- 最后只说“修好了”

> 🌐 **In English:**
> A strong task template improves scope control, reduces accidental over-editing, and makes validation expectations explicit.

## 🎯 验证清单

- 改了哪些文件
- 是否超范围
- 是否跑了验证
- 是否有风险提示
- 是否还有待确认点

## ⚠️ 最容易漏掉的验证项

### 漏项一：只验证主路径

主路径没问题，不代表失败路径和边界情况没问题。

### 漏项二：只看工具自述

AI 说“已经修好”没有意义，你最好看它提供的证据。

### 漏项三：不看 diff

最后最容易出事的，就是看起来修了一个点，实际上顺手改了一大片。

## 🧪 一个很好用的最短复核动作

就算你很忙，也尽量做这三件事：

1. 看修改文件列表
2. 看验证结果或错误输出
3. 看有没有风险和未确认项

哪怕只做这三件事，质量都会比“直接相信工具”高很多。

> 🌐 **In English:**
> Clear task structure and a repeatable validation checklist are often more valuable than generic prompting tricks.

## 📚 延伸阅读

- [01_如何把AI变成结对工程师.md](../10_ai_coding_tools_codex_cli_claude_code/01_how_to_turn_ai_into_a_pair_engineer.md)
- [02_Code_Review应该看什么.md](../12_debugging_testing_code_quality_and_review/02_what_to_look_for_in_code_review.md)
