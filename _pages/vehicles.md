---
title: "Vehicle Collection"
layout: collection
permalink: /vehicles/
collection: vehicles
sort_by: from
sort_order: forward
---

<div class="vehicles-expanded-collection">
  {% assign sorted_vehicles = site.vehicles | sort: "from" %}
  
  {% for vehicle in sorted_vehicles %}
    <div class="vehicle-expanded-item {% cycle 'odd', 'even' %}">
      <h2 id="{{ vehicle.slug }}" class="vehicle-title">{{ vehicle.name }}</h2>
      
      <div class="vehicle-metadata">
        <span class="vehicle-years">{{ vehicle.from }} - {% if vehicle.until %}{{ vehicle.until }}{% else %}Present{% endif %}</span>
      </div>
      
      <div class="vehicle-content-wrapper">
        {% if forloop.index0 | modulo: 2 == 0 %}
          <div class="vehicle-image">
            {% if vehicle.image %}
              <img src="{{ vehicle.image | relative_url }}" alt="{{ vehicle.name }}">
            {% else %}
              <img src="/assets/images/placeholder-vehicle.jpg" alt="{{ vehicle.name }}">
            {% endif %}
          </div>
          <div class="vehicle-content">
            {{ vehicle.content }}
            <a href="{{ vehicle.url }}" class="btn btn--primary">More Details</a>
          </div>
        {% else %}
          <div class="vehicle-content">
            {{ vehicle.content }}
            <a href="{{ vehicle.url }}" class="btn btn--primary">More Details</a>
          </div>
          <div class="vehicle-image">
            {% if vehicle.image %}
              <img src="{{ vehicle.image | relative_url }}" alt="{{ vehicle.name }}">
            {% else %}
              <img src="/assets/images/placeholder-vehicle.jpg" alt="{{ vehicle.name }}">
            {% endif %}
          </div>
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>
