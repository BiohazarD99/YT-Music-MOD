# Rich Music

**Pemutar musik web gratis** bergaya Spotify, dengan katalog [YouTube Music](https://music.youtube.com). Tanpa akun, tanpa iklan di dalam aplikasi, bebas dipakai.

- **Demo:** [richmusic.vercel.app](https://richmusic.vercel.app)
- **Repo:** [github.com/ramax100/YT-Music-Mod](https://github.com/ramax100/YT-Music-Mod)
- **Telegram:** [t.me/ChRichStore](https://t.me/ChRichStore)

> Project ini **gratis** dan **bebas dipakai**. Fork, modifikasi, deploy sendiri, atau bagikan ke teman — silakan.

---

## Tentang

Rich Music adalah SPA (Single Page Application) vanilla JavaScript + proxy Express. Metadata, pencarian, album, artis, dan radio diambil dari YouTube Music (InnerTube). Audio diputar lewat **pemutar resmi YouTube IFrame** — bukan unduhan gelap di latar.

Library (favorit, playlist, riwayat, statistik) tersimpan di browser (`localStorage`). Tidak perlu login.

**Bukan** produk resmi YouTube / Google / Spotify. Hanya klien web independen untuk mendengarkan musik.

---

## Bergabung

Update, update fitur, dan diskusi ada di channel Telegram:

### [t.me/ChRichStore](https://t.me/ChRichStore)

Silakan join. Project ini dibuat untuk dipakai bersama — gratis.

---

## Fitur lengkap

### Beranda (Home)
- Sapaan sesuai waktu + tanggal
- **Recently played** — kartu cepat dari riwayat
- **Mix for you** — rekomendasi dari favorit & riwayat (tanpa akun)
- Liked songs, playlist lokal, item Saved
- Rak YouTube Music (mis. *Pilihan cepat*, mix musiman)
- Carousel bisa digeser; di desktop ada panah kiri/kanan

### Cari (Search)
- Kotak cari + saran otomatis
- Filter: All, Songs, Videos, Albums, Artists, Playlists
- **Top result** sebagai kartu besar
- Hasil dikelompokkan (lagu daftar, album/artis/playlist carousel)
- Riwayat pencarian (bisa hapus satu / Clear)
- **Browse all** — 30+ mood & genre dengan warna resmi YTM
- Tombol **X** untuk mengosongkan pencarian

### Charts
- Tangga lagu, playlist genre, artis teratas
- Chart unggulan ditampilkan sebagai grid

### Library
Tanpa akun. Semua di perangkat ini.

| Tab | Isi |
| --- | --- |
| **Playlists** | Playlist buatanmu, kartu Liked Songs |
| **Favorites** | Lagu yang di-heart, Play all / Shuffle |
| **Saved** | Album, playlist, artis yang di-Save |
| **History** | Yang baru diputar |
| **Stats** | Total putar, menit, lagu unik, top artis, most played |

- **New playlist** — buat folder baru
- **Import from YT Music** — tempel link playlist / album / artis / lagu publik
- **Backup / Restore** — unduh JSON, pindah HP/laptop gampang
- Playlist lokal: rename, hapus, urutkan (panah / drag di desktop)

### Pemutaran
- Streaming resmi YouTube IFrame (default audio YTM **hd720**)
- **Quality** di menu ⋮ → YouTube max (bitrate lebih tinggi)
- Lagu pertama di sesi langsung play
- Klik lagu lain saat sedang play = **preview** (Now Playing ganti, lagu lama tetap jalan sampai kamu tekan Play)
- Shuffle (tidak mengulang lagu yang sama)
- Repeat: mati / semua / satu lagu
- Kecepatan **0.5×–2×**
- Volume + seek
- **SponsorBlock** — auto-skip intro/outro/sponsor (bisa dimatikan)
- Antrian tersimpan (`smw_qstate`) — refresh tidak auto-play

### Now Playing
- HP: layar penuh, geser ke bawah untuk menutup
- Desktop lebar: panel kanan
- Tab: **Song · Lyrics · Queue · Related**
- Favorite, Playlist, ⋮ More (Download, Share, Speed, Widget, Quality, SponsorBlock)
- Preview lagu: tombol **Play next** / **Add to queue**
- Klik nama artis → halaman artis
- Sleep timer (15 / 30 / 45 / 60 menit atau custom)

### Lirik
- Sumber berurutan: LRCLIB → YouTube Music → NetEase → Textyl → lyrics.ovh
- Lirik sinkron (karaoke), tap baris untuk seek
- Preview baris di tab Song + widget
- Tidak semua lagu punya lirik di database publik

### Antrian (Queue)
- **Your queue** diputar dulu, lalu radio otomatis
- Play next / Add to queue (tanpa dobel)
- Urutkan: panah, di desktop bisa drag
- Sidebar kiri: Now playing + Your queue (tanpa radio)
- Play dari preview **tidak** menghapus antrian buatanmu

### Related
- Lagu serupa, playlist, artis, album
- Kartu album/playlist/artis membuka halaman (bukan preview lagu)
- Fallback *Similar songs* jika related kosong

### Download
- MP3 320 kbps lewat konverter (loader.to)
- Nama file: `Artis - Judul.mp3`
- Progress % + simpan blob
- Hanya untuk konten yang memang boleh kamu unduh. Patuhi hak cipta.

### Share
- HP: menu share sistem (WA, dll.)
- Desktop / batal: salin tautan `#/song/VIDEO_ID`

### Tampilan
- Mode gelap / terang (tombol matahari/bulan, pintasan `L`)
- Now Playing tetap gelap (cover album)
- Foto rusak / kosong → placeholder, bukan ikon pecah
- Desktop: sidebar + mini player
- HP: navigasi bawah + mini player mengambang

### Widget & Picture-in-Picture
- Widget mengambang di halaman (bisa digeser)
- PiP sistem (lirik vertikal) di browser yang mendukung
- Media Session: tombol headset / notifikasi

### Pintasan keyboard

| Tombol | Aksi |
| --- | --- |
| `Space` | Play / Pause (di Now Playing: Play lagu preview) |
| `Shift` + `→` | Lagu berikutnya |
| `Shift` + `←` | Lagu sebelumnya |
| `Esc` | Tutup Now Playing |
| `L` | Ganti tema |
| `P` | Toggle widget |

---

## Cara memakai (pengguna)

1. Buka [richmusic.vercel.app](https://richmusic.vercel.app) (atau instance yang kamu deploy).
2. Hard refresh sekali setelah update: **Ctrl+Shift+R** (HP: hapus cache / tab baru).
3. Cari lagu, buka album/artis, atau pilih dari Home.
4. Lagu pertama langsung play. Lagu berikutnya: buka Now Playing, lalu **Play** jika hanya preview.
5. Heart = favorit. **Playlist** = simpan ke folder. **Save** di halaman album/artis = tab Saved.
6. Backup library dari Library → Backup sebelum ganti HP.

### HP (Chrome / Xiaomi, dll.)

Audio YouTube di tab background sering pause jika browser memakai *tampilan seluler*. Itu batas iframe YouTube, bukan crash aplikasi.

**Solusi:** menu ⋮ browser → **Situs desktop** (Desktop site). Setelah itu audio bisa bertahan lebih lama di belakang.

---

## Cara menjalankan repo (developer)

### Prasyarat

- [Node.js](https://nodejs.org) 18+ (disarankan 20)
- npm
- (Opsional) [Vercel CLI](https://vercel.com/docs/cli) untuk deploy

### Lokal

```bash
git clone https://github.com/ramax100/YT-Music-Mod.git
cd YT-Music-Mod
npm install
npm start
```

Buka **http://localhost:3000**

`npm start` menjalankan `node server.js` (Express di `0.0.0.0:3000`).

Folder `public/` disajikan statis. Semua `/api/*` di-proxy ke YouTube Music / LRCLIB / konverter unduhan.

### Struktur

```
YT-Music-Mod/
├── public/
│   ├── index.html      # kerangka UI
│   ├── app.js          # SPA: router, player, library
│   ├── styles.css      # tema Spotify-style
│   └── logo*.png       # ikon
├── server.js           # Express + InnerTube + lirik + download
├── api/index.js        # bungkus serverless Vercel
├── vercel.json         # routing production
├── package.json
└── README.md
```

### API utama (`server.js`)

| Endpoint | Fungsi |
| --- | --- |
| `GET /api/home` | Feed beranda |
| `GET /api/search?q=&filter=` | Cari |
| `GET /api/suggest?q=` | Saran ketikan |
| `GET /api/charts` | Tangga lagu |
| `GET /api/moods` | Mood & genre |
| `GET /api/browse?id=` | Album / playlist / artis |
| `GET /api/next?videoId=` | Antrian radio + id lirik/related |
| `GET /api/related?browseId=` | Kartu related |
| `GET /api/lyrics?title=&artist=` | Lirik multi-sumber |
| `GET /api/sponsorblock?videoId=` | Segmen skip |
| `GET /api/download-start` / `download-progress` | Konversi MP3 |
| `GET /api/thumb` | Proxy thumbnail |

Konteks InnerTube: `hl: id`, `gl: ID`.

### Data di browser (`localStorage`)

Awalan kunci: `smw_`

| Kunci | Isi |
| --- | --- |
| `smw_fav` | Favorit |
| `smw_pls` | Playlist lokal |
| `smw_hist` | Riwayat |
| `smw_sav` | Saved |
| `smw_stats` | Statistik dengar |
| `smw_theme` | `dark` / `light` |
| `smw_vol` | Volume |
| `smw_sb_on` | SponsorBlock |
| `smw_yt_hq` | Quality max |
| `smw_qstate` | Antrian + shuffle/repeat/speed |
| `smw_srec` | Riwayat pencarian |
| `smw_fw_pos` | Posisi widget |

Hapus data situs di browser = library hilang. Gunakan **Backup**.

---

## Deploy ke Vercel

```bash
npm i -g vercel
cd YT-Music-Mod
vercel login
vercel --prod
```

`vercel.json` sudah mengarahkan:

- `/api/*` → `api/index.js` (Express)
- file statis → `public/`
- selain itu → `index.html` (SPA)

Setelah deploy, buka URL `*.vercel.app`. Untuk update, `vercel --prod` lagi lalu hard refresh.

Bisa juga **Import Git Repository** di dashboard Vercel: pilih `ramax100/YT-Music-Mod`, framework *Other*, deploy.

---

## Batasan (bukan bug)

- Feed Home anonim YouTube Music sering hanya ~2 rak.
- Audio di HP (UA mobile) bisa pause saat tab di belakang — pakai **Situs desktop**.
- Equalizer / crossfade tidak mungkin (iframe YouTube).
- InnerTube `player` butuh login; URL DASH tidak diambil.
- Sebagian lagu tidak ada di database lirik publik.

---

## Lisensi & pemakaian

**Gratis. Bebas dipakai.**

Kamu boleh menjalankan, membagikan, memodifikasi, dan men-deploy ulang project ini. Tidak ada biaya, tidak ada akun wajib.

Mohon:

- Jangan mengaku sebagai produk resmi YouTube / Google / Spotify
- Hormati hak cipta saat memakai fitur unduh
- Cantumkan tautan repo atau channel jika membagikan ulang (sangat dihargai, bukan wajib)

Tidak berafiliasi dengan YouTube, Google, atau Spotify.

---

## Kontribusi & kontak

Issue dan pull request di repo ini diterima.

- GitHub: [ramax100/YT-Music-Mod](https://github.com/ramax100/YT-Music-Mod)
- Telegram: [t.me/ChRichStore](https://t.me/ChRichStore)
- Demo: [richmusic.vercel.app](https://richmusic.vercel.app)

Dibuat untuk didengarkan. Selamat memutar.
