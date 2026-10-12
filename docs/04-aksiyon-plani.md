# 4. Aksiyon Planı (1–2 hafta)

## 4.1 Takvim

| Gün | İş | Çıktı | Onay noktası |
|---|---|---|---|
| 1–2 | Parsel sınırını uydu görüntüsünden çizmek; `calc/` modüllerini yazmak (enerji, şarj simülasyonu, güneş, yağmur suyu, finans); saha videosundan kare çıkarmak | `data/site/parsel.geojson`, hesap raporu | Kullanıcı parsel sınırını onaylar |
| 3–5 | Blender'da parametrik kaba kütle modeli (hangar, panel çatısı, 100 otobüs, kabinler, yıkama, idari bina, trafo/BESS, depo); tepe ve yan görünüşler | `blender/build_scene.py`, ilk görünüşler | Kullanıcı yerleşimi onaylar |
| 6–8 | Malzemeler, ışık, detaylar; perspektifler (gündüz, alacakaranlık, yağmur); fSpy ile öncesi/sonrası görselleri; enerji ve su akışı diyagramları | `renders/` | Kullanıcı görselleri onaylar |
| 9–12 | Video animasyonu, final render (Cycles + OptiX, gece), ffmpeg montajı | 60–90 sn 1080p video | Teslim |

## 4.2 Teslimatlar

1. **Tepe görünüşü:** ortografik vaziyet planı, ölçülü 2D çizim (SVG/PDF) + render
2. **Yan görünüşler ve kesitler:** kuzey/güney cepheleri; hangar ve panel çatısından geçen kesit (panel eğimi, oluk, iniş borusu, yer altı deposu)
3. **Perspektif render'lar:** gündüz, alacakaranlık, yağmurlu sahne
4. **Patlatılmış aksonometrik diyagram:** enerji akışı (şebeke → trafo → BESS → şarj → otobüs) ve su akışı (çatı → oluk → filtre → depo → yıkama)
5. **Öncesi/sonrası:** 6 saha fotoğrafının her biri için
6. **Video (60–90 sn):**

| Süre | Sahne |
|---|---|
| 0–8 sn | İstanbul ve Topkapı'ya yaklaşma |
| 8–15 sn | Mevcut durumdan yeni tasarıma geçiş |
| 15–30 sn | Şafakta drone turu, otobüsler dönüyor |
| 30–45 sn | Şarj soketi yakın plan, şarj seviyesi grafiği |
| 45–60 sn | Yağmur, oluk ve depo kesit animasyonu |
| 60–75 sn | Güneşin hızlandırılmış hareketi, enerji akış çizgileri |
| 75–90 sn | Tepeden plana geçiş, göstergeler: 100 otobüs, 5 MW, 2 MWp, 6.000 m³, −7.000 t CO₂ |

## 4.3 Kullanıcının yapacakları

- [ ] Araçları kurmak (`docs/02-araclar.md`)
- [ ] Repo'yu bilgisayara indirmek ve VS Code'da açmak
- [ ] Saha videosunu `data/site/video/` klasörüne koymak
- [ ] Her onay noktasında "devam" veya düzeltme
- [ ] Final render'ı gece bilgisayarda çalıştırmak
- [ ] Müzik seçimi (ücretsiz/lisanslı kütüphane)

## 4.4 İlk VS Code oturumunda Claude'un ilk adımları

1. `CLAUDE.md` ve `docs/` dokümanlarını okumak
2. Kurulumları doğrulamak: `blender --version`, `python --version`, `ffmpeg -version`, NVIDIA/OptiX
3. Parsel çizimine başlamak (gün 1)
