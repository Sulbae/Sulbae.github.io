---
layout: home
title: Home
---

<!-- Opening Section -->
<section class="opening">
  <h1>Selamat Datang 🥳</h1>
    <p>Hi, People!</p>
    <p>
      Yang teman-teman lihat saat ini adalah ruang pameran pribadi tanpa batas yang menampung berbagai ekspresi seniman dalam menyalurkan ide-ide kreatif. Perjuangan melawan overthinking dalam kehidupan sehari-hari telah menginspirasi seniman untuk menciptakan ruang ini. Lebih dari itu, melalui platform ini, seniman juga berharap dapat memberikan inspirasi tanpa batas kepada siapapun yang mengunjunginya.
    </p>
    <p>Ayo scroll ke bawah dan eksplorasi berbagai koleksi karya di ruang ini! 👇</p>

</section>

<!-- Profile Section -->
<section id="profile">
  <h2>Profil Seniman</h2>
  <div class="profile">
    <p>
      Anggun Sulis Setyawan a.k.a Bang Suwan merupakan entry-level Machine Learning Engineer dengan latar belakang keilmuan Environmental Engineering. Ketertarikannya berada pada persimpangan antara data, sistem, dan cara manusia memahami serta memanfaatkan informasi dalam konteks nyata.
    </p>
    <p>
      Dalam proses berkarya, seniman tidak sekadar memandang setiap proyek sebagai implementasi teknis, melainkan juga ruang eksplorasi intelektual. Diawali dengan perumusan masalah, dilanjutkan dengan pemahaman data, pengambilan keputusan desain solusi, hingga evaluasi dan refleksi pasca-implementasi. Pendekatan ini membentuk pola belajar yang iteratif, kritis, dan berorientasi pada pemahaman mendalam terhadap setiap permasalahan yang diangkat.
    </p>
    <p>
      Karya-karya yang didokumentasikan dan ditampilkan pada ruang ini tidak hanya merepresentasikan hasil akhir, tetapi juga menampilkan proses berpikir di baliknya. Melalui ruang ini, seniman ingin berbagi wawasan, membuka ruang diskusi, serta mendorong pembelajaran yang berkelanjutan.
    </p>
    <div class="hashtags">
      <code>#masihbelajar</code>
      <code>#terusbelajar</code> 
      <code>#salingbelajar</code>
    </div>
  </div>
  
  <!-- Projects Section -->
  <section id="projects">
    <h2>Ruang Ide-ide Aja</h2>
    <!-- Project Grid -->
    {% assign featured_projects = site.projects
      | where_exp: "project", "project.published != false"
      | sort: "date"
      | reverse
    %}
    <!-- Kontainer Projects -->
    <div class="projects-grid">
    {% for project in featured_projects limit: 10 %}
      <article class="project-card">
        <!--Thumbnail-->
        {% if project.image %}
        <div class="project-thumbnail">
          <img src="{{ project.image | relative_url }}" 
               alt="{{ project.image_alt | default: project.title | escape }}" 
               loading="lazy">
        </div>
        {% endif %}
        <!--Project Content-->
        <div class="project-content">
          <!--Project Header-->
          <div class="project-header">
            <h3 class="project-title">
              <a href="{% if project.external_url %}{{ project.external_url }}{% else %}{{ project.url }}{% endif %}"
                target="_blank" rel="noopener">
                {{ project.title }} 
              </a>
            </h3>
            <!--Tags-->
            {% if project.tags %}
            <div class="project-tags-inline">
              {% for tag in project.tags limit: 2 %}
              <span class="tag-badge">{{ tag }}</span>
              {% endfor %}
            </div>
            {% endif %}
          </div>
          <!--Project Summary-->
          <details class="project-summary">
            <summary class="summary-toggle">
              <!--Teks Preview-->
              <span class="summary-text">{{ project.summary | truncate: 200 }}</span>
              <span class="action-read">Baca Selengkapnya</span>
            </summary>
            <!--Full Summary-->
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
              <!--Tutup details saat tombol "Tutup" diklik-->
              <div class="close-wrapper">
                <span class="action-close" onclick="this.closest('details').removeAttribute('open')">
                  Tutup
                </span>
              </div>
            </div>
          </details>
        </div>
      </article>
    {% endfor %}
    </div>
  
  {% if featured_projects.size > 10 %}
  <div class="view-all">
    <a href="/projects" class="btn">→ Lihat Semua</a>
  </div>
  {% endif %}
  
</section>
