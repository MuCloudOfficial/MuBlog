# MuBlog 使用指南

这是一个基于 Hexo 的个人博客项目。

## 本地开发

```bash
pnpm install
pnpm server
```

## 常用命令

```bash
pnpm server                # 本地预览
pnpm clean                 # 清理缓存
pnpm build                 # 生成静态文件到 public/
npx hexo new "文章标题"     # 创建新文章
```

## 文章编写

文章路径：`source/_posts/`

推荐 Front-matter 字段：

```md
---
title: 文章标题
date: 2026-04-21 10:00:00
tags: [Hexo, 入门]
categories: [建站记录]
description: 一句话摘要
cover: /images/cover.png
---
```

## 已启用能力

- RSS：`/atom.xml`
- Sitemap：`/sitemap.xml`
- 分类页：`/categories`
- 标签页：`/tags`
- 关于页：`/about`
- Giscus 评论（需填写仓库参数）

## 主题分离与自定义

项目已切换到本地主题：`themes/landscape-custom`

- 站点主题配置文件：`themes/landscape-custom/_config.yml`
- 主题模板文件：`themes/landscape-custom/layout/`
- 主题样式文件：`themes/landscape-custom/source/css/`
- 主题增强样式层：`themes/landscape-custom/source/css/_custom.styl`
- 主题交互脚本：`themes/landscape-custom/source/js/script.js`

这样你后续改主题时不会受 `node_modules` 升级覆盖影响。

当前已内置一个深色模式开关（页面右上角月亮/太阳图标），并会记住用户选择。

## Giscus 配置

请在 `themes/landscape-custom/_config.yml` 的 `giscus` 段中填写真实值：

- `enable`：填完参数后改为 `true`
- `repo`：评论绑定的 GitHub 仓库，如 `owner/repo`
- `repo_id`：仓库 ID（从 giscus 配置页可获取）
- `category`：Discussion 分类名（通常 `Announcements`）
- `category_id`：分类 ID（从 giscus 配置页可获取）

配置页：<https://giscus.app/zh-CN>

## GitHub Pages 自动发布

已添加工作流文件：`.github/workflows/deploy-pages.yml`

使用前请确认：

1. 仓库默认分支是 `main`（如果不是，请修改工作流里的分支名）。
2. 在仓库 Settings -> Pages 中将 Source 设置为 **GitHub Actions**。
3. `_config.yml` 里的 `url` 已设置为你的线上访问域名。

完成后，每次 push 到 `main` 会自动构建并发布。

> 当前仓库采用 Actions-only 发布流程，不使用本地 `hexo deploy`。
