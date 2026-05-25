> 📌 **一句话版本：** 数据建模不是技术细节，它本质上是在定义“系统如何理解业务实体、关系和规则”，字段设计好坏会直接影响产品能不能长期演进。

---

## 📖 这一节在讲什么

一个需求一旦进入系统，最终往往会变成“新增什么字段”“拆分什么表”“怎样表达关系”。这就是数据建模。它听起来很底层，但对产品设计影响极大。

## 🧠 什么叫数据建模

数据建模就是把业务世界里的对象和关系，翻译成系统可存储、可查询、可约束的数据结构。

例如：

- 用户
- 订单
- 项目
- 任务
- 评论

这些业务实体之间可能有一对一、一对多、多对多关系。

## 🎯 字段设计为什么重要

字段不只是“多一列少一列”，它会影响：

- 页面展示
- 接口结构
- 查询效率
- 权限规则
- 历史兼容性

## ⚠️ PM 常见的数据建模风险

- 一开始没想清实体边界，后面字段越堆越乱
- 把临时展示逻辑直接固化进数据结构
- 一个字段承担了多个语义
- 后期想改名、拆表、迁移时成本极高

## 🧩 为什么“字段看起来够用”往往还不够

因为字段一旦进入系统，它就不只是给当前页面用，还会被：

- 接口消费
- 数据库查询使用
- 报表统计使用
- 权限规则依赖
- 历史数据长期保留

也就是说，一个字段设计得模糊，后面会在多个地方同时制造摩擦。

## 🎯 PM 最值得练的一种能力：识别实体边界

很多建模问题的根源，不是技术实现，而是业务对象边界没想清楚。

例如：

- “任务”和“任务状态记录”是不是同一类东西
- “用户偏好”和“用户资料”是不是应当拆开
- “生成结果”和“生成任务历史”是不是应当分开存

只要边界没分清，后面字段就会越长越混乱。

> 🌐 **In English:**
> Good data modeling starts with clear entity boundaries. Without that, fields accumulate mixed meanings and long-term complexity grows fast.

## 💡 字段设计时值得提前问的几个问题

- 这个字段表达的是长期属性，还是临时状态
- 它会不会被多个模块同时依赖
- 它未来是否可能拆分
- 它是否兼具多个含义

这些问题很适合 PM 在需求阶段就先思考。

## ⚠️ 一个特别常见的坑：把展示逻辑写进数据结构

例如为了页面方便，直接加很多只为当前展示服务的字段。短期很顺，长期可能导致：

- 语义不清
- 重复数据
- 改一个页面却要动底层结构

所以数据结构最好优先表达业务事实，而不是只表达某一版页面长什么样。

> 🌐 **In English:**
> Data modeling translates business entities and relationships into system structures. Good field design improves clarity, maintainability, and future evolution.

## 📝 记住这些

- 数据建模本质上是在定义业务在系统中的表达方式。
- 字段设计会影响页面、接口、统计和后续迭代。
- PM 越早参与实体和字段讨论，后期返工越少。

## 📚 延伸阅读

- [00_SQL_数据库与查询基础.md](00_sql_databases_and_query_basics.md)
- [01_HTTP_请求_响应_状态码与接口设计.md](../06_backend_foundations_http_api_auth_and_services/01_http_requests_responses_status_codes_and_api_design.md)
- [15_完整实战案例_从PRD到上线/00_案例总览_一个功能如何从想法变成上线.md](../15_end_to_end_case_from_prd_to_launch/00_case_overview_how_a_feature_moves_from_idea_to_launch.md)
