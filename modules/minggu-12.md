# Minggu 12 — Pengenalan Tailwind CSS

> **Topik:** Berkenalan dengan Tailwind CSS — framework CSS utility-first yang mengubah cara menulis style.
> **Output akhir:** Satu halaman HTML yang sebelumnya ditulis dengan CSS manual diubah menggunakan Tailwind CSS.

---

## Daftar Isi

1. [Persiapan](#1-persiapan)
2. [Konsep: Apa Itu Tailwind CSS?](#2-konsep-apa-itu-tailwind-css)
3. [Aktivitas 1 — Setup Tailwind di Proyek](#3-aktivitas-1--setup-tailwind-di-proyek)
4. [Aktivitas 2 — Eksplorasi Utility Class Dasar](#4-aktivitas-2--eksplorasi-utility-class-dasar)
5. [Aktivitas 3 — Konversi: CSS Manual ke Tailwind](#5-aktivitas-3--konversi-css-manual-ke-tailwind)
6. [Aktivitas 4 — Layout dengan Tailwind: Flexbox & Grid](#6-aktivitas-4--layout-dengan-tailwind-flexbox--grid)
7. [Latihan Mandiri](#7-latihan-mandiri)
8. [Troubleshooting](#8-troubleshooting)

---

## 1. Persiapan

### Yang Anda Butuhkan

- VSCode dengan Live Server.
- File HTML dari minggu sebelumnya (atau buat baru).
- Browser dengan DevTools.

### Catatan Penting

> **Tailwind CSS bukan bahasa pemrograman** — ini adalah kumpulan **class CSS pendek** yang sudah ditulis untuk Anda. Sebagai contoh, alih-alih menulis `font-size: 18px; font-weight: bold;`, Anda cukup menulis `class="text-lg font-bold"`.

---

## 2. Konsep: Apa Itu Tailwind CSS?

### CSS Tradisional vs Tailwind CSS

**CSS Tradisional:**

```css
/* Di file terpisah (.css) */
.card {
    background-color: white;
    border-radius: 8px;
    padding: 16px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.card-title {
    font-size: 1.25rem;
    font-weight: bold;
    color: #333;
    margin-bottom: 8px;
}
```

**Dengan Tailwind:**

```html
<!-- Tidak perlu file CSS terpisah — semua style di dalam class HTML -->
<div class="bg-white rounded-lg p-4 shadow-md">
    <h2 class="text-xl font-bold text-gray-800 mb-2">Judul Card</h2>
</div>
```

### Mengapa Tailwind?

| Kelebihan | Penjelasan |
|---|---|
| Cepat | Tidak perlu bolak-balik ke file CSS |
| Konsisten | Desain system built-in (spacing, warna, ukuran sudah terstandarisasi) |
| Ringan (production) | Hanya class yang dipakai yang masuk ke CSS final |
| Populer | Banyak digunakan industri, bahasa JSX/React mendukung native |

### Kapan CSS Tradisional Tetap Berguna?

- Untuk memahami dasar styling (yang sudah Anda pelajari di minggu 5–7).
- Untuk selector kompleks yang sulit dijangkau class utility.
- Tailwind **bukan pengganti** CSS — ini **pendekatan berbeda** untuk menulis CSS.

---

## 3. Aktivitas 1 — Setup Tailwind di Proyek

### Cara Termudah: CDN

Untuk tujuan belajar (dan proyek semester ini), kita menggunakan **CDN** — cara paling cepat tanpa instalasi.

**Langkah 1:** Buat file baru `minggu12.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minggu 12 — Tailwind CSS</title>
    <!-- Tailwind CSS via CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 text-gray-800">
    <h1 class="text-3xl font-bold text-center py-10">Halo, Tailwind CSS!</h1>
</body>
</html>
```

**Langkah 2:** Buka dengan Live Server. Jika halaman berlatar abu-abu dengan judul besar, Tailwind sudah berhasil dimuat!

<!-- screenshot:tailwind-setup -->
> **📸 Screenshot:** Tampilkan halaman dengan latar abu-abu terang dan teks judul besar yang sudah ter-styling oleh Tailwind.

### Verifikasi dengan DevTools

Buka DevTools → tab **Elements** → inspect pada elemen `<h1>`. Anda akan melihat class Tailwind dikonversi menjadi CSS oleh JavaScript CDN.

> **Catatan CDN:** CDN ini cocok untuk开发 dan belajar. Untuk proyek production, Tailwind biasanya diinstal via npm dan di-build. Kita tidak perlu khawatir untuk modul ini.

---

## 4. Aktivitas 2 — Eksplorasi Utility Class Dasar

### Kategori Class Utama Tailwind

Berikut panduan cepat kategori class yang paling sering dipakai:

#### Layout & Spacing

```html
<!-- Padding (p = semua sisi, px = horizontal, py = vertical, pt/pb/pl/pr = per sisi) -->
<div class="p-4">Padding 16px semua sisi</div>
<div class="px-6 py-2">Padding horizontal 24px, vertical 8px</div>

<!-- Margin (m = semua sisi, mx = horizontal, my = vertical) -->
<div class="m-4">Margin 16px semua sisi</div>
<div class="mx-auto">Margin horizontal auto (untuk center) -->

<!-- Skala spacing Tailwind: 0, 0.5, 1, 1.5, 2, 3, 4, 5, 6, 7, 8, 9, 10, ... -->
<!-- Angka × 4 = pixel. Jadi: p-1 = 4px, p-2 = 8px, p-4 = 16px, p-8 = 32px -->
```

#### Typography

```html
<!-- Ukuran teks -->
<h1 class="text-4xl">Judul Besar (36px)</h1>
<h2 class="text-2xl">Judul Sedang (24px)</h2>
<p class="text-base">Teks normal (16px)</p>
<p class="text-sm">Teks kecil (14px)</p>

<!-- Berat teks -->
<p class="font-bold">Tebal</p>
<p class="font-semibold">Agak tebal</p>
<p class="font-normal">Normal</p>
<p class="font-light">Tipis</p>

<!-- Warna teks -->
<p class="text-red-500">Merah</p>
<p class="text-blue-600">Biru</p>
<p class="text-green-700">Hijau</p>

<!-- Align -->
<p class="text-center">Tengah</p>
<p class="text-right">Kanan</p>
```

#### Warna & Background

```html
<!-- Background color -->
<div class="bg-white">Latar putih</div>
<div class="bg-blue-500">Latar biru</div>
<div class="bg-gray-200">Latar abu-abu terang</div>

<!-- Warna Tailwind: 50 (paling terang) sampai 950 (paling gelap) -->
<!-- Contoh: blue-100 sangat terang, blue-900 sangat gelap -->
```

#### Border & Rounded

```html
<div class="border border-gray-300">Batas abu-abu tipis</div>
<div class="border-2 border-red-500">Batas merah tebal 2px</div>
<div class="rounded-lg">Sudut membulat besar</div>
<div class="rounded-full">Lingkaran penuh</div>
```

#### Responsive (Mobile-First)

```html
<!-- Dasar: mobile -->
<!-- sm: ≥ 640px, md: ≥ 768px, lg: ≥ 1024px, xl: ≥ 1280px -->
<div class="text-sm md:text-base lg:text-lg">
    Teks kecil di HP, sedang di tablet, besar di desktop
</div>

<div class="flex flex-col md:flex-row">
    <!-- Vertikal di HP, horizontal di tablet ke atas -->
    <div class="w-full md:w-1/2">Kolom 1</div>
    <div class="w-full md:w-1/2">Kolom 2</div>
</div>
```

### Coba Sendiri: Playground

**Langkah 1:** Tambahkan kode berikut ke `minggu12.html`:

```html
<body class="bg-gray-100 text-gray-800 p-6">
    <!-- Header -->
    <header class="bg-blue-600 text-white p-4 rounded-lg mb-6">
        <h1 class="text-2xl font-bold">Tailwind Playground</h1>
        <p class="text-blue-100">Mencoba utility class dasar</p>
    </header>

    <!-- Kartu contoh -->
    <div class="bg-white rounded-lg shadow-md p-6 mb-4">
        <h2 class="text-xl font-semibold text-gray-800 mb-2">Kartu Contoh</h2>
        <p class="text-gray-600 mb-4">Ini adalah kartu dengan padding, shadow, dan rounded corners — semua dari class Tailwind.</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
            Klik Saya
        </button>
    </div>

    <!-- Daftar dengan warna -->
    <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-semibold text-gray-800 mb-2">Daftar Warna</h2>
        <div class="flex flex-wrap gap-2">
            <span class="bg-red-100 text-red-800 px-3 py-1 rounded-full text-sm">Red</span>
            <span class="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-sm">Blue</span>
            <span class="bg-green-100 text-green-800 px-3 py-1 rounded-full text-sm">Green</span>
            <span class="bg-yellow-100 text-yellow-800 px-3 py-1 rounded-full text-sm">Yellow</span>
            <span class="bg-purple-100 text-purple-800 px-3 py-1 rounded-full text-sm">Purple</span>
            <span class="bg-pink-100 text-pink-800 px-3 py-1 rounded-full text-sm">Pink</span>
        </div>
    </div>
</body>
```

**Langkah 2:** Refresh dan lihat hasilnya.

<!-- screenshot:tailwind-playground -->
> **📸 Screenshot:** Tampilkan halaman dengan kartu, tombol, dan label warna yang sudah di-style oleh Tailwind.

---

## 5. Aktivitas 3 — Konversi: CSS Manual ke Tailwind

### Tujuan

Mengubah halaman yang sebelumnya ditulis dengan CSS manual menjadi Tailwind CSS.

### Langkah-langkah Ikuti Saya

**Langkah 1:** Berikut contoh kartu profil dengan CSS manual (ini yang mungkin sudah Anda buat di minggu 5–6):

```html
<!-- VERSI CSS MANUAL -->
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kartu Profil — CSS Manual</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f2f5;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }
        .card {
            background-color: white;
            border-radius: 12px;
            padding: 32px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            text-align: center;
            max-width: 320px;
        }
        .avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background-color: #4A90D9;
            margin: 0 auto 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 40px;
            color: white;
        }
        .name {
            font-size: 24px;
            font-weight: bold;
            color: #333;
            margin-bottom: 4px;
        }
        .role {
            font-size: 14px;
            color: #888;
            margin-bottom: 16px;
        }
        .bio {
            font-size: 14px;
            color: #666;
            line-height: 1.6;
            margin-bottom: 20px;
        }
        .btn {
            background-color: #4A90D9;
            color: white;
            border: none;
            padding: 10px 24px;
            border-radius: 8px;
            font-size: 14px;
            cursor: pointer;
        }
        .btn:hover {
            background-color: #357ABD;
        }
    </style>
</head>
<body>
    <div class="card">
        <div class="avatar">B</div>
        <div class="name">Budi Santoso</div>
        <div class="role">Mahasiswa D3 Informatika</div>
        <div class="bio">Siswa semester 1 yang tertarik dengan web design dan UI/UX.</div>
        <button class="btn">Hubungi</button>
    </div>
</body>
</html>
```

**Langkah 2:** Sekarang, buat file `kartu-profil-tailwind.html` — versi yang sama dengan Tailwind:

```html
<!-- VERSI TAILWIND CSS -->
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kartu Profil — Tailwind CSS</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 flex justify-center items-center min-h-screen">
    <div class="bg-white rounded-xl p-8 shadow-lg text-center max-w-xs">
        <!-- Avatar -->
        <div class="w-24 h-24 rounded-full bg-blue-500 mx-auto mb-4 flex items-center justify-center text-4xl text-white font-bold">
            B
        </div>
        <!-- Nama -->
        <div class="text-2xl font-bold text-gray-800 mb-1">Budi Santoso</div>
        <!-- Role -->
        <div class="text-sm text-gray-400 mb-4">Mahasiswa D3 Informatika</div>
        <!-- Bio -->
        <div class="text-sm text-gray-500 leading-relaxed mb-5">
            Siswa semester 1 yang tertarik dengan web design dan UI/UX.
        </div>
        <!-- Tombol -->
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-semibold py-2 px-6 rounded-lg transition duration-200">
            Hubungi
        </button>
    </div>
</body>
</html>
```

**Langkah 3:** Bandingkan keduanya — buka masing-masing di tab browser berbeda.

### Pemetaan CSS → Tailwind

| CSS Manual | Tailwind Equivalent |
|---|---|
| `font-family: Arial, sans-serif;` | Tidak perlu (sudah default Tailwind) |
| `background-color: #f0f2f5;` | `bg-gray-100` |
| `display: flex;` | `flex` |
| `justify-content: center;` | `justify-center` |
| `align-items: center;` | `items-center` |
| `min-height: 100vh;` | `min-h-screen` |
| `border-radius: 12px;` | `rounded-xl` |
| `padding: 32px;` | `p-8` |
| `box-shadow: 0 4px 6px ...;` | `shadow-lg` |
| `text-align: center;` | `text-center` |
| `max-width: 320px;` | `max-w-xs` |
| `width: 100px; height: 100px;` | `w-24 h-24` |
| `font-size: 24px; font-weight: bold;` | `text-2xl font-bold` |
| `color: #333;` | `text-gray-800` |
| `margin-bottom: 4px;` | `mb-1` |
| `font-size: 14px;` | `text-sm` |
| `color: #888;` | `text-gray-400` |
| `line-height: 1.6;` | `leading-relaxed` |
| `border-radius: 8px;` | `rounded-lg` |
| `:hover { background-color: ... }` | `hover:bg-blue-700` |

<!-- screenshot:kartu-perbandingan -->
> **📸 Screenshot:** Tampilkan kartu profil versi Tailwind — tampilan seharusnya sama atau hampir identik dengan versi CSS manual.

---

## 6. Aktivitas 4 — Layout dengan Tailwind: Flexbox & Grid

### Flexbox dengan Tailwind

**Langkah 1:** Tambahkan kode berikut ke `minggu12.html`:

```html
<!-- Flexbox: Horizontal -->
<h3 class="text-lg font-semibold mt-8 mb-3">Flex Horizontal (baris)</h3>
<div class="flex gap-4 bg-white p-4 rounded-lg shadow">
    <div class="bg-blue-500 text-white p-4 rounded-lg flex-1 text-center">1</div>
    <div class="bg-green-500 text-white p-4 rounded-lg flex-1 text-center">2</div>
    <div class="bg-red-500 text-white p-4 rounded-lg flex-1 text-center">3</div>
</div>

<!-- Flexbox: Responsive — vertikal di HP, horizontal di desktop -->
<h3 class="text-lg font-semibold mt-8 mb-3">Flex Responsive</h3>
<div class="flex flex-col md:flex-row gap-4 bg-white p-4 rounded-lg shadow">
    <div class="bg-purple-500 text-white p-6 rounded-lg md:flex-1 text-center">
        Kolom 1
    </div>
    <div class="bg-yellow-500 text-gray-800 p-6 rounded-lg md:flex-1 text-center">
        Kolom 2
    </div>
    <div class="bg-teal-500 text-white p-6 rounded-lg md:flex-1 text-center">
        Kolom 3
    </div>
</div>
```

### Grid dengan Tailwind

```html
<!-- Grid: 3 kolom -->
<h3 class="text-lg font-semibold mt-8 mb-3">Grid 3 Kolom</h3>
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 bg-white p-4 rounded-lg shadow">
    <div class="bg-indigo-500 text-white p-6 rounded-lg text-center">Card 1</div>
    <div class="bg-indigo-500 text-white p-6 rounded-lg text-center">Card 2</div>
    <div class="bg-indigo-500 text-white p-6 rounded-lg text-center">Card 3</div>
    <div class="bg-indigo-500 text-white p-6 rounded-lg text-center">Card 4</div>
    <div class="bg-indigo-500 text-white p-6 rounded-lg text-center">Card 5</div>
    <div class="bg-indigo-500 text-white p-6 rounded-lg text-center">Card 6</div>
</div>

<!-- Penjelasan grid responsive -->
<!-- grid-cols-1     → 1 kolom di HP -->
<!-- sm:grid-cols-2  → 2 kolom di tablet (≥640px) -->
<!-- lg:grid-cols-3  → 3 kolom di desktop (≥1024px) -->
```

**Langkah 2:** Refresh halaman dan coba resize browser untuk melihat layout responsive.

<!-- screenshot:tailwind-flexbox -->
> **📸 Screenshot:** Tampilkan area flexbox — tiga kotak berwarna dalam satu baris.

<!-- screenshot:tailwind-grid -->
> **📸 Screenshot:** Tampilkan area grid — kotak-kotak card dalam format 3 kolom (atau 2 kolom tergantung ukuran browser).

---

## 7. Latihan Mandiri

### Latihan 1 — Konversi Halaman (Mandiri)

Ambil salah satu halaman HTML yang sudah Anda buat di minggu 5–7 (halaman statis dengan CSS). Buat versi baru menggunakan Tailwind CSS.

**Langkah:**
1. Salin file HTML lama ke file baru.
2. Hapus semua isi `<style>`.
3. Tambahkan CDN Tailwind di `<head>`.
4. Ganti semua selector CSS dengan class Tailwind yang sesuai.

**Expected output:**
- Halaman terlihat sama atau hampir sama dengan versi CSS manual.
- Semua style inline menggunakan class Tailwind, tidak ada `<style>` tersisa (kecuali untuk hal yang sangat spesifik).

<!-- screenshot:latihan1-expected -->
> **📸 Screenshot:** Tampilkan halaman hasil konversi — sisi-kanan versi CSS, sisi-kiri versi Tailwind (atau tab terpisah).

### Latihan 2 — Card Layout (Mandiri)

Buat file `latihan12-2.html` yang menampilkan **3 kartu produk** dalam layout responsive:
1. Setiap kartu memiliki: gambar placeholder (`bg-gray-300` dengan teks "Gambar Produk"), nama produk, harga, dan tombol "Beli".
2. Di mobile: kartu tampil secara vertikal (1 kolom).
3. Di tablet (≥640px): 2 kolom.
4. Di desktop (≥1024px): 3 kolom.

**Gunakan hanya Tailwind CSS** — tidak ada CSS manual.

**Expected output:**
- Tiga kartu tampil rapi dalam grid responsive.
- Tombol "Beli" berwarna (misal biru) dengan efek hover.

<!-- screenshot:latihan2-expected -->
> **📸 Screenshot:** Tampilkan kartu produk responsive — cobalah di berbagai ukuran browser.

### Latihan 3 — Navbar Responsive (Opsional)

Buat file `latihan12-3.html` dengan navbar yang:
1. Horizontal di desktop (logo + navigasi berdampingan).
2. Di mobile: logo di kiri, tombol hamburger di kanan, navigasi muncul saat tombol diklik (gunakan JavaScript dari minggu 11).
3. Semua styling dengan Tailwind CSS.

**Expected output:**
- Navbar terlihat profesional dengan warna dan spacing konsisten.
- Responsive berfungsi dengan benar.

<!-- screenshot:latihan3-expected -->
> **📸 Screenshot:** Tampilkan navbar dalam tampilan desktop dan mobile.

---

## 8. Troubleshooting

### Masalah 1: Style Tailwind tidak muncul

| Cek | Solusi |
|---|---|
| CDN script sudah ada? | Pastikan `<script src="https://cdn.tailwindcss.com"></script>` ada di `<head>` |
| Koneksi internet? | CDN butuh koneksi internet — periksa apakah halaman lain bisa dimuat |
| Class name typo? | Tailwind class sangat spesifk: `bg-blue-500` ≠ `bg-blue-5000` |
| Browser cache? | Tekan `Ctrl + Shift + R` (hard refresh) |

### Masalah 2: Tidak tahu nama class yang tepat

**Solusi:** Gunakan **Tailwind Docs** sebagai referensi:
- [tailwindcss.com/docs](https://tailwindcss.com/docs)
- Cari kategori (misal: "padding", "background color", "text size") → copy-paste class.

**Tips:** Anda tidak perlu menghafal semua class! Bahkan developer profesional selalu membuka dokumentasi.

### Masalah 3: Konflik dengan CSS manual

```html
<!-- ❌ Jangan campur Tailwind dengan style manual yang konflik -->
<style>
    .card { padding: 20px; }
</style>
<div class="card p-4"> ... </div>  <!-- p-4 akan menimpa padding manual? -->

<!-- ✅ Gunakan salah satu: Tailwind SAJA atau CSS manual SAJA -->
<div class="p-5"> ... </div>
```

### Masalah 4: CDN lambat / tidak termuat

```html
<!-- Backup: gunakan versi tertentu jika CDN utama bermasalah -->
<script src="https://cdn.tailwindcss.com/3.4.1"></script>

<!-- Atau, jika tidak ada internet sama sekali, kembali ke CSS manual
     untuk proyek ini. Tailwind bisa di-install via npm nanti. -->
```

### Masalah 5: Class responsive tidak bekerja

```html
<!-- Ingat: Tailwind menggunakan MOBILE-FIRST -->
<!-- Urutan yang benar: default (mobile) → sm → md → lg → xl -->

<!-- ❌ Salah -->
<div class="lg:flex md:flex sm:flex-col flex-row">
    <!-- Browser membaca dari kiri ke kanan, tidak sesuai breakpoint -->
</div>

<!-- ✅ Benar -->
<div class="flex flex-col sm:flex-row md:flex lg:flex">
    <!-- Default: flex-col (mobile) -->
    <!-- ≥640px: sm:flex-row (tambahkan flex) -->
</div>

<!-- Atau cara lebih sederhana -->
<div class="flex flex-col md:flex-row">
    <!-- Default: vertikal, ≥768px: horizontal -->
</div>
```

---

> **⏭️ Selanjutnya:** Minggu 13 — Kita akan berkenalan dengan **React**, framework JavaScript paling populer saat ini. Kita akan memahami konsep **komponen**, **JSX**, dan **props** tanpa membuat aplikasi React yang lengkap.
