> 一句话版本：App 内弹窗不是“有话就弹”，而是根据用户当下任务选择合适的提示层级。

## 1. App 内提醒的类型

| 类型 | 打断程度 | 适合场景 | 不适合场景 |
|---|---:|---|---|
| Modal Alert 弹窗 | 高 | 重要确认、风险提示、权限前解释 | 普通营销、日常提醒 |
| Bottom Sheet 底部面板 | 中高 | 设置时间、选择星期、完成后引导 | 紧急错误 |
| Banner 顶部或卡片横幅 | 中 | 首页提示、任务状态、轻量召回 | 必须用户立刻处理的事 |
| Toast/Snackbar | 低 | 保存成功、已加入提醒、已撤销 | 需要长时间阅读的内容 |
| Inline Card 行内卡片 | 低 | 首页今日建议、空状态引导 | 紧急确认 |
| Badge/红点 | 很低 | 有未读、未完成状态 | 复杂解释 |

## 2. 弹窗的使用原则

弹窗适合“需要用户停下来做决定”的事情。比如：

- 是否保存提醒设置。
- 是否允许通知。
- 是否退出正在进行的训练。
- 是否清空历史记录。

弹窗不适合“我们希望用户多看一点”的事情。比如：

- 推荐一个普通功能。
- 告诉用户今天可以运动。
- 提醒用户有一个新内容。

这些更适合用首页卡片、轻横幅或 More 页入口。

## 3. 健康运动 App 的典型弹窗流程

### 场景 A：首次完成训练后设置提醒

触发时机：用户完成一节训练，处于正反馈状态。

推荐流程：

1. 显示完成反馈：`Nice work today`
2. 轻量解释价值：`A gentle reminder can help you keep a steady routine.`
3. 给默认时间：`8:00 AM, Every day`
4. 允许用户点 `Set Reminder` 或 `Maybe Later`

不要在用户第一次打开 App 时就强弹系统通知权限。更好的做法是先用 App 内弹窗解释价值，用户点确认后再触发系统权限框。

### 场景 B：首页今日运动提示

触发时机：用户打开首页，但今天还没有运动。

推荐形式：首页 Exercise 卡副标题或卡片内提示。

示例：

- `Today: 8 min gentle plan`
- `Reminder 8:00 AM`
- `Set a gentle reminder`

不推荐一打开首页就弹大弹窗，因为首页是用户扫描信息的地方，不应该频繁阻断。

### 场景 C：用户关闭通知权限

推荐形式：在提醒设置页显示一条静态说明。

示例：

`Notifications are off in system settings. You can still use in-app reminders here.`

不要反复弹窗要求用户去系统设置。权限是一种信任，不是 App 可以反复讨要的东西。

## 4. 弹窗结构模板

一个好的提醒弹窗通常包含四部分：

| 部分 | 作用 | 示例 |
|---|---|---|
| 标题 | 说明发生了什么或要做什么 | `Set a daily movement reminder?` |
| 简介 | 解释价值，不超过两行 | `We’ll remind you at your chosen time.` |
| 主按钮 | 明确动作结果 | `Set Reminder` |
| 次按钮 | 给用户退出选择 | `Maybe Later` |

## 5. 弹窗文案要避免的写法

| 不推荐 | 问题 | 推荐 |
|---|---|---|
| `Don’t miss your workout!` | 有催促感 | `Your gentle movement is ready` |
| `Prevent disease now` | 医疗承诺风险 | `Keep a steady movement routine` |
| `You failed today` | 羞辱用户 | `Try a short session when you feel ready` |
| `Allow notifications to continue` | 像强制条件 | `Get a reminder at your chosen time` |

## 6. App 内弹窗的验收清单

- 弹窗是否只在必要时出现。
- 用户是否能关闭或稍后再说。
- 主按钮是否说明点击后的真实结果。
- 文案是否避免恐吓、夸大、医疗承诺。
- 弹窗是否会遮挡正在进行的关键任务。
- 对老年用户，字号、按钮区域、对比度是否足够。

## 延伸阅读

- [Material Design 3: Dialogs](https://m3.material.io/components/dialogs/overview)
- [Material Design 3: Snackbar](https://m3.material.io/components/snackbar/overview)
- [Nielsen Norman Group: 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/)

