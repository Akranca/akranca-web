# AGENTS.md — Akranca AI Geliştirme ve Yerel Hafıza Kuralları

Bu dosya, Akranca projesinde çalışan tüm AI ajanları için bağlayıcı çalışma kurallarını tanımlar.

Bu dosya GitHub üzerinde tutulur ve projenin AI ajanlarına verilen kalıcı talimatların ana kaynağıdır.

AI ajanı hangi model, sağlayıcı, terminal, IDE veya oturum üzerinden çalışıyor olursa olsun, projede herhangi bir işlem yapmadan önce bu dosyadaki kurallara uymalıdır.

## 1. Ana Amaç

Akranca üzerinde çalışan AI ajanının temel amacı yalnızca kod yazmak değildir.

AI ajanı:

- Projenin mevcut durumunu anlamalıdır.
- Daha önce yapılan çalışmaları unutmamalıdır.
- Önceki kararları değiştirmemelidir.
- Başka bir AI ajanının yaptığı çalışmayı bozmamalıdır.
- Kullanıcının açıkça istemediği değişiklikleri yapmamalıdır.
- Her yeni görevden önce mevcut proje bağlamını yeniden oluşturmalıdır.
- Çalışma sırasında elde ettiği önemli bilgileri yerel AI hafızasına kaydetmelidir.
- Oturum, terminal veya context window değişse bile çalışmaya kaldığı yerden devam edebilmelidir.

AI ajanı hiçbir zaman yalnızca mevcut kullanıcı mesajına bakarak projede değişiklik yapmamalıdır.

## 2. Zorunlu Okuma Sırası

AI ajanı yeni bir görev aldığında kod yazmaya veya dosya değiştirmeye başlamadan önce aşağıdaki sırayı takip etmek zorundadır.

**Adım 1 — AGENTS.md**

Önce bu dosyayı tamamen okumalıdır.

Bu dosyadaki kurallar mevcut kullanıcı talimatlarından sonra gelen ek bağlam olarak değil, proje çalışma kuralları olarak kabul edilmelidir.

**Adım 2 — Yerel AI Hafızası**

Proje kökünde aşağıdaki klasör mevcutsa okunmalıdır:

```
.ai-memory/
```

Özellikle şu dosyalar okunmalıdır:

- `.ai-memory/PROJECT_STATE.md`
- `.ai-memory/CURRENT_TASK.md`
- `.ai-memory/WORK_LOG.md`
- `.ai-memory/DECISIONS.md`

Dosyalardan biri mevcut değilse AI ajanı bunu hata olarak değerlendirmemelidir.

Gerekli dosya mevcut değilse ve oluşturulması gerekiyorsa oluşturabilir.

**Adım 3 — Proje Dokümantasyonu**

Görevle ilgili mevcut dokümantasyon okunmalıdır.

Özellikle:

- `Docs/`
- `README.md`
- `tech_spec.md`
- `marka.md`

gibi dosyalar mevcutsa ve görevle ilgiliyse okunmalıdır.

Mimari bir değişiklik yapılacaksa `tech_spec.md` mutlaka okunmalıdır.

Tasarım, renk, tipografi veya marka ile ilgili değişiklik yapılacaksa `marka.md` mutlaka okunmalıdır.

**Adım 4 — Mevcut Kod ve Dosya Yapısı**

AI ajanı mevcut dosya yapısını kontrol etmelidir.

Görevle ilgili dosyalar incelenmeden yeni dosya veya yeni mimari oluşturulmamalıdır.

Önce mevcut yapının nasıl çalıştığı anlaşılmalıdır.

**Adım 5 — Git Durumu**

AI ajanı çalışmaya başlamadan önce mevcut Git durumunu kontrol etmelidir.

Özellikle:

```
git status
```

ile kullanıcı tarafından daha önce yapılmış ve henüz commit edilmemiş değişiklikler kontrol edilmelidir.

Kullanıcı tarafından yapılmış değişiklikler kesinlikle silinmemeli, geri alınmamalı veya üzerine yazılmamalıdır.

## 3. Yerel AI Hafıza Sistemi

Akranca projesinde AI ajanları için yerel bir hafıza sistemi kullanılır.

Bu hafıza GitHub'a gönderilmez.

Amaç:

- context limitinin dolması,
- terminalin kapanması,
- yeni terminal açılması,
- yeni AI oturumu başlatılması,
- farklı AI modeli kullanılması,
- önceki konuşmanın kaybolması,
- aynı bilgisayarda daha sonra projeye tekrar dönülmesi

