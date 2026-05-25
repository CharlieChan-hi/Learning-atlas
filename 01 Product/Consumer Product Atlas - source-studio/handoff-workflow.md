# Knowledge Atlas Handoff | 项目交接与续写手册

最后更新：2026-04-27

这份文档是给“晚上换一台电脑继续做”的场景准备的。它不讨论某一章具体写了什么，而是整理这套书稿现在处在什么状态、接下来应该怎么继续、哪些 skill 和工具最值得用、什么东西不能碰歪，以及每次收尾前怎么验。

## 当前项目状态

当前工作目录是 `/Users/mac/Desktop/Consumer Product Playbook`。书稿主目录是 `/Users/mac/Desktop/Consumer Product Playbook/knowledge-atlas`。这一轮收口后，`knowledge-atlas` 里已经有一套完整主文件。

- `README.md`：导读页
- `00` 到 `13`：正文章
- `14_glossary-and-source-index.md`：附录页
- `handoff-workflow.md`：这份交接手册
- `project-memory.md`：给后续模型快速读入的短记忆文件

现在的正文状态可以直接接着写，不是半成品目录，也不是残缺提纲。`00-13` 都已经回到统一教材结构，`README.md` 和 `14_glossary-and-source-index.md` 也已经按导读页与附录页重新整理。

## 这套书到底在做什么

项目目标不是做一个知识卡片库，而是做一套适合在 Obsidian 连续阅读的中文教材型书稿，主题是消费级产品经理如何理解用户价值、路径、引导、留存、增长、支付墙、定价和案例。核心写法是“零基础可读、像书一样往前推、但又保留真实产品和真实原话的现场感”。

这套书已经从早期的“引导页 / 订阅页知识树”扩成更完整的结构。现在“引导设计”和“支付墙与订阅变现”仍然是核心章，但它们只是整条价值链里的两章，不再单独承担全书。

## 不能改坏的写作契约

这是后续续写时最重要的一组约束。只要这组约束不破，后面换电脑、换模型、换几轮修改，整套书都还会是同一种声音。

- 文件名、编号和路径保持不变。不要重排 `00-14`。
- 一级标题保留双语，正文标题一律中文。
- `README.md` 只做导读，不要塞进体验区、原话区、复盘区。
- `14_glossary-and-source-index.md` 只做附录，不要写成教学正文。
- `00-13` 全部维持统一教学结构。

`00-13` 的统一结构如下：

1. 开场问题场景
2. `> 零基础先记住这一句`
3. 4 到 6 个主二级标题的连续正文
4. `## 推荐体验 App 与体验任务`
5. `## X 与论坛原话`
6. `## 本章复盘`
7. `## 延伸阅读与来源`

还有几条必须长期坚持：

- 正文以简体中文为主。
- 英文缩写第一次出现时，写成“中文名（缩写 / 英文原文，解释）”。
- 第二次开始，优先只用中文，不要把装饰性英文重新带回正文结构。
- 每章在“零基础先记住这一句”下面固定保留 1 句 `English takeaway`。
- Markdown 只用标准标题、表格、blockquote、checklist、少量 Mermaid。
- 不用 frontmatter、不用 HTML 折叠、不依赖 Obsidian callout。
- 不再使用任何批量重排结构的脚本。手工改稿统一用 `apply_patch`。

## 来源质量标准

来源标准是这套书的底线之一。后面不管是谁继续写，都要沿用同一个筛选口径。

优先来源有三类：

- 官方与一手来源：官网、帮助中心、开发者文档、定价页、应用商店页、平台规则页
- 平台级方法源：Amplitude、Mixpanel、Appcues、Braze、OneSignal、Branch、RevenueCat、Apple、Google Play 等
- 活人证据层：`X` 原帖、Hacker News 高赞讨论

明确排除：

- 知乎
- 百度
- 内容农场
- 截图转引
- 没有原帖链接的二次整理号
- 只会罗列“最佳实践”的低质量搬运博客

原话使用规则也要保留：

- 只摘关键一句或极短一段
- 紧跟中文解释
- 保留原帖或原评论链接
- 写明热度说明
- 再配一个平台级长文或官方长文锚点

当前论坛来源只保留两类：

- `X`
- Hacker News

不要继续扩到 Reddit、Indie Hackers 或别的社区，除非你以后明确要改这条策略。

## 推荐的续写工作流

这是后续最稳的一套顺序。每次开工都按这个节奏走，能少很多返工。

### 第一步，先读这些文件

如果是新电脑、新模型或新会话，先读四份材料：

1. [project-memory.md](./project-memory.md)
2. [README.md](./README.md)
3. [00_consumer-product-atlas.md](./00_consumer-product-atlas.md)
4. 你本次要改的目标章节

