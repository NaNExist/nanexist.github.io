---
layout: page
title: 友链
icon: fas fa-link
order: 4
description: 朋友们的博客与值得访问的网站
permalink: /friends/
---

<div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
  {% for friend in site.data.friends %}
    <div class="col">
      <a
        href="{{ friend.link }}"
        class="card h-100 text-decoration-none"
        target="_blank"
        rel="noopener noreferrer"
      >
        <div class="card-body d-flex align-items-center">
          {% if friend.avatar %}
            <img
              src="{{ friend.avatar }}"
              alt="{{ friend.name }} 的头像"
              class="rounded-circle flex-shrink-0 me-3"
              width="64"
              height="64"
              loading="lazy"
            >
          {% endif %}
          <div>
            <h2 class="h5 card-title mb-1">{{ friend.name }}</h2>
            <p class="card-text text-muted mb-0">{{ friend.description }}</p>
          </div>
        </div>
      </a>
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
