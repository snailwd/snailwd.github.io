
---
title: "Projects"
permalink: /projects/
layout: archive
author_profile: true
---

{% for proj in site.projects %}
  <div class="archive__item">
    <div class="archive__item-body">
      <h2 class="archive__item-title">
        {% if proj.repo_url %}
        <!-- 有仓库链接：直接跳转到 GitHub -->
          <a href="{{ proj.repo_url }}" target="_blank">{{ proj.title }}</a>
        {% else %}
        <!-- 无仓库链接：进入项目详情页 -->
          <a href="{{ proj.url | relative_url }}">{{ proj.title }}</a>
        {% endif %}
      </h2>
      <div class="archive__item-excerpt">
        <p>{{ proj.excerpt | markdownify | strip_html | truncatewords: 30 }}</p>
      </div>
      {% if proj.repo_url %}
        <a href="{{ proj.repo_url }}" class="btn btn--primary" target="_blank">View Project</a>
      {% else %}
        <a href="{{ proj.url | relative_url }}" class="btn btn--primary">View Project</a>
      {% endif %}
    </div>
    {% if proj.main_image %}
      <div class="archive__item-teaser">
        <img src="{{ proj.main_image | relative_url }}" alt="{{ proj.title }}">
      </div>
    {% endif %}
  </div>
{% endfor %}