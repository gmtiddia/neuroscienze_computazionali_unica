---
permalink: /team/
title: "Membri"
author_profile: false
---

<div class="team-grid">

{% for m in site.data.members %}
{% unless m.alumni %}

<div class="team-card">

  <img src="{{ m.photo | relative_url }}"
       alt="{{ m.name }}"
       class="team-photo">

  <h3>{{ m.name }}</h3>

  <p class="team-role">{{ m.role }}</p>

  <p class="team-bio">{{ m.bio }}</p>

  {% if m.orcid %}
  <a href="https://orcid.org/{{ m.orcid }}"
     target="_blank"
     class="team-orcid">ORCID</a>
  {% endif %}

</div>

{% endunless %}
{% endfor %}

</div>
