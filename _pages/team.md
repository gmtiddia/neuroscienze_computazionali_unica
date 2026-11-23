---
permalink: /team/
title: "Membri"
author_profile: false
---

{% for m in site.data.members %}{% unless m.alumni %}
### {{ m.name }}
*{{ m.role }}*

![{{ m.name }}]({{ m.photo | relative_url }}){: width="150"}

{{ m.bio }}
{% endunless %}{% endfor %}
