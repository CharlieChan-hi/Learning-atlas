> One-line version: Do not judge subscription design by purchase conversion alone. Measure the whole journey.

---

## 为什么不能只看首购

一个 paywall 可以短期提高首购，但长期伤害信任。

如果它带来：

- 高退款。
- 高取消。
- 低付费后使用。
- 低 D1 / D7 留存。
- 高投诉。

那它不是好方案。

> English:
> A good paywall does not only convert. It should create paid users who continue using the product.

## Loading Metrics

| Metric | 看什么 |
|---|---|
| Time to interactive | 用户多久能开始操作 |
| Loading drop-off | 等待中流失 |
| Generation completion | AI 生成是否完成 |
| Retry rate | 加载失败后是否重试 |
| Long wait rate | 超过阈值的等待比例 |

## Onboarding Metrics

| Metric | 看什么 |
|---|---|
| Onboarding completion | 是否走完引导 |
| Step drop-off | 哪一步流失 |
| Continue CTR | 每屏继续点击 |
| Time to first value | 多久看到价值 |
| Permission opt-in | 权限授权 |
| Quiz completion | 问卷完成 |

## Paywall Metrics

| Metric | 看什么 |
|---|---|
| Paywall view rate | 有多少人看到订阅页 |
| Trial start rate | 开始试用 |
| Purchase rate | 直接购买 |
| Close rate | 关闭 |
| Plan mix | 选择周/月/年比例 |
| Restore rate | 恢复购买 |

## Payment Metrics

| Metric | 看什么 |
|---|---|
| Purchase success | 支付成功 |
| Payment failure | 支付失败 |
| Retry after fail | 失败后重试 |
| Cancel during checkout | 支付中取消 |
| Post-purchase action | 买完是否继续使用 |

## Long-Term Metrics

| Metric | 看什么 |
|---|---|
| Trial conversion | 试用转正 |
| Refund rate | 退款 |
| Cancellation rate | 取消订阅 |
| Paid retention | 付费留存 |
| Paid usage depth | 付费后使用深度 |
| LTV | 生命周期价值 |

## A/B Test Ideas

### Loading

- Logo only vs logo + subtle motion。
- Static loading vs generated animation。
- No text vs short status text。

### Onboarding

- Result-first 1 page vs 3 pages。
- Same video with changing copy vs different video per step。
- Chinese copy vs English copy。
- Big title vs small title。

### Paywall

- Video background vs static background。
- Yearly default vs weekly default。
- Trial vs no trial。
- Credits explanation vs unlimited wording。

### Payment

- Success page vs direct return to result。
- Generic failure text vs clear retry text。

## How To Read Results

不要只看某一步转化。

例子：

```text
Version A:
Paywall conversion higher
Refund higher
D7 lower

Version B:
Paywall conversion lower
Refund lower
D7 higher
```

Version B 可能更健康。

## For Our AIGC Prototype

优先测：

- 三屏结果引导 vs 单长视频引导。
- 引导页英文短文案 vs 中文短文案。
- 订阅页视频背景类型。
- View Plans 出现时机。
- 支付后回首页 vs 回结果页。

