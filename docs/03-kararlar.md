# 3. Kararlar ve Varsayımlar

## 3.1 Kullanıcının onayladığı kararlar

| Konu | Karar |
|---|---|
| Araçlar | Ücretsiz: VS Code + Claude Code, Blender, Python, fSpy |
| Bilgisayar | Windows + NVIDIA; final render kullanıcının bilgisayarında |
| Hangar | Korunur ve yenilenir (siluet + cephe yazısı) |
| Şarj | 15 × 360 kW kabin, ~100 soket; 10 otobüs kapalı alanda, ~90 açık alanda; 20 kabine genişleyebilir |
| Kapalı alan (5 dönüm) | Bakım-onarım, iç şarj bölümü (10 otobüs), depo |
| Açık alan (10 dönüm) | Otobüs parkı, açık yıkama ünitesi, idari binalar, personel otoparkı |
| Yağmur suyu | Hangar ve panel çatısından toplanır, açık yıkama ünitesinde kullanılır |
| Parsel | Uydu görüntüsünden Claude çizer, kullanıcı onaylar |
| Hedef | İETT/İBB sunumu: kurumsal, teknik, ikna edici |
| Görsel stil | Fotogerçekçi render + enerji/su akışı diyagramları |
| Video | **Kapsam dışı.** Sadece durağan görseller ve paftalar (4K) |
| Dil | Türkçe |
| Otobüs | Markasız 12 m solo, İETT renklerinde |
| Logo | Kullanılmaz, yer tutucu |
| Takvim | ~1 hafta |

## 3.2 Claude'un varsayımları (kullanıcı itiraz etmedikçe geçerli)

- İç şarj bölümü: yangın duvarıyla ayrılmış, sprinkler, termal kamera, acil tahliye yolu. Kesit görselinde gösterilir.
- Personel otoparkı ~40 araç.
- Mevcut tek katlı idari bina korunur.
- Yıkama ünitesi girişte, otobüsün giriş rotası üzerinde.
- Trafo merkezi ve batarya depolama konutlardan en uzak köşede, akustik perde arkasında.
- Kesin konum ve kuzey yönü, uydu görüntüsü ile saha fotoğraflarının eşleştirilmesiyle belirlenir.

## 3.3 Açık noktalar

- Saha videosu: gönderilen `.mov` dosyası 0,5 sn, 480×368, 15 karelik bir iPhone Live Photo klibi. Yedek parça cephesini (fotoğraf 03 ile aynı açı) gösteriyor. Daha uzun bir saha turu videosu çekilirse `data/site/video/` klasörüne konmalı ve `video-analiz` skill'i ile incelenmeli.
- Hangarın ölçüleri (uzunluk, genişlik, mahya yüksekliği) şimdilik fotoğraflardan tahmin edilecek; ölçüm gelirse güncellenir.
