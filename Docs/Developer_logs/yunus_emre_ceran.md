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

### 05.08.2026 - 02:35 (TR)
**Branch:** `feature/update-hero-content`

#### Yeni Başvuru Sayfası ve Google Apps Script Entegrasyonu
- `basvuru.html` sayfası oluşturuldu: Akranca tasarım diline ve marka rehberine tam uyumlu, ortalanmış (`max-w-[500px]`), 4 alanlı (Başvuru Türü, Ad Soyad, E-posta, LinkedIn) başvuru formu hazırlandı.
- Google Apps Script (`doPost`) entegrasyonu tamamlandı: Fetch API ve `URLSearchParams` kullanılarak CORS uyumlu form gönderimi, dinamik buton loading state (`Gönderiliyor...`) ve başarı/hata geri bildirim mesajları uygulandı.
- Sayfa yönlendirmeleri güncellendi: `index.html`, `hakkimizda.html` ve `pedagoglar.html` sayfalarındaki "Gönüllü Ol" ve "Uzman Olarak Katıl" CTA butonları `katil.html` yerine `basvuru.html` sayfasına yönlendirildi.

### 06.08.2026 - 01:35 (TR)
**Branch:** `feature/fix-form-submission-fields`

#### Form Entegrasyonu ve Parametre Eşleme
- `basvuru.html` sayfasındaki JavaScript form gönderim mantığı güncellendi: Seçilen rol ("Gönüllü" / "Uzman") string olarak ve isim `name` parametresi olarak Google Apps Script `doPost` fonksiyonunun beklediği şemayla (`role`, `name`, `email`, `linkedin`) birebir eşlendi.

#### Terminoloji ve Karakter Standardizasyonu
- Site genelinde yer alan "Pedagog" terimleri "Uzman" olarak güncellendi (`katilim-formu.html`, `pedagoglar.html`, `hakkimizda.html`, `README.md`).
- `iletisim.html` ve diğer sayfalardaki Türkçe karakter karmaşaları (I, i, ı, ü, ö, ş, ç) düzeltildi ve nav/footer bağlantıları standartlaştırıldı (`Uzmanlarımız`, `İletişim`, `Hakkımızda`, `Topluluğa Katıl`, vb.).


### 07.08.2026 - 22:52 (TR)
**Branch:** `feature/contact-form-apps-script`

#### İletişim Formu — Google Apps Script Entegrasyonu
- `iletisim.html` iletişim formuna Fetch API ile Google Apps Script `doPost` bağlantısı eklendi.
- Form gönderiminde `e.preventDefault()` ile sayfa yenilenmesi engellendi.
- Gönderim sırasında buton `disabled` yapılarak metni `"Gönderiliyor..."` olarak güncellendi; `finally` bloğu ile eski haline döndürüldü.
- Form alanları (`name`, `email`, `subject`, `message`) `URLSearchParams` ile toplandı, `POST` metodu ve `mode: 'no-cors'` (CORS kısıtlası aşmak için) ile gönderildi. KVKK onay kutusu sadece HTML doğrulamasında kullanıldı, backend'e gönderilmedi.
- Butonun altına `#form-feedback` div'i eklendi: başarıda yeşil, hatada kırmızı bildirim mesajı gösteriliyor.
- Başarılı gönderimde form `reset()` ile temizlendi ve karakter sayacı sıfırlandı.
- Google Apps Script endpoint URL'si `AKfycbypPza83s0RIzSEdX6_CGgBAEhXDl5Wo25FYUnsPGOO9adP1z5mVencRuhWmW8fSC-3Gw/exec` olarak güncellendi (yeni deployment).
