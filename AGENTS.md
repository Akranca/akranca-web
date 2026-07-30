# AGENTS.md — Akranca Proje Kuralları

Bu dosya, bu repoda çalışan tüm AI ajanları için her zaman geçerli kuralları içerir. Görev akışı için `start.md` ve `end.md` kullanılır; bu dosya oturum akışından bağımsız olarak her durumda uygulanır.

## Dil

Kullanıcıyla Türkçe konuş. Kod, değişken adları, commit mesajları ve branch adları İngilizce olur.

## Güvenlik (istisnasız)

- API anahtarı, token, şifre, veritabanı bağlantı stringi veya `.env` içeriğini **asla** yazma, yazdırma, logla veya commit'leme.
- Bunları bir dosyada veya çıktıda görürsen kullanıcıya bildir, kendin taşıma veya kopyalama.
- Gerçek `.env` dosyaları repoya girmez. Yeni bir ortam değişkeni gerekiyorsa `.env.example` dosyasına adını ekle, değerini boş bırak.
- Kullanıcı verisi (isim, e-posta, telefon, konum) örnek veri olarak bile kullanılmaz; sahte ve açıkça uydurma değerler kullan.

## Git

- `main` branch'ine doğrudan push yapma, merge etme veya üzerinde çalışma. Tüm iş `feature/...` branch'lerinde yapılır.
- Kullanıcının kaydedilmemiş değişikliği varken `stash`, `reset`, `checkout` veya `clean` çalıştırma — önce sor.
- `git push --force` kullanma.

## Geri alınamaz işlemler

Şu işlemleri kullanıcı onayı almadan çalıştırma: dosya/klasör silme, veritabanı migration çalıştırma, deploy, bağımlılık sürümü yükseltme, üretim ortamına dokunan her komut. Önce ne yapacağını anlat, onay bekle.

## Mimari

Projenin tüm mimari kuralları `tech_spec.md` dosyasındadır. Mimariyi ilgilendiren bir iş yapmadan önce o dosyayı oku ve kurallarının dışına çıkma.

## Çalışma tarzı

- Emin olmadığın bir şeyi varsayma; sor.
- Kapsam dışına çıkma. Görevle ilgisi olmayan dosyaları "iyileştirmek" için değiştirme.
- Kod yazmadan önce ne yapacağını kısaca anlat.
- Marka renkleri, tipografi ve tonlar `marka.md` dosyasından alınır; göz kararı renk veya font kullanma.

## İnisiyatif sınırı

git commit, git push, log dosyası yazımı ve branch birleştirme işlemlerini
ASLA kendi inisiyatifinle yapma. Bu işlemler yalnızca sana o an açıkça
söylendiğinde yapılır. Kodlama bittiğinde durup beklemek doğru davranıştır.