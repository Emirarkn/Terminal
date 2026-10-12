# Proje bağlamı (Claude için)

Bu repo, İETT Topkapı garajının 100 araçlık elektrikli otobüs garajına dönüştürülmesi için konsept tasarım ve görselleştirme projesidir. Kullanıcıyla Türkçe konuş.

Başlamadan önce `docs/` altındaki dört dokümanı oku. Kararlar `docs/03-kararlar.md` içinde. Kullanıcı bunları onayladı, yeniden sorma.

## Çalışma kuralları

- Tüm sayılar `params/project.yaml` dosyasından okunur. Script'lere sabit sayı gömme.
- Sadece ücretsiz araçlar: Blender (Python/bpy, Blender MCP bağlantısı), Python, fSpy, ffmpeg, isteğe bağlı DaVinci Resolve.
- Kullanıcının bilgisayarı: Windows + NVIDIA. Final render Cycles + OptiX ile; taslaklar EEVEE.
- Blender'ı arka planda çalıştırma: `blender -b -P blender/<script>.py -- <argümanlar>`.
- Logo kullanılmaz: İETT/İBB logosu yerine yer tutucu.
- Otobüs: markasız 12 m solo, İETT renklerinde.
- Render ve video çıktıları git'e girmez (`.gitignore`).
- Görseller konsept/sunum amaçlıdır; uygulama projesi değildir.
