---
permalink: /eventos/
title: Conferências e outros eventos
---

<div id="main" role="main">

<h1>{{ page.title }}</h1>

<style type="text/css">
ul.events-list {
  list-style-type: none;
  padding-bottom: 2rem;
}
ul.events-list li.event-single {
  margin-left: 0;
  padding: 2rem 1rem;
  border-top: 1px solid #dddddd;
  display: flex;
  flex-direction: row;
  align-items: flex-start;
}
ul.events-list li.event-single .event-photo {
  flex-shrink: 0;
  padding-right: 2.5rem;
}
ul.events-list li.event-single .event-info h4 {
  margin-top: 0;
  margin-bottom: 0.25rem;
  font-size: 16px;
}
ul.events-list li.event-single .event-info div.event-info-details {
  margin-bottom: 1.5rem;
}
ul.events-list li.event-single .event-info div.event-info-details div.event-info-date {
  margin-bottom: 0rem;
}
ul.events-list li.event-single .event-info div.event-info-details div.event-info-location {
  margin-bottom: 0rem;
}
ul.events-list li.event-single .event-info p:last-of-type {
  margin-bottom: 0;
}
ul.events-list li.event-single:last-of-type {
  border-bottom: 1px solid #dddddd;
}
@media (max-width: 767px) {
  ul.events-list li.event-single {
    flex-direction: column;
  }
  ul.events-list li.event-single .event-photo {
    padding-right: 0;
  }
  ul.events-list li.event-single .event-info h4 {
    margin-top: 1.5rem;
  }
}
@media (max-width: 480px) {
  ul.events-list li.event-single .event-info h4 {
    font-size: 14px;
  }
  ul.events-list li.event-single .event-info p {
    font-size: 12px;
  }
}
</style>

<ul class="events-list">
  {% assign sorted = site.events | sort: "number" | reverse %}
  {% for e in sorted %}
    <li class="event-single">
      <div class="event-photo">
        {% if e.image %}
          <img src="{{e.image | relative_url }}" style="width: 200px;">
        {% else %}
          <div style="width: 200px; height: 200px;"></div>
        {% endif %}
      </div>
      <div class="event-info">
        <h4>
          <a href="{{e.link}}" target="_blank">{{e.title}}</a>
        </h4>
        {{e.date_string}}
        <p>
          {{ e.content | markdownify }}
        </p>
      </div>
    </li>
  {% endfor %}
</ul>

</div>

