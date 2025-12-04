{% for pub in site.publications %}
  <div class="list__item">
    <div class="archive__item">
      {% if pub.image %}
        <div class="archive__item-teaser">
          <img src="{{ pub.image }}" alt="{{ pub.title }}">
        </div>
      {% endif %}
      <h2 class="archive__item-title">{{ pub.title }}</h2>
      <div class="archive__item-excerpt">
        <p>{{ pub.excerpt | markdownify | strip_html | truncatewords: 30 }}</p>
      </div>
      {% if pub.url %}  <!-- 统一判断 url 字段 -->
        <a href="{{ pub.url }}" class="btn btn--primary" target="_blank">View Paper</a>
      {% endif %}
      <a href="{{ pub.url | relative_url }}" class="btn">Details</a>
    </div>
  </div>
{% endfor %}