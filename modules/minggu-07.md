# Minggu 7 — CSS Layout: Grid & Responsive Design (Media Query)

**Mata Kuliah:** Pengenalan Workshop Desain Web
**Program Studi:** D3 Informatika — Semester 1
**Durasi:** 3 jam kelas: 1 jam teori dan 2 jam praktik

---

## Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa diharapkan dapat:

1. Menjelaskan konsep CSS Grid untuk layout dua dimensi.
2. Membuat layout grid dengan baris dan kolom.
3. Menggunakan media query untuk membuat halaman responsif.
4. Menerapkan prinsip mobile-first.
5. Membangun halaman yang tampil baik di layar besar maupun kecil.

---

## Alat yang Dibutuhkan

- Laptop dengan **VSCode** terpasang.
- Extension **Live Server**.
- Browser modern.
- Folder proyek `latihan-grid` (buat baru).

---

## Ringkasan Teori (Minimal)

### CSS Grid

Grid adalah sistem layout **dua dimensi** — mengatur baris **dan** kolom sekaligus. Berbeda dengan flexbox yang satu dimensi, grid sangat cocok untuk layout halaman penuh (header, sidebar, konten, footer).

```
+--------------------------------------------------+
|  Grid Container (display: grid)                  |
|  +--------+  +--------+  +--------+             |
|  |  col 1 |  |  col 2 |  |  col 3 |   <- baris 1
|  +--------+  +--------+  +--------+             |
|  +--------+  +--------+  +--------+             |
|  |  col 1 |  |  col 2 |  |  col 3 |   <- baris 2
|  +--------+  +--------+  +--------+             |
+--------------------------------------------------+
```

### Media Query

Media query memungkinkan CSS **berubah** berdasarkan ukuran layar perangkat. Ini adalah kunci dari **responsive design**.

```css
@media (max-width: 768px) {
    /* Aturan ini hanya berlaku saat layar <= 768px */
}
```

### Breakpoint Umum

| Breakpoint | Target Perangkat |
|---|---|
| `max-width: 600px` | Ponsel |
| `max-width: 768px` | Tablet |
| `max-width: 992px` | Laptop kecil |
| `min-width: 1200px` | Desktop besar |

---

## Praktikum 1 — Menyiapkan Proyek

**Langkah 1:** Buat folder `latihan-grid` di VSCode.

**Langkah 2:** Buat file `index.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Latihan Grid</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="grid">
        <div class="cell">1</div>
        <div class="cell">2</div>
        <div class="cell">3</div>
        <div class="cell">4</div>
        <div class="cell">5</div>
        <div class="cell">6</div>
    </div>
</body>
</html>
```

**Langkah 3:** Buat file `style.css`:

```css
.grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;  /* 3 kolom sama lebar */
    gap: 10px;
}

.cell {
    background-color: lightcoral;
    border: 2px solid darkred;
    padding: 30px;
    text-align: center;
    font-size: 20px;
}
```

**Langkah 4:** Buka dengan Live Server. Enam sel tersusun dalam **3 kolom × 2 baris**.

---

## Praktikum 2 — Mengatur Kolom dan Baris

**Langkah 1:** Ubah `grid-template-columns` menjadi berbagai variasi:

```css
.grid {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;  /* kolom tengah 2x lebih lebar */
    gap: 10px;
}
```

**Langkah 2:** Coba juga dengan satuan tetap:

```css
.grid {
    display: grid;
    grid-template-columns: 200px 1fr;  /* kolom pertama 200px, sisanya fleksibel */
    gap: 10px;
}
```

**Langkah 3:** Tambahkan `grid-template-rows`:

```css
.grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 100px 200px;  /* baris 1 = 100px, baris 2 = 200px */
    gap: 10px;
}
```

**Langkah 4:** Amati bagaimana tinggi baris berbeda.

> **Tips:** `1fr` berarti "1 fraksi dari ruang yang tersedia". `1fr 2fr` berarti kolom kedua dua kali lebih lebar dari kolom pertama.

---

## Praktikum 3 — Menempatkan Item di Grid

