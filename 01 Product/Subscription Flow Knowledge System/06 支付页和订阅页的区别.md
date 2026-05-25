> One-line version: Payment is not the place to persuade. It is the place to complete the transaction clearly and safely.

---

## 支付页和订阅页的区别

订阅页负责说服。

支付页负责完成。

如果把支付页也做成营销页，用户会觉得流程变复杂。如果订阅页没有说清楚价格，等到平台支付弹窗才让用户理解，用户会觉得被偷袭。

> English:
> The paywall should explain the offer. Checkout should confirm and complete it.

## 支付前必须说清楚

- 价格。
- 周期。
- 试用时长。
- 试用结束后的价格。
- 自动续费。
- 取消方式。
- 购买后得到什么。

## 支付中要避免什么

- 重复弹窗。
- 页面闪烁。
- 视频重载。
- CTA 连点导致多个请求。
- 用户返回后状态丢失。
- 支付取消后直接清空用户上下文。

## 支付成功后最重要

支付成功后不要只说：

```text
Thank you
```

更好的方式是回到价值：

```text
Your HD preview is unlocked.
Continue generating in this style.
```

或者：

```text
Pro is active.
Your watermark-free export is ready.
```

用户刚付钱，最想要的是马上得到他买的东西。

## 支付失败怎么写

支付失败不要吓人，也不要责怪用户。

推荐：

```text
Payment could not be completed.
No charge was made. Please try again.
```

或者：

```text
We could not confirm your purchase.
You can try again or restore purchases.
```

## 支付取消怎么处理

用户取消支付不等于永远不买。取消后应该回到原来的上下文。

例如 AIGC：

```text
返回刚刚的 preview。
保留用户选择的模板。
允许稍后再看方案。
```

不要：

- 清空生成结果。
- 强制回首页。
- 弹很重的挽回窗口。

## Restore Purchases

Restore Purchases 是订阅产品必须认真处理的入口。

它解决：

- 用户换手机。
- 用户重新安装。
- 用户已经买过但状态没同步。
- 用户不确定是否购买成功。

Restore 不应该藏得太深。它可以小，但要可见。

## AIGC 支付后回流

适合回流到：

- 高清结果页。
- 去水印导出页。
- 原模板继续生成。
- 点数余额页。
- 首页创作入口。

不适合：

- 空白成功页。
- 只显示会员徽章。
- 让用户重新选择照片。

## 检查清单

- 支付前价格是否清楚？
- 试用结束价格是否清楚？
- 支付成功后回到哪里？
- 支付失败后能不能重试？
- 支付取消后上下文是否保留？
- Restore 是否可见？
- 用户买完是否立刻得到价值？

## Sources

- [Apple - Auto-renewable subscriptions](https://developer.apple.com/app-store/subscriptions/)
- [Apple - App Store Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- [Google Play - Create and manage subscriptions](https://support.google.com/googleplay/android-developer/answer/140504?hl=en)

