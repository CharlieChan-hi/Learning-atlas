> 📌 **一句话版本：** `HTTP` 是浏览器、前端和后端通信的基本协议，而接口设计的质量，直接决定了联调成本、错误处理和系统可维护性。

---

## 📖 这一节在讲什么

你已经知道页面会发请求、后端会回结果，但如果不理解 `HTTP` 和接口设计，很多常见问题还是会像“只会看热闹”。这一节把最关键的通信层讲清楚。

## 🧠 HTTP 在做什么

`HTTP` 是客户端和服务端交换信息的一套规则。它规定了：

- 请求怎么发
- 参数放哪
- 响应怎么回
- 状态如何表达

## 🎯 一个请求通常包含什么

- 请求方法：`GET`、`POST`、`PUT`、`DELETE`
- 路径：访问哪个资源
- 参数：路径参数、查询参数、请求体
- 请求头：身份、格式、认证信息等

## 🎯 一个响应通常包含什么

- 状态码：例如 `200`、`401`、`404`、`500`
- 响应头
- 响应体：很多时候是 JSON

> 🌐 **In English:**
> HTTP defines how clients and servers exchange requests and responses. Good API design makes integration clearer, safer, and easier to maintain.

## 🧩 为什么 PM 一定要看懂“请求”和“响应”

因为几乎所有 Web 功能，最终都落在这条线上：

- 前端发请求
- 后端收请求
- 后端返回响应
- 前端根据响应更新页面

只要你能把这一条线看清，很多功能问题就不再是“完全黑盒”。

## 🎯 不同请求方法的大致感觉

你不需要死背规范，但至少可以有个直觉：

- `GET`：更像取数据
- `POST`：更像提交新动作或新数据
- `PUT` / `PATCH`：更像更新
- `DELETE`：更像删除

这会帮助你读接口文档时更快建立感觉。

## 💡 为什么“接口设计清晰”对 PM 也很重要

接口设计清晰时：

- 前后端联调更容易
- 错误处理更统一
- 需求变更影响范围更容易判断

接口设计混乱时：

- 字段语义容易漂移
- 前端逻辑会堆很多兼容判断
- 后面一改就容易连带出问题

> 🌐 **In English:**
> Clear APIs reduce coordination cost. They help PMs reason about scope, errors, and the downstream impact of changes.

## ⚠️ 接口看起来“能用”但设计不好的典型信号

- 字段命名模糊
- 成功和失败结构不一致
- 状态码和业务含义混乱
- 某些边界情况没有明确定义

只要这些问题出现，后面维护成本往往会持续上升。

## ⚠️ PM 最值得理解的状态码

- `200`：通常表示成功
- `400`：请求本身有问题
- `401`：未认证
- `403`：已认证但没权限
- `404`：资源不存在
- `500`：服务端内部错误

这些状态码虽然简单，但对排错特别有帮助。

## 💡 什么叫好的接口设计

- 字段命名清晰
- 成功与失败结构稳定
- 参数规则明确
- 错误信息可理解
- 边界情况有定义

## 📝 记住这些

- HTTP 是前后端通信的基础语言。
- 状态码和 JSON 结构是 PM 读接口最值得先掌握的两层。
- 接口设计越清晰，联调和维护成本越低。

## 📚 延伸阅读

- [00_后端到底在做什么.md](00_what_the_backend_is_really_doing.md)
- [02_JSON_YAML_TOML与配置文件.md](../02_terminal_shell_filesystem_and_environment/02_json_yaml_toml_and_configuration_files.md)
- [02_路由_数据获取与接口联调.md](../05_frontend_engineering_react_next_and_api_integration/02_routing_data_fetching_and_api_integration.md)
