# Minggu 3 — HTML Dasar: Struktur & Semantic Tag

---

| Item | Detail |
|---|---|
| **Minggu ke-** | 3 |
| **Topik** | HTML dasar: struktur dokumen, elemen, atribut, semantic tag |
| **Output** | Halaman HTML statis (multi-section) yang valid dan terstruktur |
| **Durasi** | 3 jam kelas: 1 jam teori dan 2 jam praktik |
| **Prasyarat** | VS Code + Live Server terinstal (Minggu 1), akun GitHub |
| **Tools** | VS Code, Live Server, browser, W3C Validator (https://validator.w3.org) |

---

## Tujuan Pembelajaran

Setelah menyelesaikan modul ini, kamu akan mampu:

1. Menjelaskan struktur dasar dokumen HTML (doctype, html, head, body).
2. Menggunakan elemen HTML dasar: heading, paragraph, link, image, list.
3. Membedakan dan menggunakan **semantic tag** (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`, dsb).
4. Menulis HTML yang **valid** menggunakan W3C Validator.
5. Menghubungkan file HTML ke file eksternal (CSS) secara dasar.

---

## Bagian A — Live Coding: Struktur Dokumen HTML

> **Ikuti langkah-langkah berikut secara berurutan.** Pengerjaan bersama dosen.

### A.1. Buat Proyek Baru

1. Di VS Code, buat folder baru: **File → Open Folder → New Folder** → beri nama `latihan-web-3`.
2. Buat file baru: `index.html`.

### A.2. Struktur Dasar HTML

Ketik kode berikut di `index.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Latihan HTML — Minggu 3</title>
</head>
<body>
    <h1>Halo dari HTML!</h1>
</body>
</html>
```

**Apa yang terjadi di sini?**

| Baris | Fungsi |
|---|---|
| `<!DOCTYPE html>` | Memberitahu browser bahwa ini dokumen HTML5 |
| `<html lang="id">` | Elemen root — semua kode ada di dalamnya. `lang="id"` menandakan bahasa Indonesia |
| `<head>` | Metadata — tidak terlihat di halaman, tapi penting untuk browser & SEO |
| `<meta charset="UTF-8">` | Set karakter encoding (agar huruf Indonesia seperti é, ü, dsb muncul benar) |
| `<meta name="viewport"...>` | Agar halaman responsif di mobile |
| `<title>` | Judul yang muncul di tab browser |
| `<body>` | Konten yang **terlihat** oleh pengguna |

### A.3. Live Coding: Elemen-Elemen Dasar

Tambahkan kode berikut di dalam `<body>`, **di bawah** `<h1>`:

```html
<!-- Heading: h1 sampai h6 -->
<h1>Ini Heading 1 (Judul Utama)</h1>
<h2>Ini Heading 2 (Judul Section)</h2>
<h3>Ini Heading 3 (Sub-judul)</h3>

<!-- Paragraph -->
<p>Ini adalah paragraf biasa. HTML menggunakan tag untuk mendefinisikan konten.</p>
<p>Paragraf kedua. Setiap tag <code>&lt;p&gt;</code> akan membuat baris baru.</p>

<!-- Link (Anchor) -->
<p>Kunjungi <a href="https://developer.mozilla.org" target="_blank">MDN Web Docs</a> untuk belajar HTML lebih lanjut.</p>

<!-- Image (gambar dari internet — placeholder) -->
<img src="https://placehold.co/600x300" alt="Contoh gambar placeholder" width="600" height="300">

<!-- List tidak berurut (Unordered List) -->
<h3>Tools yang Kita Gunakan:</h3>
<ul>
    <li>VS Code — editor kode</li>
    <li>Live Server — preview otomatis</li>
    <li>Browser — melihat hasil</li>
    <li>GitHub — menyimpan kode</li>
</ul>

<!-- List berurut (Ordered List) -->
<h3>Langkah Instalasi:</h3>
<ol>
    <li>Download VS Code dari website resmi</li>
    <li>Install ekstensi Live Server</li>
    <li>Buat file index.html</li>
    <li>Klik kanan → Open with Live Server</li>
</ol>

<!-- Horizontal Rule (garis pemisah) -->
<hr>

<!-- Strong & Emphasis -->
<p>HTML itu <strong>sangat penting</strong> untuk dipelajari karena fondasi semua website.</p>
<p>Kamu pasti <em>bisa</em> menguasai ini!</p>
```

**Simpan file (Ctrl + S) → buka dengan Live Server.**

### A.4. Verifikasi

✅ **Ceklis:** Apakah browser menampilkan:
- 3 heading (h1, h2, h3) dengan ukuran berbeda?
- 2 paragraf?
- 1 link (bergaris bawah)?
- 1 gambar placeholder?
- 1 list dengan titik (bullet)?
- 1 list bernomor?
- 1 garis horizontal?
- 1 teks tebal dan 1 teks miring?

<!-- Screenshot placeholder: Browser yang menampilkan semua elemen HTML dasar -->
> **📸 Screenshot C1:** Browser yang menampilkan hasil elemen HTML dasar — pastikan terlihat heading, paragraph, link, gambar, lists, strong, em.

---

## Bagian B — Live Coding: Semantic HTML

> **Semantic HTML** = menggunakan tag yang tidak hanya mendeskripsikan tampilan, tapi juga **makna** konten. Ini penting untuk SEO, aksesibilitas, dan keterbacaan kode.

### B.1. Apa Bedanya?

| Non-Semantic | Semantic | Kapan Pakai |
|---|---|---|
| `<div>` untuk semua section | `<header>` untuk bagian atas | Gunakan tag semantik saat konten punya peran jelas |
| `<div>` untuk daftar menu | `<nav>` untuk navigasi | `<nav>` memberitahu browser ini bagian navigasi |
| `<div>` untuk konten utama | `<main>` untuk konten utama | Hanya ada **satu** `<main>` per halaman |
| `<div>` untuk footer | `<footer>` untuk bagian bawah | Setiap halaman sebaiknya punya `<footer>` |
| `<div>` untuk section | `<section>` atau `<article>` | `section` = bagian tematik; `article` = konten mandiri |

### B.2. Live Coding: Rekonstruksi dengan Semantic Tag

Buat file baru bernama `profil.html` di folder yang sama. Ketik kode berikut:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil Diri — Latihan Semantic HTML</title>
</head>
<body>

    <!-- HEADER: Berisi navigasi -->
    <header>
        <h1>Portfolio Saya</h1>
        <nav>
            <ul>
                <li><a href="#tentang">Tentang</a></li>
                <li><a href="#keahlian">Keahlian</a></li>
                <li><a href="#proyek">Proyek</a></li>
                <li><a href="#kontak">Kontak</a></li>
            </ul>
        </nav>
    </header>

    <!-- MAIN: Konten utama halaman -->
    <main>

        <!-- SECTION: Tentang Saya -->
        <section id="tentang">
            <h2>Tentang Saya</h2>
            <img src="https://placehold.co/200x200" alt="Foto profil" width="200" height="200">
            <p>Halo! Nama saya [Nama Lengkap], mahasiswa semester 1
               D3 Informatika di [Nama Kampus]. Saya tertarik
               dengan dunia desain web dan ingin belajar membangun
               website yang menarik dan mudah digunakan.</p>
        </section>

        <!-- SECTION: Keahlian -->
        <section id="keahlian">
            <h2>Keahlian</h2>
            <ul>
                <li>HTML & dasar CSS</li>
                <li>Figma (wireframing)</li>
                <li>Microsoft Office</li>
                <li>Dasar pemrograman (belajar)</li>
            </ul>
        </section>

        <!-- SECTION: Proyek -->
        <section id="proyek">
            <h2>Proyek</h2>

            <!-- ARTICLE: Konten mandiri tentang 1 proyek -->
            <article>
                <h3>Website Profil Diri</h3>
                <p>Website statis pertama saya yang dibuat dengan HTML
                   dan CSS. Berisi informasi profil diri, daftar
                   keahlian, dan cara menghubungi saya.</p>
                <p><strong>Teknologi:</strong> HTML, CSS</p>
            </article>

            <article>
                <h3>Landing Page Produk</h3>
                <p>Halaman promosi produk sederhana yang dibuat
                   sebagai latihan layout dengan Flexbox.</p>
                <p><strong>Teknologi:</strong> HTML, CSS</p>
            </article>
        </section>

        <!-- SECTION: Kontak -->
        <section id="kontak">
            <h2>Kontak</h2>
            <p>Email: <a href="mailto:nama@email.com">nama@email.com</a></p>
            <p>GitHub: <a href="https://github.com/username" target="_blank">github.com/username</a></p>
        </section>

    </main>

    <!-- FOOTER -->
    <footer>
        <p>&copy; 2026 [Nama Lengkap]. Dibuat untuk mata kuliah Desain Web.</p>
    </footer>

</body>
</html>
```

**Simpan file → buka dengan Live Server.**

### B.3. Bandingkan dengan Non-Semantic

Perhatikan perbedaan:

```html
<!-- ❌ Non-Semantic — semua pakai div -->
<div class="header">
    <div class="nav">
        <div class="menu-item">Tentang</div>
    </div>
</div>
<div class="main">
    <div class="section">...</div>
</div>
<div class="footer">...</div>

<!-- ✅ Semantic — menggunakan tag yang tepat -->
<header>
    <nav>
        <a href="#tentang">Tentang</a>
    </nav>
</header>
<main>
    <section>...</section>
</main>
<footer>...</footer>
```

**Kenapa semantic lebih baik?**
1. **Screen reader** (untuk tunanetra) bisa membaca struktur halaman dengan benar.
2. **Search engine** (Google) lebih mudah memahami konten halaman.
3. **Developer lain** (dan kamu 3 bulan lagi) lebih mudah membaca kode.

---

## Bagian C — Live Coding: Elemen Pendukung Penting

### C.1. Anchor (Link) — Detail Atribut

```html
<!-- Link ke halaman lain -->
<a href="https://www.google.com">Google</a>

<!-- Link ke email -->
<a href="mailto:budi@email.com">Kirim Email</a>

<!-- Link ke section di halaman yang sama (anchor link) -->
<a href="#keahlian">Lihat Keahlian</a>

<!-- Buka di tab baru -->
<a href="https://www.google.com" target="_blank" rel="noopener noreferrer">
    Google (tab baru)
</a>

<!-- Gambar sebagai link -->
<a href="https://www.google.com">
    <img src="logo.png" alt="Logo Google" width="100">
</a>
```

### C.2. Image — Detail Atribut

```html
<!-- Gambar dasar -->
<img src="foto.jpg" alt="Deskripsi gambar" width="400" height="300">

<!-- Gambar dari URL -->
<img src="https://placehold.co/400x300" alt="Placeholder">

<!-- Gambar dengan figure & caption -->
<figure>
    <img src="foto.jpg" alt="Foto profil" width="200" height="200">
    <figcaption>Foto profil saya — diambil tahun 2026</figcaption>
</figure>
```

**⚠️ Aturan penting untuk `alt` pada gambar:**
- **Selalu** isi atribut `alt`.
- `alt` harus **mendeskripsikan gambar**, bukan hanya "gambar" atau "foto".
- Jika gambar murni dekoratif (tidak bermakna), gunakan `alt=""` (kosong).

### C.3. Tabel Dasar (Preview — akan dibahas lebih dalam Minggu 4)

```html
<table>
    <caption>Jadwal Kuliah Semester 1</caption>
    <thead>
        <tr>
            <th>Hari</th>
            <th>Mata Kuliah</th>
            <th>Jam</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Senin</td>
            <td>Desain Web</td>
            <td>08:00 – 10:00</td>
        </tr>
        <tr>
            <td>Rabu</td>
            <td>Algoritma</td>
            <td>10:00 – 12:00</td>
        </tr>
    </tbody>
</table>
```

---

## Bagian D — Live Coding: Menghubungkan HTML ke CSS (Dasar)

> **Catatan:** CSS detail akan dipelajari di Minggu 5. Ini hanya pengenalan cara menghubungkan file.

### D.1. Buat File CSS

1. Di folder yang sama, buat file baru: `style.css`.
2. Ketik kode CSS berikut:

```css
/* Reset dasar */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    line-height: 1.6;
    color: #333;
}

/* Header */
header {
    background-color: #2c3e50;
    color: white;
    padding: 20px;
    text-align: center;
}

header nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: center;
    gap: 20px;
}

header nav a {
    color: white;
    text-decoration: none;
}

/* Main content */
main {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
}

section {
    margin-bottom: 40px;
}

/* Footer */
footer {
    background-color: #2c3e50;
    color: white;
    text-align: center;
    padding: 10px;
}
```

### D.2. Hubungkan ke HTML

Di file `profil.html`, tambahkan tag `<link>` di dalam `<head>`:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil Diri — Latihan Semantic HTML</title>
    <link rel="stylesheet" href="style.css">
</head>
```

**Simpan kedua file → buka `profil.html` via Live Server.**

**✅ Ceklis:** Apakah tampilan halaman berubah (ada warna, layout lebih rapi)?

<!-- Screenshot placeholder: Halaman profil.html dengan CSS yang sudah terhubung -->
> **📸 Screenshot C2:** Halaman `profil.html` di browser dengan CSS — pastikan terlihat header berwarna gelap, layout terpusat, dan footer berwarna gelap.

---

## Bagian E — Validasi HTML

### E.1. Cek Validasi

1. Buka **https://validator.w3.org/#validate_by_input**.
2. Pilih tab **Direct Input**.
3. Copy seluruh isi `profil.html` → paste ke kolom teks.
4. Klik **Check**.
5. Pastikan hasil: **"Document checking completed. No errors or warnings to show."** ✅

<!-- Screenshot placeholder: W3C Validator yang menunjukkan hasil validasi tanpa error -->
> **📸 Screenshot C3:** W3C HTML Validator — pastikan terlihat pesan "No errors or warnings to show".

**Jika ada error**, perbaiki berdasarkan pesan yang diberikan validator, lalu cek ulang.

---

## Bagian F — Latihan Mandiri

> Kerjakan latihan ini **secara mandiri**.

### F.1. Latihan 1 — Halaman "Tips Belajar HTML"

Buat file baru bernama `tips.html` dengan struktur semantic HTML yang lengkap. Halaman ini berisi:

**Section yang wajib ada:**

1. **Header** dengan judul "Tips Belajar HTML untuk Pemula" dan **nav** (minimal 3 anchor link ke section di bawah).
2. **Section "Mengapa HTML Penting"** — 2 paragraf penjelasan.
3. **Section "Tips Pertama"** — ordered list (numbered) berisi minimal 5 tips.
4. **Section "Kesalahan Umum"** — unordered list (bullet) berisi minimal 4 kesalahan, masing-masing dijelaskan dalam paragraf terpisah.
5. **Section "Sumber Belajar"** — unordered list berisi minimal 3 link ke website belajar HTML (MDN, W3Schools, dsb). Setiap link harus:
   - Menggunakan `target="_blank"`.
   - Menggunakan `rel="noopener noreferrer"`.
6. **Footer** dengan hak cipta tahun 2026.

**Persyaratan teknis:**
- Gunakan **hanya** tag semantic (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>` jika relevan, `<footer>`).
- Tidak boleh ada `<div>` untuk section — gunakan tag semantic.
- Semua gambar harus punya `alt` yang deskriptif.
- File harus **valid** di W3C Validator.

### F.2. Latihan 2 — Push ke GitHub

1. Inisialisasi Git di folder `latihan-web-3`:

```bash
git init
git remote add origin https://github.com/NAMA_USER/latihan-web-3.git
```

2. Buat repository baru di GitHub (public, dengan README).
3. Push kode:

```bash
git add .
git commit -m "Latihan HTML minggu 3: semantic tags"
git branch -M main
git push -u origin main
```

4. Buka repository di GitHub → pastikan file `index.html`, `profil.html`, `tips.html`, dan `style.css` terlihat.

**✅ Ceklis:**
- [ ] Semua file sudah di-push ke GitHub.
- [ ] `tips.html` valid di W3C Validator.
- [ ] Tidak ada tag `<div>` yang digunakan sebagai section placeholder.
- [ ] Semua gambar memiliki `alt` attribute.
- [ ] Link eksternal menggunakan `target="_blank" rel="noopener noreferrer"`.

---

## Bagian G — Ringkasan & Checklist

### Yang sudah kamu pelajari hari ini:

- [ ] Struktur dasar dokumen HTML (doctype, html, head, body).
- [ ] Elemen dasar: heading, paragraph, link, image, list, strong, em, hr.
- [ ] Semantic tags: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`.
- [ ] Perbedaan semantic vs non-semantic HTML.
- [ ] Menghubungkan HTML ke file CSS eksternal.
- [ ] Validasi HTML menggunakan W3C Validator.

### Cheat Sheet Tag Semantic:

```
<header>   → Bagian atas halaman (judul, nav)
<nav>      → Navigasi / menu
<main>     → Konten utama (hanya 1 per halaman)
<section>  → Bagian tematik dalam main
<article>  → Konten mandiri (bisa dipindah ke halaman lain)
<aside>    → Konten sampingan (sidebar)
<footer>   → Bagian bawah halaman
<figure>   → Gambar + caption
<figcaption> → Caption untuk figure
```

---

## Troubleshooting

| Masalah | Solusi |
|---|---|
| Gambar tidak muncul di browser | Cek path `src` — gunakan URL lengkap untuk gambar online, atau pastikan nama file benar untuk gambar lokal |
| Link tidak berfungsi (anchor) | Pastikan `href="#section-id"` cocok dengan `id="section-id"` pada section target |
| W3C Validator menampilkan error | Baca pesan error — biasanya tag tidak ditutup (`</p>`) atau nesting salah |
| CSS tidak terlihat | Pastikan `<link rel="stylesheet" href="style.css">` ada di `<head>`, dan nama file CSS benar |
| Halaman tidak responsif di mobile | Tag `<meta name="viewport" ...>` harus ada di `<head>` |
| Teks berantakan / paragraf tidak terpisah | Pastikan setiap paragraf dibungkus tag `<p>`, bukan hanya enter di kode |

---

## Referensi

- [MDN Web Docs — HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/HTML)
- [MDN Web Docs — Semantic HTML](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#Semantics_in_HTML)
- [W3C HTML Validator](https://validator.w3.org/)
- [HTML Element Reference — MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
