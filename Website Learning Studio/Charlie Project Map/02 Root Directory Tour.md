> 一句话版本：根目录像项目总控制台，负责说明项目身份、统一脚本、工作区范围和工具配置。

---

## 这一节在讲什么

这一节带你认识项目根目录。根目录是打开项目后的第一层，它告诉你这个项目叫什么、用什么工具、有哪些命令、哪些目录属于工作区。

如果你不知道从哪里读项目，先读根目录，而不是随机打开某个深层文件。

## 概念解释

根目录通常包含几个关键文件。

`package.json` 是 Node 项目的说明书。它记录项目名称、版本、脚本、依赖和工具版本。

`pnpm-workspace.yaml` 是 pnpm workspace 的范围说明。它告诉 pnpm 哪些子目录属于同一个工作区。

`.gitignore` 告诉 Git 哪些文件不该被提交，例如依赖、构建输出或本地临时文件。

配置文件负责连接工具。例如 TypeScript、Astro、Cloudflare 或测试工具可能都有自己的配置。

## 现实例子

你进入一栋教学楼，门口的楼层指引告诉你教室、办公室、实验室在哪里。根目录就是这个楼层指引。

如果你跳过指引，直接冲进某个房间，你可能看到很多细节，却不知道整体结构。

看项目也一样。根目录先告诉你「这个项目怎么运行」「有哪些子项目」「用什么工具」。

## Charlie 项目案例

Charlie 根目录 `package.json` 显示项目名是 `charliechanstudio.com`，使用 `pnpm@10.33.4`，Node 版本范围是 `>=24 <26`。

脚本里有：

```json
"dev": "node scripts/dev.mjs",
"build": "node scripts/build.mjs",
"check": "...",
"verify": "corepack pnpm test && corepack pnpm check && corepack pnpm build && corepack pnpm run doctor"
```

`pnpm-workspace.yaml` 内容很短：

```yaml
packages:
  - "apps/*"
  - "packages/*"
```

这表示 `apps` 和 `packages` 是项目的两个核心工作区入口。

## 小练习

1. 打开一个项目时，先找 `package.json`。
2. 在 `scripts` 里找出 `dev`、`build`、`check`。
3. 用一句话解释 `pnpm-workspace.yaml` 的作用。

## 检查问题

1. 根目录是不是只放首页代码？
2. `package.json` 里的 scripts 是给谁用的？
3. workspace 文件为什么能帮助理解项目结构？

## 常见误解

常见误解是把根目录当成普通文件夹。根目录在项目里有特殊意义，它是工具查找配置和命令的起点。

另一个误解是认为 `scripts` 里的命令都要马上执行。零基础学习时，先理解命令名字和用途，再考虑执行。

## 记住这些

- 根目录是项目总控制台。
- `package.json` 是项目说明书和命令表。
- `pnpm-workspace.yaml` 说明哪些子目录属于同一项目体系。
