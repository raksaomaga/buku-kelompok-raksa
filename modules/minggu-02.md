# Minggu 2 — Figma Dasar & Pengantar UI/UX

---

| Item | Detail |
|---|---|
| **Minggu ke-** | 2 |
| **Topik** | Figma dasar (wireframe & mockup), prinsip dasar UI/UX (heuristik, hierarchy, aksesibilitas) |
| **Output** | Wireframe 1 halaman web di Figma |
| **Durasi** | 3 jam (1 jam workshop + 2 jam praktikum mandiri) |
| **Prasyarat** | Akun Figma gratis (https://www.figma.com), akun GitHub (dari Minggu 1) |
| **Tools** | Figma (browser atau desktop app), browser untuk referensi |

---

## Tujuan Pembelajaran

Setelah menyelesaikan modul ini, kamu akan mampu:

1. Mengoperasikan antarmuka dasar Figma (frame, shape, text, layers).
2. Membuat wireframe sederhana untuk satu halaman web.
3. Menjelaskan 3 konsep dasar UI/UX: **heuristik**, **hierarchy**, dan **aksesibilitas**.
4. Menerapkan konsep UI/UX tersebut ke dalam desain wireframe.

---

## Bagian A — Live Coding: Pengenalan Figma

> **Ikuti langkah-langkah berikut secara berurutan.**

### A.1. Akses Figma

1. Buka **https://www.figma.com** di browser.
2. Klik **Log in** → masuk dengan akun yang sudah dibuat (atau daftar jika belum).
3. Kamu akan melihat halaman **Drafts** — ini adalah ruang kerja default.

**💡 Tips:** Figma bisa digunakan langsung di browser, tapi lebih nyaman menggunakan **Figma Desktop App** (download dari https://www.figma.com/downloads/).

### A.2. Membuat File & Frame Pertama

1. Klik **New design file** (tombol biru di pojok kanan atas).
2. Di canvas kosong, tekan **F** di keyboard → arahkan mouse ke canvas → drag untuk membuat sebuah **Frame**.
3. Di panel **Design** (kanan), atur ukuran frame:
   - **Preset:** pilih **Web 1920** (1920 × 1080 px) atau **MacBook Air** untuk ukuran layar laptop.

<!-- Screenshot placeholder: Canvas Figma dengan frame kosong berukuran Web 1920 -->
> **📸 Screenshot B1:** Canvas Figma dengan satu frame kosong — pastikan panel Design di kanan menunjukkan ukuran frame (misal: 1440 × 900 untuk MacBook Air).

### A.3. Kenali Tools Dasar Figma

Pelajari toolbar di bagian atas canvas:

| Shortcut | Tool | Fungsi |
|---|---|---|
| `V` | Move | Memilih & memindahkan objek |
| `F` | Frame | Membuat frame (artboard) |
| `R` | Rectangle | Membuat kotak persegi |
| `O` | Ellipse | Membuat lingkaran/oval |
| `T` | Text | Membuat teks |
| `L` | Line | Membuat garis |
| `P` | Pen | Membuat bentuk bebas |
| `Ctrl + Z` | Undo | Membatalkan aksi terakhir |

**Latihan cepat:** Di dalam frame yang sudah dibuat, coba:
1. Tekan **R** → drag di dalam frame untuk membuat kotak.
2. Tekan **T** → klik di dalam frame → ketik "Hello Figma".
3. Tekan **V** → klik objek untuk memilih → drag untuk memindahkan.

### A.4. Panel Layers & Properties

Di panel kiri ada **Layers** — setiap objek yang kamu buat akan muncul sebagai layer.

- **Double-click** layer untuk mengganti nama (misal: rename "Rectangle 1" jadi "Header Background").
- **Urutan layer** = urutan di atas canvas (layer di atas menimpa layer di bawah).

Di panel kanan ada **Design Properties** — ubah:
- **Fill:** warna isi objek
- **Stroke:** garis tepi
- **Corner Radius:** sudut membulat
- **Font & Size:** untuk objek teks

**Latihan cepat:** Ubah warna kotak yang dibuat tadi menjadi biru, dan ubah teks "Hello Figma" menjadi ukuran 24px.

---

## Bagian B — Live Coding: Membuat Wireframe Halaman Web

> **Wireframe** = sketsa rendah detail yang menunjukkan struktur dan penempatan elemen halaman. Bukan desain final.

### B.1. Apa Itu Wireframe?

| Tingkat Detail | Nama | Fungsi |
|---|---|---|
| Rendah | **Wireframe** | Menunjukkan layout & struktur (tanpa warna/font detail) |
| Sedang | **Mockup** | Menambahkan warna, font, gambar (visual lebih realistis) |
| Tinggi | **Prototype** | Interaktif — bisa diklik dan dinavigasi |

**Kita mulai dari wireframe** (tingkat rendah) karena fokusnya adalah **struktur**, bukan tampilan cantik.

### B.2. Live Coding: Wireframe Halaman "Profil Diri"

Kita akan mendesain wireframe halaman web profil diri sederhana. Ikuti langkah berikut:

#### Langkah 1: Buat Frame untuk Mobile

1. Tekan **F** → pilih preset **iPhone 14** (390 × 844 px) di panel kanan.
2. Rename layer frame ini jadi `Wireframe - Profil Diri (Mobile)`.

#### Langkah 2: Header / Navigasi

1. Tekan **R** → buat rectangle di bagian atas frame.
   - Lebar: isi full (390 px), Tinggi: ~60 px.
   - Rename layer jadi `Header`.
   - Warna: abu-abu terang (#E0E0E0) — wireframe menggunakan warna netral.
2. Tekan **T** → klik di atas rectangle header → ketik `Nama Kamu`.
   - Posisikan di kiri header.
   - Font: regular, 16px.

#### Langkah 3: Hero / Foto Profil

1. Tekan **O** → buat lingkaran di bawah header.
   - Ukuran: 120 × 120 px, posisi center horizontal.
   - Warna: abu-abu (#CCCCCC).
   - Rename layer jadi `Foto Profil`.
2. Tekan **T** → di bawah lingkaran, ketik:
   ```
   [Nama Lengkap]
   Mahasiswa D3 Informatika
   ```
   - Font: bold untuk nama, regular untuk keterangan.

#### Langkah 4: Bagian "Tentang Saya"

1. Tekan **T** → ketik `Tentang Saya` sebagai judul section.
   - Font: bold, 18px.
2. Tekan **R** → buat 2-3 rectangle kecil di bawah judul sebagai placeholder paragraf:
   - Lebar: hampir full (misal: 350 px), Tinggi: ~16 px × 3 baris.
   - Warna: abu-abu sangat terang (#F0F0F0).
   - Rename layer: `Paragraf Placeholder 1`, `Paragraf Placeholder 2`, dst.

#### Langkah 5: Bagian "Keahlian"

1. Ketik judul `Keahlian`.
2. Buat 3-4 rectangle kecil sebagai placeholder "skill card":
   - Ukuran: ~160 × 80 px, sejajar horizontal (atau 2×2 grid).
   - Warna: abu-abu (#E8E8E8).
   - Di dalam masing-masing, tambahkan teks placeholder: `Skill 1`, `Skill 2`, dst.

#### Langkah 6: Footer

1. Tekan **R** → buat rectangle di bagian bawah frame.
   - Lebar: full (390 px), Tinggi: ~50 px.
   - Warna: abu-abu gelap (#999999).
2. Tambahkan teks: `© 2026 Nama Kamu`.

### Hasil Wireframe

<!-- Screenshot placeholder: Wireframe halaman Profil Diri di Figma -->
> **📸 Screenshot B2:** Wireframe halaman "Profil Diri" di Figma — pastikan terlihat section: Header, Foto Profil, Tentang Saya, Keahlian, dan Footer dengan rapi.

**✅ Ceklis:** Apakah wireframe kamu memiliki minimal 5 section (Header, Foto, Tentang Saya, Keahlian, Footer)?

---

## Bagian C — Pemahaman: 3 Konsep Dasar UI/UX

### C.1. Heuristik (Evaluasi Kegunaan)

**Heuristik** = aturan umum desain yang membantu agar UI mudah digunakan. Kita pelajari 3 heuristik paling relevan untuk pemula:

| # | Heuristik | Penjelasan Singkat | Contoh Penerapan di Wireframe |
|---|---|---|---|
| 1 | **Visibility of System Status** | Pengguna harus tahu apa yang sedang terjadi | Tambahkan indikator loading atau progress saat halaman memuat |
| 2 | **Match Between System and Real World** | Gunakan bahasa yang dipahami pengguna | Judul "Tentang Saya" lebih jelas daripada "Bio Data Seksi 4" |
| 3 | **Error Prevention** | Cegah kesalahan pengguna sebelum terjadi | Form input harus punya placeholder/label yang jelas |

**📌 Catatan:** Ada 10 heuristik Nielsen Norman Group lengkapnya. Tiga di atas adalah yang paling sering ditemui dan paling mudah diterapkan untuk pemula.

### C.2. Hierarchy (Hierarki Visual)

**Hierarchy** = pengaturan elemen agar mata pembaca tahu mana yang dilihat **duluan**.

Ada dua jenis hierarchy:

| Jenis | Fungsi | Contoh |
|---|---|---|
| **Hierarki ukuran** | Elemen lebih besar = lebih penting | Nama besar di atas, deskripsi kecil di bawah |
| **Hierarki warna** | Warna kontras = menarik perhatian | Tombol "Hubungi Saya" berwarna biru di antara elemen abu-abu |

**Latihan di Figma:**
1. Di wireframe yang sudah dibuat, pastikan:
   - Nama di bagian Hero **lebih besar** dari teks deskripsi.
   - Judul section (Tentang Saya, Keahlian) **lebih besar** dari konten di bawahnya.
2. Jika belum, ubah ukuran teks di Figma untuk mencerminkan hierarchy.

### C.3. Aksesibilitas (Accessibility)

**Aksesibilitas** = desain yang bisa digunakan oleh **semua orang**, termasuk yang memiliki keterbatasan (penggunaan layar, penglihatan rendah, dsb).

**3 hal yang harus diperhatikan pemula:**

| Aspek | Yang Harus Diperhatikan |
|---|---|
| **Kontras warna** | Teks harus terbaca dengan latar belakang. Rasio kontras minimal **4.5:1** untuk teks normal. |
| **Ukuran teks** | Minimal **16 px** untuk teks body. Jangan gunakan ukuran yang terlalu kecil. |
| **Struktur heading** | Gunakan heading secara berurutan (`h1` → `h2` → `h3`), jangan loncat-loncat. |

**📌 Tool bantuan:** Gunakan **WebAIM Contrast Checker** (https://webaim.org/resources/contrastchecker/) untuk mengecek kontras warna.

**Latihan di Figma:**
1. Di wireframe, pastikan warna teks di atas background cukup kontras.
2. Jika menggunakan warna abu-abu di atas putih, pastikan tidak terlalu tipis/pucat.

---

## Bagian D — Latihan Mandiri

> Kerjakan latihan ini **secara mandiri**.

### D.1. Latihan 1 — Wireframe Halaman "Portfolio" (Desktop)

Buat wireframe baru untuk halaman **portofolio** di Figma dengan spesifikasi:

- **Frame:** Web 1920 (1920 × 1080 px).
- **Section yang wajib ada:**
  1. **Navbar** — logo di kiri, 3-4 menu di kanan (Home, Portofolio, About, Contact).
  2. **Hero** — judul besar + tombol "Lihat Proyek".
  3. **Grid Proyek** — minimal 6 kotak (card) yang mewakili proyek.
  4. **Tentang Saya** — foto placeholder + teks deskripsi.
  5. **Footer** — copyright & ikon media sosial placeholder.

**Tips:**
- Gunakan **Frame** → pilih preset **Web 1920**.
- Untuk grid proyek, buat 1 card lalu **Ctrl + D** (duplicate) untuk duplikasi.
- Gunakan warna netral (abu-abu) untuk wireframe.

**✅ Ceklis:**
- [ ] Wireframe memiliki minimal 5 section.
- [ ] Setiap section memiliki judul yang jelas.
- [ ] Ukuran elemen mencerminkan hierarchy (judul lebih besar dari konten).
- [ ] Layer sudah di-rename dengan nama yang deskriptif.

<!-- Screenshot placeholder: Wireframe halaman Portfolio di Figma -->
> **📸 Screenshot B3:** Wireframe halaman Portfolio di Figma (tampilan penuh) — pastikan terlihat Navbar, Hero, Grid Proyek, Tentang Saya, dan Footer.

### D.2. Latihan 2 — Evaluasi Heuristik pada Website Nyata

1. Buka salah satu website berikut di browser:
   - https://www.google.com
   - https://www.tokopedia.com
   - https://www.instagram.com (halaman login)
2. Evaluasi website tersebut menggunakan **3 heuristik** yang sudah dipelajari:

| Heuristik | Website Menjalankan dengan Baik? | Bukti / Contoh |
|---|---|---|
| Visibility of System Status | Ya / Tidak | [tulis contoh spesifik] |
| Match Between System and Real World | Ya / Tidak | [tulis contoh spesifik] |
| Error Prevention | Ya / Tidak | [tulis contoh spesifik] |

3. Tulis hasil evaluasi dalam format di atas dan siapkan untuk dibahas di pertemuan berikutnya.

### D.3. Latihan 3 — Cek Kontras Aksesibilitas

1. Pilih 2 kombinasi warna dari wireframe yang kamu buat.
2. Buka **https://webaim.org/resources/contrastchecker/**.
3. Masukkan warna teks dan background → cek rasio kontras.
4. Pastikan minimal satu kombinasi memenuhi **WCAG AA** (4.5:1 untuk normal text).

<!-- Screenshot placeholder: WebAIM Contrast Checker dengan hasil pengecekan -->
> **📸 Screenshot B4:** WebAIM Contrast Checker — pastikan terlihat rasio kontras dan status "Pass" atau "Fail".

---

## Bagian E — Ringkasan & Checklist

### Yang sudah kamu pelajari hari ini:

- [ ] Mengoperasikan Figma: membuat frame, shapes, teks, mengatur properties.
- [ ] Membuat wireframe sederhana untuk halaman web.
- [ ] 3 konsep dasar UI/UX: Heuristik, Hierarchy, Aksesibilitas.
- [ ] Menerapkan hierarchy dan aksesibilitas di wireframe.
- [ ] Mengecek kontras warna dengan WebAIM Contrast Checker.

### Jangan lupa:

- [ ] Wireframe sudah disimpan di Figma (otomatis tersimpan).
- [ ] Nama layer sudah di-rename dengan rapi.
- [ ] Wireframe memenuhi checklist (section lengkap, hierarchy jelas).
- [ ] Hasil evaluasi heuristik website nyata sudah ditulis.

---

## Troubleshooting

| Masalah | Solusi |
|---|---|
| Figma tidak bisa dibuka di browser | Gunakan Figma Desktop App, atau coba browser Chrome/Firefox versi terbaru |
| Frame tidak bisa dibuat | Tekan shortcut **F** (huruf F, bukan function key) untuk aktifkan tool Frame |
| Objek tidak bisa dipindahkan | Pastikan tool **Move (V)** aktif, bukan tool lain |
| Layer tidak muncul di panel | Scroll panel Layers di sebelah kiri canvas — mungkin tersembunyi di bawah |
| Perubahan tidak tersimpan | Figma auto-save, tapi pastikan koneksi internet stabil. Cek ikon cloud di pojok kanan atas |
| Tidak bisa membuat duplikat | Select objek → tekan **Ctrl + D** (Windows) atau **Cmd + D** (Mac) |

---

## Referensi

- [Figma Help Center — Getting Started](https://help.figma.com/hc/en-us/articles/360040318013)
- [Nielsen Norman Group — 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Figma Wireframe Templates (Community)](https://www.figma.com/community/tag/wireframe)
