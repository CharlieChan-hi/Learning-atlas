> 📌 **一句话版本：** `Git` 不是“保存代码的网盘”，而是一套记录变更、分支试验、多人协作和回退历史的版本控制系统。

---

## 📖 这一节在讲什么

只要你开始和代码打交道，迟早会遇到 `Git`。很多人会背 `git add`、`git commit`、`git push`，但并不知道自己到底在操作什么，所以一旦冲突、回滚、分支切换就容易慌。这一节先帮你建立 Git 的正确心智模型。

## 🧠 Git 最核心的三件事

1. 它记录“改动历史”
2. 它允许你“分叉试验”
3. 它帮助团队“合并结果”

换句话说，Git 管的不是“文件本身”，而是文件在时间维度上的变化。

> 🌐 **In English:**
> Git is a version control system. It tracks change history, supports branching experiments, and helps teams merge work safely.

## 🎯 三个最重要的对象

### 工作区 Working Tree

工作区就是你当前能直接看到和编辑的文件。

### 暂存区 Staging Area

暂存区像一个“准备提交的购物车”。你可以选择这次到底提交哪些变化，而不是把所有改动都一次性塞进去。

### 仓库 Repository

仓库保存正式历史记录。每次 `commit`，你都在往历史时间线上新增一个节点。

## 🧭 你可以把 Git 想成拍快照

每一次提交都像给当前项目状态拍了一张快照，并附上一句说明：“我这次改了什么”。这让你能回看、比较、回退，也让团队知道每次变更的意图。

## ⚖️ 分支 Branch 到底是什么

分支不是“复制一份项目”，而是“从某个历史节点出发，继续向前演化的一条新时间线”。

这很重要，因为：

- 你可以在不打扰主线的情况下试新改动
- 不同人可以并行工作
- 出问题时更容易定位是哪条线引入的

## 💡 对 PM 来说，Git 最重要的不是会背命令，而是理解协作语义

### 你该知道什么叫“当前分支”

因为不同分支代表不同工作上下文。

### 你该知道什么叫“未提交改动”

因为很多工具无法切换分支或回退，就是因为你本地还有未处理的改动。

### 你该知道什么叫“冲突”

冲突不是系统坏了，而是 Git 发现两边都改了同一块内容，无法替你自动判断应该保留哪一个。

> 🌐 **In English:**
> For product managers, Git is mainly about collaboration semantics: branch context, uncommitted changes, commit history, and merge conflicts.

## ⚠️ 常见误解

### 误解一：提交越少越好

实际上，清晰的小提交通常比一次巨大的提交更容易 review、回退和定位问题。

### 误解二：分支越少越安全

没有分支才更危险，因为你会把实验性改动直接做在主线上。

### 误解三：看见冲突就说明出大事了

大多数冲突只是正常协作中的文本差异，关键是你要知道哪一边的意图应该保留。

## 🧪 一个最常见的基本流程

```bash
git status
git checkout -b feature/report-page
git add .
git commit -m "add report page draft"
git push
```

你不必急着背每个细节，但要理解这串动作在做什么：

- 看当前状态
- 新建并切到功能分支
- 选择要提交的改动
- 形成一次历史快照
- 推到远端供团队查看或合并

## 🎯 Git 和 AI Coding 的关系

当你让 AI 改代码时，Git 是最重要的保险装置之一。因为它能帮你：

- 看 AI 改了哪些文件
- 对比改前改后差异
- 只提交你认可的那部分
- 在出问题时回到之前的稳定状态

所以，AI 越强，Git 反而越重要。

## 🧩 你在真实项目里最常看到的 Git 画面

很多时候，PM 不一定需要自己频繁手写 Git 命令，但你至少要看得懂这些状态：

### `git status`

它告诉你：

- 当前在哪个分支
- 有没有未提交改动
- 有哪些文件被修改、新增或删除

### `git diff`

它告诉你这次到底改了什么，而不是只看“这个文件被改过”。

### Pull Request

它像一次“正式请求合并”的沟通节点。别人可以 review、评论、提修改意见，再决定要不要进入主线。

> 🌐 **In English:**
> In practice, understanding Git status, diffs, and pull requests is often more important than memorizing many commands.

## 💡 为什么一次清晰的提交很重要

一条好的提交记录，价值不只是在于“保存当前工作”，而在于：

- 以后能回看这次为什么改
- review 时更容易理解意图
- 出 bug 时更容易定位来源
- 回滚时影响范围更可控

你可以把提交信息理解成“写给未来团队的说明书”。

## ⚠️ 冲突本质上是在争同一段历史

当两个人或两条分支都修改了同一块内容时，Git 不知道该保留哪一版，就会要求人工处理。这时候你要做的不是害怕，而是回到业务意图：

- 哪一版更符合当前需求
- 有没有两边都该保留的部分
- 合并后是否需要重新测试

## 🎯 PM 与 Git 最相关的判断问题

- 这次改动是局部修复还是大范围重构
- 这次提交信息能否让人看懂改动目的
- 这次 PR 影响了哪些模块
- 这个冲突是文本冲突，还是业务逻辑冲突
- 这次改动是否需要回归测试

## 📝 记住这些

- Git 管的是“变化历史”，不是单纯的文件存储。
- 分支是为了隔离试验和支持协作。
- 你至少要能读懂工作区、暂存区、提交、分支、冲突这些概念。

## 📚 延伸阅读

- [00_终端_Shell_文件系统入门.md](../02_terminal_shell_filesystem_and_environment/00_terminal_shell_and_filesystem_basics.md)
- [00_Web应用是怎样跑起来的.md](../04_web_foundations_html_css_js_ts/00_how_web_apps_actually_run.md)
- [00_Codex_CLI与Claude_Code全景.md](../10_ai_coding_tools_codex_cli_claude_code/00_codex_cli_and_claude_code_overview.md)
