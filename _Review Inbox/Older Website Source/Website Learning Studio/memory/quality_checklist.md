# Quality Checklist

## Article structure

每篇教学文章应包含：

1. 一句话版本。
2. 这一节在讲什么。
3. 概念解释。
4. 现实例子。
5. Charlie 项目案例。
6. 小练习。
7. 检查问题。
8. 常见误解。
9. 记住这些。

`README.md` 和少数参考文件可以使用更适合导航的结构，但仍要保持清楚、可读、可回查。

## Language rules

正文以中文为主。必要英文术语保留英文，例如 `HTML`、`CSS`、`JavaScript`、`component`、`route`、`build command`、`Cloudflare Pages`。

英文术语第一次出现时，要给出中文解释或上下文解释。

避免为了显得专业而堆英文。英文应帮助读者连接真实项目和工具。

## Formatting rules

使用标准 Markdown。

禁止使用：

- Obsidian wikilink，指双中括号链接写法。
- Obsidian callout，指方括号感叹号提示块写法。
- Dataview block。
- HTML 折叠块。
- HTML non-breaking space entity。

表格尽量控制在 4 列以内。代码块保持短行，避免打印或导入 Notion 时难读。

## Content quality rules

每篇文章都要服务一个明确学习目标。

每个抽象概念都要有现实例子。

Charlie 项目案例必须基于只读观察。没有确认的内容要标注「待只读确认」。

不要把文章写成纯理论教材。读者读完后应能完成一个小动作，例如解释一个目录、画一条内容流、写一句首页文案。

## Beginner-friendly rules

假设读者完全零基础。

不要连续使用多个未解释术语。

遇到复杂概念，先讲它解决什么问题，再讲它叫什么。

每篇文章都要提供小练习和检查问题，让读者从「看过」变成「能复述」。

## Readability and design-depth rules

每篇面向小白的文章都要回答三个问题：这是什么，它解决什么问题，我可以怎么用它设计或理解网页。

如果文章出现英文术语，要把术语放进层级里解释，例如访问、页面、结构、工具、上线。不要只给中文翻译。

设计类文章不能只说原则，要给判断问题。例如「读者 2 秒内能不能知道网站属于谁」「按钮是否说明点击后的结果」「项目是否说明它证明了什么能力」。

代码类文章不能只讲命令，要说明命令在哪个目录执行、是否只读、是否会生成文件、它和网页上线有什么关系。

上线类文章不能只讲平台名，要说明仓库、分支、构建命令、输出目录、域名和 DNS 的顺序。

练习类文章要有明确产出，例如一张目录地图、一条内容流、一段首页文案、一个部署设置草稿。

## Personal website strategy rules

所有设计、文案和结构建议都要服务个人介绍型网站。

首页第一屏优先表达：我是谁、我做什么、为什么值得继续看。

项目展示可以放在下方，用来证明能力和方向。

黑白极简是学习基线，不是最终设计锁定。

## Verification checklist

交付或扩写后检查：

```bash
find "/Users/mac/Desktop/Website Learning Studio" -type f -name "*.md" | wc -l
find "/Users/mac/Desktop/Website Learning Studio" -print | LC_ALL=C grep -n '[^ -~]'
find "/Users/mac/Desktop/Website Learning Studio" -type f -name "*.md" -exec sh -c 'for f do first=$(LC_ALL=C sed -n "1p" "$f"); [ "$first" = "---" ] && printf "%s\n" "$f"; done' sh {} +
```

额外人工检查：确认没有 Obsidian-only 语法、HTML non-breaking space entity 或 HTML 折叠块。

期望结果：

- 第一版 Markdown 数量为 46。
- 文件和目录名保持英文 ASCII。
- 没有 YAML frontmatter 开头。
- 没有 Obsidian-only 语法。
- 没有 HTML non-breaking space entity。

## Expansion rules

以后新增文章时，优先补充练习和案例，不要只增加理论。

新增目录前先确认是否能放入现有模块。避免为了一个小主题增加新的顶层目录。

新增 Charlie 项目案例前，先做只读确认，不要凭记忆写路径。
