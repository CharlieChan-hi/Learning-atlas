> 📌 **一句话版本：** 这页不是教你背命令，而是把你最常会碰到的终端、Git 和 Python 命令归成“看到它时大概知道它在做什么”的速查表。

---

## 📖 这一节在讲什么

你不需要记住所有命令，但至少要对高频命令有直觉。这样看到 AI 或工程师给你的命令时，你不会完全没感觉。

## 🧠 高频终端命令

- `pwd`：看当前目录
- `ls`：看当前目录内容
- `cd`：切换目录
- `mkdir`：创建目录
- `cat`：查看文件内容

## 🧠 高频 Git 命令

- `git status`：看当前改动状态
- `git diff`：看具体改了什么
- `git checkout -b xxx`：新建并切换分支
- `git add`：加入暂存区
- `git commit`：形成一次提交快照

## 🧠 高频 Python 相关命令

- `python3 --version`：看 Python 版本
- `python3 file.py`：运行脚本
- `pip install`：安装依赖

> 🌐 **In English:**
> This cheat sheet is meant to build recognition and confidence, not rote memorization.

## 🎯 看到命令时，先怎么拆

一个命令通常至少包含这些部分：

- 程序名
- 子命令
- 参数
- 路径或目标对象

例如：

```bash
git checkout -b feature/report-page
```

你可以这样看：

- `git`：程序
- `checkout`：子命令
- `-b`：参数
- `feature/report-page`：目标分支名

只要会这样拆，很多命令就不再像整块黑箱。

## 💡 再补一批高频但值得认识的命令

### 终端

- `which xxx`：看某个程序在哪
- `echo $PATH`：看命令查找路径
- `rm -rf`：强删除，危险度高

### Git

- `git log`：看历史提交
- `git pull`：拉远端更新
- `git push`：把当前分支推上去

### Python

- `python3 -m venv .venv`：创建虚拟环境
- `source .venv/bin/activate`：激活虚拟环境
- `pip freeze`：看已装依赖列表

> 🌐 **In English:**
> Command fluency starts from recognition. Once you can parse what each segment does, command lines become much easier to trust and verify.

## ⚠️ 命令速查时最该带着的警惕

### 警惕一：路径问题

同一条命令在不同目录下，效果可能完全不同。

### 警惕二：副作用问题

有的命令只是看状态，有的命令会真正写入、删除、覆盖。

### 警惕三：环境问题

有时命令本身没错，只是当前机器没装、版本不对或权限不够。

## 🧪 最实用的习惯

以后看到命令时，先在心里问：

1. 它要调用什么程序
2. 它会改什么
3. 它需要我在哪执行

这三个问题一过，命令风险就会清楚很多。

## ⚠️ 使用提醒

- 看到删除、覆盖、批量操作命令要格外谨慎
- 先确认路径，再执行
- 先看状态，再做改动

## 📚 延伸阅读

- [00_终端_Shell_文件系统入门.md](../02_terminal_shell_filesystem_and_environment/00_terminal_shell_and_filesystem_basics.md)
- [00_Git的核心心智模型.md](../03_git_github_and_collaboration_flow/00_the_core_mental_model_of_git.md)
- [00_Python最适合产品经理的学习方式.md](../08_python_foundations_and_automation/00_the_best_way_for_product_managers_to_learn_python.md)
