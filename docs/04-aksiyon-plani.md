# 4. Aksiyon Planı (~1 hafta)

Animasyon videosu kapsam dışı. Çıktılar durağan görseller ve paftalardır.

## 4.1 Takvim

| Gün | İş | Çıktı | Onay noktası |
|---|---|---|---|
| 1 | Parsel sınırını uydu görüntüsünden çizmek; `calc/` modüllerini yazmak (enerji, şarj, güneş, yağmur suyu, finans) | `data/site/parsel.geojson`, hesap raporu | Kullanıcı parsel sınırını onaylar |
| 2–3 | Blender'da parametrik kaba kütle modeli (hangar, panel çatısı, 100 otobüs, kabinler, yıkama, idari bina, trafo/BESS, depo); tepe ve yan görünüşler | `blender/build_scene.py`, ilk görünüşler | Kullanıcı yerleşimi onaylar |
| 4–5 | Malzemeler, ışık, detaylar; perspektifler; fSpy ile öncesi/sonrası; enerji ve su akışı diyagramları | `renders/` | Kullanıcı görselleri onaylar |
| 6–7 | Final render'lar (4K, Cycles + OptiX), paftaların PDF'e dizilmesi | Sunum paketi | Teslim |

## 4.2 Teslimatlar

1. **Tepe görünüşü:** ortografik vaziyet planı, ölçülü 2D çizim (SVG/PDF) + render
2. **Yan görünüşler ve kesitler:** kuzey/güney cepheleri; hangar ve panel çatısından geçen kesit (panel eğimi, oluk, iniş borusu, yer altı deposu)
3. **Perspektif render'lar:** gündüz, alacakaranlık, yağmurlu sahne, kuş bakışı
4. **Patlatılmış aksonometrik diyagram:** enerji akışı (şebeke → trafo → BESS → şarj → otobüs) ve su akışı (çatı → oluk → filtre → depo → yıkama)
5. **Öncesi/sonrası:** 6 saha fotoğrafının her biri için
6. **Göstergeler paftası:** 100 otobüs, 5 MW, 2 MWp, 6.000 m³, −7.000 t CO₂

## 4.3 Kullanıcının yapacakları

- [ ] Araçları kurmak (`docs/02-araclar.md`)
- [ ] Repo'yu bilgisayara indirmek ve VS Code'da açmak
- [ ] Her onay noktasında "devam" veya düzeltme
- [ ] Final render'ları bilgisayarda çalıştırmak

## 4.4 İlk VS Code oturumunda Claude'un ilk adımları

1. `CLAUDE.md` ve `docs/` dokümanlarını okumak
2. Kurulumları doğrulamak: `git --version`, `blender --version`, `python --version`, NVIDIA/OptiX
3. Parsel çizimine başlamak (gün 1)
