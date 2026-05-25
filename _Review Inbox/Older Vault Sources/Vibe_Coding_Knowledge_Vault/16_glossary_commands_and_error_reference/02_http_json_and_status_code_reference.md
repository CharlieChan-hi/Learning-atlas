> 📌 **一句话版本：** 这一页帮你在看接口、抓包、浏览器网络面板和日志时，快速对上 `HTTP`、`JSON`、字段结构和状态码这些最关键的信息。

---

## 📖 这一节在讲什么

接口相关内容是 PM 最容易反复碰见、也最容易一时想不起细节的部分，所以这里专门做一页速查。

## 🧠 高频状态码

- `200`：成功
- `400`：请求有问题
- `401`：未认证
- `403`：无权限
- `404`：资源不存在
- `500`：服务端错误

## 🧠 高频 JSON 判断点

- 最外层是对象还是数组
- 哪个字段是真正业务数据
- 字段类型是否稳定
- 是否存在空值或缺字段

> 🌐 **In English:**
> When reading APIs, focus on status codes, JSON structure, field meaning, and error patterns before jumping to conclusions.

## 🎯 看到接口信息时，先看什么

很多人一看到一大段返回结果就发蒙，其实可以按固定顺序看：

1. 状态码
2. 请求路径
3. 关键参数
4. 响应体结构
5. 业务字段

这样你会更快判断这是“请求没发对”“权限不够”“接口挂了”，还是“字段对不上”。

## 💡 高频 JSON 观察角度

### 先看外层结构

是对象还是数组，决定你后面应该怎么找字段。

### 再看真正业务字段在哪

很多接口会有 `code / message / data` 这种外壳，重点通常在 `data` 里。

### 再看异常表示方式

有些接口用状态码表达失败，有些还会在 JSON 里带错误信息。你要同时看。

## ⚠️ PM 最容易漏掉的点

### 漏点一：只看状态码不看内容

接口可能返回 `200`，但业务结果仍然是空、错或异常。

### 漏点二：只看字段名不看类型

字段名对了，不代表类型没变。字符串变数字、对象变数组，都会直接影响前端和脚本。

### 漏点三：只看一次成功示例

真正有价值的是连失败和边界情况也能看懂。

> 🌐 **In English:**
> API reading is not only about status codes. You should also inspect structure, business fields, types, and failure patterns.

## 🧪 一个速查时很好用的小模板

看任何接口时，你都可以在心里快速回答：

- 成功了吗
- 数据在哪
- 类型稳不稳
- 失败时怎么表现

如果这四句你能答出来，接口速查就很高效了。

## 📚 延伸阅读

- [02_JSON_YAML_TOML与配置文件.md](../02_terminal_shell_filesystem_and_environment/02_json_yaml_toml_and_configuration_files.md)
- [01_HTTP_请求_响应_状态码与接口设计.md](../06_backend_foundations_http_api_auth_and_services/01_http_requests_responses_status_codes_and_api_design.md)
