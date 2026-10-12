# 2. Araçlar ve Kurulum

Karar: **tamamen ücretsiz araç zinciri**, çalışma ortamı VS Code.

## 2.1 Araç zinciri

| Araç | Rolü | Ücret |
|---|---|---|
| VS Code + Claude Code eklentisi | Script yazma, hesaplar, Blender'ı yönetme | Ücretsiz (Claude aboneliği mevcut) |
| Blender (güncel LTS) + resmi Blender bağlantısı | 3D model, görünüşler, render, animasyon | Ücretsiz, ticari kullanım dahil |
| Python 3.11+ (pvlib, numpy, pyyaml, matplotlib) | Enerji, güneş, yağmur suyu, finans hesapları | Ücretsiz |
| fSpy | Fotoğraflara kamera eşleme (öncesi/sonrası) | Ücretsiz |
| ffmpeg (isteğe bağlı) | Saha videosundan kare çıkarma | Ücretsiz |
| Git | Sürüm kontrolü | Ücretsiz |
| PVGIS (AB JRC) | Güneş üretim verisi | Ücretsiz |
| Poly Haven | Gökyüzü ışık haritaları, dokular, ağaçlar | Ücretsiz (CC0) |

Kullanılmayacaklar: Fusion, SketchUp, Adobe (ücretli). Animasyon videosu kapsam dışı olduğu için video kurgu aracı da gerekmez.

## 2.2 Kurulum (Windows)

1. **VS Code** → Extensions → **Claude Code** (Anthropic) → aynı Claude hesabıyla giriş.
2. **Git:** PowerShell'de `winget install --id Git.Git -e --source winget`, sonra VS Code'u kapatıp yeniden aç
3. **Python 3.11+:** https://python.org (kurulumda "Add to PATH" işaretli)
4. **Blender LTS:** https://blender.org → Claude ayarlarından Blender bağlantısını etkinleştir.
5. **ffmpeg (isteğe bağlı):** PowerShell'de `winget install Gyan.FFmpeg`
6. **fSpy:** https://fspy.io
7. Python paketleri (repo klasöründe):
   ```
   python -m venv .venv
   .venv\Scripts\activate
   pip install pvlib numpy pyyaml matplotlib
   ```

## 2.3 Donanım

Windows + NVIDIA ekran kartı. Blender'da: Edit → Preferences → System → Cycles Render Devices → **OptiX**.
Taslaklar EEVEE ile, final render'lar Cycles + OptiX ile (görsel başına birkaç dakika).

## 2.4 Sınırlar

- Görseller konsept ve sunum amaçlıdır. Statik, elektrik ve tesisat uygulama projeleri lisanslı mühendis imzası gerektirir.
- İETT/İBB logosu kullanılmaz; yer tutucu konur.
- Otobüs modeli markasızdır, Blender'da üretilir (telif riski yok).

## 2.5 Disk alanı

Video olmadığı için toplam ~2–3 GB yeter: `.blend` sahne dosyaları ve dokular ~0,5–1 GB, 4K render'lar (~20–30 görsel × ~20 MB) ~0,5 GB, taslaklar ~0,5 GB.