**Langkah 1:** Buat file `layout.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Layout Grid</title>
    <link rel="stylesheet" href="layout.css">
</head>
<body>
    <div class="layout">
        <header class="header">Header</header>
        <nav class="nav">Navigasi</nav>
        <main class="main">Konten Utama</main>
        <aside class="aside">Sidebar</aside>
        <footer class="footer">Footer</footer>
    </div>
</body>
</html>
```

**Langkah 2:** Buat `layout.css`:

```css
.layout {
    display: grid;
    grid-template-columns: 1fr 3fr;   /* 2 kolom: sidebar + konten */
    grid-template-rows: auto auto 1fr auto;
    gap: 10px;
    min-height: 100vh;
}

.header {
    grid-column: 1 / -1;   /* header membentang semua kolom */
    background-color: #2c3e50;
    color: white;
    padding: 20px;
}

.nav {
    background-color: #3498db;
    color: white;
    padding: 20px;
}

.main {
    background-color: #ecf0f1;
    padding: 20px;
}

.aside {
    background-color: #e67e22;
    color: white;
    padding: 20px;
}

.footer {
    grid-column: 1 / -1;   /* footer membentang semua kolom */
    background-color: #2c3e50;
    color: white;
    padding: 20px;
    text-align: center;
}
```

**Langkah 3:** Buka di Live Server. Anda memiliki layout halaman lengkap: header di atas, sidebar kiri, konten tengah, dan footer di bawah.

**Langkah 4:** Coba ubah `grid-template-columns` menjadi `1fr 2fr` dan amati perubahannya.

> **Catatan:** `grid-column: 1 / -1` berarti item membentang dari kolom 1 sampai kolom terakhir.

---

## Praktikum 4 — Pengenalan Media Query

**Langkah 1:** Buat file `responsive.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive</title>
    <link rel="stylesheet" href="responsive.css">
</head>
<body>
    <h1>Halaman Responsif</h1>
    <div class="konten">
        <div class="kartu">Kartu 1</div>
        <div class="kartu">Kartu 2</div>
        <div class="kartu">Kartu 3</div>
    </div>
</body>
</html>
```

**Langkah 2:** Buat `responsive.css`:

```css
body {
    font-family: Arial, sans-serif;
    margin: 20px;
}

.konten {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;  /* 3 kolom di layar besar */
    gap: 15px;
}

.kartu {
    background-color: #3498db;
    color: white;
    padding: 40px;
    text-align: center;
    border-radius: 8px;
}

/* Media query: saat layar <= 768px (tablet) */
@media (max-width: 768px) {
    .konten {
        grid-template-columns: 1fr 1fr;  /* jadi 2 kolom */
    }
}

/* Media query: saat layar <= 480px (ponsel) */
@media (max-width: 480px) {
    .konten {
        grid-template-columns: 1fr;  /* jadi 1 kolom */
    }
    h1 {
        font-size: 20px;
    }
}
```

**Langkah 3:** Buka di Live Server. Persempit dan lebarkan jendela browser. Amati bagaimana jumlah kolom berubah: 3 → 2 → 1.

> **Tips:** Gunakan DevTools (F12) → ikon perangkat (toggle device toolbar) untuk mensimulasikan layar ponsel/tablet.

---

## Praktikum 5 — Mobile-First

Prinsip **mobile-first**: tulis CSS untuk layar kecil dulu, lalu gunakan `min-width` untuk layar yang lebih besar.

**Langkah 1:** Buat file `mobile-first.css`:

```css
/* Default: untuk ponsel (layar kecil) */
.konten {
    display: grid;
    grid-template-columns: 1fr;  /* 1 kolom di ponsel */
    gap: 15px;
}

.kartu {
    background-color: #27ae60;
    color: white;
    padding: 40px;
    text-align: center;
    border-radius: 8px;
}

/* Layar >= 600px (tablet) */
@media (min-width: 600px) {
    .konten {
        grid-template-columns: 1fr 1fr;  /* 2 kolom */
    }
}

/* Layar >= 992px (desktop) */
@media (min-width: 992px) {
    .konten {
        grid-template-columns: 1fr 1fr 1fr;  /* 3 kolom */
    }
}
```

**Langkah 2:** Buat file `mobile-first.html` yang memakai CSS ini (salin dari `responsive.html`, ganti nama file CSS).

