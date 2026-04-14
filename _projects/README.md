## 1. Copy template
`cp _projects/_default/project-template.md _projects/nama-proyek-baru.md`

## 2. Edit front matter & konten
- Ganti title, date, summary, tags
- Tambahkan image ke assets/images/projects/
- Isi body dengan markdown (problem, method, insight)

## 3. Optimasi gambar (opsional tapi recommended)
`python optimize_image.py raw-screenshot.png assets/images/projects/nama-proyek.webp`

## 4. Test lokal
`bundle exec jekyll serve`

## 5. Push & deploy
```
git add .
git commit -m "feat: add new project: Nama Proyek"
git push origin main
```