durumlarında AI ajanının projede ne olduğunu ve en son ne yaptığını anlayabilmesini sağlamaktır.

## 4. Yerel Hafıza Klasörü

Proje kökünde aşağıdaki yapı kullanılmalıdır:

```
.ai-memory/
├── PROJECT_STATE.md
├── CURRENT_TASK.md
├── WORK_LOG.md
└── DECISIONS.md
```

Bu klasör yalnızca geliştiricinin kendi bilgisayarında bulunur.

GitHub'a gönderilmez.

## 5. PROJECT_STATE.md

`PROJECT_STATE.md` projenin genel ve güncel durumunu tutar.

Bu dosyada aşağıdaki bilgiler bulunmalıdır:

- Projenin amacı
- Mevcut mimari
- Kullanılan teknolojiler
- Önemli klasörler
- Önemli servisler
- Veritabanı yapısı
- API yapısı
- Frontend yapısı
- Backend yapısı
- Deployment yapısı
- Lokal ve production ortamları arasındaki farklar
- Şu anda çalışan sistemler
- Henüz tamamlanmamış sistemler
- Bilinen teknik problemler
- Önemli kısıtlamalar
- Daha önce alınmış önemli kararların kısa özeti

Bu dosya proje hakkında genel hafızadır.

Her görevden sonra gereksiz yere tamamen yeniden yazılmamalıdır.

Yalnızca proje durumunda gerçekten değişiklik olduğunda güncellenmelidir.

## 6. CURRENT_TASK.md

`CURRENT_TASK.md` o bilgisayarda AI ile şu anda üzerinde çalışılan görevin durumunu tutar.

Dosyada mümkün olduğunca şu bilgiler bulunmalıdır:

- Görev:
- Amaç:
- Başlangıç durumu:
- Yapılanlar:
- Şu anda yapılan işlem:
- Tamamlananlar:
- Devam edenler:
- Karşılaşılan sorunlar:
- Alınan kararlar:
- Değiştirilen dosyalar:
- Test durumu:
- Bir sonraki adım:

AI ajanı yeni bir görev aldığında önce bu dosyayı kontrol etmelidir.

Görev tamamlandığında dosya güncellenmelidir.

Yeni bir görev başladığında eski görev silinmemeli; tamamlandıysa `WORK_LOG.md` içerisine aktarılmalıdır.

## 7. WORK_LOG.md

`WORK_LOG.md`, AI ajanının bu bilgisayarda projede yaptığı çalışmaların kronolojik kaydıdır.

Her önemli çalışma tamamlandığında kısa bir kayıt eklenmelidir.

Örneğin:

```
[2026-08-15]

Görev:
Navbar responsive yapısı düzeltildi.

Değiştirilen dosyalar:
- index.html
- assets/css/style.css

Yapılanlar:
- Mobil menü düzeltildi.
- Desktop navbar korunmuştur.

Test:
- Desktop kontrol edildi.
- Mobile kontrol edildi.

Sonraki adım:
- Footer responsive kontrolü.
```

Kayıtlar gereksiz ayrıntılarla şişirilmemelidir.

Ancak gelecekte AI ajanının "daha önce ne yaptım?" sorusuna cevap verebilmesini sağlayacak kadar bilgi bulunmalıdır.

## 8. DECISIONS.md

`DECISIONS.md`, proje boyunca alınan önemli teknik ve tasarımsal kararları tutar.

Örneğin:

```
## Veritabanı

Prisma schema ana kaynak olarak kullanılacaktır.
Directus veritabanı şemasının sahibi değildir.

## Dosya depolama

Medya dosyaları R2 üzerinde tutulacaktır.
Veritabanında yalnızca medya URL'si tutulacaktır.

## Environment

Lokal ve production bağlantıları .env üzerinden yönetilecektir.
Kod içine environment'a özel URL yazılmayacaktır.
```

AI ajanı daha önce alınmış bir kararı değiştirmek isterse bunun nedenini belirtmelidir.

Önemli bir mimari karar değiştirilecekse kullanıcı onayı alınmalıdır.

## 9. Hafıza Dosyalarının Önceliği

Yerel hafıza dosyaları çok önemlidir ancak GitHub'daki gerçek proje dosyalarının yerine geçmez.

Öncelik sırası:

