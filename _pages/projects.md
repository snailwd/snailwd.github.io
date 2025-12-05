---
title: "Projects"
permalink: /projects/
layout: archive
author_profile: true
---

{% for proj in site.portfolio %}
  <div class="list__item--project">
    <div class="project__content">
      <h2 class="archive__item-title">{{ proj.title }}</h2>
      <div class="archive__item-excerpt">
        <p>{{ proj.excerpt | markdownify | strip_html | truncatewords: 30 }}</p>
      </div>
      {% if proj.repo_url %}
        <!-- 有仓库链接：直接跳转 GitHub -->
        <a href="{{ proj.repo_url }}" class="btn btn--cv" target="_blank">View Project</a>
      {% else %}
        <!-- 无仓库链接：进入项目详情页 -->
         <a href="{{ proj.url | relative_url }}" class="btn btn--cv">View Project</a>
      {% endif %}
    </div>
    {% if proj.main_image %}
      <div class="project__image">
        <img src="{{ proj.main_image | relative_url }}" alt="{{ proj.title }}">
      </div>
    {% endif %}
  </div>
{% endfor %}