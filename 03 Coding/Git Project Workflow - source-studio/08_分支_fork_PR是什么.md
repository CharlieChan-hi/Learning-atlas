> 一句话版本：main 是主线，branch 是平行时间线，fork 通常用于复制别人的项目，PR 是请求合并改动。

---

## 这一篇解决什么问题

你提到 main、分支、fork 这些词。它们很常见，但初学者很容易混在一起。

读完这一篇，你应该能用人话解释：main、branch、merge、fork、clone、PR 分别是什么。

## main 和 master

`main` 和 `master` 都常用来表示项目主分支。

以前很多项目默认叫 `master`，现在新项目更多叫 `main`。

你的 `charliechanstudio.com` 当前主分支是：

```text
main
```

你可以把 main 理解成：项目的主线、稳定线、未来最可能部署上线的线。

## branch 是什么

branch 是分支。你可以把它理解成平行时间线。

例如：

```text
main:          A --- B --- C
                    \
feature-page:       D --- E
```

意思是：你从 main 的某个点分出来，在新分支上做新功能。这样你可以实验，不直接影响 main。

## 什么时候需要分支

个人项目刚开始可以简单一点：

| 情况 | 是否需要分支 |
| --- | --- |
| 小文档修改 | 可以直接 main |
| 小内容改动 | 可以直接 main |
| 大功能 | 建议新分支 |
| 危险重构 | 建议新分支 |
| 尝试新设计 | 建议新分支 |
| 不确定能不能成功的实验 | 建议新分支 |

命令示例：

```bash
git switch -c 新分支名
```

切回 main：

```bash
git switch main
```

## merge 是什么

merge 是合并。意思是把一个分支的改动并回另一个分支。

例如你在 `feature-page` 做完功能，想放回 `main`，就需要 merge。

命令大概是：

```bash
git switch main
git merge feature-page
```

但你现在先理解概念就好。真实项目里不要随便 merge，先用练习仓库试。

## fork 是什么

fork 是在 GitHub 上把别人的仓库复制一份到你的 GitHub 账号下面。

常见场景：你想给别人的开源项目贡献代码，但你没有直接写入权限。

fork 更像：

```text
别人的 GitHub 仓库
  → 复制一份到我的 GitHub 账号
```

对你自己的 `charliechanstudio.com`，fork 不是主要备份方式。你应该创建自己的 private repository，然后 push。

## clone 是什么

clone 是把远程仓库下载到本机。

```bash
git clone 仓库地址
```

clone 通常用于：

- 新电脑第一次拿项目；
- 从 GitHub 下载自己的项目；
- 下载别人的开源项目。

## PR 是什么

PR 是 Pull Request。

它的意思是：我做了一些改动，请求把这些改动合并到目标分支。

公司和开源项目常用 PR，因为它可以：

- 合并前看 diff；
- 讨论风险；
- 跑测试；
- 让别人 review。

你的个人项目初期不一定需要复杂 PR 流程，但以后和朋友或 AI 协作时会有用。

## 这一篇记住这些

- main 是主线。
- branch 是平行时间线。
- merge 是把分支合回来。
- fork 通常用于复制别人的项目。
- clone 是把远程仓库下载到本机。
- PR 是请求合并改动。