1. Kullanıcının mevcut açık talimatı
2. AGENTS.md
3. Gerçek proje kodu ve mevcut dosya yapısı
4. `tech_spec.md` ve proje dokümantasyonu
5. Git geçmişi ve mevcut repository durumu
6. Yerel AI hafızası

Yerel hafıza ile gerçek kod arasında çelişki varsa AI ajanı hafızaya körü körüne güvenmemelidir.

Önce gerçek proje durumunu kontrol etmelidir.

Hafıza eskiyse güncellenmelidir.

AI ajanı hiçbir zaman eski hafızaya dayanarak mevcut kod hakkında varsayım yapmamalıdır.

## 10. Her Görevden Önce Zorunlu Kontrol

Kullanıcı herhangi bir görev verdiğinde AI ajanı aşağıdaki mantığı uygulamalıdır:

```
Kullanıcı talebini anla
        ↓
AGENTS.md oku
        ↓
.ai-memory/ dosyalarını oku
        ↓
İlgili dokümantasyonu oku
        ↓
İlgili mevcut kodu incele
        ↓
git status kontrol et
        ↓
Mevcut durum ile hafızayı karşılaştır
        ↓
Görevin kapsamını belirle
        ↓
Kullanıcıya kısa planı bildir
        ↓
Gerekli değişiklikleri yap
        ↓
Test et
        ↓
Hafızayı güncelle
        ↓
Sonucu bildir
```

Bu sıra mümkün olduğunca korunmalıdır.

## 11. Kod Yazmadan Önce Anlama

AI ajanı doğrudan kod yazmaya başlamamalıdır.

Önce:

- ne istendiğini,
- mevcut sistemin nasıl çalıştığını,
- hangi dosyaların etkileneceğini,
- mevcut mimarinin ne olduğunu,
- daha önce alınmış kararları,
- mevcut değişiklikleri

anlamalıdır.

Belirsizlik varsa tahmin yapmak yerine kullanıcıya sormalıdır.

## 12. Çalışma Sırasında Hafızayı Güncelleme

AI ajanı yalnızca görevin sonunda hafızayı güncellememelidir.

Uzun süren veya birden fazla aşamadan oluşan görevlerde önemli aşamalar tamamlandıkça hafıza güncellenmelidir.

Özellikle şu durumlarda hafıza güncellenmelidir:

- önemli bir mimari karar alındığında,
- önemli bir dosya değiştirildiğinde,
- yeni bir sistem oluşturulduğunda,
- bir bug çözüldüğünde,
- test tamamlandığında,
- bir işlem başarısız olduğunda,
- görevin bir kısmı tamamlandığında,
- kullanıcı yeni bir gereksinim verdiğinde,
- çalışmanın devamı başka bir oturuma bırakılacaksa.

Amaç, AI ajanının context'i aniden kaybetmesi durumunda son güvenli durumun mümkün olduğunca güncel kalmasıdır.

## 13. Context Limit ve Oturum Kaybı

AI ajanının context window'u dolarsa veya oturum kapanırsa proje çalışması kaybolmamalıdır.

Bu nedenle önemli bilgiler yalnızca sohbet içinde tutulmamalıdır.

Aşağıdaki bilgiler mutlaka yerel dosyalara yazılmalıdır:

- ne yapılıyordu,
- neden yapılıyordu,
- ne tamamlandı,
- ne tamamlanmadı,
- hangi dosyalar değiştirildi,
- hangi kararlar alındı,
- hangi problem bulundu,
- hangi testler yapıldı,
- sıradaki adım nedir.

Yeni bir AI oturumu başladığında AI ajanı önce bu hafızayı okuyarak çalışmayı yeniden oluşturmalıdır.

## 14. Yeni Terminal / Yeni AI Oturumu

Yeni bir terminal veya yeni bir AI oturumu açılması, önceki çalışmanın unutulduğu anlamına gelmez.

AI ajanı:

1. Proje klasörüne girmeli.
2. AGENTS.md dosyasını okumalı.
3. `.ai-memory/` klasörünü kontrol etmeli.
4. `CURRENT_TASK.md` dosyasını okumalı.
5. `PROJECT_STATE.md` dosyasını okumalı.
6. Gerekirse `WORK_LOG.md` ve `DECISIONS.md` dosyalarını incelemeli.
7. Git durumunu kontrol etmeli.
8. Gerçek kod ile hafızadaki durumu karşılaştırmalı.
9. Son kaldığı noktadan devam etmelidir.

