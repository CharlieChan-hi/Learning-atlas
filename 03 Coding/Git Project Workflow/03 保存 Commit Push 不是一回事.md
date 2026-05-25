> 一句话版本：保存文件、commit、push 是三件事；保存只在电脑文件里，commit 只在本地 Git，push 才到 GitHub 云端。

---

## 这一篇解决什么问题

很多 Git 混乱都来自把“保存”“提交”“上传”混在一起。

读完这一篇，你应该能清楚解释：为什么我明明保存了文件，GitHub 上却没有？为什么我 commit 了，B 电脑还是看不到？

## 三个动作不是一回事

| 动作 | 发生在哪里 | 代表什么 |
| --- | --- | --- |
| 保存文件 | 编辑器 / 本机文件系统 | 文件内容已经写到电脑硬盘 |
| commit | 本地 Git 仓库 | Git 记录了一个正式版本点 |
| push | GitHub 等远程仓库 | 本地版本上传到云端 |

你要记住：

```text
保存文件 ≠ Git 已经记录
commit ≠ 云端已经备份
push 才是上传到远程仓库
```

## 一个真实例子

假设你改了网站首页。

### 只保存文件

你按了保存，电脑里的文件变了。

但 Git 还只是看到：这个文件被修改了。它还没有把这个变化记录成正式历史。

### 做了 commit

你创建了一次 commit。

这时本机 Git 已经有了一个正式存档点。以后你可以看到这次修改，也可以回到这次修改之前。

但这仍然只在这台电脑上。

### 做了 push

你把 commit 推送到 GitHub。

这时 GitHub 上也有了这次历史。B 电脑可以通过 pull 或 clone 拿到它。

## Git 和普通网盘有什么区别

网盘更像“同步当前文件夹”。Git 更像“保存每次改变背后的历史”。

| 问题 | 网盘 | Git |
| --- | --- | --- |
| 能看到每次改了哪几行吗 | 通常不方便 | 可以，`git diff` 很清楚 |
| 能写每次修改原因吗 | 不适合 | commit message 就是原因 |
| 能多人或多电脑合并吗 | 容易冲突 | 专门解决这个问题 |
| 能连接部署平台吗 | 通常不能 | GitHub 可以连接 Cloudflare Pages |
| 能安全回滚某一次修改吗 | 有时困难 | 可以用 revert / restore |

不要把 `.git` 文件夹放进网盘当主要备份方式。网盘可能在同步过程中破坏 Git 内部文件。

更可靠的做法是：

```text
本地 Git
+ GitHub 私有仓库
+ 清楚的 commit / push 流程
```

## 对你的项目意味着什么

对 `charliechanstudio.com` 来说，未来最安全的节奏是：

```text
小范围修改
→ 本地运行检查
→ 看 git status
→ 看 git diff
→ 只 add 相关文件
→ commit
→ push 到 GitHub 私有仓库
→ Cloudflare Pages 从 GitHub 部署
```

但是现在先不要急着 push。你的项目还有未提交改动，需要先看懂状态。

## 这一篇记住这些

- 保存文件只是保存到电脑。
- commit 是本地 Git 的正式存档。
- push 是上传到 GitHub。
- B 电脑看不到 A 电脑只 commit 没 push 的内容。
- GitHub private repository 才是未来跨电脑和部署的中心。
