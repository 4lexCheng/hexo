---
title: 安装音乐、追番页、Live2D看板娘
abbrlink: a99da82b
date: 2025-11-03 23:15:43
description: 为 Hexo 博客增加音乐页面、追番页面和 Live2D 看板娘的实用配置指南。
tags:
  - Hexo
  - Live2D
  - 页面增强
categories:
  - 建站指南
---

{% note primary %}
这篇文章聚焦博客“可玩性增强”：音乐页、追番页、Live2D。先保证能跑，再做美化。
{% endnote %}

## 1. Live2D 看板娘

插件仓库：<https://github.com/EYHN/hexo-helper-live2d>

### 1.1 安装依赖

```bash
npm install hexo-helper-live2d --save
npm install live2d-widget-model-koharu --save
```

### 1.2 站点配置

在根目录 `_config.yml` 添加：

```yaml
live2d:
  enable: true
  scriptFrom: local
  tagMode: false
  debug: false
  model:
    use: live2d-widget-model-koharu
  display:
    position: right
    width: 150
    height: 300
  mobile:
    show: true
```

### 1.3 验证效果

```bash
hexo clean
hexo generate
hexo server
```

访问 `http://localhost:4000/`，检查页面右下角是否出现看板娘。

## 2. 音乐页（建议方案）

可选做法：

- 方案 A：使用主题内置音乐页能力（优先，改动最小）
- 方案 B：使用 APlayer + Meting 手动嵌入

如果走方案 B，可先安装：

```bash
npm install hexo-tag-aplayer --save
```

然后在文章或页面中按插件语法插入播放器。

## 3. 追番页（建议方案）

常见做法是使用番剧页面插件，例如：

```bash
npm install hexo-bilibili-bangumi --save
```

安装后根据插件文档创建页面并填写数据源。

{% note info %}
追番页通常依赖第三方接口，首次配置建议先做最小可用版本，再逐步美化样式。
{% endnote %}

## 4. 故障排查

### 4.1 Live2D 不显示

- 确认 `live2d.enable: true`
- 确认模型包已安装
- 先执行 `hexo clean` 再 `hexo generate`
- 浏览器控制台查看是否有脚本加载错误

### 4.2 页面打开慢

- 降低 Live2D 模型尺寸
- 减少首页挂载的特效和第三方脚本
- 优先使用本地静态资源或稳定 CDN

## 5. 发布建议

每次新增插件后，建议执行：

```bash
hexo clean
hexo generate
hexo deploy
```

{% note success %}
这篇后续可以继续扩展成“博客功能增强合集”，统一维护所有插件配置。
{% endnote %}
