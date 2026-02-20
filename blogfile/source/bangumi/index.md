---
title: 追番窗口
date: 2026-02-20 16:30:00
type: page
top_img: false
aside: false
---

{% note primary %}
这是追番窗口页。数据由 `hexo-bilibili-bangumi` 生成，窗口内容来自 `/bangumis/`。
{% endnote %}

<div class="bangumi-frame-wrap">
  <iframe
    src="/bangumis/"
    title="追番窗口"
    loading="lazy"
    class="bangumi-frame">
  </iframe>
</div>

<div class="bangumi-empty-guide">
  <strong>如果窗口为空，请按下面步骤排查：</strong>
  <ol>
    <li>确认 B 站追番列表不是空，并且对外可见。</li>
    <li>确认站点配置中的 <code>bangumi.vmid</code> 已填写你的 UID。</li>
    <li>在博客目录执行：<code>hexo bangumi -u</code>。</li>
    <li>再执行：<code>hexo generate</code> 或 <code>hexo server</code>。</li>
  </ol>
</div>
