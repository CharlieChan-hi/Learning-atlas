> 一句话版本：`package.json` 记录项目身份、依赖和脚本，scripts 是项目常用命令的名字表。

---

## 这一节在讲什么

这一节解释 `package.json` 和 scripts。你会学习如何通过它理解一个 Node 项目怎么开发、检查、构建和测试。

`package.json` 是读项目时非常重要的入口。

## 概念解释

`package.json` 是 Node 项目的配置文件。它通常包含项目名、版本、是否私有、依赖、开发依赖、脚本和工具版本。

`scripts` 是命令别名。开发者可以把长命令写成短名字，例如 `dev`、`build`、`test`、`check`。

依赖是项目需要的外部工具或库。`dependencies` 通常是运行时需要的包，`devDependencies` 通常是开发和检查时需要的包。

## 现实例子

如果一个项目把 `build` 写成 `astro build`，你以后只要运行对应脚本，就能触发 Astro 的构建流程。

这像把复杂操作写进菜单。你不需要每次都记住完整命令，但要知道菜单项大概做什么。

## Charlie 项目案例

Charlie 根目录 `package.json` 有这些脚本：

```json
"dev": "node scripts/dev.mjs",
"build": "node scripts/build.mjs",
"test": "vitest run",
"verify": "corepack pnpm test && corepack pnpm check && corepack pnpm build && corepack pnpm run doctor"
```

`apps/web/package.json` 有：

```json
"dev": "astro dev",
"build": "astro build",
"preview": "astro preview",
"check": "astro check"
```

这说明根目录负责整体流程，`apps/web` 负责 Astro 主站的开发、构建和检查。

## 小练习

1. 在一个 `package.json` 里找到 `scripts`。
2. 写出 `dev`、`build`、`test` 可能代表什么。
3. 判断 `verify` 为什么通常比 `build` 更全面。

## 检查问题

1. `package.json` 是否只记录项目名字？
2. scripts 是命令结果，还是命令别名？
3. 根目录脚本和子应用脚本可能有什么区别？

## 常见误解

常见误解是看到脚本就马上运行。新手应先读名字和内容，理解它可能影响什么。

另一个误解是把 `dependencies` 当作自己写的代码。依赖通常来自外部包。

## 记住这些

- `package.json` 是 Node 项目说明书。
- scripts 是常用命令表。
- 根目录和子应用可能有不同脚本。
