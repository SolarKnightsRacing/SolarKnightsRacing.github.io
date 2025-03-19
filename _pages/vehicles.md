---
permalink: /vehicles/
title: Vehicles
layout: single
classes: wide
---

{% assign sorted_vehicles = site.vehicles | sort: "from" %}
  
{% for vehicle in sorted_vehicles %}
<div class="vehicle-profile">
  <h1>{{ vehicle.name }}</h1>
  
  {% if vehicle.from %}
  <div class="vehicle-meta">
	<p> {{ vehicle.from }} - <p/>
	{% if vehicle.until %}
		<p> {{ vehicle.until }} </p>
	{% else %}
		<p> Now </p>
	{% endif %}
  </div>
  {% endif %}
  
  <div class="vehicle-content">
    {{ vehicle.exerpt }}
  </div>
</div>
{% endfor %}
