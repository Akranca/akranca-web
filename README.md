# Akranca Web

Akranca — akran zorbalığı hakkında farkındalık yaratan platform için tanıtım web sitesi.

## Sayfalar

| Dosya | Sayfa |
|---|---|
| `index.html` | Ana Sayfa |
| `hakkimizda.html` | Hakkımızda |
| `pedagoglar.html` | Pedagoglar |
| `uygulama.html` | Uygulama Detayları |
| `katilim-formu.html` | Katılım Formu |
| `gizlilik-politikasi.html` | Gizlilik Politikası |

## Klasör Yapısı

```
akranca-web/
├── *.html                  # Sayfa dosyaları
├── assets/
│   ├── css/                # Paylaşılan stiller (revize aşamasında doldurulacak)
│   └── screenshots/        # Stitch'ten gelen referans ekran görüntüleri
└── Docs/
    └── design/             # Design system belgeleri
        ├── design-system.md
        └── community-system.md
```

## Notlar

- Her HTML şu an bağımsız (inline stil). Revizyon aşamasında ortak `assets/css/style.css`'e taşınacak.
- Ekip içi belgeler (prd, tech_spec, marka vb.) `.gitignore` kapsamındadır.
