---
layout: home
title: Home
---

# Selamat Datang
🥳 Hi, People! 

Yang teman-teman lihat saat ini adalah ruang pameran pribadi tanpa batas yang menampung berbagai ekspresi seniman dalam menyalurkan ide-ide kreatif. Perjuangan melawan overthinking dalam kehidupan sehari-hari telah menginspirasi seniman untuk menciptakan ruang ini. Lebih dari itu, melalui platform ini, seniman juga berharap dapat memberikan inspirasi tanpa batas kepada siapapun yang mengunjunginya. 

Ayo scroll ke bawah dan eksplorasi berbagai koleksi karya di ruang ini! 👇

## Profil Seniman
<div class="profile">
Anggun Sulis Setyawan a.k.a Bang Suwan merupakan entry-level Machine Learning Engineer dengan latar belakang keilmuan Environmental Engineering. Ketertarikannya berada pada persimpangan antara data, sistem, dan cara manusia memahami serta memanfaatkan informasi dalam konteks nyata.

Dalam proses berkarya, seniman tidak sekadar memandang setiap proyek sebagai implementasi teknis, melainkan juga ruang eksplorasi intelektual. Diawali dengan perumusan masalah, dilanjutkan dengan pemahaman data, pengambilan keputusan desain solusi, hingga evaluasi dan refleksi pasca-implementasi. Pendekatan ini membentuk pola belajar yang iteratif, kritis, dan beorientasi pada pemahaman mendalam terhadap setiap permasalahan yang diangkat.

Karya-karya yang didokumentasikan dan ditampilkan pada ruang ini tidak hanya merepresentasikan hasil akhir, tetapi juga menampilkan proses berpikir di baliknya. Melalui ruang ini, seniman ingin berbagi wawasan, membuka ruang diskusi, serta mendorong pembelajaran yang berkelanjutan.
</div>

`#masihbelajar` `#terusbelajar` `#salingbelajar`

## Ruang Ide-ide Aja
### Koleksi 1
{% assign featured_projects = site.projects
  | where_exp: "project", "project.draft != true"
  | sort: "date"
  | reverse
%}

{% for project in featured_projects limit: 6%}
  {% assign title = project.title | default: "Untitled Project" %}
  {% assign url = project.url | default: "#" %}
  {% assign summary = project.summary | default: "No description available." | truncate: 160 %}

{% if project.image %}
  <img src="{{ project.image | relative_url }}" 
       alt="{{ project.title | escape }}" 
       width="100%" 
       style="border-radius: 8px; margin: 8px 0;"
       loading="lazy">
{% endif %}

- **[{% if project.external_url %}{{ title }}{% else %}{{ title }}{% endif %}]({% if project.external_url %}{{ project.external_url }}{% else %}{{ url }}{% endif %})**{% if project.tags %} `{{ project.tags | join: "`, `" }}`{% endif %})

  {{ summary }}{% if project.date %} <small>• {{ project.date | date: "%b %Y" }}</small>{% endif %}
{% endfor %}

{% if fetured_projects.size > 6 %}
[→ Lihat semua](/projects)
{% endif %}
