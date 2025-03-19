---
permalink: /vehicles/
title: Vehicles
layout: single
classes: wide
---

<div class="vehicles-collection">
  {% assign sorted_vehicles = site.vehicles | sort: "from" %}
  
  {% for vehicle in sorted_vehicles %}
    <div class="vehicle-item {% cycle 'image-right', 'image-left' %}">
      <div class="vehicle-content">
        <h2 class="vehicle-name">{{ vehicle.name }}</h2>
        
        <div class="vehicle-years">
          {% if vehicle.from %}
            <span class="years-active">{{ vehicle.from }} - {% if vehicle.until %}{{ vehicle.until }}{% else %}Present{% endif %}</span>
          {% endif %}
        </div>
        
        <div class="vehicle-description">
          {% if vehicle.excerpt %}
            {{ vehicle.excerpt }}
          {% elsif vehicle.content %}
            {{ vehicle.content | strip_html | truncatewords: 50 }}
          {% endif %}
        </div>
        
        <a href="{{ vehicle.url }}" class="btn btn--primary">Read More</a>
      </div>
      
      <div class="vehicle-image">
        {% if vehicle.image %}
          <img src="{{ vehicle.image | relative_url }}" alt="{{ vehicle.name }}">
        {% else %}
          <img src="/assets/images/placeholder-vehicle.jpg" alt="{{ vehicle.name }}">
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>
