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
  | where_exp: "project", "project.published != false"
  | sort: "date"
  | reverse
%}

<div class="projects-grid">
{% for project in featured_projects limit: 10 %}
  <article class="project-card">
    {% if project.image %}
    <div class="project-tumbhnail">
      <img src="{{ project.image | relative_url }}" 
           alt="{{ project.image_alt | default: project.title | escape }}" 
           loading="lazy">
    </div>
    {% endif %}
    <div class="project-content">
      <h3 class="project-title">
        <a href="{% if project.external_url %}{{ project.external_url }}{% else %}{{ project.url }}{% endif %}"
          target="_blank" rel="noopener">
          {{ project.title }}
          {% if project.external_url %}{% endif %}
        </a>
      </h3>
      {% if project.tags %}
      <div class="project-tags">
        {% for tag in project.tags limit 3 %}
        <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
      <details class="project-summary">
        <summary class="summary-toggle">
          <span class="summary-text">{{ project.summary | truncate: 100 }}</span>
          <span class="read-more">Baca Selengkapnya</span>
        </summary>
        <div class="summary-content">
          <p>{{ project.summary }}</p>
          <div class="project-links">
            {% if project.repo_url %}
            <a href="{{ project.repo_url }}" class="btn btn-secondary" target="_blank">
              Source Code
            </a>
            {% endif %}
            {% if project.demo_url %}
            <a href="{{ project.demo_url }}" class="btn btn-primary" target="_blank">
              Demo
            </a>
            {% endif %}
          </div>
          <small class="project-date">{{ project.date | date: "%B %Y" }}</small>
        </div>
      </details>
    </div>
  </article>
{% endfor %}      
</div>  

{% if fetured_projects.size > 10 %}
<div class="view-all">
  <a href="/projects" class="btn btn-outline">→ Lihat Semua</a>
</div>
{% endif %}
