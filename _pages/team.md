---
permalink: /team/
title: "Membri e contatti"
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

  <div class="team-links">
    {% if m.email %}
    <a href="mailto:{{ m.email }}"
       class="team-icon"
       aria-label="Email di {{ m.name }}"
       title="Email">
      <img src="{{ '/images/email.png' | relative_url }}" alt="" width="24" height="24">
    </a>
    {% endif %}

    {% if m.orcid %}
    <a href="https://orcid.org/{{ m.orcid }}"
       class="team-icon"
       target="_blank"
       rel="noopener"
       aria-label="Profilo ORCID di {{ m.name }}"
       title="ORCID">
      <img src="{{ '/images/orcid.svg' | relative_url }}" alt="" width="24" height="24">
    </a>
    {% endif %}
  </div>

</div>

{% endunless %}
{% endfor %}

</div>
