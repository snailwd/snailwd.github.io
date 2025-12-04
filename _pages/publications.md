---
title: "Publications"
permalink: /publications/
layout: archive
author_profile: true
---

<style>
  .pub-title-link {
    color: #000;
    text-decoration: none;
    border-bottom: 2px solid #007acc;
    transition: all 0.2s ease;
    display: inline-block;
    margin-bottom: 8px;
  }
  .pub-title-link:hover {
    color: #007acc;
    border-bottom-color: #0056b3;
    transform: translateY(-1px);
  }
  .pub-title-link::after {
    content: "↗";
    font-size: 0.8em;
    margin-left: 5px;
    opacity: 0.7;
  }
</style>

{% assign pubs = site.publications | sort: 'date' | reverse %}
{% for pub in pubs %}
  <div class="list__item" style="margin-bottom: 40px; padding-bottom: 30px; border-bottom: 1px solid #eee;">
    
    {% if pub.image %}
      <div style="width: 100%; height: 200px; overflow: hidden; border-radius: 4px; margin-bottom: 15px;">
        <img src="{{ pub.image | relative_url }}" alt="{{ pub.title }}" style="width: 100%; height: 100%; object-fit: cover;">
      </div>
    {% endif %}
    
    <h2 class="archive__item-title" style="margin-bottom: 10px;">
      <a href="{{ pub.external_url }}" target="_blank" class="pub-title-link">{{ pub.title }}</a>
    </h2>
    
    <div style="font-size: 0.9em; color: #666; margin-bottom: 10px;">
      <strong>{{ pub.venue }}</strong> • {{ pub.date | date: "%B %Y" }}
    </div>
    
    <div class="archive__item-excerpt" style="margin-bottom: 15px;">
      {{ pub.excerpt | markdownify }}
    </div>
    
  </div>
{% endfor %}