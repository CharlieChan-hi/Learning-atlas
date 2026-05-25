> 一句话版本：Charlie 项目的内容从 `content/projects` 出发，经过 `packages/content` 读取，再进入 Astro 页面和组件显示出来。

---

## 这一节在讲什么

这一节解释文件之间如何关联。你会看到一个项目内容文件，怎样变成网站上的项目卡片和项目详情页。

这是理解真实项目的关键，因为页面不是孤立文件，内容也不是自动出现。

## 概念解释

现代网站常把内容和显示分开。内容文件负责写「是什么」，页面和组件负责决定「怎么展示」。

读取函数负责把内容文件变成代码能使用的数据。数据进入页面后，页面再传给组件。

组件是可复用的显示单元。例如项目卡片可以在首页和项目列表页重复使用。

## 现实例子

你写一份简历内容，这只是文字。

设计师把简历排版成页面，读者才容易阅读。

如果简历里每段经历都按固定格式整理，系统就能自动生成经历卡片。网站内容流动也是这个逻辑。

## Charlie 项目案例

只读观察确认项目内容样例在：

```text
content/projects/focus-training.en.mdx
content/projects/focus-training.zh.mdx
```

这些文件包含 `title`、`slug`、`locale`、`summary`、`type`、`status`、`date`、`cover`、`tags` 等 frontmatter。

`packages/content/src/projects.ts` 会读取 `content/projects`，解析文件名，校验 frontmatter，然后输出项目数据。

首页 `apps/web/src/pages/index.astro` 调用：

```js
const { projects } = await readProjects({ locale: "en" });
```

项目详情页 `apps/web/src/pages/projects/[slug].astro` 会通过 `getStaticPaths` 生成每个项目页面，并用 `renderProjectMarkdown(project.body)` 渲染正文。

项目卡片 `apps/web/src/components/ProjectCard.astro` 接收 `project`，显示标题、摘要和标签。

## 小练习

1. 画出这条线：内容文件 → 读取函数 → 页面 → 组件 → 浏览器显示。
2. 在每个箭头旁写一个 Charlie 项目路径。
3. 用一句话解释为什么内容和组件要分开。

## 检查问题

1. `ProjectCard.astro` 是内容文件，还是显示组件？
2. `readProjects` 的作用更接近读取内容，还是设置域名？
3. `[slug].astro` 里的 `slug` 和项目文件名有什么关系？

## 常见误解

新手常以为把 MDX 文件放进项目，页面就会自动出现。实际需要读取、校验、路由生成和渲染。

另一个误解是认为组件保存内容。组件通常保存展示结构，真正的内容来自数据。

## 记住这些

- 内容从 `content/projects` 出发。
- `packages/content` 负责读取和校验。
- Astro 页面负责组织 route。
- 组件负责展示。
