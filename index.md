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
      Yang teman-teman lihat saat ini adalah <strong>ruang pameran pribadi tanpa batas</strong> yang menampung berbagai ekspresi seniman dalam menyalurkan ide-ide kreatif. Perjuangan melawan <i>overthinking</i> dalam kehidupan sehari-hari telah menginspirasi seniman untuk menciptakan ruang ini. Lebih dari itu, melalui ruang ini, seniman juga berharap dapat memberikan inspirasi tanpa batas kepada siapapun yang mengunjunginya.
    </p>
    <p>Ayo eksplorasi berbagai koleksi karya di ruang ini! 👇</p>
</section>
  
<!-- Projects Section -->
<section id="projects" class="projects">
  <h2>Karya</h2>  
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
                <a href="{% if project.deck_url and project.deck_url != '' %}{{ project.deck_url }}{% else %}{{ project.url }}{% endif %}" target="_blank" rel="noopener noreferrer" itemprop="url">
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
                  {% assign clean_demo_url = project.demo_url | strip %}
                  {% if clean_demo_url != "" %}
                    <a href="{{ clean_demo_url }}" class="btn btn-primary" target="_blank">
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
        <strong>Anggun Sulis Setyawan</strong> a.k.a <strong>Bang Suwan</strong> atau lebih dikenal sebagai Mas Sul merupakan <i>Data Scientist</i> dengan latar belakang keilmuan <i>Environmental Engineering</i>. Ketertarikannya berada pada persimpangan antara <strong>data</strong>, <strong>sistem</strong>, dan cara manusia memahami serta memanfaatkan <strong>informasi</strong> dalam konteks nyata.
      </p>
      <p>
        Seniman terbiasa bekerja menggunakan beberapa alat seperti <strong>Excel/GSheet</strong>, <strong>Python</strong>, <strong>SQL</strong>, <strong>Looker Studio</strong>, dan <strong>Power BI</strong> serta didukung oleh <strong>AI tools (Claude, ChatGPT, Gemini)</strong> sebagai asistennya. Dalam proses berkarya, seniman tidak sekadar memandang setiap proyek sebagai implementasi teknis, melainkan juga ruang eksplorasi intelektual. Diawali dari perumusan masalah, dilanjutkan dengan pemahaman data dan pola, perancangan solusi, hingga evaluasi dan refleksi pasca-implementasi. Pendekatan ini membentuk pola belajar yang iteratif, kritis, dan berorientasi pada pemahaman mendalam terhadap setiap permasalahan yang dihadapi.
      </p>
      <p>
        Karya-karya yang didokumentasikan dan ditampilkan pada ruang ini tidak hanya merepresentasikan hasil akhir, tetapi juga menampilkan proses berpikir di baliknya. Melalui ruang ini, seniman ingin berbagi wawasan, membuka ruang diskusi, serta mendorong pembelajaran yang berkelanjutan. Seniman selalu terbuka untuk menyambut peluang kolaborasi pengembangan solusi berbasis data dengan berbagai pihak.
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
<!-- Kisah Section -->
<section id="kisah" class="kisah-section" aria-labelledby="kisah-heading">
  <div class="kisah-container">
    <header class="kisah-header">
      <span class="kisah-kicker">Kronologi Perjalanan</span>
      <h2 id="kisah-heading" class="kisah-title">Kisah ~</h2>
      <p class="kisah-intro">
        Rekam jejak kronologis seniman dari masa ke masa membawa diri seniman untuk terus tumbuh menjadi lebih baik.
      </p>
    </header>
    <!-- Alur Kisah -->
    <ol class="timeline-vertikal">
      <!-- Agu 2026 - Sekarang: Admin & Facilitator Bootcamp — Halotech Academy -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Agu 2026 - Sekarang</span>
            <span class="timeline-tag">Pengalaman Kerja/Proyek · Part Time</span>
          </div>
          <h3 class="timeline-heading">Admin &amp; Facilitator Bootcamp — Halotech Academy</h3>
          <p class="timeline-desc">
            Mengelola administrasi dan database peserta bootcamp Data Analyst menggunakan
            spreadsheet, mengatur jadwal kelas online (Google Classroom, Calendar, Zoom), menyiapkan
            bahan belajar (Canva, Google Classroom, Excel, DBeaver, Google Colab), menyusun laporan
            evaluasi harian/mingguan bersama mentor, serta mendampingi progres peserta lewat
            WhatsApp Group.
          </p>
        </article>
      </li>
      <!-- Feb 2025 - Mei 2025: Non-Class Mentor — DBSF Coding Camp 2025 for SMK -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Feb 2025 - Mei 2025</span>
            <span class="timeline-tag">Pengalaman Kerja/Proyek · Kontrak</span>
          </div>
          <h3 class="timeline-heading">Non-Class Mentor — DBSF Coding Camp 2025 for SMK</h3>
          <p class="timeline-desc">
            Membimbing peserta tingkat SMK terkait dasar-dasar machine learning dan soft-skill,
            serta berkolaborasi bersama mentor lain menyusun dan menyelenggarakan sesi berbagi
            santainya untuk mendukung perjalanan belajar peserta.
          </p>
        </article>
      </li>
      <!-- Agu 2019 - Mei 2025: Teknik Lingkungan — Universitas Diponegoro -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Agu 2019 - Mei 2025</span>
            <span class="timeline-tag">Pendidikan · Sarjana</span>
          </div>
          <h3 class="timeline-heading">Teknik Lingkungan — Universitas Diponegoro</h3>
          <p class="timeline-desc">
            Menyelesaikan studi Sarjana Teknik Lingkungan (IPK 3,74/4) dengan tugas akhir
            Perencanaan Pengelolaan Air Hujan dengan Penerapan Low Impact Development (LID) Pada
            DAS Bringin Kota Semarang.
          </p>
        </article>
      </li>
      <!-- Des 2024 - Sekarang: External Academy Code Reviewer — Dicoding Indonesia -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Des 2024 - Sekarang</span>
            <span class="timeline-tag">Pengalaman Kerja/Proyek · Freelance</span>
          </div>
          <h3 class="timeline-heading">External Academy Code Reviewer — Dicoding Indonesia</h3>
          <p class="timeline-desc">
            Memeriksa dan mengevaluasi tugas proyek siswa pelatihan Machine Learning dan Data
            Science sesuai kriteria serta praktik industri, sekaligus memberikan umpan balik yang
            terstruktur untuk meningkatkan keterampilan dan hasil belajar siswa.
          </p>
        </article>
      </li>
      <!-- Jul 2024 - Des 2024: Machine Learning — DBSF Coding Camp 2024 -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Jul 2024 - Des 2024</span>
            <span class="timeline-tag">Pengalaman Kerja/Proyek · Proyek Akhir</span>
          </div>
          <h3 class="timeline-heading">Machine Learning — DBSF Coding Camp 2024</h3>
          <p class="timeline-desc">
            Mengembangkan analisis sentimen NLP kepuasan pengguna aplikasi GoPay, klasifikasi
            gambar sampah kemasan minuman dengan transfer learning CNN, model regresi baseline
            densitas nutrisi makanan berbasis komposisi gizi, serta sistem rekomendasi makanan
            berbasis content-based dan collaborative filtering.
          </p>
        </article>
      </li>
      <!-- Feb 2024 - Jul 2024: Bangkit Academy 2024 (Google, GoTo, Traveloka) -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Feb 2024 - Jul 2024</span>
            <span class="timeline-tag">Pendidikan dan Pelatihan · Jalur Machine Learning</span>
          </div>
          <h3 class="timeline-heading">Bangkit Academy 2024 (Google, GoTo, Traveloka)</h3>
          <p class="timeline-desc">
            Mempelajari konsep dan penerapan AI untuk berbagai masalah machine learning melalui
            kelas Analisis Data dengan Python, Matematika untuk Sains Data, Machine Learning
            Specialization, dan TensorFlow Specialization, serta mengembangkan model klasifikasi
            gambar sampah domestik berbasis CNN pada Capstone Project bersama tim.
          </p>
        </article>
      </li>
      <!-- Jan 2024: 10 Besar dari 180 Peserta — Entredibles Academy (Fiksioner Indonesia) -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Jan 2024</span>
            <span class="timeline-tag">Pencapaian</span>
          </div>
          <h3 class="timeline-heading">10 Besar dari 180 Peserta — Entredibles Academy (Fiksioner Indonesia)</h3>
          <p class="timeline-desc">
            Meraih posisi 10 besar dari 180 peserta dalam program Entredibles Academy yang
            diselenggarakan oleh Fiksioner Indonesia.
          </p>
        </article>
      </li>
      <!-- Jun 2023 - Okt 2024: Data & Research — WCD Jawa Tengah -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Jun 2023 - Okt 2024</span>
            <span class="timeline-tag">Pengalaman Kerja/Proyek · Sukarelawan</span>
          </div>
          <h3 class="timeline-heading">Data &amp; Research — WCD Jawa Tengah</h3>
          <p class="timeline-desc">
            Mengelola dan merapikan database volunteer, mitra (komunitas/instansi), serta arsip
            dokumen World Clean Up Day Jawa Tengah menggunakan spreadsheet dan Google Drive, serta
            menjadi koordinator pengelolaan sampah pada upacara penyambutan mahasiswa baru
            Universitas Diponegoro 2024.
          </p>
        </article>
      </li>
      <!-- Mar 2023 - Jul 2023: Asisten — DLH Kota Salatiga -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Mar 2023 - Jul 2023</span>
            <span class="timeline-tag">Pengalaman Kerja/Proyek · Proyek Dosen</span>
          </div>
          <h3 class="timeline-heading">Asisten — DLH Kota Salatiga</h3>
          <p class="timeline-desc">
            Merekapitulasi dan mengolah data kondisi serta kegiatan pengelolaan lingkungan hidup
            Kota Salatiga tahun 2022, dan berkolaborasi dalam tim untuk menyusun laporan Informasi
            Kinerja Pengelolaan Lingkungan Hidup Kota Salatiga tahun 2022.
          </p>
        </article>
      </li>
      <!-- Okt 2022 - Des 2022: Marketing Officer — Harisenin.com -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Okt 2022 - Des 2022</span>
            <span class="timeline-tag">Pengalaman Kerja/Proyek · Magang</span>
          </div>
          <h3 class="timeline-heading">Marketing Officer — Harisenin.com</h3>
          <p class="timeline-desc">
            Melakukan riset calon partner kolaborasi dalam penulisan artikel serta menganalisis 3
            platform komunitas kompetitor untuk menyusun rekomendasi strategi pengembangan
            platform komunitas.
          </p>
        </article>
      </li>
      <!-- Agu 2022 - Des 2022: Wirausaha Muda Merdeka — LPIK ITB -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Agu 2022 - Des 2022</span>
            <span class="timeline-tag">Pendidikan dan Pelatihan · Kewirausahaan</span>
          </div>
          <h3 class="timeline-heading">Wirausaha Muda Merdeka — LPIK ITB</h3>
          <p class="timeline-desc">
            Berlatih menganalisis rencana bisnis startup EduTech dan memberikan rekomendasi
            pengembangan lanjutan, serta merancang ide bisnis Vendoraya sebagai platform agregator
            yang menghubungkan pelanggan dengan vendor konveksi lokal.
          </p>
        </article>
      </li>
      <!-- Jul 2022 - Sept 2022: Market Research & Analyst — Harisenin.com -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Jul 2022 - Sept 2022</span>
            <span class="timeline-tag">Pengalaman Kerja/Proyek · Magang</span>
          </div>
          <h3 class="timeline-heading">Market Research &amp; Analyst — Harisenin.com</h3>
          <p class="timeline-desc">
            Menyusun laporan analisis produk dan layanan 2 kompetitor, mengevaluasi formulir
            pendaftaran customer agar data yang dikumpulkan valid, serta membersihkan, mengolah,
            menganalisis, dan memvisualisasikan data menjadi dashboard karakteristik customer
            selama 6 bulan terakhir.
          </p>
        </article>
      </li>
      <!-- Feb 2022 - Jul 2022: Data Analytics, Product & Marketing — RevoU Academy -->
      <li class="timeline-item">
        <span class="timeline-marker" aria-hidden="true"></span>
        <article class="timeline-card">
          <div class="timeline-meta">
            <span class="timeline-period">Feb 2022 - Jul 2022</span>
            <span class="timeline-tag">Pendidikan dan Pelatihan · Studi Independen</span>
          </div>
          <h3 class="timeline-heading">Data Analytics, Product &amp; Marketing — RevoU Academy</h3>
          <p class="timeline-desc">
            Mengikuti pelatihan studi independen terkait pemahaman bisnis, pembersihan data,
            visualisasi data, pelaporan, serta studi kasus Product Management, Data Analytics,
            Digital Marketing, dan Sales Development—termasuk riset produk fitur GoFood pada
            aplikasi Gojek.
          </p>
        </article>
      </li>
    </ol>
  </div>
</section>
