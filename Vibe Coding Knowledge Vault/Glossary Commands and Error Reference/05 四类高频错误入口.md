> 📌 **一句话版本：** 很多报错看起来五花八门，但真正的排查套路其实高度相似；这页把最常见的错误类型和排查路线整理成一个可直接套用的模板。

---

## 📖 这一节在讲什么

你学到后面会发现，最消耗精力的不是听不懂概念，而是遇到错误时不知道该从哪里开始。这个速查页就是为这种时刻准备的。

## 🧠 四类高频错误入口

### 终端错误

常见关键词：

- `command not found`
- `permission denied`
- `no such file or directory`

### 前端错误

常见关键词：

- 页面白屏
- 控制台报错
- 状态没更新
- 接口成功但页面没显示

### 接口错误

常见关键词：

- `401`
- `403`
- `404`
- `500`

### 环境错误

常见关键词：

- 依赖版本不对
- 配置缺失
- 本地可以、线上不行

> 🌐 **In English:**
> Many errors look different on the surface, but the troubleshooting route often follows the same pattern: identify the layer, inspect the context, then narrow the scope.

## 🎯 一个统一排查模板

你可以对任何错误先问这五句：

1. 这是哪一层的问题
2. 触发动作是什么
3. 当前上下文是什么
4. 影响范围多大
5. 现在最该先看哪条信息

## 💡 为什么这个模板特别适合 PM

因为它不要求你立刻懂底层实现，但能让你先把问题从“混乱现象”整理成“可协作对象”。

## ⚠️ 最容易让排查失效的行为

- 只贴一句报错
- 不说明触发动作
- 不区分是页面现象还是接口现象
- 一上来就问“怎么修”

## 🧪 一个很实用的记录格式

你可以这样写：

- 现象：
- 触发动作：
- 层级判断：
- 关键线索：
- 影响范围：
- 下一步检查：

## 📝 记住这些

- 真正的排查，不是立刻修，而是先立刻分层。
- 模板化记录会显著提高你和 AI、工程师的协作效率。
- 报错越多，越需要模板，而不是越需要猜。

## 📚 延伸阅读

- [11_产品经理的技术判断力/02_如何看报错_日志与影响范围.md](../11_pm_technical_judgment/02_how_to_read_errors_logs_and_impact_scope.md)
- [02_终端_Shell_文件系统与环境/03_常用命令与排错思路.md](../02_terminal_shell_filesystem_and_environment/03_common_commands_and_troubleshooting_patterns.md)
