---
layout: single
title: "Vehicles"
permalink: /vehicles/
---

---
{% assign vehicles = site.vehicles | sort: 'from' %}
{% for vehicle in vehicles %}
  <div class="feature__wrapper">
    <div class="feature__item{% cycle '--left', '--right' %}">
      <div class="archive__item">
        <div class="archive__item-teaser">
          {% if vehicle.image %}
            <img src="{{ vehicle.image | relative_url }}" alt="{{ vehicle.title }}">
          {% else %}
            <img src="https://placehold.co/256?text=256x256+{{ vehicle.title | url_encode }}" alt="{{ vehicle.title }}">
          {% endif %}
        </div>
        <div class="archive__item-body">
          <h2 class="archive__item-title no-toc">{{ vehicle.title }}</h2> <small>{{ vehicle.from }} - {{ vehicle.until }}</small>
          <div class="archive__item-excerpt">
            {{ vehicle.content }}
          </div>
        </div>
      </div>
    </div>
  </div>
{% endfor %}
