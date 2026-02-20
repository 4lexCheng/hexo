---
title: SEO优化
abbrlink: c0d13edc
date: 2025-10-30 23:22:23
description: Hexo 博客 SEO 基础优化清单：链接、搜索、站点地图与发布检查。
tags:
  - Hexo
  - SEO
  - 优化
categories:
  - 建站指南
---

{% note primary %}
这篇记录 Hexo 最实用的 SEO 基础配置，优先做“低成本、高收益”的优化项。
{% endnote %}

## 1. 参考资料

- 视频参考：<https://www.bilibili.com/video/BV1oY4y1c7p2>
- Hexo 官方文档：<https://hexo.io/docs/>

## 2. 优化文章链接（推荐）

目标：让文章链接更短、更稳定，便于分享和收录。

### 2.1 安装插件

```bash
npm install hexo-abbrlink --save
```

插件地址：<https://github.com/ohroy/hexo-abbrlink>

### 2.2 配置站点

在 `_config.yml` 中添加（或确认）以下配置：

```yaml
permalink: posts/:abbrlink.html
abbrlink:
  alg: crc32
  rep: hex
```

## 3. 开启本地搜索

目标：提高站内检索体验，也方便搜索引擎抓取结构化内容。

### 3.1 安装插件

```bash
npm install hexo-generator-search --save
```

插件地址：<https://github.com/wzpan/hexo-generator-search>

### 3.2 配置站点

在 `_config.yml` 中添加：

```yaml
search:
  path: search.xml
  field: all
  content: true
```

## 4. 开启站点地图

目标：帮助搜索引擎更高效发现你的页面。

```bash
npm install hexo-generator-sitemap --save
npm install hexo-generator-baidu-sitemap --save
```

生成后通常会出现：

- `sitemap.xml`
- `baidusitemap.xml`

## 5. 发布前检查清单

- `url` 已设置为线上地址（例如 `https://4lexcheng.github.io/`）
- `permalink` 与 `abbrlink` 配置已生效
- `search.xml`、`sitemap.xml` 可正常生成
- 新文章包含明确标题、描述、标签、分类

发布命令：

```bash
hexo clean
hexo generate
hexo deploy
```

{% note success %}
先把这 5 项做完，已经能覆盖大多数个人博客的 SEO 基础需求。
{% endnote %}
