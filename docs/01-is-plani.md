# 1. İş Planı (ön fizibilite)

Rakamlar gösterge niteliğindedir. `params/project.yaml` ve `calc/` modülleriyle doğrulanacaktır.

## 1.1 Sahadan gözlemler (fotoğraflar: `data/site/photos/`)

| Gözlem | Projeye etkisi |
|---|---|
| Beşik çatılı tarihi hangar, "İETT OTOBÜS GARAJI" yazısı, bayrak | Kimlik öğesi: siluet ve yazı korunarak yenilenir. Çatının panel yükünü taşıyıp taşımadığı ve asbest kontrol edilecek. |
| "Yağ Yakıt Sıvı İkmal" bölümü | Dizel ikmal kalkınca yer açılır. Yer altı tankları sökülmeli, zemin kirliliği taranmalı. |
| "Tehlikeli Atık Alanı" | Lityum batarya atığı için yangına karşı korunmuş alana dönüşür. |
| "Bakım Onarım", "Yedek Parça" | Kapalı alanın ana işlevi; yüksek gerilim güvenlik alanları ve çatı üstü batarya erişim platformları eklenir. |
| Asfaltta göllenmeler | Drenaj sorunu var; yağmur suyu geri kazanımı için gerekçe. |
| Bitişik 4–5 katlı konutlar | Gece şarj fanı gürültüsü ve ışık kirliliği riski; çatı "beşinci cephe" olarak görünür. |
| Personel araç otoparkları | Yerleşime personel otoparkı dahil edilir. |
| Topkapı konumu | Kara Surları'na yakınlık nedeniyle sit alanı / UNESCO tampon bölgesi kısıtları olabilir. Teyit edilecek. |

## 1.2 Rakamların sağlaması

| Parametre | Varsayım | Sonuç |
|---|---|---|
| Günlük yol | ~250 km/otobüs | 100 otobüs, yılda ~9,1 milyon km |
| Tüketim | ~1,2 kWh/km | ~300 kWh/otobüs/gün |
| Batarya | ~420–480 kWh | Gün tek gece şarjıyla çıkar |
| Gecelik filo enerjisi | 100 × 300 kWh | ~30 MWh/gece |
| Şarj penceresi | 23:30–05:30 (~6 saat) | 30 MWh / 6 saat = **5 MW** |

5 MW değeri doğru ama pay bırakmıyor; bina yükleri de bu 5 MW'ın içinde. Bu yüzden:
- akıllı şarj yönetimi (OCPP 2.0.1),
- ~2 MWh batarya depolama (gündüz güneşle dolar, gece otobüslere verir),
- gün ortası seferden dönen otobüslere güneşle ara şarj.

**Şarj:** 15 × 360 kW güç kabini, her birine 6–7 soket, toplam ~100 soket. Her park yerinde soket olduğu için gece otobüs yer değiştirmez. 10 otobüs kapalı alanda, ~90 otobüs açık alanda panel çatısı altında şarj olur. Altyapı 20 kabine genişleyebilir. Şebeke: 34,5 kV OG (BEDAŞ), 3 × 2500 kVA trafo.

**Güneş enerjisi**

| Yüzey | Alan | Güç |
|---|---|---|
| Hangar çatısı | 5.000 m² × %65 | ~0,75 MWp |
| Panel çatısı (otobüs parkı üstü) | ~6.000 m² | ~1,3 MWp |
| Toplam | | ~2 MWp → yılda ~2,5 GWh → filo tüketiminin ~%20–25'i |

**Yağmur suyu**
- Toplama yüzeyi ~11.000 m², yıllık yağış ~680 mm → yılda ~6.000 m³.
- Açık yıkama ünitesi (geri dönüşümlü) yılda ~7.000 m³ temiz su ister; yağmur suyu ~%80'ini karşılar. Kalanı WC ve sulamaya.
- Sistem: hangarda sifonik çatı drenajı, panel çatısında kirişe gömülü oluk, ilk kirli yağış ayırıcı, filtre + UV, ~400 m³ yer altı deposu, taşkın İSKİ şebekesine.
- İmar yönetmeliğindeki yağmur suyu deposu zorunluluğu teyit edilecek.

