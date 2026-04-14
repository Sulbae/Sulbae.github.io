# Thumbnail proyek
```
assets/images/projects/
├── carbon-emission.webp     # Format WebP, <100KB, rasio 16:9
├── air-quality.webp
├── waste-cnn.webp
└── default.webp             # Fallback jika proyek tidak punya image
```

### Best Practice
| Aspek | Rekomendasi |
|-------|-------------|
| Format | WebP/AVIF (kompresi 30-50% lebih kecil dari PNG) |
| Ukuran | Max 1200x675px (16:9), <100Kb |
| Alt tex | Wajib diisi untuk aksesibilitas & SEO |

### Tools Konversi Image
```
from PIL import Image

def optimize_image(input_path, output_path, max_width=1200, quality=80):
    img = Image.open(input_path)
    # Resize jika terlalu besar
    if img.width > max_width:
        ratio = max_width / img.width
        img = img.resize((max_width, int(img.height * ratio)), Image.Resampling.LANCZOS)
    # Simpan sebagai WebP
    img.save(output_path, "WEBP", quality=quality, method=6)
```
