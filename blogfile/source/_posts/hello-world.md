---
title: Hello World
abbrlink: 4a17b156
date: 2025-09-29 23:44:37
description: Hexo 新站第一篇文章模板：快速上手写作、预览、生成与部署。
tags:
  - Hexo
  - 入门
categories:
  - 建站指南
---

{% note primary %}
这是 Hexo 默认首文的增强版，保留核心命令并补充了更清晰的上手流程。
{% endnote %}

## 1. 这篇文章能帮你做什么

- 新建一篇文章
- 本地预览站点
- 生成静态文件
- 一键部署到远端

## 2. 快速开始

### 2.1 新建文章

```bash
hexo new "我的第一篇文章"
```

更多说明：<https://hexo.io/docs/writing.html>

### 2.2 本地预览

```bash
hexo server
```

默认访问：`http://localhost:4000/`

更多说明：<https://hexo.io/docs/server.html>

### 2.3 生成静态文件

```bash
hexo generate
```

更多说明：<https://hexo.io/docs/generating.html>

### 2.4 部署到远端

```bash
hexo deploy
```

更多说明：<https://hexo.io/docs/one-command-deployment.html>

## 3. 常见问题

### 3.1 执行命令报错找不到 `hexo`

可用 `npx` 方式执行：

```bash
npx hexo server
npx hexo generate
npx hexo deploy
```

### 3.2 页面内容没更新

推荐按顺序执行：

```bash
hexo clean
hexo generate
hexo deploy
```

{% note success %}
后续你可以把这篇当作博客操作手册入口页，给新文章统一引用。
{% endnote %}