## 1.3 Yerleşim konsepti

- **Açık alan (~10 dönüm):** 20 şerit × 5 otobüs, arka arkaya park. Otobüsler girdiği yönde çıkar. Üstte ~5,5 m serbest yükseklikte panel çatısı; şarj kabloları çatıdan sarkar.
- **Girişte açık yıkama ünitesi**, otobüsün giriş rotası üzerinde.
- **Kapalı alan (5 dönüm):** bakım-onarım, yüksek gerilim atölyesi, 10 otobüslük iç şarj bölümü (yangın duvarı, sprinkler, termal kamera, tahliye yolu), yedek parça ve batarya deposu.
- **İdari binalar** ve **personel otoparkı** açık alanda; mevcut tek katlı idari bina korunur.
- **Trafo merkezi ve batarya depolama** konutlardan en uzak köşede, akustik perde arkasında.

## 1.4 Yatırım tutarı (otobüsler hariç)

| Kalem | Milyon € |
|---|---|
| OG bağlantısı, trafo merkezi | 1,2 – 1,8 |
| 15 kabin, ~100 soket, kurulum | 3,0 – 3,8 |
| 2 MWp güneş (çatı + panel çatısı çeliği) | 1,8 – 2,3 |
| 2 MWh batarya depolama | 0,6 – 0,8 |
| Yağmur suyu sistemi | 0,25 – 0,4 |
| Hangar yenileme, saha betonu, drenaj | 3,0 – 4,5 |
| Yangın güvenliği, izleme, garaj yönetim yazılımı | 0,8 – 1,1 |
| Proje, izinler, %10–15 beklenmeyen gider | 1,5 – 2,0 |
| **Toplam** | **~12 – 17** |

100 elektrikli otobüs ayrıca ~€45–55 milyon; dizele göre fark ~€20–25 milyon.

## 1.5 Yıllık getiri

- Dizel tasarrufu: ~4,1 milyon litre ≈ €4,7 milyon
- Şebeke elektriği: ~8,5 GWh ≈ €1,1 milyon (güneş ~2,5 GWh'i karşılar)
- Bakım tasarrufu: ~€0,5–0,9 milyon
- **Net tasarruf ~€4–4,5 milyon/yıl.** Altyapı ~4 yılda, otobüs farkıyla birlikte ~8–10 yılda geri döner.
- **CO₂:** ~11.000 t → ~3.800 t, yılda ~7.000 t azalma (~%65).

## 1.6 İş modeli ve finansman

1. İETT kendi yatırır ve işletir.
2. Şarj hizmet olarak alınır (özel ortak kurar, İETT kWh başına öder).
3. Güneş panelleri enerji alım anlaşmasıyla kurulur.

Ek gelir: gündüz boştaki şarj kapasitesi, karbon kredisi (Türkiye ETS pilot aşaması).
Finansman: EBRD, EIB, Dünya Bankası yeşil kredileri, yeşil tahvil.

## 1.7 Aşamalar (garaj çalışmaya devam ederken)

| Faz | Süre | İçerik |
|---|---|---|
| 0 | 0–6 ay | Fizibilite, zemin etüdü, BEDAŞ başvurusu (en uzun süren iş), Koruma Kurulu, İSKİ |
| 1 | 6–15 ay | OG merkezi, ilk 10 şerit panel çatısı, 8 kabin, 50 otobüs, yağmur suyu deposu |
| 2 | 15–24 ay | Kalan şeritler, 7 kabin, batarya depolama, dizel ikmalin sökülmesi |
| 3 | 24–30 ay | Hangar yenileme, çatı güneş paneli, sifonik drenaj, iç şarj bölümü |

## 1.8 Riskler

1. Yoğun kent dokusunda 5 MW şebeke kapasitesi
2. Tarihi alan kısıtları
3. Eski hangarın taşıyıcı sistemi ve asbest
4. Lityum batarya yangını (özellikle iç şarj bölümü)
5. Komşulara gürültü ve ışık
6. 100 otobüsün 10 dönüme sığması (~8.500 m² yeterli, ama sınırda)
