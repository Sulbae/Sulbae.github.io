---
layout: default
title: Home
---

# Profil Seniman

Anggun Sulis Setyawan a.k.a Bang Suwan merupakan Entry-level Machine Learning Engineer.

---

# Koleksi
## Karya 1

{% for project in site.projects %}
- **[{{ project.title }}]({{ project.url }})**
  {{ project.summary }}
{% endfor %}