如果要动来源或原话，再补读 [14_glossary-and-source-index.md](./14_glossary-and-source-index.md)。

如果要理解更早期的结构原则，可以回看根目录里的 [knowledge_base_workflow_general.md](/Users/mac/Desktop/Consumer Product Playbook/knowledge_base_workflow_general.md)。它不是当前正文模板，但它仍然是这套项目早期骨架和阅读顺序观念的重要来源。

### 第二步，先判断你是在做哪一类工作

后续工作大致只有四类，别混着做。

- 结构重写：某一章推进感不够、像资料稿，不像文章
- 证据补强：某章 `X`、Hacker News 或官方锚点不够贴
- 中文清稿：句式别扭、段落过碎、太像知识卡片
- 附录更新：术语、来源索引、热度说明、章节映射变化

如果一轮里什么都想做，通常会把章节又写乱。更稳的方式是一次只抓一类主任务。

### 第三步，按固定顺序使用写作 skill

当前最适合这套书稿的 skill 组合是下面四个，顺序也尽量别乱。

1. `academic-writing-style`
2. `blog-writing-guide`
3. `chinese-content-writing-guideline`
4. `copy-editing`

它们在这台机器上的路径分别是：

- `/Users/mac/.agents/skills/academic-writing-style/SKILL.md`
- `/Users/mac/.agents/skills/blog-writing-guide/SKILL.md`
- `/Users/mac/.agents/skills/chinese-content-writing-guideline/SKILL.md`
- `/Users/mac/.agents/skills/copy-editing/SKILL.md`

各自负责的事情如下：

- `academic-writing-style`：把章节写成连续可读的长文，负责结构推进和段落组织
- `blog-writing-guide`：强化开头、转场、论证顺序和可读性，避免章节像抽屉并排
- `chinese-content-writing-guideline`：借它的去套话、收句子、反机械节奏原则
- `copy-editing`：最后做压缩、去重复、修排版密度

有两个提醒一定要记住：

- `chinese-content-writing-guideline` 原始说明偏正体中文，但这里不能把正文切成繁体，只借它的清稿原则
- `blog-writing-guide` 里有很强的英文博客风格规则，这里只借“先讲问题、再讲结构、再讲取舍”的方法，不把正文写成英文工程博客口气

### 第三步半，中英学习感要怎么落

这里的双语目标不是把正文改成双语资料页，而是让中文读者在顺读时自然带走一点英文表达。后续任何续写都按下面的规则执行。

- 正文主语言始终是中文。
- 每章只保留 1 句 `English takeaway`，放在“零基础先记住这一句”下面。
- 重要术语第一次出现时，写成“中文名（英文原文，简短解释）”。
- `X` 与 Hacker News 的原话保留英文，后接中文解释。
- 不做整段中英对照翻译。
- 不把小标题改成中英双轨标题。
- 每章只挑 3 到 8 个真正值得记住的英文词，不为了显得国际化而堆英文。

### 第四步，研究时的工具选择

工具和插件的使用策略已经比较清楚了，后面直接沿用就行。

- `web`：默认研究入口，适合找官方文档、平台文章、产品页、`X` 原帖、Hacker News 线程
- `Computer Use`：只在网页需要人工可视核实时使用，适合点状确认，不做大规模采集
- `Browser Use`：如果以后要在浏览器里实际点开本地页面或站内页面，可以用它做局部验证
- `rg`：全文搜索、结构检查、老残词排查
- `sed`：局部阅读已有稿子
- `apply_patch`：唯一推荐的手工编辑方式

不要再走回旧路：

- 不写批量改结构脚本
- 不用自动化爬虫批量扒网页
- 不大段复制原文
- 不为了热闹去扩更多来源层

### 第五步，章节真正落笔时怎么写

最稳的章内节奏是这样的：

- 先用一个真实问题把读者带进去
- 再用“零基础先记住这一句”把本章核心判断压缩成一句
- 再补 1 句 `English takeaway`，帮助读者顺手记住最值得学的英文表达
- 中段用 4 到 6 个主二级标题推进，不要过密
- 每个 `##` 下先有连续正文，再出现列表
- 体验区只做“像产品经理一样体验”的任务，不做竞品堆砌
- 原话区只做证据层，不要让它抢走正文主线
- 复盘只收三件事：最重要的判断、最容易犯的错、和下一章的连接

正文里最需要避免的，是重新回到“一句一行”“标题下面只有 bullet”“像提纲而不像文章”的节奏。

## 当前最值得继续做的 backlog

现在这套书稿已经可读，但如果你晚上继续推进，我建议优先做下面几件事。

