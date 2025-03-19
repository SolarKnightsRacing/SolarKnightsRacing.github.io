---
layout: single
title: "Vehicles"
permalink: /vehicles/
---

{% assign vehicles = site.vehicles | sort: 'acquisition_year' %}
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
          <h2 class="archive__item-title">{{ vehicle.title }}</h2>
          <h3 class="archive__item-subtitle">{{ vehicle.year_range }}</h3>
          <div class="archive__item-excerpt">
            {{ vehicle.content }}
          </div>
        </div>
      </div>
    </div>
  </div>
{% endfor %}
