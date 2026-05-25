# Knowledge Atlas Memory | 项目记忆文件

最后更新：2026-04-27

## 这是什么

这是一份给后续会话快速读入的短记忆文件。任何新模型或新电脑接手这套书稿时，先读这份，再读 [README.md](./README.md)、[00_consumer-product-atlas.md](./00_consumer-product-atlas.md) 和目标章节。

## 项目目标

把 `knowledge-atlas` 维护成一套适合在 Obsidian 连续阅读的中文教材型书稿，主题是消费级产品经理如何理解用户价值、路径、引导、留存、生命周期、增长、支付墙、定价、品类与案例。它不是知识卡片库，也不是两页专题站。

## 当前目录状态

- `README.md`：导读页
- `00-13`：正文章
- `14_glossary-and-source-index.md`：附录页
- `handoff-workflow.md`：完整交接手册
- `project-memory.md`：本记忆文件

## 绝对不能改坏的契约

- 文件名、编号、路径保持不变
- 一级标题保留双语，正文标题只用中文
- `README.md` 不加入体验区、原话区、复盘区
- `14_glossary-and-source-index.md` 不改成教学正文
- `00-13` 必须全部拥有完整正文主讲

`00-13` 的固定结构：

1. 开场问题场景
2. `> 零基础先记住这一句`
3. `> English takeaway`
4. 4 到 6 个主二级标题的连续正文
5. `## 推荐体验 App 与体验任务`
6. `## X 与论坛原话`
7. `## 本章复盘`
8. `## 延伸阅读与来源`

## 写法与排版约束

- 正文用简体中文
- 英文缩写首次出现写成“中文名（缩写 / 英文原文，解释）”
- 第二次开始优先只用中文
- 每章固定保留 1 句 `English takeaway`
- 正文不做整段中英对照翻译
- Markdown 只用标准标题、普通表格、blockquote、checklist、少量 Mermaid
- 不用 frontmatter、HTML 折叠、Obsidian 专属 callout
- 章节不要写回“一句一行”的资料稿
- 列表只保留在体验任务、复盘、延伸阅读与来源
- 手工改稿统一用 `apply_patch`
- 不再使用批量结构脚本

## 来源标准

优先三类来源：

- 官方与一手来源
- 平台级方法源
- `X` 原帖与 Hacker News 高质量讨论

明确排除：

- 知乎
- 百度
- 内容农场
- 截图转引
- 没有原帖链接的二次整理
- Reddit、Indie Hackers 等额外论坛来源

## 推荐 skill 顺序

1. `academic-writing-style`
2. `blog-writing-guide`
3. `chinese-content-writing-guideline`
4. `copy-editing`

使用原则：

- `academic-writing-style` 负责把章节写成连续长文
- `blog-writing-guide` 负责开头、转场、论证顺序
- `chinese-content-writing-guideline` 只借清稿原则，不切成繁体
- `copy-editing` 负责终稿压缩和舒适排版
- 英文只承担术语说明、`English takeaway` 和原始引文三种角色

## 推荐工具策略

- `web`：默认研究入口
- `Computer Use`：只做网页点状人工核实
- `rg`：搜索和结构校验
- `sed`：局部阅读
- `apply_patch`：编辑

## 目前最重要的待办

- 优先替换 [11_pricing-and-offer-architecture.md](./11_pricing-and-offer-architecture.md) 当前的次优 `X` 原话
- 定期更新 Apple、Google Play、RevenueCat、Mixpanel 等平台链接
- 继续增强贴章更强的 `X` 与 Hacker News 证据，但不要破坏当前章结构

## 开新会话时先做什么

1. 读本文件
2. 读 [README.md](./README.md)
3. 读 [00_consumer-product-atlas.md](./00_consumer-product-atlas.md)
4. 读目标章节
5. 如果会动来源，再读 [14_glossary-and-source-index.md](./14_glossary-and-source-index.md)

## 快速验证命令

检查固定章节结构：

```bash
rg -n '^## 推荐体验 App 与体验任务$|^## X 与论坛原话$|^## 本章复盘$|^## 延伸阅读与来源$' /Users/mac/Desktop/'Consumer Product Playbook'/knowledge-atlas/{00_consumer-product-atlas.md,01_consumer-product-foundations.md,02_user-research-and-demand-discovery.md,03_value-proposition-and-category-strategy.md,04_core-flows-and-information-architecture.md,05_onboarding-design-atlas.md,06_retention-and-habit-systems.md,07_lifecycle-and-crm-systems.md,08_metrics-and-experimentation.md,09_growth-and-distribution.md,10_paywall-monetization-atlas.md,11_pricing-and-offer-architecture.md,12_category-benchmarks.md,13_case-benchmarks-and-teardowns.md}
```

检查旧版标题与旧脚手架词：

```bash
rg -n '^## X 精选与原话$|推荐英文命名|子模块名可用|Document Identity|Page Naming|Editorial Logic' /Users/mac/Desktop/'Consumer Product Playbook'/knowledge-atlas
```
