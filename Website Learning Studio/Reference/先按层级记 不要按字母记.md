> 一句话版本：词汇表帮助你把陌生英文技术词转成可理解的中文概念，再回到真实项目里识别它们。

---

## 这一节在讲什么

这一节提供个人网站学习常见术语。它不是完整技术词典，而是帮助你读本资料库和 Charlie 项目。

遇到术语时，先看这里，再回到原文。不要把词汇表当成背单词表，它更像地图上的图例。

## 先按层级记，不要按字母记

小白最容易被术语吓到，是因为所有词同时出现。你可以先按层级记。

第一组是“访问网站”的词，例如 `browser`、`domain`、`DNS`、`server`。

第二组是“页面长什么样”的词，例如 `HTML`、`CSS`、`JavaScript`、`layout`、`accessibility`。

第三组是“项目怎么组织”的词，例如 `component`、`route`、`frontmatter`、`MDX`、`slug`、`locale`。

第四组是“项目怎么运行”的词，例如 `Node.js`、`pnpm`、`TypeScript`、`package.json`、`build command`。

第五组是“网站怎么上线”的词，例如 `output directory`、`Cloudflare Pages`、`SEO`。

你每次只看一组，就不会被一整页英文词压住。

## 访问网站相关

| Term | 中文理解 | 学习时怎么用 |
|------|----------|--------------|
| website | 网站 | 浏览器能访问的一组页面和资源 |
| browser | 浏览器 | 打开和显示网页的工具，例如 Safari 或 Chrome |
| server | 服务器 | 提供网页资源的地方 |
| domain | 域名 | 人能读的网址，例如 `charliechanstudio.com` |
| DNS | 域名系统 | 把域名指向正确服务位置 |

## 页面与设计相关

| Term | 中文理解 | 学习时怎么用 |
|------|----------|--------------|
| HTML | 页面结构语言 | 定义标题、段落、链接等结构 |
| CSS | 样式语言 | 控制字体、颜色、布局和间距 |
| JavaScript | 脚本语言 | 控制网页交互和动态行为 |
| layout | 布局 | 页面公共结构和内容排列方式 |
| accessibility | 可访问性 | 让更多用户能读、能操作、能理解网站 |
| visual hierarchy | 视觉层级 | 决定读者先看哪里、再看哪里 |
| hero section | 首页第一屏 | 用户打开首页后最先看到的区域 |
| CTA | 行动按钮 | 引导读者点击下一步，例如查看项目 |

## 项目结构相关

| Term | 中文理解 | 学习时怎么用 |
|------|----------|--------------|
| component | 组件 | 可复用的界面单元，例如项目卡片 |
| route | 路由 | 页面访问路径，例如 `/projects` |
| frontmatter | 文件元数据 | Markdown 顶部的结构化信息 |
| MDX | Markdown 扩展格式 | 可在 Markdown 中结合组件或元数据 |
| slug | URL 标识 | 用于生成路径的短名称 |
| locale | 语言区域 | 区分英文、中文等版本 |
| workspace | 工作区 | 一个项目里同时管理多个应用和包 |
| package | 包 | 可被应用复用的内部或外部模块 |

## 工具与代码相关

| Term | 中文理解 | 学习时怎么用 |
|------|----------|--------------|
| Astro | 前端框架 | 适合内容型网站和作品集 |
| React | UI 函式库 | 适合交互界面和应用组件 |
| Vite | 构建工具 | 快速开发和构建前端应用 |
| Node.js | 运行环境 | 让 JavaScript 在浏览器外运行 |
| pnpm | 包管理器 | 安装依赖、运行脚本、管理 workspace |
| TypeScript | 类型增强语言 | 给 JavaScript 增加类型检查 |
| package.json | 项目说明文件 | 记录脚本、依赖和项目配置 |
| script | 脚本命令 | `package.json` 里可重复执行的命令名 |

## 上线与维护相关

| Term | 中文理解 | 学习时怎么用 |
|------|----------|--------------|
| build command | 构建命令 | 把源代码变成可发布文件 |
| output directory | 输出目录 | 构建后要发布的文件夹 |
| Cloudflare Pages | 托管平台 | 发布静态网站和前端应用 |
| Git | 版本控制工具 | 记录项目文件变化 |
| GitHub | 代码托管平台 | 保存仓库并连接部署服务 |
| SEO | 搜索引擎优化 | 让页面标题和描述更适合被理解和索引 |
| deploy | 部署 | 把网站发布到线上可访问环境 |

## Charlie 项目中的例子

`apps/web/src/pages/index.astro` 是首页 route 的源文件。

`content/projects/focus-training.en.mdx` 是项目内容文件。

`packages/content/src/projects.ts` 会读取项目内容。

`ProjectCard.astro` 是展示项目摘要的 component。

`apps/web/src/layouts/BaseLayout.astro` 提供页面公共 layout。

`packages/lib/src/routes.ts` 管理导航和站点信息。

## 术语消化方法

遇到一个新词时，不要只问“它是什么意思”。你可以按四步问。

1. 它属于哪一层：访问、页面、结构、工具，还是上线？
2. 它在 Charlie 项目里有没有真实路径？
3. 它解决什么问题？
4. 如果没有它，网站会少什么能力？

例如 `route` 属于页面结构层。它在项目里对应 `apps/web/src/pages`。它解决“某个网址应该显示哪个页面”的问题。如果没有 route，读者就无法通过 `/projects` 这类路径进入对应页面。

## 小练习

1. 选 10 个最陌生的词，抄到自己的问题清单里。
2. 给每个词写一个 Charlie 项目里的路径例子。
3. 每周回来看一次，划掉已经理解的词。
4. 把每个词归入访问、页面、结构、工具、上线五类之一。

## 检查问题

1. `route` 和 `component` 是同一个概念吗？
2. `build command` 和 `output directory` 有什么关系？
3. `locale` 为什么和双语内容有关？
4. 为什么按层级记术语比按字母记更适合新手？

## 记住这些

- 术语要放回真实路径里理解。
- 英文词不是障碍，是项目里的原始标签。
- 不懂的词先记录，再逐步消化。
- 先分类，再深入，学习压力会小很多。
