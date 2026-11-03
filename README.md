# Ambite

Aplikasi belajar offline (tugas, unggah berkas tugas, kalender, pomodoro, latihan soal, analisis) bergaya monokrom elegan dengan efek kaca.
Semua data tersimpan di perangkat. Tanpa AI, tanpa server.

## Struktur
- `www/` : aplikasi (HTML/CSS/JS), manifest PWA, service worker, ikon
- `capacitor.config.json`, `package.json` : pembungkus Android (Capacitor)
- `.github/workflows/pages.yml` : deploy otomatis ke GitHub Pages
- `.github/workflows/android.yml` : build APK otomatis di GitHub Actions

## Langkah
1. Buat repo baru di GitHub, lalu unggah seluruh isi folder ini ke branch `main` (termasuk folder `.github`).
   Tanpa laptop: buka repo di GitHub Codespaces lewat browser, unggah zip ini, jalankan `unzip` di terminal, lalu `git add . && git commit -m init && git push`.
2. **Web/PWA:** di repo, buka Settings > Pages > Source: pilih **GitHub Actions**. Alamat aplikasi akan muncul setelah workflow selesai. Buka di Chrome HP, lalu menu > Tambahkan ke layar utama.
3. **APK Android:** buka tab Actions > "Build APK Android" > Run workflow. Setelah hijau, unduh artifact `ambite-debug-apk`, ekstrak, lalu pasang `app-debug.apk` di HP (izinkan pemasangan dari sumber tidak dikenal).

APK yang dihasilkan adalah versi debug untuk dipakai sendiri. Untuk Play Store diperlukan build rilis bertanda tangan.

## Catatan fitur Berkas
Berkas disimpan di IndexedDB perangkat (offline, tidak keluar dari HP). Pencarian dan filter mapel tersedia. Membuka/mengunduh PDF paling andal di Chrome (versi PWA). Di APK, pratinjau gambar berfungsi, sedangkan pembukaan PDF bergantung pada WebView.
