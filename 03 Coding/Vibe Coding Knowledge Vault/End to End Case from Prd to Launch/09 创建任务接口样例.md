> 📌 **一句话版本：** 这一页给你一组案例接口与 JSON 样例，让前面的需求、状态和输出结构不再停留在抽象层，而是落成“实际应该长什么样”。

---

## 📖 这一节在讲什么

完整案例走到这里，最值得补的一步就是把接口样例和 JSON 结构具象化。这样你后面再看前端、后端、状态和 AI 输出时，会更有“这是真实系统”的感觉。

## 🔌 创建任务接口样例

```json
{
  "workspace_id": "wk_001",
  "date_range": "2026-W13",
  "raw_notes": "本周完成了版本规划、接口梳理和竞品分析",
  "style": "professional"
}
```

成功返回可以像这样：

```json
{
  "code": 0,
  "message": "accepted",
  "data": {
    "task_id": "task_1001",
    "status": "pending"
  }
}
```

## 🔍 查询任务状态接口样例

```json
{
  "code": 0,
  "message": "ok",
  "data": {
    "task_id": "task_1001",
    "status": "success",
    "result": {
      "summary": "本周完成版本规划与竞品分析。",
      "highlights": ["梳理了接口边界", "明确了迭代目标"],
      "risks": ["下周资源排期仍需确认"],
      "next_week_focus": ["推进评审", "补充验收清单"]
    }
  }
}
```

## 📚 历史记录接口样例

```json
{
  "code": 0,
  "message": "ok",
  "data": {
    "list": [
      {
        "task_id": "task_1001",
        "status": "success",
        "created_at": "2026-03-31T10:00:00Z"
      }
    ],
    "page": 1,
    "page_size": 20,
    "total": 1
  }
}
```

## ⚠️ 失败返回样例

```json
{
  "code": 1003,
  "message": "content too long",
  "data": null
}
```

## 🎯 为什么这些样例重要

因为一旦你把结构写出来，很多原本模糊的点就会暴露出来：

- 状态到底用什么值
- 历史记录需不需要分页
- 输出字段是否足够稳定
- 失败时前端拿什么做反馈

> 🌐 **In English:**
> Concrete JSON examples make the system real. They reveal hidden ambiguity in status values, result fields, history design, and failure handling.

## 📝 记住这些

- 接口样例是连接需求、前端、后端和测试的中间桥梁。
- 一旦 JSON 结构稳定，很多协作成本会显著下降。
- PM 不一定亲自写接口，但必须能看懂接口样例在表达什么。

## 📚 延伸阅读

- [02_从数据结构到AI输出与状态设计.md](02_from_data_models_to_ai_output_and_state_design.md)
- [01_HTTP_请求_响应_状态码与接口设计.md](../06_backend_foundations_http_api_auth_and_services/01_http_requests_responses_status_codes_and_api_design.md)
