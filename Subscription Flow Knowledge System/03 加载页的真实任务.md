> One-line version: Loading is the first trust moment. It tells users whether the app feels alive, premium, and worth waiting for.

---

## 加载页的真实任务

加载页不是装饰页。它解决的是等待中的不确定感。

用户在加载时会想：

- App 是不是卡了？
- 这个产品质感怎么样？
- 它是不是在真的处理我的任务？
- 等待会不会很久？
- 我是不是可以相信它？

> English:
> Loading design is perceived performance design.
> It manages uncertainty while the product prepares the next value moment.

## 加载页的四种类型

### 1. Launch Loading

App 第一次打开时出现。

适合：

- 品牌 Logo。
- 极短动画。
- 高级极简背景。
- 不放解释型文案。

目标：

```text
让用户觉得这是一个完整、可信、有质感的产品。
```

### 2. Task Loading

用户触发任务后出现，比如上传照片、生成视频、分析内容。

适合：

- 真实状态。
- 阶段反馈。
- 预计等待。
- 可以取消或后台等待。

目标：

```text
让用户知道任务正在发生，而不是页面死掉。
```

### 3. AI Generation Loading

AI 图片/视频/文本生成时出现。

适合：

- 生成感动效。
- Analyzing / Rendering / Enhancing 等阶段文案。
- 预览占位。
- 结果期待。

不适合：

- 假进度条。
- 过度炫技动画。
- 跟结果无关的装饰。

### 4. Skeleton Loading

内容页或列表页加载时出现。

适合：

- 新闻、社区、内容流、工具列表。
- 需要保持布局稳定的页面。

不适合：

- 情绪化 onboarding。
- 需要品牌质感的首次进入。

## 等待时间和设计策略

| 等待时间 | 用户感受 | 设计策略 |
|---|---|---|
| 0-1 秒 | 几乎无感 | 系统 launch screen 即可 |
| 1-3 秒 | 可以接受 | Logo + 轻动效 |
| 3-8 秒 | 开始怀疑 | 明确告诉用户正在做什么 |
| 8 秒以上 | 明显焦虑 | 进度、阶段、取消、后台等待 |
| 15 秒以上 | 高流失风险 | 给通知/后台完成/重试机制 |

## AIGC 加载页怎么做

推荐方向：

- 深色背景。
- 小 Logo。
- 中心微光。
- 呼吸动效。
- 不要大段文案。
- 真生成时才显示生成阶段。

示例结构：

```text
[Small Logo]

Creating your preview

subtle breathing light
```

或者更极简：

```text
[Small Logo]
[Tiny luminous point]
```

## 为什么 AIGC 加载不能太廉价

AI 生成本来就有一点“黑箱感”。如果加载页看起来廉价，用户会把这种黑箱感理解成不可信。

廉价感来自：

- 粗糙粒子。
- 过大的 Logo。
- 和品牌无关的小花/星星。
- 假进度。
- 动效卡顿。
- 文案像机器翻译。

高级感来自：

- 克制。
- 稳定。
- 动效少但精。
- 品牌位置清楚。
- 视觉不抢结果页。

## 加载页文案库

### 极简

```text
Preparing
Loading
```

### AI 生成

```text
Creating your preview
Rendering your result
Applying the selected style
Enhancing your photo
```

### 结果期待

```text
Your preview is almost ready
Making the first version
Generating a shareable result
```

### 长等待兜底

```text
This may take a few more seconds.
You can keep this running in the background.
We will save the result when it is ready.
```

## 加载页反模式

- 进度条每次都从 0 到 100，但和真实进度无关。
- Logo 大到像广告。
- 首次进入就讲一堆产品使命。
- 生成等待超过 10 秒但没有任何阶段反馈。
- 用户无法取消。
- 加载失败只显示 error。

## 检查清单

- 这里是真加载还是假等待？
- 等待时间大概多久？
- 是否需要品牌 Logo？
- 是否需要阶段反馈？
- 是否会出现失败？
- 失败时用户能不能重试？
- 动效是否会挡住主体？
- 是否支持 reduced motion？

## Sources

- [Apple Human Interface Guidelines - Launching](https://developer.apple.com/design/human-interface-guidelines/launching)
- [Android Developers - Splash screens](https://developer.android.com/develop/ui/views/launch/splash-screen)
- [Nielsen Norman Group - Response Times](https://www.nngroup.com/articles/response-times-3-important-limits/)