**Langkah 3:** Buka di Live Server dan amati: di layar kecil tampil 1 kolom, makin lebar makin banyak kolom.

> **Perbedaan:** Mobile-first memakai `min-width` (dari kecil ke besar), sedangkan pendekatan biasa memakai `max-width` (dari besar ke kecil). Keduanya sah, mobile-first lebih disarankan.

---

## Praktikum 6 — Membuat Layout Responsif Lengkap

**Langkah 1:** Buat file `halaman.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halaman Responsif Lengkap</title>
    <link rel="stylesheet" href="halaman.css">
</head>
<body>
    <header class="header">
        <h1>Website Saya</h1>
        <nav>
            <ul class="menu">
                <li><a href="#">Beranda</a></li>
                <li><a href="#">Tentang</a></li>
                <li><a href="#">Kontak</a></li>
            </ul>
        </nav>
    </header>

    <main class="konten">
        <section class="artikel">
            <h2>Artikel Utama</h2>
            <p>Ini adalah konten utama halaman. Teks ini akan menyesuaikan lebar layar.</p>
        </section>
        <aside class="sidebar">
            <h3>Sidebar</h3>
            <p>Informasi tambahan.</p>
        </aside>
    </main>

    <footer class="footer">
        <p>&copy; 2026 Website Saya</p>
    </footer>
</body>
</html>
```

**Langkah 2:** Buat `halaman.css` (mobile-first):

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
}

.header {
    background-color: #2c3e50;
    color: white;
    padding: 20px;
    text-align: center;
}

.menu {
    list-style: none;
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 10px;
}

.menu a {
    color: white;
    text-decoration: none;
}

.konten {
    display: grid;
    grid-template-columns: 1fr;  /* 1 kolom di ponsel */
    gap: 20px;
    padding: 20px;
    max-width: 1200px;
    margin: 0 auto;
}

.artikel {
    background-color: #ecf0f1;
    padding: 20px;
    border-radius: 8px;
}

.sidebar {
    background-color: #bdc3c7;
    padding: 20px;
    border-radius: 8px;
}

.footer {
    background-color: #2c3e50;
    color: white;
    text-align: center;
    padding: 15px;
}

/* Tablet: 2 kolom untuk konten */
@media (min-width: 600px) {
    .konten {
        grid-template-columns: 2fr 1fr;  /* artikel lebih lebar dari sidebar */
    }
}

/* Desktop: menu di kanan header */
@media (min-width: 992px) {
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        text-align: left;
    }
    .menu {
        margin-top: 0;
    }
}
```

**Langkah 3:** Buka di Live Server. Uji di berbagai ukuran layar (gunakan DevTools device toolbar).

**Langkah 4:** Amati:
- Di ponsel: konten 1 kolom, header di tengah.
- Di tablet: konten 2 kolom (artikel + sidebar).
- Di desktop: header jadi sejajar (logo kiri, menu kanan).

> **Latihan mandiri:** Ubah warna sidebar dan artikel agar lebih kontras, lalu tambahkan media query baru untuk layar sangat besar (`min-width: 1400px`).

---

## Latihan Mandiri

Buat halaman **portofolio** yang responsif. Ketentuan:

1. Buat file `portofolio.html` dan `portofolio.css`.
2. Halaman berisi:
   - Header dengan nama Anda dan menu navigasi.
   - Bagian "Tentang Saya" (paragraf singkat).
   - Bagian "Proyek" berisi minimal 6 kartu proyek.
   - Footer.
3. Gunakan:
   - CSS Grid untuk menyusun kartu proyek.
   - Media query (mobile-first) agar:
     - Ponsel: 1 kolom kartu.
     - Tablet: 2 kolom kartu.
     - Desktop: 3 kolom kartu.
   - Flexbox untuk menu navigasi.

**Struktur yang disarankan:**

```html
<header class="header">
    <h1>Nama Anda</h1>
    <nav>
        <ul class="menu">
            <li><a href="#">Beranda</a></li>
            <li><a href="#">Tentang</a></li>
            <li><a href="#">Proyek</a></li>
        </ul>
    </nav>
</header>

<section class="tentang">
    <h2>Tentang Saya</h2>
    <p>...</p>
</section>

