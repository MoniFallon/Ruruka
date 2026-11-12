# Ruruka

一个轻量的中文静态博客，使用 HTML、CSS、JavaScript 和无依赖 Node.js 构建脚本。

网站地址：**https://monifallon.github.io/Ruruka/**

## 功能

- 响应式首页、分类筛选与全文关键词搜索
- 独立文章页、关于页、404 页面
- 深浅色主题切换（偏好保存在浏览器本地）
- RSS、站点地图与基本 SEO 元数据
- 无第三方前端依赖、无追踪脚本、无数据库

当前三篇文章均为明确标注的建站示例，可替换为原创文章。

## 本地预览

需要 Node.js 20 或更新版本，无需安装 npm 依赖。

```bash
npm run build
npm run check
npm run preview
```

访问 http://127.0.0.1:4173/Ruruka/ 。

## 发布文章

编辑 `content/posts.json`，按现有格式添加文章：

- `slug`：唯一的英文小写、数字或短横线标识
- `title`、`summary`：标题与摘要
- `category`：分类；首页会自动生成分类按钮
- `date`：`YYYY-MM-DD`
- `art`：`sun`、`window` 或 `leaf`，也可扩展构建脚本加入新配图
- `sections`：正文段落，每段包含 `title` 与 `text`

示例标记在 `scripts/build.mjs` 的页面模板中。发布真实文章时请按实际情况调整示例提示。

修改后执行：

```bash
npm run build
npm run check
git add content assets scripts docs README.md package.json
git commit -m "docs: update blog content"
git push origin main
```

## GitHub Pages 部署

仓库 Settings → Pages：选择 **Deploy from a branch**，分支 **main**，目录 **/docs**。

`docs/` 是生成并提交的静态站点。推送其更新后，GitHub Pages 自动发布，无需服务器。
只修改 `content/` 或 `assets/` 不会自动重建页面，请先运行 `npm run build` 并提交生成结果。

## 目录

```text
content/posts.json  文章内容
assets/            样式与浏览器脚本
scripts/           构建、检查和本地预览工具
docs/              GitHub Pages 发布目录
```

## 许可证

暂未指定开源许可证。
