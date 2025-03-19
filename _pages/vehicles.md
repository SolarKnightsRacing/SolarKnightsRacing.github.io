---
title: "Vehicles"
layout: single
permalink: /vehicles/
---

{% assign sorted_vehicles = site.vehicles | sort: "from" %}
  
{% for vehicle in sorted_vehicles %}
<h1> vehicle.name </h1>
<span>{{ vehicle.from }} - {% if vehicle.until %}{{ vehicle.until }}{% else %}Present{% endif %}</span>
{% if forloop.index0 | modulo: 2 == 0 %}
              <img src="{{ vehicle.image | relative_url }}" alt="{{ vehicle.name }}" width="300" height="300">{: .align-left}
            {{ vehicle.content }}
        {% else %}
            {{ vehicle.content }}
              <img src="{{ vehicle.image | relative_url }}" alt="{{ vehicle.name }}" width="300" height="300">{: .align-right}
        {% endif %}
  {% endfor %}
