# DocLantern – AI Notebook tanıtım sitesi

Statik site, derleme gerektirmez. Bütün dosyalar tek seviyededir (klasör yok); GitHub'ın
web arayüzünden hepsini seçip yüklemek yeterli.

| Dosya | Ne işe yarar |
|---|---|
| `index.html` | Tanıtım sayfası (TR + EN) |
| `privacy.html` | Gizlilik politikası (TR + EN); Partner Center'daki "Privacy policy URL" |
| `logo.png`, `favicon.png` | Logo ve sekme ikonu |
| `chat-tr.webp` … `export-en.webp` | Özellikler bölümündeki ekran görüntüleri (her özellik için TR ve EN) |
| `.nojekyll` | GitHub Pages'e "dosyaları olduğu gibi yayınla" der |

## Yayın adresi
GitHub Pages: `https://od-forge.github.io/docmind/` (depo adı `docmind`).
Depo adını `doclantern` yaparsan adres `https://od-forge.github.io/doclantern/` olur;
o zaman Partner Center'daki gizlilik/web sitesi adreslerini ve uygulamadaki
`packaging/store_config.json` → `website_url` alanını da güncelle.

## Güncelleme
GitHub'da depo → **Add file → Upload files** → değişen dosyaları sürükle → **Commit changes**.
Aynı adlı dosyaların üstüne yazılır; 1–2 dakika içinde site güncellenir.

## Store bağlantısı
Uygulama Store'da yayına girince `index.html` (ve `privacy.html`) içindeki betiğin başındaki
satırı doldurun:

```js
const SITE = {
  storeUrl: "https://apps.microsoft.com/detail/9MT3XFMKP9C5",
  ...
```

Boşken indirme düğmeleri "Yakında Microsoft Store'da" yazar ve fiyat bölümüne kaydırır.

## Dil
Ziyaretçinin tarayıcı dili Türkçeyse site Türkçe, değilse İngilizce açılır; sağ üstteki
TR / EN ile değiştirilebilir ve seçim hatırlanır.

## Ekran görüntüleri
Uygulamadaki `tools/make_help_shots.py` ile üretilir (`web/help/img/<dil>/<ad>.webp`).
Buraya `<ad>-<dil>.webp` adıyla kopyalanır (ör. `chat-tr.webp`).
