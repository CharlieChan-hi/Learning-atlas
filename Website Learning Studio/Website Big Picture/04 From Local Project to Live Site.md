> 一句话版本：本地项目经过安装、构建和部署，才会变成别人能通过网址访问的 live site。

---

## 这一节在讲什么

这一节解释一个网站从本地项目到线上网站的过程。你会理解为什么项目里会有 `package.json`、build command、`dist`、Cloudflare Pages 这些东西。

你不需要现在执行部署，但要知道每一步在解决什么问题。

## 概念解释

本地项目是你电脑上的文件夹。里面有源代码、内容、配置、图片和脚本。

安装依赖是让项目拿到需要的工具和库。Node 项目通常通过 `pnpm install`、`npm install` 或类似命令完成。

构建是把源代码转换成线上可用的文件。这个过程通常叫 `build`，输出目录可能叫 `dist`。

部署是把构建结果交给托管平台，例如 Cloudflare Pages。平台负责把这些文件提供给访问者。

## 现实例子

你在本地写了一篇项目介绍，这只是你电脑上的内容。

项目构建后，这篇内容会变成网站页面的一部分。

部署后，别人打开域名才能看到它。

所以「写完文件」和「线上可访问」之间还隔着构建和部署。

## Charlie 项目案例

Charlie 根目录 `package.json` 里有这些脚本：

```json
"dev": "node scripts/dev.mjs",
"build": "node scripts/build.mjs",
"check": "...",
"verify": "corepack pnpm test && corepack pnpm check && corepack pnpm build && corepack pnpm run doctor"
```

这说明项目把开发、构建、检查和验证拆成不同命令。`apps/web/package.json` 里还有 `astro build`，说明 web 应用由 Astro 构建。

对新手来说，不要把这些命令当成魔法。它们只是把复杂流程命名，方便重复执行。

## 小练习

1. 用自己的话解释本地项目和 live site 的区别。
2. 写出「安装依赖」「构建」「部署」三步顺序。
3. 在 Charlie 的根目录脚本里找出 `build` 和 `verify` 的用途。

## 检查问题

1. `build` 是把线上网站下载到本地吗？
2. `dist` 通常接近源代码，还是构建输出？
3. 为什么部署前需要先构建？

## 常见误解

常见误解是认为本地能打开就等于线上能访问。本地开发和线上部署是两个环境。

另一个误解是认为 `build command` 只是给工程师看的。实际上，Cloudflare Pages 这类平台也需要知道用什么命令生成上线文件。

## 记住这些

- 本地项目是源头。
- build 把源代码变成可发布文件。
- deploy 把构建结果放到线上。
