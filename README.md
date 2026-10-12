# Topkapı Elektrikli Otobüs Garajı

İETT Topkapı garajının 100 araçlık elektrikli otobüs garajına dönüştürülmesi için konsept tasarım, 3D model ve render projesi. Animasyon videosu kapsam dışı. Hedef: İETT/İBB sunumu.

| | |
|---|---|
| Filo | 100 × 12 m solo elektrikli otobüs (menzil 300–400 km) |
| Şarj | 15 × 360 kW güç kabini, ~100 soket (10'u kapalı alanda) |
| Bağlantı gücü | 5 MW (34,5 kV OG, BEDAŞ) |
| Toplam alan | 15 dönüm (kapalı 5 dönüm, açık 10 dönüm) |
| Güneş enerjisi | ~2 MWp (hangar çatısı + panel çatısı) |
| Yağmur suyu | ~6.000 m³/yıl, açık yıkama ünitesinde kullanım |

## Dokümanlar

1. [İş planı](docs/01-is-plani.md): rakamların sağlaması, yatırım, tasarruf, fazlar, riskler
2. [Araçlar ve kurulum](docs/02-araclar.md): ücretsiz araç zinciri
3. [Kararlar ve varsayımlar](docs/03-kararlar.md)
4. [Aksiyon planı](docs/04-aksiyon-plani.md): 1–2 haftalık iş takvimi

Tüm sayısal değerlerin tek kaynağı: [`params/project.yaml`](params/project.yaml).

## Klasör yapısı

```
params/project.yaml   tek parametre kaynağı
calc/                 enerji, güneş, yağmur suyu, finans hesapları (Python)
data/site/            saha fotoğrafları, video, parsel sınırı, fSpy dosyaları
blender/              sahne üretim scriptleri ve asset'ler
exports/              .glb / .fbx / .obj dışa aktarımları
renders/              render çıktıları (git'e girmez)
docs/                 iş planı ve proje dokümanları
```