Önceki AI'ın yaptığı işi tekrar yapmamalıdır.

## 15. Başka Bir AI Ajanının Çalışmasını Bozma

Bir AI ajanı başka bir AI ajanının daha önce yaptığı çalışmayı silmemeli veya gereksiz yere değiştirmemelidir.

Önce mevcut kod incelenmelidir.

Aynı problem için daha önce uygulanmış bir çözüm varsa bunun neden uygulandığı araştırılmalıdır.

"Bu kod daha iyi yazılabilir" gerekçesi tek başına mevcut çalışan kodu değiştirmek için yeterli değildir.

Kapsam dışı refactor yapılmaz.

## 16. Görev Kapsamı

AI ajanı yalnızca kullanıcı tarafından istenen işi yapmalıdır.

Görevle ilgisi olmayan:

- refactor,
- dosya taşıma,
- yeniden isimlendirme,
- dependency değişikliği,
- tasarım değişikliği,
- mimari değişiklik,
- kod temizliği

kendiliğinden yapılmamalıdır.

Bir ek değişiklik teknik olarak gerekli görünüyorsa AI ajanı bunu kullanıcıya açıklamalıdır.

## 17. Belirsizlik

AI ajanı emin olmadığı bir şeyi gerçekmiş gibi kabul etmemelidir.

Örneğin:

- olmayan bir dosya varmış gibi davranmamalı,
- API endpoint'i uydurmamalı,
- database tablosu uydurmamalı,
- environment variable uydurmamalı,
- mevcut olmayan bir feature varmış gibi kabul etmemeli,
- hafızadaki eski bilgiyi güncel gerçek olarak kabul etmemeli.

Belirsizlik varsa:

1. mevcut kodu kontrol et,
2. dokümantasyonu kontrol et,
3. Git geçmişini kontrol et,
4. hâlâ belirsizse kullanıcıya sor.

## 18. Git Kuralları

`main` branch üzerinde doğrudan çalışma yapılmaz.

Yeni bir göreve başlanmadan önce çakışmaları (conflict) önlemek için kesinlikle şu sıra izlenmelidir: önce `main` branch'ine geçilmeli, `git pull origin main` komutuyla projenin en güncel sürümü çekilmeli ve ancak bu güncel kod üzerinden yeni `feature/...` branch'i açılmalıdır.

Yeni geliştirmeler için uygun bir feature branch kullanılmalıdır.

Örnek:

- `feature/login`
- `feature/api-auth`
- `feature/mobile-navbar`
- `fix/navbar-responsive`
- `fix/database-connection`

Kullanıcının kaydedilmemiş değişiklikleri varsa:

- `git stash`
- `git reset`
- `git checkout`
- `git clean`

gibi işlemler kullanıcı onayı olmadan kullanılmaz.

Kullanıcının mevcut çalışması hiçbir şekilde kaybedilmemelidir.

`git push --force` kullanılmaz.

## 19. Commit ve Push

AI ajanı kendi inisiyatifiyle:

- `git commit`
- `git push`
- `git merge`

yapmaz.

Kullanıcı açıkça istediğinde bu işlemleri gerçekleştirebilir.

Kodlama tamamlandıktan sonra AI ajanı durmalı ve kullanıcıdan sonraki Git işlemi için talimat beklemelidir.

## 20. Geri Alınamaz İşlemler

Aşağıdaki işlemler kullanıcı onayı olmadan yapılmaz:

- dosya silme,
- klasör silme,
- database migration,
- production database değişikliği,
- deploy,
- production ortamına müdahale,
- dependency major upgrade,
- veri silme,
- toplu dosya yeniden yapılandırması.

Önce yapılacak işlem açıklanmalı ve onay beklenmelidir.

## 21. Güvenlik

Aşağıdaki bilgiler hiçbir şekilde commit edilmez, loglanmaz veya AI hafızasına açık değer olarak yazılmaz:

- API key
- secret
- token
- password
- database password
- database connection string
- `.env` içeriği
- private credentials
- production secret

Gerçek `.env` dosyaları repository'ye gönderilmez.

Yeni bir environment variable gerekiyorsa yalnızca `.env.example` içine değişken adı eklenir ve değer boş bırakılır.

Örneğin:

```
DATABASE_URL=
R2_ACCESS_KEY=
R2_SECRET_KEY=
R2_BUCKET=
R2_ENDPOINT=
FCM_SERVER_KEY=
BASE_URL=
```

