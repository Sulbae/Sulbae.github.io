---
layout: home
title: Home
description: Portfolio Machine Learning dan Data Science Anggun Sulis Setyawan - Kumpulan proyek/karya.
permalink: /
---

<!-- Opening Section -->
<section class="opening">
  <h1>Selamat Datang 🥳</h1>
    <p>Hi, People!</p>
    <p>
      Yang teman-teman lihat saat ini adalah <strong>ruang pameran pribadi tanpa batas</strong> yang menampung berbagai ekspresi seniman dalam menyalurkan ide-ide kreatif. Perjuangan melawan overthinking dalam kehidupan sehari-hari telah menginspirasi seniman untuk menciptakan ruang ini. Lebih dari itu, melalui platform ini, seniman juga berharap dapat memberikan inspirasi tanpa batas kepada siapapun yang mengunjunginya.
    </p>
    <p>Ayo eksplorasi berbagai koleksi karya di ruang ini! 👇</p>
</section>
  
<!-- Projects Section -->
<section id="projects" class="projects">
  <h2>Koleksi Karya</h2>  
  <!-- Project Grid -->
  {% assign featured_projects = site.projects
    | where_exp: "project", "project.published != false"
    | sort: "date"
    | reverse
  %}
  
  <!-- Kontainer Projects -->
  <div class="projects-grid-wrapper">
    <!-- Grid -->
    <div class="projects-grid" id="projectsGrid">
      {% for project in featured_projects limit: 10 %}
        <article class="project-card" data-index="{{ forloop.index0 }}" itemscope itemtype="https://schema.org/CreativeWork">
          <!--Thumbnail-->
          {% if project.image %}
          <div class="project-thumbnail">
            <img src="{{ project.image | relative_url }}" 
                 alt="{{ project.image_alt | default: 'Thumbnail proyek' | append: project.title | escape }}" 
                 loading="lazy"
                 itemprop="image">
          </div>
          {% endif %}
          <!--Project Content-->
          <div class="project-content">
            <!--Project Header-->
            <div class="project-header">
              <h3 class="project-title">
                <a href="{% if project.deck_url %}{{ project.deck_url }}{% else %}{{ project.url }}{% endif %}"
                  target="_blank" rel="noopener noreferrer"
                  itemprop="url">
                  {{ project.title }} 
                </a>
              </h3>
              <!--Tags-->
              {% if project.tags %}
              <div class="project-tags-inline" itemprop="keywords">
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
                <span class="summary-text" itemprop="description">{{ project.summary | truncate: 200 }}</span>
                <span class="action-read">Lihat</span>
              </summary>
              <!--Full Summary-->
              <div class="summary-content">
                <p>{{ project.summary }}</p>
                <div class="project-links">
                  {% if project.repo_url %}
                  <a href="{{ project.repo_url }}" class="btn btn-secondary" target="_blank">
                    Detail Karya
                  </a>
                  {% endif %}
                  {% if project.demo_url %}
                  <a href="{{ project.demo_url }}" class="btn btn-primary" target="_blank">
                    Demo App
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
  </div>

  <!-- Scroll Progress Dots -->
  <div class="scroll-progress-dots" id="scrollDots"></div>

  <!-- Scroll Navigation Buttons -->
  <div class="projects-nav">
    <button class="scroll-btn scroll-prev" aria-label="Geser kiri">
      <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3">
        <path d="M15 18l-6-6 6-6"/>
      </svg>
    </button>
    <button class="scroll-btn scroll-next" aria-label="Geser kanan">
      <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3">
        <path d="M9 18l6-6-6-6"/>
      </svg>
    </button>
  </div>

  {% if featured_projects.size > 10 %}
  <div class="view-all">
    <a href="/projects" class="btn">→ Lihat Semua</a>
  </div>
  {% endif %}
</section>

<!-- Profile Section -->
<section id="profile" class="profile">
  <h2>Profil Seniman ~</h2>
  <div class="profile-content">
    <!-- Kolom Teks -->
    <div class="profile-text">
      <p>
        <strong>Anggun Sulis Setyawan</strong> a.k.a <strong>Bang Suwan</strong> merupakan entry-level Machine Learning Engineer dengan latar belakang keilmuan Environmental Engineering. Ketertarikannya berada pada persimpangan antara <strong>data</strong>, <strong>sistem</strong>, dan cara manusia memahami serta memanfaatkan <strong>informasi</strong> dalam konteks nyata.
      </p>
      <p>
        Dalam proses berkarya, seniman tidak sekadar memandang setiap proyek sebagai implementasi teknis, melainkan juga ruang eksplorasi intelektual. Diawali dengan perumusan masalah, dilanjutkan dengan pemahaman data, pengambilan keputusan desain solusi, hingga evaluasi dan refleksi pasca-implementasi. Pendekatan ini membentuk pola belajar yang iteratif, kritis, dan berorientasi pada pemahaman mendalam terhadap setiap permasalahan yang diangkat.
      </p>
      <p>
        Karya-karya yang didokumentasikan dan ditampilkan pada ruang ini tidak hanya merepresentasikan hasil akhir, tetapi juga menampilkan proses berpikir di baliknya. Melalui ruang ini, seniman ingin berbagi wawasan, membuka ruang diskusi, serta mendorong pembelajaran yang berkelanjutan.
      </p>
      <!-- Hashtag -->
      <div class="hashtags">
        <code>#masihbelajar</code>
        <code>#terusbelajar</code> 
        <code>#salingbelajar</code>
      </div>
    </div>
    <!-- Kolom Foto -->
    <div class="profile-image">
      <img src="/assets/images/homepage/profile-picture.png"
        alt="Foto Profil"
        loading="lazy">
    </div>
  </div>
</section>
