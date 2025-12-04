---
title: "Projects"
permalink: /projects/
layout: archive
author_profile: true
---

{% for proj in site.projects %}
  <div class="list__item">
    <div class="archive__item">
      {% if proj.image %}
        <div class="archive__item-teaser">
          <img src="{{ proj.image }}" alt="">
        </div>
      {% endif %}
      <h2 class="archive__item-title">{{ proj.title }}</h2>
      <div class="archive__item-excerpt">
        <p>{{ proj.excerpt | markdownify | strip_html | truncatewords: 30 }}</p>
      </div>
      <a href="{{ proj.url }}" class="btn">View Project</a>
    </div>
  </div>
{% endfor %}