<section class="proyek">
    <h2>Proyek Saya</h2>
    <div class="grid-proyek">
        <div class="kartu">Proyek 1</div>
        <!-- ... 6 kartu ... -->
    </div>
</section>

<footer class="footer">
    <p>&copy; 2026 Nama Anda</p>
</footer>
```

---

## Hasil yang Diharapkan (Expected Output)

Setelah menyelesaikan semua praktikum, Anda memiliki:

- Folder `latihan-grid` berisi file: `index.html`, `style.css`, `layout.html`, `layout.css`, `responsive.html`, `responsive.css`, `mobile-first.html`, `mobile-first.css`, `halaman.html`, `halaman.css`.
- Halaman `index.html` dengan 6 sel dalam 3 kolom.
- Halaman `layout.html` dengan layout lengkap: header, sidebar, konten, footer.
- Halaman `responsive.html` yang berubah dari 3 → 2 → 1 kolom saat layar dipersempit.
- Halaman `halaman.html` yang responsif dari ponsel hingga desktop.
- Halaman `portofolio.html` (latihan mandiri) dengan kartu proyek yang menyesuaikan jumlah kolom.

---

## Troubleshooting

| Masalah | Kemungkinan Penyebab | Solusi |
|---|---|---|
| Grid tidak tampil | `display: grid` belum ditambahkan | Pastikan properti `display: grid` ada di kontainer |
| Item tidak pindah kolom saat layar kecil | Media query salah atau tidak ada | Pastikan ada `@media (max-width: ...)` atau `@media (min-width: ...)` |
| Media query tidak berpengaruh | Urutan media query salah | Letakkan media query **setelah** aturan dasar; untuk `min-width`, urutkan dari kecil ke besar |
| Layout berantakan di ponsel | Tidak ada `viewport` meta tag | Pastikan ada `<meta name="viewport" content="width=device-width, initial-scale=1.0">` |
| Kolom tidak sama lebar | Menggunakan satuan tetap | Gunakan `1fr` untuk kolom yang fleksibel |
| Item menumpuk | `grid-template-columns` tidak sesuai | Periksa jumlah kolom yang didefinisikan |
| Perubahan tidak terlihat | Browser cache | Refresh dengan Ctrl+Shift+R |

---

## Rangkuman

- CSS Grid mengatur layout **dua dimensi** (baris + kolom).
- `grid-template-columns` dan `grid-template-rows` menentukan struktur grid.
- `1fr` = satu fraksi ruang yang tersedia.
- `grid-column: 1 / -1` membuat item membentang semua kolom.
- Media query membuat halaman **responsif** terhadap ukuran layar.
- **Mobile-first**: tulis CSS ponsel dulu, lalu tingkatkan dengan `min-width`.
- Selalu sertakan `<meta name="viewport">` untuk halaman responsif.

---

## Referensi

- MDN Web Docs — CSS Grid: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids
- MDN Web Docs — Responsive Design: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design
- CSS-Tricks — A Complete Guide to Grid: https://css-tricks.com/snippets/css/complete-guide-grid/
- Grid Garden (game latihan): https://cssgridgarden.com/

---

## Screenshot Placeholder

> **📸 Screenshot 1:** Hasil `index.html` dengan 6 sel dalam 3 kolom grid.
>
> **📸 Screenshot 2:** Hasil `index.html` dengan `grid-template-columns: 1fr 2fr 1fr` (kolom tengah lebih lebar).
>
> **📸 Screenshot 3:** Hasil `layout.html` (header, sidebar, konten, footer).
>
> **📸 Screenshot 4:** Hasil `responsive.html` di layar desktop (3 kolom).
>
> **📸 Screenshot 5:** Hasil `responsive.html` di layar ponsel (1 kolom) — gunakan DevTools device toolbar.
>
> **📸 Screenshot 6:** Hasil `halaman.html` di layar desktop (konten 2 kolom, header sejajar).
>
> **📸 Screenshot 7:** Hasil `halaman.html` di layar ponsel (konten 1 kolom, header di tengah).
>
> **📸 Screenshot 8:** Hasil latihan mandiri `portofolio.html` di layar desktop (3 kolom kartu).
>
> **📸 Screenshot 9:** Hasil latihan mandiri `portofolio.html` di layar ponsel (1 kolom kartu).
