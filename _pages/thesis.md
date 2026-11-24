---
permalink: /thesis/
title: "Tesi"
author_profile: false
---

{% assign levels = "dottorato,magistrale,triennale" | split: "," %}
{% assign titles = "Tesi di dottorato,Tesi magistrali,Tesi triennali" | split: "," %}

{% for level in levels %}
## {{ titles[forloop.index0] }}

{% assign items = site.data.theses | where: "level", level | sort: "year" | reverse %}
{% for t in items %}
- **{{ t.name }}** ({{ t.year }}){% if t.status == "in corso" %} *(in corso)*{% endif %}{% if t.title %}: *{{ t.title }}*{% endif %}{% if t.supervisor %}. Relatore: {{ t.supervisor }}{% endif %}{% if t.cosupervisor %}. Co-relatore: {{ t.cosupervisor }}{% endif %}{% if t.link != "" and t.link %} [[link]({{ t.link }})]{% endif %}
{% endfor %}
{% endfor %}
