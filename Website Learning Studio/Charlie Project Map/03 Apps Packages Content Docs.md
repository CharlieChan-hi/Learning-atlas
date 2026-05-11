> 一句话版本：`apps` 放可运行应用，`packages` 放共享能力，`content` 放内容素材，`docs` 放说明文档。

---

## 这一节在讲什么

这一节解释 Charlie 项目中几个大目录之间的分工。你会知道为什么一个网站项目不只需要 `pages`，还需要应用、包、内容和文档。

理解这些目录后，你就能初步判断一个问题应该去哪里找答案。

## 概念解释

`apps` 通常放可以独立运行的应用。一个 workspace 里可以有主站、后台、实验 demo 或独立小工具。

`packages` 通常放多个应用共享的能力。例如内容读取、路线生成、UI 工具、配置。

`content` 通常放文本、项目说明、笔记或页面素材。它不一定直接显示，需要被代码读取和渲染。

`docs` 通常放给人看的说明，例如架构、部署、内容规则或项目记忆。

## 现实例子

如果把网站当成展览空间，`apps/web` 是对外开放的展厅。

`content/projects` 是展品说明文字。

`packages/content` 是把展品说明整理成可展示数据的工作人员。

`packages/ui` 是展览里可复用的展架和展示框。

`docs` 是策展手册和运营说明。

## Charlie 项目案例

只读观察确认 `apps` 下有：

- `apps/web`，Astro 主站。
- `apps/focus-training`，可运行的 focus training 应用。
- `apps/console`，控制台相关应用，具体用途可后续继续只读确认。

`packages` 下有：

- `packages/content`，读取和校验内容。
- `packages/lib`，路线和 SEO 等共享工具。
- `packages/ui`，项目框架等 UI 逻辑。
- `packages/config`，共享配置。

`content` 下有 `projects`、`about`、`lab`、`notes`。这说明内容不仅服务项目页，也为未来关于页、实验室和笔记预留了空间。

## 小练习

1. 把 `apps`、`packages`、`content`、`docs` 写成四列。
2. 把 Charlie 的关键目录放进对应列。
3. 标出你认为首页会主要涉及哪些列。

## 检查问题

1. `apps/web` 和 `packages/content` 的职责一样吗？
2. 内容文件为什么需要代码读取？
3. `docs` 会直接成为网站页面吗？

## 常见误解

常见误解是看到 `content` 就以为它一定等于页面。内容需要页面和组件来承载，才会被访问者看到。

另一个误解是把 `packages` 叫成插件。这里的 package 更接近项目内部共享模块。

## 记住这些

- `apps` 是可运行应用。
- `packages` 是共享能力。
- `content` 是内容素材。
- `docs` 是给人读的项目说明。
