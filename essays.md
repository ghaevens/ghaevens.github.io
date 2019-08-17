---
layout: default
---

<div class="row">
  {% assign sorted = (site.essays | sort: 'date') | reverse %}
  {% for essay in sorted | sort: "date" %}
    <div class="col-md-6 col-lg-4 mb-4">
      <div class="card">
        {% if essay.image %}
          <img class="card-img-top image-scale" src="{{ essay.image | relative_url }}" alt="{{ essay.title }}">
        {% endif %}
        <div class="card-body">
          <p class="card-text"><small class="text-muted">{{ essay.date | date: "%Y-%m-%d" }}</small></p>
          <h5 class="card-title">
            <a href="{{ essay.url | relative_url }}">{{ essay.title }}</a>
          </h5>
          <!--p class="card-text">{{ essay.excerpt }}</p-->
          <p class="card-text"><small class="text-muted">{{ essay.tags | camelcase }}</small></p>
        </div>
      </div>
    </div>
  {% endfor %}
</div>
