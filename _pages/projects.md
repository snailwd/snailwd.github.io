---
title: "Projects"
permalink: /projects/
layout: archive
author_profile: true
---

{% for proj in site.projects %}
  <div class="list__item" style="clear: both; margin-bottom: 30px; min-height: 120px;">
    {% if proj.main_image %}
      <div style="float: left; width: 120px; height: 120px; margin-right: 20px; overflow: hidden; border-radius: 8px; box-shadow: 0 2px 4px rgba(68, 68, 68, 0.1);">
        <img src="{{ proj.main_image | relative_url }}" alt="{{ proj.title }}" style="width: 100%; height: 100%; object-fit: cover; display: block;">
      </div>
    {% endif %}
    <div style="margin-left: 140px;">
      <h2 class="archive__item-title" style="margin-top: 0;">{{ proj.title }}</h2>
      <div class="archive__item-excerpt">
        <p>{{ proj.excerpt | markdownify | strip_html | truncatewords: 25 }}</p>
      </div>
      <a href="{{ proj.url | relative_url }}" class="btn btn--small">View Project</a>
    </div>
  </div>
{% endfor %}