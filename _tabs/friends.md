---
layout: page
title: 友链
icon: fas fa-link
order: 4
description: 朋友们的博客与值得访问的网站
permalink: /friends/
---

<div class="mb-5">
  {% for friend in site.data.friends %}
    <div class="d-flex align-items-center gap-3 border rounded p-3 mb-3">
      {% if friend.avatar %}
        <img
          src="{{ friend.avatar }}"
          alt="{{ friend.name }} 的头像"
          class="rounded-circle flex-shrink-0"
          width="64"
          height="64"
          style="width: 4rem; height: 4rem; object-fit: cover;"
        >
      {% endif %}
      <div>
        <a
          href="{{ friend.link }}"
          class="fs-5 fw-semibold text-decoration-none"
          target="_blank"
          rel="noopener noreferrer"
        >
          {{- friend.name -}}
        </a>
        <p class="text-muted mb-0 mt-1">{{ friend.description }}</p>
      </div>
    </div>
  {% endfor %}
</div>

## 交换友链

如果你希望交换友链，可以通过侧边栏的邮箱联系我。申请时请附上网站名称、网站地址、一句话简介，以及头像或 Logo 地址。

## 本站信息

```yaml
- name: NaNExist的博客
  link: https://nanexist.github.io
  description: 专注于编程、科研与个人成长的博客，记录学习与探索的过程
  avatar: https://nanexist.github.io/icon.jpg
```