### 最高优先级

- 替换 [11_pricing-and-offer-architecture.md](./11_pricing-and-offer-architecture.md) 当前的次优 `X` 原话
  备注：这一章现在已经在正文和附录里明确标成“次优替代证据”，后面最好换成更直接指向月付、年付、优惠节奏或价格结构的高质量原帖

### 第二优先级

- 更新 Apple、Google Play、RevenueCat、Mixpanel 等平台链接是否有新页面或新规则
- 定期重看 `X` 与 Hacker News 的热度说明，避免长期保留明显过时或贴章不够紧的证据
- 继续给 `12` 和 `13` 补更强的案例与品类对照材料，但不要破坏当前结构

### 第三优先级

- 如果以后要继续扩厚，可以新增更多“体验任务”的观察角度，而不是新增更多章节
- 如果某一章变得过长，先重压结构，再决定要不要拆子页

## 另一台电脑怎么接起来

如果你晚上在别的电脑继续，最实用的接手清单如下。

1. 先把整个 `/Users/mac/Desktop/Consumer Product Playbook` 同步过去，至少保证 `knowledge-atlas/` 和 `knowledge_base_workflow_general.md` 在。
2. 如果你希望沿用同一套 skill 提示，最好同步 `.agents/skills/` 里的相关 skill。
3. 如果另一台电脑没有这些 skill，可以至少保证你有这四个名字对应的说明，或者按下方命令补装外部 skill。
4. 新会话开始时，先把 [project-memory.md](./project-memory.md) 喂给模型，再补 `README`、`00` 和目标章节。
5. 开始改之前，先跑一遍验证命令，确认书稿结构没有被别的修改打乱。

如果另一台电脑缺少外部 skill，可以参考这些命令：

```bash
npx -y skills add getsentry/skills@blog-writing-guide
npx -y skills add coreyhaines31/marketingskills@copy-editing
```

可选补强，但不是默认主流程：

- `npx skills add humanizerai/agent-skills@readability`
- `npx skills add miantiao-me/aigc-weekly@chinese-writing`
- `npx skills add seefreed/skills@en-to-zh-translator`

本地已有但不一定要强依赖的辅助 skill：

- `/Users/mac/.agents/skills/find-skills/SKILL.md`
- `/Users/mac/.agents/skills/executing-plans/SKILL.md`
- `/Users/mac/.agents/skills/verification-before-completion/SKILL.md`

## 常用验证命令

这些命令是目前最实用的一组。目录如果换机器但路径不变，可以直接跑；如果路径变化，把前缀目录改掉就行。

检查 `00-13` 是否保留四个固定尾部区块：

```bash
rg -n '^## 推荐体验 App 与体验任务$|^## X 与论坛原话$|^## 本章复盘$|^## 延伸阅读与来源$' /Users/mac/Desktop/'Consumer Product Playbook'/knowledge-atlas/{00_consumer-product-atlas.md,01_consumer-product-foundations.md,02_user-research-and-demand-discovery.md,03_value-proposition-and-category-strategy.md,04_core-flows-and-information-architecture.md,05_onboarding-design-atlas.md,06_retention-and-habit-systems.md,07_lifecycle-and-crm-systems.md,08_metrics-and-experimentation.md,09_growth-and-distribution.md,10_paywall-monetization-atlas.md,11_pricing-and-offer-architecture.md,12_category-benchmarks.md,13_case-benchmarks-and-teardowns.md}
```

检查旧版 `X` 标题是否已经清空：

```bash
rg -n '^## X 精选与原话$' /Users/mac/Desktop/'Consumer Product Playbook'/knowledge-atlas
```

检查旧脚手架词是否回流：

```bash
rg -n '推荐英文命名|子模块名可用|Document Identity|Page Naming|Editorial Logic' /Users/mac/Desktop/'Consumer Product Playbook'/knowledge-atlas
```

检查相对链接是否断掉：

```bash
ruby -e 'require "pathname"; bad=[]; Dir["/Users/mac/Desktop/Consumer Product Playbook/knowledge-atlas/*.md"].each do |f|; base=File.dirname(f); File.read(f).scan(/\]\((\.\/[^)]+)\)/).flatten.each do |t|; path=File.expand_path(t.sub(%r{^\./},""), base); bad << "#{f} -> #{t}" unless File.exist?(path); end; end; puts(bad.empty? ? "OK" : bad.join("\n"))'
```

## 最后一个提醒

这套书目前最宝贵的，不是“已经写了很多”，而是终于建立了一套比较稳的书稿契约。后面所有继续扩写的工作，最好都围绕这套契约慢慢长厚，而不是再把它打回到卡片库、资料池或结构实验场。
