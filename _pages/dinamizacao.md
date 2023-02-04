---
title: Dinamização
permalink: /dinamizacao/
---
<div id="main" role="main">

<h1>{{ page.title }}</h1>

<style type="text/css">
.team-members-page h3.team-member-group-title {
  font-weight: bold;
}
.team-members-page .team-member-group-affiliated {
  margin-top: 3rem;
}
ul.team-members-list {
  list-style-type: none;
  padding-bottom: 2rem;
}
ul.team-members-list li.team-member {
  margin-left: 0;
  padding: 1rem 1rem;
  border-top: 1px solid #dddddd;
  display: flex;
  flex-direction: row;
  align-items: flex-start;
}
ul.team-members-list li.team-member .team-member-photo {
  flex-shrink: 0;
  padding-right: 2.5rem;
}
ul.team-members-list li.team-member .team-member-bio h4 {
  margin-top: 0;
  margin-bottom: 1rem;
}
ul.team-members-list li.team-member .team-member-bio p:last-of-type {
  margin-bottom: 0;
}
ul.team-members-list li.team-member:last-of-type {
  border-bottom: 1px solid #dddddd;
}
@media (max-width: 767px) {
  ul.team-members-list li.team-member {
    flex-direction: column;
  }
  ul.team-members-list li.team-member .team-member-photo {
    padding-right: 0;
  }
  ul.team-members-list li.team-member .team-member-bio h4 {
    margin-top: 1.5rem;
  }
}
@media (max-width: 480px) {
  ul.team-members-list li.team-member .team-member-bio h4 {
    font-size: 14px;
  }
  ul.team-members-list li.team-member .team-member-bio p {
    font-size: 12px;
  }
}
</style>




<ul class="team-members-list">
  {% assign sorted = site.people | sort: "surname" %}
  {% for p in sorted %}
    <li class="team-member">
      <div class="team-member-photo">
        {% if p.image %}
          <img src="{{p.image | relative_url}}" alt="{{p.given_name}} {{p.surname}}" style="width: 200px;">
        {% else %}
          <div style="width: 200px; height: 200px;"></div>
        {% endif %}
      </div>
      <div class="team-member-bio">
        <h4>
          {%- if p.personal_webpage -%}
          <a href="{{p.personal_webpage}}" target="_blank">
            {{p.given_name}} {{p.surname}}</a>
          {%- else -%}
            {{p.given_name}} {{p.surname}}
          {%- endif -%}
          {%- if p.affiliation -%}
            , {{p.affiliation}}
          {%- endif -%}
        </h4>
        <p>
          {{ p.content | markdownify }}
        </p>
      </div>
    </li>
  {% endfor %}
</ul>
</div>
