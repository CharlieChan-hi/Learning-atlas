> 一句话版本：Astro 是适合内容型网站的框架，它把页面、布局、组件和构建流程组织起来。

---

## 这一节在讲什么

这一节解释 Astro basics。你会学习 Astro 在个人网站中的作用，以及 `.astro` 页面文件为什么重要。

Astro 对个人介绍、作品集、博客和内容站很常见，因为它适合生成快速、内容清楚的网站。

## 概念解释

Astro 是前端框架。它可以用 `.astro` 文件定义页面、布局和组件。

`src/pages` 通常负责路由。文件路径会变成网站路径，例如 `src/pages/projects/index.astro` 对应 `/projects`。

`layout` 负责页面公共结构，例如 `<html>`、`head`、导航、footer。

Astro 也可以集成 React。你可以在 Astro 项目里使用 React 组件，但不是所有页面都必须是 React。

## 现实例子

一个个人网站可能有首页、关于页、项目列表页、项目详情页。Astro 可以把这些页面按文件组织。

你不需要手写每个最终 HTML 文件。Astro 会根据源文件和内容生成可部署结果。

## Charlie 项目案例

Charlie 主站 `apps/web/package.json` 使用 `astro`，脚本包括 `astro dev`、`astro build`、`astro preview`、`astro check`。

`apps/web/astro.config.mjs` 中有：

```js
integrations: [react()]
```

这说明 Astro 主站集成了 React。页面文件在 `apps/web/src/pages`，公共布局在 `apps/web/src/layouts/BaseLayout.astro`。

## 小练习

1. 找出 Charlie 的首页文件路径。
2. 找出项目列表页文件路径。
3. 解释 `src/pages` 和 `src/components` 的区别。

## 检查问题

1. Astro 是否只能做博客？
2. `src/pages` 里的文件为什么和 route 有关？
3. Astro 集成 React 是否代表整个项目都必须用 React？

## 常见误解

常见误解是看到 `.astro` 就以为它完全不同于网页基础。它仍然会生成浏览器能理解的 HTML、CSS 和 JavaScript。

另一个误解是把 Astro 和 React 对立起来。它们可以协作，Astro 负责页面组织，React 可用于交互组件。

## 记住这些

- Astro 适合内容型网站。
- `src/pages` 决定路由入口。
- Layout 提供公共页面结构。
