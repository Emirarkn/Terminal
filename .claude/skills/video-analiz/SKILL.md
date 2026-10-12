---
name: video-analiz
description: Saha videolarını (.mov, .mp4) izlemek ve analiz etmek için. Kullanıcı bir video verdiğinde, "videoyu izle/incele" dediğinde ya da data/site/video/ klasörüne yeni video eklendiğinde kullan. Videodan kareler çıkarır, temas sayfası (contact sheet) oluşturur ve kareleri görsel olarak okur.
---

# Video analizi

Claude videoyu doğrudan oynatamaz; videoyu **kareye bölüp kareleri görsel olarak okur**. Bu skill bunu standart hale getirir.

## 1. Videoyu tanı

```
ffprobe -v error -show_entries stream=index,codec_type,codec_name,width,height,r_frame_rate,nb_frames:format=duration -of compact "<video>"
```

Not: ffprobe çıktısını `head` ile kesme; ses akışı önce listelenir, video akışı arkada kalabilir.
iPhone "Live Photo" videoları ~0,5 sn ve düşük çözünürlüklüdür; bu normaldir.

## 2. Kare çıkar

Çıktılar `data/site/video/frames/<video-adı>/` altına (git'e girmez).

- **Kısa video (< 5 sn):** tüm kareleri değil, başı-ortası-sonu:
  ```
  ffmpeg -v error -i "<video>" -vf "select='eq(n,0)+eq(n,N/2)+eq(n,N-1)'" -vsync 0 frames/f_%02d.jpg
  ```
  (`N` = nb_frames)
- **Uzun video:** saniyede 1 kare:
  ```
  ffmpeg -v error -i "<video>" -vf "fps=1,scale=1280:-1" frames/f_%04d.jpg
  ```
- **Sahne değişimlerini yakala:**
  ```
  ffmpeg -v error -i "<video>" -vf "select='gt(scene,0.3)',scale=1280:-1" -vsync 0 frames/sahne_%03d.jpg
  ```

## 3. Temas sayfası (tek görselde genel bakış)

```
ffmpeg -v error -i "<video>" -vf "fps=1,scale=480:-1,tile=4x3" -frames:v 1 frames/temas.jpg
```

Önce temas sayfasını oku, sonra ilginç kareleri tam çözünürlükte oku. Okunacak kare sayısını 10–15 ile sınırla.

## 4. Raporla

Her önemli kare için: zaman (sn), ne görünüyor, projeye etkisi (yapı, cephe, zemin, komşu bina, tabela, ölçek ipucu).
fSpy veya öncesi/sonrası görseli için uygun kareleri ayrıca işaretle ve `data/site/photos/` altına kopyala.

## Sınırlar

- Ses dinlenemez. Konuşma varsa ve gerekiyorsa `pip install openai-whisper` ile yerelde yazıya dökülebilir; kullanıcıya sor.
- Kareler video çözünürlüğündedir; düşük çözünürlüklü videodan ölçü çıkarma.
