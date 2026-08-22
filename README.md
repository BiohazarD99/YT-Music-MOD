# Rich Music

Pemutar musik web gratis dengan data dari YouTube Music.

## Fitur

- 🏠 **Home** — shelf/carousel musik (Quick picks, mixes, dsb.) + Recently played
- 🔍 **Search** — pencarian dengan saran (suggestions) & filter: Songs, Videos, Albums, Artists, Playlists; halaman "Browse all" dengan tile mood & genre
- 📈 **Charts** — tangga lagu
- ▶️ **Pemutaran** — streaming lewat pemutar resmi YouTube (IFrame API), layar Now Playing full-screen dengan latar blur
- 🎶 **Antrean otomatis** — antrean "up next" untuk setiap lagu, plus tab Related yang tangguh (fallback "Similar songs" bila halaman related kosong)
- 🎤 **Lirik sinkron** — karaoke-style dari LRCLIB (fallback lirik plain), bisa di-tap untuk seek, dengan matcher multi-strategi
- 🔀 Shuffle, 🔁 Repeat (off/all/one), ⏱ Sleep timer, kontrol volume
- ♥ **Favorites**, ➕ **Playlist lokal**, 🕘 **History** — tersimpan di browser (localStorage), tanpa login
- 🔖 **Save to library** — simpan album/playlist/artis apa pun ke tab Saved
- 📥 **Import playlist** — tempel link playlist/album YouTube Music publik, langsung jadi playlist lokal
- ✨ **Mix for you** — shelf rekomendasi di Home berdasarkan riwayat & favoritmu (tanpa akun)
- 💾 **Backup / Restore** — ekspor-impor seluruh library sebagai file JSON (pindah perangkat gampang)
- ⏩ **SponsorBlock** — auto-skip intro/outro/sponsor/bagian non-musik (bisa di-toggle)
- 📊 **Listening stats** — total plays, menit didengar, top artis, lagu terbanyak diputar
- ⚡ **Playback speed** 0.5×–2×
- ⌨️ Shortcut: Space (play/pause), Shift+→/← (next/prev), Esc (tutup Now Playing)
- 📱 Responsif: sidebar ala Spotify di desktop, bottom navigation di ponsel
- 🎛 Media Session API (kontrol notifikasi media & tombol media)

## Menjalankan

```bash
npm install
node server.js
# buka http://localhost:3000
```

## Deploy ke Vercel

```bash
vercel deploy --prod
```

Konfigurasi sudah disiapkan di `vercel.json` + `api/index.js` (Express dibungkus sebagai serverless function, `public/` disajikan statis).

## Arsitektur

- `server.js` — Express server yang mem-proxy YouTube Music InnerTube API
  (`browse`, `search`, `next`, `music/get_search_suggestions`) dan LRCLIB untuk lirik,
  lalu mem-parsing respons menjadi JSON sederhana.
- `public/` — SPA vanilla JS (tanpa framework): router hash, pemutar, lirik sinkron, library lokal.

> Catatan: proyek ini tidak berafiliasi dengan YouTube/Google dan hanya untuk keperluan edukasi.
