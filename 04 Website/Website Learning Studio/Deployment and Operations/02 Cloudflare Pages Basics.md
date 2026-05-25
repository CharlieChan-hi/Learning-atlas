> 一句话版本：Cloudflare Pages 可以把构建后的前端网站发布到线上，并和 GitHub、build command、output directory 配合工作。

---

## 这一节在讲什么

这一节解释 Cloudflare Pages 的基础。你会知道它在网站上线流程里的位置，以及它为什么需要构建命令和输出目录。

本节不要求你马上部署，只让你先理解部署平台的职责。等你未来真的设置网页时，你会知道每个输入框大概在问什么。

## 概念解释

`Cloudflare Pages` 是静态网站和前端应用的托管平台。它可以从 GitHub 仓库拉取代码，执行 build command，然后发布 build output。

`build command` 是构建命令，例如 `pnpm build` 或某个项目指定命令。

`output directory` 是构建结果目录，例如 `dist`。Cloudflare Pages 需要知道最终发布哪些文件。

部署不是直接把源代码暴露给用户，而是把构建好的可访问文件发布出去。

## 小白先理解这 4 个设置

Cloudflare Pages 设置页面里，最容易让新手紧张的是几个英文输入项。你可以先这样理解。

`Project name` 是 Cloudflare 里显示的项目名字。它帮助你识别项目，不一定等于网站正式标题。

`Production branch` 是正式上线使用的 Git 分支。常见是 `main`，但要以项目实际设置为准。

`Build command` 是让平台生成网站文件的命令。它通常来自 `package.json` 的 scripts。

`Build output directory` 是构建完成后，平台要发布的目录。Astro 项目常见输出是 `dist`，但多应用 workspace 需要按项目配置确认。

这 4 个设置的关系可以写成：Cloudflare 先拿到 GitHub 代码，再切到指定分支，运行构建命令，然后发布输出目录。

## 现实例子

你把网站项目推到 GitHub。Cloudflare Pages 监听到新提交，开始构建。

构建成功后，它把输出目录里的文件发布到全球网络。用户访问域名时，就会拿到这些文件。

如果 build command 错了，部署会失败。如果 output directory 错了，部署成功也可能看不到正确页面。

## 从本地项目到 Cloudflare 的顺序

你可以把上线理解成 6 步。

```text
本地项目
  ↓
Git 记录变化
  ↓
GitHub 保存仓库
  ↓
Cloudflare Pages 连接仓库
  ↓
Cloudflare 运行 build command
  ↓
Cloudflare 发布 output directory
```

这条线能帮你判断问题位置。如果本地项目本身构建失败，Cloudflare 通常也会失败。如果 GitHub 没有最新代码，Cloudflare 也拿不到最新内容。如果 output directory 配错，构建成功也可能发布错文件。

## Charlie 项目案例

Charlie 根目录有 `build` 和 `verify` 脚本，`apps/web` 有 `astro build`。这说明上线前需要明确使用哪个命令生成主站输出。

Charlie 项目还存在 `cloudflare` 目录，说明它可能包含与 Cloudflare 部署或函数相关的配置，具体内容可在后续只读学习中继续展开。

因为 Charlie 是 workspace，不要直接套用普通单应用教程。它有根目录脚本，也有 `apps/web` 子应用脚本。未来设置 Cloudflare 时，要确认平台在哪个目录执行命令，以及最终发布哪个输出目录。

## 设置网页时要问的 5 个问题

1. 这个网站的代码在哪个 GitHub 仓库？
2. 正式上线使用哪个分支？
3. 构建命令来自根目录，还是来自 `apps/web`？
4. 构建输出目录到底是哪一个？
5. 自定义域名是否已经通过 DNS 指向 Cloudflare？

这 5 个问题能帮你从“我不知道怎么设置”转成“我知道要确认哪些信息”。

## 小练习

1. 写出 Cloudflare Pages 的一句话定义。
2. 写出 build command 和 output directory 的区别。
3. 想象一次部署失败，列出两个可能原因。
4. 试着填写一张部署设置草稿：项目名、分支、构建命令、输出目录、域名。

## 检查问题

1. Cloudflare Pages 是否负责设计首页？
2. output directory 是源代码目录，还是构建结果目录？
3. build command 配错会影响什么？
4. 为什么 workspace 项目不能直接照抄普通教程？

## 常见误解

常见误解是以为连接 Cloudflare 就等于网站上线成功。上线还取决于构建、输出目录、域名和配置。

另一个误解是认为部署平台会理解你的项目意图。它只会按你提供的命令和设置执行。

还有一个误解是把域名设置和网站设计混在一起。域名解决访问地址，设计解决读者看到什么、如何理解你。

## 记住这些

- Cloudflare Pages 负责托管和发布。
- build command 负责生成发布文件。
- output directory 告诉平台发布哪里。
- 设置网页时，先确认仓库、分支、命令、输出目录和域名。
