---
layout: single
title: "Events"
permalink: /events/
---

---
{% assign events = site.events | sort: 'date' %}
{% for event in events %}
  <div class="feature__wrapper">
    <div class="feature__item">  
      <div class="archive__item --left">
        <div class="archive__item-teaser">
          {% if event.image %}
            <img src="{{ event.image | relative_url }}" alt="{{ event.title }}">
          {% else %}
            <img src="https://placehold.co/256?text=256x256+{{ event.title | url_encode }}" alt="{{ event.title }}">
          {% endif %}
          <small> {{ event.eventdate }} </small>
        </div>
        <div class="archive__item-body">
          <h2 class="archive__item-title no-toc">{{ event.title }}</h2> <p> {{ event.location }} </p>
          <div class="archive__item-excerpt">
            {{ event.content }}
          </div>
        </div>
      </div>
    </div>
  </div>
{% endfor %}
