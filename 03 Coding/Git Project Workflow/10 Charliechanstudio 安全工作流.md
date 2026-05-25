> 一句话版本：你的项目应该先看懂状态，再整理第一次可靠提交，然后创建 GitHub 私有仓库，最后连接 Cloudflare Pages。

---

## 这一篇解决什么问题

Git 学会后，真正要落到你的 `charliechanstudio.com` 项目上。

读完这一篇，你应该知道：你的项目下一步应该按什么顺序做，哪些操作这次不应该急。

## 当前项目事实

你的项目当前是：

```text
项目：charliechanstudio.com
技术栈：Astro + React + TypeScript + Tailwind CSS + pnpm workspace
本地 Git：已有
当前分支：main
远程 GitHub：未配置
Cloudflare Pages：未来要连接 GitHub
当前状态：有多处未提交改动
```

所以现在最重要的是建立可靠流程。

## 阶段 1：只读理解当前状态

先只运行安全命令：

```bash
git status --short --branch
git diff
git log --oneline --graph --decorate --all
```

目标是看懂：

- 哪些文件修改了；
- 哪些文件删除了；
- 哪些文件是新增但还没被 Git 跟踪；
- 最近一次 commit 是什么；
- 当前是不是在 main 分支。

这一步不会改变项目，只是观察。

## 阶段 2：整理第一次可靠提交

这一步不要急。要先确认：

- 哪些改动是你确认要保留的；
- 哪些删除是正确的；
- 哪些新增文档是新的权威文档；
- 有没有临时文件、截图、构建产物不应该提交；
- `.env`、密钥、账号信息绝对不能提交。

尤其不要直接：

```bash
git add .
```

更安全做法是一个文件一个文件确认。

## 阶段 3：本地验证

对重要代码改动，项目文档建议运行：

```bash
corepack pnpm test
corepack pnpm check
corepack pnpm build
corepack pnpm run doctor
```

如果只是文档改动，可以按实际情况减少验证。但在第一次可靠提交前，最好完整跑一次。

## 阶段 4：创建 GitHub 私有仓库

建议先创建 private repository。

原因：

- 网站还在建设阶段；
- 里面可能有未公开规划；
- 部署配置和项目记忆不一定适合公开；
- private repo 更适合作为早期可信源。

创建后，本机项目需要连接 remote。典型命令长这样：

```bash
git remote add origin GitHub仓库地址
git push -u origin main
```

但这一步会改变项目远程状态，需要单独确认后再做。

## 阶段 5：连接 Cloudflare Pages

Cloudflare Pages 最稳定的方式是连接 GitHub 仓库。

未来流程会变成：

```text
本机修改
→ commit
→ push 到 GitHub
→ Cloudflare Pages 自动构建部署
```

这就是 Git 对你的网站最重要的原因：它不只是保存工具，也是部署入口。

## 对你的项目的安全原则

```text
先看 status
再看 diff
再决定 add 哪些文件
提交前跑检查
先 private repo
再 push
再连接 Cloudflare
```

## 这一篇记住这些

- 不要一开始就 push。
- 先理解当前未提交改动。
- 第一次 commit 要非常谨慎。
- GitHub private repo 是未来跨电脑和部署中心。
- Cloudflare Pages 最好连接 GitHub，而不是依赖本机文件夹。
