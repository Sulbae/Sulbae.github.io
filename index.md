---
layout: default
title: Pameran Pribadi
---

# Salam kenal, I'm Suwan

Entry-level Machine Learning Engineer with a background in Environmental Science.

---

## Koleksi

{% for project in site.projects %}
- **[{{ project.title }}]({{ project.url }})**
  {{ project.summary }}
{% endfor %}
