# Hüma

Üniversite öğrencileri için sohbet eden, kaynak gösteren yapay zekâ asistanı. Öğrencinin sorularını üniversitenin herkese açık sayfalarında ve yönetmeliklerinde arayıp cevabın hangi sayfaya dayandığını gösterir. Ders anlatır, eklenen fotoğraf ve PDF'leri okur.

Bağımsız bir öğrenci projesidir, herhangi bir üniversitenin resmî hizmeti değildir. Bu depo yalnız tanıtım içindir; kaynak kod gizlidir.

> **Hüma'ya git:** https://terminology-instant-guides-costumes.trycloudflare.com
>
> **Erişim:** Hüma herkese açık değildir. Yalnız Yusuf Baran Ozmakgil'den alınan şifre ile girilebilir.
>
> Deneme sürümüdür; geliştiricinin bilgisayarı kapalıyken açılmaz, adres zaman zaman değişebilir.

## Ekran görüntüleri

Görüntüler uygulamanın kendisinden alındı, cevaplar gerçek model cevaplarıdır. PDF örneği deneme amaçlı küçük bir nottur.

**Ders anlatımı**

![Türevi örnekle anlatan cevap](ekran/ders-anlatimi.webp)

**Fotoğraf ve PDF ekleme**

![Soru kutusuna eklenmiş PDF](ekran/dosya-ekleme.webp)

![PDF özeti ve düşen mesaj hakkı](ekran/pdf-ozeti.webp)

**Telefon, koyu tema**

<img src="ekran/telefon-koyu.webp" alt="Telefonda koyu temada cevap" width="320">

## Neler yapıyor

- Üniversite sorularını taranmış sayfalarda arar, kaynağını gösterir; kaynakta yoksa uydurmak yerine bulamadığını söyler
- Sohbet eder, ders anlatır, örnek çözer
- Fotoğraf ve PDF okur; PDF'in kelime sayısına göre daha çok mesaj hakkı düşer
- Bölüm, sınıf gibi notları sonraki sohbetlerde hatırlar
- Sohbetler ve dosyalar sunucuda saklanmaz

## Teknik özet

| Katman | Kullanılan |
|---|---|
| Veri toplama | Python, robots.txt kurallarına uyan tarayıcı |
| Arama | SQLite FTS5 kelime araması + e5-small anlam araması |
| Cevap | Claude Haiku 5.5, araç kullanımı, akarak yazım, kaynak atıfları |
| Sunucu | FastAPI |
| Arayüz | Çerçevesiz HTML, CSS ve JavaScript |
| Kalite | 171 otomatik test, 147 soruluk ölçüm seti, GitHub Actions |

## Ölçülen sonuçlar

147 soruluk test setiyle, 31 Ekim 2026:

| Ölçü | Sonuç |
|---|---|
| İlk kelimeye kadar süre (ortanca) | 1,24 sn |
| Soruların %90'ında ilk kelime | 1,83 sn içinde |
| Hakem puanı: doğru / kısmen / yanlış | 103 / 43 / 1 |

Puanlar başka bir yapay zekâ hakeminden gelir, bağımsız bir sınav değildir. Sorular geliştirme sırasında görüldü; gerçek kullanıcılarla ölçüm henüz yapılmadı.

## Geliştiren

Yusuf Baran Ozmakgil
