---
title: "Publications"
permalink: /publications/
layout: archive
author_profile: true
---

{% assign pubs = site.publications | sort: 'date' | reverse %}
{% for pub in pubs %}
  <div class="list__item">
    <div class="archive__item">
      {% if pub.image %}
        <div class="archive__item-teaser">
          <img src="{{ pub.image | relative_url }}" alt="">
        </div>
      {% endif %}
      <h2 class="archive__item-title">{{ pub.title }}</h2>
      <div class="archive__item-excerpt">
        <p>{{ pub.excerpt | markdownify | strip_html | truncatewords: 30 }}</p>
      </div>
      <p>
        {% if pub.external_url %}
          <a href="{{ pub.external_url }}" class="btn btn--primary" target="_blank">View Paper</a>
        {% endif %}
        <a href="{{ pub.url | relative_url }}" class="btn">Details</a>
      </p>
    </div>
  </div>
{% endfor %}