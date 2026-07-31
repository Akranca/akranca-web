
### 2026-07-31 16:11
**Branch:** feature/app-detail-page
**�zet:**
- Kullanicinin talebi �zerine t�m toplu tasarim ve metin g�ncellemeleri geri alindi (git reset --hard 43a717f).
- Repo, 'pedagoglar hero tasarimi' ve 'ana sayfadan anonim/g�venli rozeti kaldirma' islemlerinin yapildigi asamaya geri d�nd�r�ld�.
- Su an branch'te commit edilmeyi bekleyen yeni bir degisiklik bulunmamaktadir.

### 2026-08-01 01:17
**Branch:** feature/update-hero-content
**Özet:**
- index.html sayfasından 'Sessiz Kalmayın' (istatistik) bölümü silindi. 'Kimler İçin' (hedef kitle) bölümünün tasarımı yalınlaştırılarak metinler güncellendi. Hedef Kitle üst başlığının yanlarına dekoratif çizgiler eklendi. Ana sayfadaki 'sessizlikte büyür' metni daha yüksek kontrast için koyulaştırıldı.
- hakkimizda.html sayfasından 'Ekibimiz' bölümü tamamen çıkarıldı.
- Tüm HTML sayfalarının (Ana Sayfa, Hakkımızda, Pedagoglar, Uygulama, Katılım Formu) alt bilgisinde (footer) yer alan kurumsal metin güncellendi ("toplumsal dayanışma alanınız") ve taşmaması için kapsayıcı genişliği (max-w-md) artırıldı.
- pedagoglar.html sayfası için ssets/data/pedagoglar.json listesine entegrasyon mantığı eklendi. Veri çekildiğinde uzmanlar listelenecek, boş ise uyarı kartı çıkacak şekilde ayarlandı.
