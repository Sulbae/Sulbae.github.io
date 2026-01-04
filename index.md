---
layout: default
title: Home
---

# About
Hi, People! 
Yang teman-teman lihat saat ini adalah ruang pameran pribadi tanpa batas yang menampung berbagai ekspresi seniman dalam menyalurkan ide-ide kreatif. Perjuangan melawan overthinking dalam kehidupan sehari-hari telah menginspirasi seniman untuk menciptakan ruang ini. Lebih dari itu, melalui platform ini, seniman juga berharap mampu memberikan inspirasi tanpa batas kepada siapapun yang mampir. 

Ayo scroll ke bawah dan eksplorasi berbagai koleksi karya di ruang ini! 

# Profil Seniman

Anggun Sulis Setyawan a.k.a Bang Suwan merupakan Entry-level Machine Learning Engineer.

---

# Koleksi
## Karya 1

{% for project in site.projects %}
- **[{{ project.title }}]({{ project.url }})**
  {{ project.summary }}
{% endfor %}
