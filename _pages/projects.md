---
title: "Projects"
permalink: /projects/
layout: archive
author_profile: true
---

{% for proj in site.projects %}
  <div class="list__item" style="margin-bottom: 40px; position: relative;">
    <div style="padding-right: 140px; min-height: 120px;">
      <h2 class="archive__item-title">{{ proj.title }}</h2>
      <div class="archive__item-excerpt">
        <p>{{ proj.excerpt | markdownify | strip_html | truncatewords: 30 }}</p>
      </div>
      {% if proj.repo_url %}
        <!-- 有仓库链接：直接跳转到 GitHub -->
        <a href="{{ proj.repo_url }}" class="btn btn--cv" target="_blank">View Project</a>
      {% else %}
        <!-- 无仓库链接：进入项目详情页 -->
         <a href="{{ proj.url | relative_url }}" class="btn btn--small">View Project</a>
      {% endif %}   
    </div>
    {% if proj.main_image %}
      <div style="position: absolute; top: 0; right: 0; width: 220px; height: 120px; overflow: hidden; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.15);">
        <img src="{{ proj.main_image | relative_url }}" alt="{{ proj.title }}" style="width: 100%; height: 100%; object-fit: cover; display: block;">
      </div>
    {% endif %}
  </div>
{% endfor %}