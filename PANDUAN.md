# ELPI Certificate Monitor — Aplikasi HP (PWA)

Folder ini adalah "pembungkus" yang membuat Certificate Monitor bisa di-install di HP dan laptop:
ikon ELPI di layar utama, terbuka layar penuh tanpa bilah alamat, dan ada layar pembuka.
Isi aplikasinya tetap web app Apps Script, jadi setiap update di Apps Script langsung ikut tampil.

Isi folder:
- `index.html` — halaman aplikasi (link Apps Script ada di baris `APP_URL`)
- `manifest.webmanifest` — nama, ikon, dan warna aplikasi
- `sw.js` — supaya bisa di-install dan cepat terbuka
- `icons/` — ikon dan logo ELPI

## 1. Siapkan Apps Script (sekali)

1. Ganti **Code.gs** dengan versi terbaru (sudah mengizinkan aplikasi dibuka di dalam pembungkus).
2. **Terapkan → Kelola deployment → ikon pensil**:
   - Jalankan sebagai: **Saya**
   - Yang memiliki akses: **Siapa saja** (wajib; halaman login Google tidak bisa tampil di dalam aplikasi)
   - Versi: **Versi baru** → **Terapkan**

## 2. Upload ke GitHub Pages (gratis, sekali)

1. Buat akun di https://github.com (gratis), lalu login.
2. Klik **+** (kanan atas) → **New repository**.
   - Repository name: `elpi-cert`
   - Pilih **Public** → **Create repository**.
3. Di halaman repository baru, klik **uploading an existing file**.
4. Seret **semua isi folder ini** (index.html, manifest.webmanifest, sw.js, PANDUAN.md, dan folder `icons`)
   ke halaman tersebut → klik **Commit changes**.
5. Buka **Settings → Pages**:
   - Source: **Deploy from a branch**
   - Branch: **main**, folder **/ (root)** → **Save**
6. Tunggu 1–2 menit. Alamat aplikasi akan tampil di halaman itu, misalnya:
   `https://namaakun.github.io/elpi-cert/`

Catatan: repository ini hanya berisi pembungkus dan link aplikasi, tanpa data sertifikat.
Data tetap terlindungi password aplikasi.

## 3. Install di HP / laptop

- **Android (Chrome):** buka alamat GitHub Pages di atas → ketuk **Install** pada banner yang muncul,
  atau menu **⋮ → Install aplikasi / Tambahkan ke layar utama**.
- **iPhone / iPad (Safari):** buka alamatnya → ikon **Bagikan** → **Tambah ke Layar Utama**.
- **Laptop (Chrome / Edge):** buka alamatnya → klik ikon **Install** di ujung kanan bilah alamat.

Bagikan alamat GitHub Pages tersebut ke tim; masing-masing cukup install sekali dan login dengan password aplikasi.

## Perawatan

- Update fitur di Apps Script → otomatis ikut di aplikasi, tidak perlu install ulang.
- Bila link `/exec` Apps Script berubah (misalnya membuat deployment baru), ubah baris `APP_URL` di
  `index.html` langsung di GitHub (buka file → ikon pensil → simpan dengan **Commit changes**).
- Bar biru "Aplikasi ini dibuat oleh pengguna Google Apps Script" dipasang Google dan tetap muncul;
  pengguna bisa menutupnya dengan tanda ×.
- Login password diminta sekali di aplikasi (terpisah dari login di browser biasa).
