> 一句话版本：domain、DNS、build output 三者分别解决访问地址、地址指向和发布文件的问题。

---

## 这一节在讲什么

这一节把 domain、DNS 和 build output 放在同一张图里理解。你会知道为什么网站上线不仅是写完代码。

这三个概念经常一起出现，但职责不同。

## 概念解释

`domain` 是人类可读的网址，例如 `charliechanstudio.com`。

`DNS` 负责把 domain 指向正确的服务位置。

`build output` 是构建后的发布文件。对 Astro 这类项目来说，构建后通常会生成适合部署的静态文件或服务输出。

上线需要三件事配合：有文件可发布，有平台托管，有地址能找到平台。

## 现实例子

如果你有一个漂亮的网站，但没有部署，它只在本地电脑。

如果你部署了文件，但 domain 没指向正确位置，别人可能访问不到。

如果 domain 配对了，但 build output 错了，别人可能看到空页面或旧页面。

## Charlie 项目案例

Charlie 的 Astro 配置里设置了：

```js
site: "https://charliechanstudio.com"
```

这说明正式站点地址参与了项目配置。

根目录脚本负责构建和验证，Cloudflare 相关目录可能参与部署配置。学习时可以把它们放在一条线上：源代码 → build output → Cloudflare Pages → domain/DNS → 访问者浏览器。

## 小练习

1. 画出源代码到浏览器的 5 步流程。
2. 把 domain 和 DNS 分别写一句定义。
3. 写出 build output 为什么不是源代码本身。

## 检查问题

1. domain 是否等于服务器？
2. DNS 是否负责生成页面文件？
3. build output 错误会影响线上显示吗？

## 常见误解

常见误解是把 domain、DNS、hosting 混在一起。它们配合工作，但不是同一个东西。

另一个误解是部署成功就一定内容正确。构建内容和输出目录仍然需要检查。

## 记住这些

- domain 是地址。
- DNS 是地址指向。
- build output 是要发布的文件结果。
