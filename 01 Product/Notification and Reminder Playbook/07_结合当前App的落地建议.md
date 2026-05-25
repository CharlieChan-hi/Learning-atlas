> 一句话版本：当前项目最适合先做“运动本地提醒 + 首页 Exercise 卡提示 + More 设置入口”，远程推送后置。

## 1. 当前源码现状

根据已阅读的项目源码，当前结构大致是：

- 主 Tab：`Plan / Trends / More`
- 首页入口：`Plan/ViewController.swift`
- 首页 Daily Routine 有 Exercise 卡。
- Exercise 卡现在点击进入 `ResistanceBandViewController`。
- Exercise 卡副标题目前根据今日 `activeMinutes` 显示 `Active 0 mins` 或 `Active X mins`。
- More 页目前没有运动提醒入口。
- 药物提醒已有 `MedicineReminderManager` 和 `MedicineSettingsViewController`，但那套逻辑不应该直接复用成运动提醒。
- Firebase/FCM 有管理类，但启动配置被注释，远程推送未启用。

## 2. 第一阶段目标

第一阶段不要试图一次完成 28 天计划、远程推送、运营分群、问卷匹配和完整训练系统。先完成一个闭环：

```text
用户打开首页
  -> 看到 Exercise 卡提示
  -> 进入运动页
  -> 完成训练
  -> App 内提示是否设置提醒
  -> 用户选择时间和星期
  -> 本地通知按规则提醒
  -> 点击通知回到运动页
```

## 3. 需要新增的数据

建议新增独立模型，不塞进药物设置：

```text
RMExerciseReminderSettings
- id: deviceId
- isEnabled: Bool
- hour: Int
- minute: Int
- weekdays: String
- titleKey: String
- bodyKey: String
- updatedAt: Date
```

`weekdays` 第一版可以用逗号字符串保存，例如：

```text
1,2,3,4,5,6,7
```

后续如果规则复杂，再迁移成更结构化的数据。

## 4. 需要新增的通知管理器

建议新增：

```text
ExerciseReminderManager
```

职责：

- 请求通知权限。
- 根据设置创建本地通知。
- 取消旧运动提醒。
- 设置修改后重建提醒。
- 生成通知 identifier。

identifier 示例：

```text
exercise-reminder-1
exercise-reminder-2
exercise-reminder-3
```

其中数字对应 weekday。

## 5. 首页提示规则

在 `ViewController.updateExerciseSubtitle()` 中加入提醒状态判断。

优先级建议：

1. 今日已运动：显示 `Active X mins`
2. 今日未运动，已开启提醒：显示 `Reminder 8:00 AM`
3. 今日未运动，未开启提醒：显示 `Set a gentle reminder`

接入 28 天计划后再扩展：

1. 今日已完成计划：`Done today`
2. 今日有计划未完成：`Today: 8 min gentle plan`
3. 已开启提醒：`Reminder 8:00 AM`
4. 未开启提醒：`Set a gentle reminder`

## 6. More 页入口

More 页建议新增一个设置项：

```text
Exercise Reminder
Set a daily movement time
```

位置建议放在 General 里，Share App 上方或下方都可以。

点击进入：

```text
ExerciseReminderSettingsViewController
```

页面内容：

- 开关：Exercise Reminder
- 时间选择：8:00 AM
- 重复星期：Sun Mon Tue Wed Thu Fri Sat
- 保存按钮：Save Reminder
- 权限状态提示：Notifications are off in system settings

## 7. 训练完成后的 App 内提示

`ResistanceBandViewController` 里现在已有视频完成回调 `onVideoFinished`。可以在完成后判断：

- 如果用户未开启运动提醒，弹出底部面板引导设置。
- 如果已开启，不重复弹。

弹窗建议：

标题：

```text
Set a reminder for your next session?
```

简介：

```text
A gentle reminder can help you keep a steady routine.
```

按钮：

```text
Set Reminder
Maybe Later
```

## 8. 通知文案第一版

标题：

```text
Time for gentle movement
```

简介：

```text
Your 8-minute plan is ready. Move slowly and take breaks if needed.
```

如果担心通知正文太长，可用更短版：

```text
Your 8-minute plan is ready.
```

## 9. 远程推送后置原因

暂时不建议第一阶段启用远程推送，原因：

- 当前 Firebase 配置未启用。
- 远程推送需要 APNs、证书、权限、后端策略、用户分群、退订逻辑。
- 运动提醒是用户本地设置，不需要服务器。
- 先做本地提醒更简单、稳定、隐私友好。

远程推送适合第二或第三阶段：

- 新计划上线。
- 用户连续多日未打开 App。
- 个性化计划更新。
- 订阅权益或内容提醒。

## 10. 风险点

| 风险 | 说明 | 应对 |
|---|---|---|
| 权限被拒 | 用户不同意通知 | 允许 App 内提示继续工作 |
| 文案医疗化 | 可能触碰健康声明风险 | 不承诺疗效，不诊断 |
| 提醒过多 | 用户关闭通知 | 第一版每天最多 1 条 |
| 与药物提醒混淆 | 药物提醒和运动提醒性质不同 | 独立模型和管理器 |
| 多语言溢出 | 本地化文案变长 | UI 留宽，按钮允许缩放 |

## 11. 最小实现清单

第一版代码任务可以拆成：

1. 新增 `RMExerciseReminderSettings`。
2. `DatabaseManager` 增加保存和读取方法。
3. 新增 `ExerciseReminderManager`。
4. 新增 `ExerciseReminderSettingsViewController`。
5. More 页增加入口。
6. 首页 Exercise 卡接入提醒状态。
7. 训练完成后引导设置提醒。
8. 增加本地化文案。
9. 测试开启、修改、关闭、权限拒绝、点击通知跳转。

