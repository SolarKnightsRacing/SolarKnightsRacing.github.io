---
permalink: /vehicles/
title: Vehicles
layout: single
classes: wide
---

{% assign sorted_vehicles = site.vehicles | sort: "from" %}
  
{% for vehicle in sorted_vehicles %}
  <h1>{{ vehicle.name }}</h1>
  
  {% if vehicle.from %}
	<p> {{ vehicle.from }} - <p/> {% if vehicle.until %} <p> {{ vehicle.until }} </p> {% else %} <p> Now </p> {% endif %}
  {% endif %}
  {{ vehicle.exerpt }}
{% endfor %}
