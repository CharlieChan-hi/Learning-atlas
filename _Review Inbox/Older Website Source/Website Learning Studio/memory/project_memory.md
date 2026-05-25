# Project Memory

## Project purpose

`Website Learning Studio` 是一个独立 Markdown 学习库，位置是 `/Users/mac/Desktop/Website Learning Studio`。它面向零基础学习者，用来理解个人介绍型网站的设计、内容、代码、目录结构、部署和后续维护。

本学习库只做学习、解释、训练和案例拆解。它不修改、不运行、不预览 `/Users/mac/Desktop/charliechanstudio.com`。

## Source request

使用者希望创建一个桌面学习文件夹，用英文目录名和文件名组织内容，正文以中文为主，保留必要英文技术术语。内容要精确、详细、适合小白学习，不要把所有内容塞进一个大文件。

使用者强调个人网站的重点是先自我介绍，再往下展示项目。设计方向以黑白、极简、易读、可信为学习基线。

## Workflow decision

本项目参考 `/Users/mac/Desktop/Learning Studio/knowledge_base_workflow_general.md` 的知识库生产方法，采用适配版 7 阶段流程：

1. 需求确认与用户画像。
2. 模块结构设计。
3. 排版规范确定。
4. 分批内容生产。
5. 质量审查与修复。
6. 通用 Markdown 兼容性检查。
7. 交付与记忆存档。

本项目不照搬 Obsidian 绑定要求。目录和文件名保持英文 ASCII，正文使用标准 Markdown。

## Structure decision

第一版包含 46 个 Markdown 文件：

- `README.md`
- `00_orientation`
- `01_website_big_picture`
- `02_charlie_project_map`
- `03_personal_site_strategy`
- `04_design_foundations`
- `05_code_foundations`
- `06_content_and_copywriting`
- `07_deployment_and_operations`
- `08_practice_labs`
- `09_reference`
- `memory`

每篇教学文章采用固定骨架：一句话版本、这一节在讲什么、概念解释、现实例子、Charlie 项目案例、小练习、检查问题、常见误解、记住这些。

## Confirmed Charlie observations

只读观察确认：

- Charlie 项目位于 `/Users/mac/Desktop/charliechanstudio.com`。
- 根目录 `package.json` 使用 `pnpm@10.33.4`，Node 范围是 `>=24 <26`。
- `pnpm-workspace.yaml` 指定 `apps/*` 和 `packages/*`。
- `apps/web` 是 Astro 主站，依赖 Astro、React、Tailwind、Vite。
- `apps/web/src/pages/index.astro` 是英文首页入口。
- `apps/web/src/pages/zh/index.astro` 是中文首页入口。
- `content/projects/focus-training.en.mdx` 和 `focus-training.zh.mdx` 是项目内容样例。
- `packages/content/src/projects.ts` 读取和校验项目内容。
- `packages/content/src/schema.ts` 定义项目 frontmatter schema。
- `apps/web/src/components/ProjectCard.astro` 展示项目卡片。
- `apps/web/src/pages/projects/[slug].astro` 生成项目详情页。
- `packages/lib/src/routes.ts` 定义站点信息和导航。

## Existing Charlie git state

执行本学习库前，只读检查发现 Charlie 项目已有多个未提交改动和未跟踪文件。本学习任务没有清理、提交、覆盖或修改这些文件。

## Unconfirmed or future checks

以下内容可未来继续只读确认：

- `apps/console` 的具体用途。
- `cloudflare` 目录的部署配置细节。
- `packages/ui` 中所有 UI 工具的完整关系。
- Cloudflare Pages 实际 build command 和 output directory。

## Quality note

如果以后扩写本学习库，应保持零基础友好、路径真实、术语解释充分、练习可操作，并继续区分「已只读确认」和「待只读确认」。
