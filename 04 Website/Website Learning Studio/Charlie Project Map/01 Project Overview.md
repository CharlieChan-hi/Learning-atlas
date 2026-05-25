> 一句话版本：Charlie 项目可以被理解为一个个人品牌入口、项目展示区、可运行应用容器和长期内容系统的组合。

---

## 这一节在讲什么

这一节给你一个 Charlie 项目的总览。你会知道这个项目不是单一网页，而是由主站、内容、共享包、应用和部署配置组成的工作区。

对零基础来说，先不要试图读懂每一行代码。你要先知道哪些目录负责什么。

## 概念解释

真实网站项目会把不同责任拆开。页面入口、内容文件、组件、样式、配置、构建脚本、部署文件通常不会放在同一个地方。

Charlie 项目使用 `pnpm workspace`。这意味着根项目下面可以有多个应用和多个共享包。根目录负责统一管理，具体功能分散在 `apps/*` 和 `packages/*`。

你可以把它理解成一个工作室：`apps` 是对外展示或运行的空间，`packages` 是内部工具和材料库，`content` 是文字资料，`docs` 是说明文档。

## 现实例子

一个个人网站可能同时需要首页、项目页、中文页、英文页、可运行 demo、未来笔记和联系入口。

如果所有东西都塞进一个文件，短期看起来简单，长期会很混乱。

拆成目录后，初看会复杂，但每个目录有职责。学习项目的第一步，就是给目录贴上职责标签。

## Charlie 项目案例

只读观察确认这些路径存在：

- `/Users/mac/Desktop/charliechanstudio.com/apps/web`
- `/Users/mac/Desktop/charliechanstudio.com/apps/focus-training`
- `/Users/mac/Desktop/charliechanstudio.com/apps/console`
- `/Users/mac/Desktop/charliechanstudio.com/packages/content`
- `/Users/mac/Desktop/charliechanstudio.com/packages/lib`
- `/Users/mac/Desktop/charliechanstudio.com/packages/ui`
- `/Users/mac/Desktop/charliechanstudio.com/content/projects`
- `/Users/mac/Desktop/charliechanstudio.com/cloudflare`

根目录 `package.json` 里有 `dev`、`build`、`check`、`verify` 等脚本。`pnpm-workspace.yaml` 指定了 `apps/*` 和 `packages/*`。

这说明 Charlie 项目更像一个小型产品工作区，而不是只有一个静态页面文件夹。

## 小练习

1. 把 `apps`、`packages`、`content`、`docs` 四个词写下来。
2. 给每个词写一句「它大概负责什么」。
3. 找出你最想先理解的一个目录。

## 检查问题

1. `apps/web` 更像主站入口，还是内容数据库？
2. `packages/content` 为什么不直接叫 `pages`？
3. 根目录脚本的作用是什么？

## 常见误解

新手常以为目录越多代表项目越乱。目录多不一定乱，关键要看职责是否清楚。

另一个误解是看到 `node_modules` 就想读。这个目录通常是安装依赖生成的，不是学习项目结构的第一入口。

## 记住这些

- 先看根目录，再看 `apps` 和 `packages`。
- Charlie 项目是 workspace，不是单页文件夹。
- 学习时只读观察，不修改正式项目。