Gerçek değerler yalnızca lokal veya production environment içerisinde tutulur.

## 22. Yerel Hafıza Git'e Gönderilmez

`.ai-memory/` klasörü geliştiricinin lokal hafızasıdır.

Bu nedenle `.gitignore` içerisinde bulunmalıdır:

```
.ai-memory/
```

AI ajanı bu klasördeki dosyaları Git'e eklememelidir.

Özellikle `git add .` gibi komutlar kullanıldığında `.ai-memory/` dosyalarının yanlışlıkla commit'e girmediği kontrol edilmelidir.

## 23. Yerel Hafıza Proje Kaynağı Değildir

`.ai-memory/` yalnızca AI'ın çalışma hafızasıdır.

Gerçek kaynak:

- Source Code
- Database Schema
- Configuration
- Documentation
- Git History

olmaya devam eder.

AI ajanı hafızaya dayanarak gerçek kodu değiştirmemelidir.

Hafızadaki bilgi ile kod arasında fark varsa:

1. Gerçek proje durumunu esas al
2. → hafızayı düzelt
3. → sonra çalışmaya devam et

## 24. Tamamlanan Görevler

Bir görev tamamen tamamlandığında yapılması gereken 2 aşama vardır:

**Aşama 1: Yerel Hafızayı Güncelleme**

`CURRENT_TASK.md` güncellenmeli, `WORK_LOG.md` içerisine tamamlanan iş kaydedilmeli, gerekirse `PROJECT_STATE.md` ve `DECISIONS.md` güncellenmelidir.

**Aşama 2: Takım Hafızasını (Developer Logs) Güncelleme**

`.ai-memory/` klasörü GitHub'a gönderilmediği için, takımın repoda yapılan işleri görebilmesi adına AI ajanı otomatik olarak takım loglarını da güncellemelidir.

Bunun için `Docs/Developer_logs/<kullanici_adi>.md` dosyasını bulmalı (yoksa oluşturmalı) ve en altına şu formatta bir ekleme yapmalıdır:

- Günün tarihi
- Üzerinde çalışılan Branch adı
- Yapılan işin kısa, teknik ve maddeler halinde özeti

**Dikkat:** Bu log dosyası GitHub'a yükleneceği için içine kesinlikle API key, şifre veya gizli bir veri yazılmamalıdır.

## 25. Yarım Kalan Görevler

Bir görev tamamlanmadan oturum sona erecekse AI ajanı mümkün olduğunca önce hafızayı güncellemelidir.

Özellikle `CURRENT_TASK.md` içerisinde:

- Şu anda ne yapılıyordu?
- Ne tamamlandı?
- Ne tamamlanmadı?
- Hangi dosyalara dokunuldu?
- Herhangi bir hata var mı?
- Sonraki işlem tam olarak nedir?

sorularının cevabı bulunmalıdır.

Böylece başka bir AI ajanı hiçbir şey bilmeden görevi devraldığında kaldığı yerden devam edebilir.

## 26. Hafıza Güncelleme Kuralı

AI ajanı hafızayı gereksiz şekilde büyütmemelidir.

Hafızaya yalnızca gelecekte tekrar ihtiyaç duyulabilecek bilgiler yazılmalıdır.

Özellikle:

- kalıcı teknik kararlar,
- proje mimarisi,
- tamamlanan önemli işler,
- devam eden işler,
- bilinen problemler,
- önemli kısıtlamalar,
- sonraki adımlar

saklanmalıdır.

Her terminal komutu veya her küçük değişiklik ayrı ayrı kaydedilmemelidir.

## 27. Proje Mimarisi ve Teknik Kaynaklar (Single Source of Truth)

Projenin mimarisi, kullanılan frameworkler ve altyapı teknolojileri bu dosyada yazmaz.

AI ajanı, sistemin nasıl çalıştığını öğrenmek ve kod yazmak için kesinlikle şu dosyaları temel kaynak kabul etmelidir:

- `Docs/tech_spec.md`: Tüm backend, mobil, database ve medya depolama (storage) kuralları buradadır.
- `Docs/prd.md`: Uygulamanın etkileşim sınırları ve felsefesi buradadır.

Bu bilgiler ile yerel hafıza çelişirse, her zaman güncel dokümantasyon dosyaları kazanır.

## 28. Veritabanı Kuralı

