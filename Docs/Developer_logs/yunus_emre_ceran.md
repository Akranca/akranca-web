## 2026-07-30 -- 22:54 (TR)

**Branch:** `feature/organize-stitch-files`

### Yapilan Degisiklikler

#### Navbar ve Footer Standardizasyonu (tum sayfalar)
- Tum HTML sayfalarinda navbar yapisi tek bir standarda oturtuldu (index, hakkimizda, pedagoglar, katilim-formu, uygulama, gizlilik-politikasi, kullanim-kosullari).
- Navbar: logo sol, nav linkleri orta, "Topluluga Katil" butonu sag; sayfa bazli aktif state (alt cizgi) eklendi.
- Mobil hamburger menu JS kodu her sayfaya eklendi; hidden/flex toggle mekanizmasi.
- Footer: tum sayfalarda 4 sutunlu yapi (Logo+aciklama, Kurumsal, Yasal, Iletisim) standart hale getirildi.
- Footer logo boyutu h-12 w-auto olarak sabitlendi; eski genislik kisitlayici wrapper'lar kaldirildi.

#### Yeni Sayfalar
- iletisim.html olusturuldu: 2 sutunlu iletisim formu (Ad Soyad, E-posta, Konu secici, Mesaj textarea, KVKK onayi), gercek zamanli dogrulama, basari animasyonu, karakter sayaci.
- katil.html olusturuldu: WhatsApp toplulugu yonlendirme sayfasi; hero bolumu, nabiz (pulse) animasyonlu WhatsApp butonu, 3 fayda karti, kim katilabilir bolumu.
- kullanim-kosullari.html olusturuldu: Gizlilik politikasindan klonlanan yasal sayfa.

#### Kimler Icin Bolumu Yeniden Tasarimi (index.html)
- Dis kaynakli fotograf arka planlar kaldirildi.
- Marka uyumlu 3 kart: Ogrenci (acik mavi zemin), Veli (kehribar zemin), Ogretmen (beyaz surface zemin).
- Her kartta: Material Symbols ikonu, kehribar rozet, baslik, aciklama, 3 madde listesi.
- Hover'da translateY(-4px) micro-animation eklendi.

#### Link Guncellemeleri
- Tum sayfalardaki "Bize Ulasin" linki # yerine iletisim.html olarak guncellendi (7 sayfa).
- Footer'daki Gizlilik Politikasi ve Kullanim Kosullari linkleri dogru sayfalara yonlendirildi.
- "Topluluga Katil" butonlari katil.html'e yonlendirildi.

#### Terminoloji
- Tum sayfalarda "Pedagoglar" terimi "Uzmanlarimiz" olarak guncellendi.

#### .gitignore Guncelleme
- Docs/Developer_logs/ satiri .gitignore'dan cikarildi; klasor artik git tarafindan takip ediliyor.

#### logo.svg Duzeltmesi
- width="1024px" -> width="100%" olarak degistirildi; Tailwind h-* siniflarinin SVG'yi dogru boyutlandirmasi saglandi.
### 31.07.2026 - 00:59
**Branch:** feature/footer-and-animations
- Tüm HTML sayfalarındaki (index.html, hakkimizda.html vb. toplam 9 dosya) footer bölümü baştan yazılarak tek tipleştirildi.
- Footer yapısı eski grid diziliminden çıkarılıp mobil ve tablet uyumlu, taşmaları (üst üste binmeleri) tamamen önleyen lex ve grid kombinasyonuyla (sağ tarafta grid-cols-2 sm:grid-cols-3) yeniden oluşturuldu.
- Tailwind config dosyalarındaki farklılıklardan kaynaklanan "görünmez metin" (boş footer) hatası engellendi; metin renkleri doğrudan Tailwind'in kalıcı 	ext-white utility sınıflarına bağlandı.
- Footer içindeki sosyal medya linklerine Instagram, X, YouTube ve LinkedIn SVG ikonları eklendi.
- Sayfalar arası geçişi yumuşatmak için CSS tabanlı global bir pageFadeIn animasyonu sisteme entegre edildi.
