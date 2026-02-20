---
title: QA汇总
abbrlink: 49b95b18
date: 2025-10-28 23:44:11
description: Hexo 建站常见问题与快速处理方案。
tags:
  - Hexo
  - FAQ
  - 博客
categories:
  - 建站指南
---

{% note primary %}
这篇文章整理了 Hexo 博客最常见的问题，按「现象 -> 原因 -> 处理」给出快速方案。
{% endnote %}

## 1. 如何给文章设置标题？

新建文章后，在文件顶部填写 `Front Matter`：

```yaml
---
title: 这里是文章标题
date: 2024-01-15 14:30:00
tags:
  - 标签1
  - 标签2
categories:
  - 分类名称
---
```

`title` 会显示在文章页、首页列表和浏览器标题中。

## 2. 网站出现乱码怎么办？

最常见原因是文件编码不统一。

{% note warning %}
请确保 `source/_posts` 下所有 Markdown 文件，以及根目录的 `_config.yml` 都是 `UTF-8` 编码。
{% endnote %}

推荐排查顺序：

- 编辑器右下角确认编码为 `UTF-8`
- 重新保存乱码文件为 `UTF-8`
- 终端执行 `hexo clean && hexo g && hexo s` 再查看

## 3. 如何安装 Hexo 主题？

官方主题库：<https://hexo.io/themes/>

基础步骤：

```bash
# 1) 进入博客目录
cd blogfile

# 2) 下载主题（示例：butterfly）
git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly

# 3) 修改站点配置
# _config.yml
# theme: butterfly

# 4) 安装依赖（如主题文档要求）
npm install

# 5) 本地预览
hexo clean && hexo g && hexo s
```

## 4. 部署前快速自检

- `url` 是否配置为你的线上地址
- `deploy.repository` 是否指向 `用户名.github.io` 仓库
- `deploy.branch` 是否和 Pages 分支一致（常见为 `main`）
- 本地预览无报错后再执行部署

```bash
hexo clean
hexo g
hexo d
```

{% note success %}
如果部署成功但页面没更新，先等 1-3 分钟，再强制刷新浏览器缓存（Ctrl + F5）。
{% endnote %}