Veritabanı şemasının ana kaynağı yazılan koddur (ORM vb.). Admin panelleri veya harici arayüzler şemanın sahibi değildir. Database migration (göç) veya şema değişikliği yapılmadan önce mutlaka kullanıcı onayı alınmalıdır.

## 29. Local ve Production Ortamları

Lokal ve production ortamları birbirinden ayrıdır. Kod içerisine kesinlikle environment'a (ortama) özel sabit URL veya şifre (hardcoded) yazılmamalıdır. Tüm bağlantılar `.env` değişkenleri üzerinden yönetilmelidir.

## 30. API ve Endpoint Kuralları

API endpoint'leri ve medya dosyalarının nasıl aktarılacağı (storage kuralları) `tech_spec.md` içerisindeki tanımlara göre uygulanır. AI ajanı kafasına göre yeni bir endpoint uydurmamalı veya sunucunun üzerinden ağır dosya geçirmeye çalışmamalıdır. Gerekli görüyorsa kullanıcıya bildirmelidir.

## 31. Tasarım Kuralları

Marka renkleri, tipografi, görsel dil ve ton `Docs/marka.md` dosyasından alınır. AI ajanı kendi zevkine göre renk, font veya arayüz (UI) kuralları belirlememelidir.

## 33. Test

Kod değişikliğinden sonra mümkün olan uygun testler çalıştırılmalıdır.

Test çalıştırılamıyorsa neden çalıştırılamadığı belirtilmelidir.

AI ajanı test edilmemiş bir değişikliği test edilmiş gibi sunmamalıdır.

Sonuçta:

```
Test:
- Başarılı
```

veya

```
Test:
- Çalıştırılamadı: <neden>
```

şeklinde açık bilgi verilmelidir.

## 34. Görev Sonu Raporu

Bir görev tamamlandığında AI ajanı kullanıcıya kısa ve net şekilde şunları bildirmelidir:

- Ne yapıldı?
- Hangi dosyalar değiştirildi?
- Test edildi mi?
- Herhangi bir sorun kaldı mı?
- Sonraki mantıklı adım nedir?

Gereksiz uzun açıklamalar yapılmamalıdır.

## 35. En Önemli Kural

AI ajanı şu prensibi her zaman uygulamalıdır:

Önce anla, sonra değiştir.

Hiçbir AI ajanı "muhtemelen böyledir" diyerek proje üzerinde değişiklik yapmamalıdır.

Önce:

```
Oku
→ Kontrol et
→ Anla
→ Planla
→ Uygula
→ Test et
→ Hafızayı güncelle
```

## 36. AI Devralma Protokolü

Yeni bir AI ajanı projeye başladığında aşağıdaki soruların cevabını yerel hafızadan ve gerçek projeden çıkarmalıdır:

1. Bu proje nedir?
2. Projenin mevcut mimarisi nedir?
3. Şu anda hangi aşamadayız?
4. En son ne yapıldı?
5. Şu anda hangi görev devam ediyor?
6. Hangi dosyalar değiştirildi?
7. Daha önce hangi teknik kararlar alındı?
8. Bilinen problemler nelerdir?
9. Kullanıcının açık kısıtlamaları nelerdir?
10. Bir sonraki adım nedir?

Bu sorular cevaplanmadan AI ajanı büyük bir değişikliğe başlamamalıdır.

## 37. Son Kural — Hafıza Kaybını Önle

AI ajanının konuşma geçmişini hatırlaması garanti değildir.

Context window sınırlıdır. Terminal değişebilir. Model değişebilir. Oturum kapanabilir.

Bu nedenle proje için önemli bilgiler yalnızca sohbet içerisinde tutulmamalıdır.

Kalıcı olması gereken bilgiler dosyalara yazılmalıdır.

Özellikle devam eden görevler için `CURRENT_TASK.md` güncel tutulmalıdır.

AI ajanının görevi yalnızca kod yazmak değil, gerektiğinde sonraki AI ajanının çalışmayı güvenli şekilde devralabilmesini sağlamaktır.

## Kısa Çalışma Prensibi

Her görevde:

```
AGENTS.md
    ↓
.ai-memory/
    ↓
Dokümantasyon
    ↓
Mevcut kod
    ↓
Git status
    ↓
Anlama
    ↓
Kısa plan
    ↓
Kodlama
    ↓
Test
    ↓
Hafızayı güncelle
    ↓
Kullanıcıya raporla
```

Bu akış Akranca üzerinde çalışan tüm AI ajanları için standart çalışma yöntemidir.
