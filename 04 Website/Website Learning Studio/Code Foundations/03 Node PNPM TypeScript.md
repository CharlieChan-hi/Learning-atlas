> 一句话版本：Node 提供 JavaScript 运行环境，pnpm 管理依赖和 workspace，TypeScript 给代码增加类型约束。

---

## 这一节在讲什么

这一节解释 Node、pnpm 和 TypeScript。你会知道它们在现代前端项目里分别扮演什么角色。

理解这些工具后，你看到项目配置时会少很多陌生感。

## 概念解释

`Node.js` 让 JavaScript 可以在浏览器之外运行。构建工具、脚本和本地开发服务器常常依赖 Node。

`pnpm` 是 package manager，也就是包管理器。它负责安装依赖、运行脚本、管理 workspace。

`TypeScript` 是 JavaScript 的类型增强版本。它帮助开发者在写代码时发现类型问题。

`workspace` 允许一个项目包含多个应用和包。Charlie 项目就是这种结构。

## 现实例子

如果网站项目像一个工作室，Node 是让工具运转的环境，pnpm 是仓库管理员，TypeScript 是检查表。

仓库管理员负责把工具放好，检查表帮助你在出错前发现问题。

## Charlie 项目案例

Charlie 根目录 `package.json` 指定：

```json
"packageManager": "pnpm@10.33.4",
"engines": {
  "node": ">=24 <26"
}
```

`pnpm-workspace.yaml` 指定：

```yaml
packages:
  - "apps/*"
  - "packages/*"
```

`apps/web/package.json` 和多个 `packages/*` 都使用 TypeScript 相关依赖或源码。这说明项目依赖 Node、pnpm 和 TypeScript 共同工作。

## 小练习

1. 写出 Node、pnpm、TypeScript 各自一句话定义。
2. 找出 Charlie 项目要求的 Node 版本范围。
3. 解释 workspace 为什么适合多应用项目。

## 检查问题

1. pnpm 是编程语言吗？
2. TypeScript 是否负责页面部署？
3. Node 版本不匹配可能导致什么问题？

## 常见误解

常见误解是把 Node、pnpm、TypeScript 混成一个东西。它们协作，但职责不同。

另一个误解是忽略版本。真实项目里版本会影响命令能否运行。

## 记住这些

- Node 是运行环境。
- pnpm 是包管理器。
- TypeScript 是类型系统。
- workspace 让多应用和多包一起管理。
