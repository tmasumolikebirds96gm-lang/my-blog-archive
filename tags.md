---
layout: page
title: Tags
permalink: /tags/
---

## 🏷️ 全タグ一覧

{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
  <h3>
    <a href="#{{ tag | first | slugify }}">#{{ tag | first }}</a>
    ({{ tag | last | size }})
  </h3>
  <a name="{{ tag | first | slugify }}"></a>
  <ul>
    {% for post in tag | last %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
{% endfor %}
