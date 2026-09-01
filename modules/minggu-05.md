# Minggu 5 — CSS Dasar: Selector, Box Model, Typography

**Mata Kuliah:** Pengenalan Workshop Desain Web
**Program Studi:** D3 Informatika — Semester 1
**Durasi:** 3 jam kelas: 1 jam teori dan 2 jam praktik

---

## Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa diharapkan dapat:

1. Menjelaskan peran CSS dalam halaman web.
2. Menulis CSS dengan tiga cara: inline, internal, dan eksternal.
3. Menggunakan berbagai jenis selector (tag, class, id, descendant).
4. Memahami dan menerapkan konsep box model (margin, border, padding, content).
5. Menerapkan dasar typography: font, ukuran, warna, dan spasi teks.

---

## Alat yang Dibutuhkan

- Laptop dengan **VSCode** terpasang.
- Extension **Live Server** di VSCode.
- Browser modern (Chrome/Edge/Firefox).
- Folder proyek `latihan-css` (buat baru).

---

## Ringkasan Teori (Minimal)

CSS (Cascading Style Sheets) adalah bahasa untuk mengatur **tampilan** halaman web. HTML menentukan **struktur**, CSS menentukan **penampilan**.

> **Ingat:** CSS tidak mengubah isi halaman, hanya cara halaman itu ditampilkan.

### Box Model

Setiap elemen HTML dianggap sebagai sebuah **kotak** yang terdiri dari 4 lapisan:

```
+---------------------------+
|        margin             |
|  +---------------------+  |
|  |      border         |  |
|  |  +---------------+  |  |
|  |  |   padding     |  |  |
|  |  |  +---------+  |  |  |
|  |  |  | content |  |  |  |
|  |  |  +---------+  |  |  |
|  |  +---------------+  |  |
|  +---------------------+  |
+---------------------------+
```

- **Content** — isi elemen (teks/gambar).
- **Padding** — ruang di dalam border, antara border dan content.
- **Border** — garis pembatas elemen.
- **Margin** — ruang di luar border, antara elemen dan elemen lain.

---

## Praktikum 1 — Menyiapkan Proyek

**Langkah 1:** Buka VSCode, lalu buat folder baru bernama `latihan-css`.

**Langkah 2:** Di dalam folder tersebut, buat file baru bernama `index.html`.

**Langkah 3:** Ketik struktur dasar HTML berikut:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Latihan CSS</title>
</head>
<body>
    <h1>Selamat Datang di Latihan CSS</h1>
    <p>Ini adalah paragraf pertama saya.</p>
    <p class="highlight">Ini paragraf dengan class highlight.</p>
    <p id="spesial">Ini paragraf dengan id spesial.</p>
</body>
</html>
```

**Langkah 4:** Klik kanan pada file `index.html`, pilih **Open with Live Server**.

**Langkah 5:** Buka browser, pastikan halaman tampil. Anda akan melihat teks polos tanpa styling.

> **Catatan:** Belum ada CSS, jadi halaman tampil apa adanya (default browser).

---

## Praktikum 2 — Cara Menulis CSS

Ada 3 cara menulis CSS. Kita akan mencoba semuanya.

### 2a. Inline CSS (langsung di tag)

**Langkah 1:** Ubah tag `<h1>` menjadi:

```html
<h1 style="color: blue; text-align: center;">Selamat Datang di Latihan CSS</h1>
```

**Langkah 2:** Simpan (Ctrl+S) dan lihat hasilnya di browser. Judul menjadi biru dan di tengah.

> **Catatan:** Inline CSS hanya berlaku untuk satu elemen. Cara ini jarang dipakai karena sulit dirawat.

### 2b. Internal CSS (di dalam tag `<style>`)

**Langkah 1:** Di dalam `<head>`, tambahkan tag `<style>`:

```html
<head>
    <meta charset="UTF-8">
    <title>Latihan CSS</title>
    <style>
        p {
            color: green;
            font-size: 18px;
        }
    </style>
</head>
```

**Langkah 2:** Simpan dan lihat hasilnya. Semua paragraf menjadi hijau.

### 2c. Eksternal CSS (file terpisah) — **CARA YANG DISARANKAN**

**Langkah 1:** Buat file baru bernama `style.css` di folder yang sama.

**Langkah 2:** Ketik isi berikut:

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 20px;
}
```

**Langkah 3:** Hubungkan file CSS ke HTML. Di dalam `<head>`, tambahkan:

```html
<link rel="stylesheet" href="style.css">
```

**Langkah 4:** Hapus tag `<style>` dan atribut `style` yang tadi dibuat, supaya bersih.

**Langkah 5:** Simpan dan lihat hasilnya. Latar belakang menjadi abu-abu muda dan teks memakai font Arial.

> **Kesimpulan:** Gunakan **eksternal CSS** untuk proyek nyata karena mudah dirawat dan dipakai ulang.

---

## Praktikum 3 — Selector

Selector menentukan **elemen mana** yang akan diberi style.

**Langkah 1:** Buka file `style.css` dan tambahkan:

```css
/* 1. Selector tag: semua elemen <h1> */
h1 {
    color: navy;
    text-align: center;
}

/* 2. Selector class: elemen dengan class="highlight" */
.highlight {
    background-color: yellow;
    font-weight: bold;
}

/* 3. Selector id: elemen dengan id="spesial" */
#spesial {
    color: red;
    font-size: 24px;
}

/* 4. Selector descendant: <p> di dalam <div> */
div p {
    color: purple;
}
```

**Langkah 2:** Tambahkan sebuah `<div>` di dalam `<body>`:

```html
<div>
    <p>Ini paragraf di dalam div, warnanya ungu.</p>
</div>
```

**Langkah 3:** Simpan dan amati hasilnya di browser.

**Langkah 4:** Uji pemahaman — ubah warna pada masing-masing selector dan lihat perubahannya.

> **Tips:**
> - **Class** (`.nama`) bisa dipakai banyak elemen → paling sering digunakan.
> - **Id** (`#nama`) hanya untuk satu elemen unik.
> - **Selector tag** memengaruhi semua elemen dengan tag tersebut.

---

## Praktikum 4 — Box Model

**Langkah 1:** Buat file baru `box.html` dengan isi:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Box Model</title>
    <link rel="stylesheet" href="box.css">
</head>
<body>
    <div class="kotak">Kotak 1</div>
    <div class="kotak">Kotak 2</div>
</body>
</html>
```

**Langkah 2:** Buat file `box.css`:

```css
.kotak {
    width: 200px;
    height: 100px;
    background-color: lightblue;
    border: 3px solid navy;
    padding: 20px;
    margin: 15px;
    text-align: center;
    line-height: 100px;
}
```

**Langkah 3:** Buka `box.html` dengan Live Server. Amati jarak antar kotak (margin), ruang dalam kotak (padding), dan garis tepi (border).

**Langkah 4:** Sekarang ubah nilai-nilai berikut satu per satu dan amati perubahannya:

```css
.kotak {
    padding: 5px;      /* coba ubah dari 20px */
    margin: 50px;      /* coba ubah dari 15px */
    border: 10px dashed red;  /* coba ubah */
}
```

**Langkah 5:** Gunakan **DevTools** (F12 → tab Elements → tab Computed) untuk melihat kotak model secara visual.

> **Latihan mandiri:** Buat kotak dengan `border-radius: 50%` dan amati hasilnya (menjadi lingkaran).

---

## Praktikum 5 — Typography

**Langkah 1:** Buat file `tipografi.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Tipografi</title>
    <link rel="stylesheet" href="tipografi.css">
</head>
<body>
    <h1>Judul Halaman</h1>
    <h2>Sub Judul</h2>
    <p class="paragraf-1">Ini paragraf pertama dengan pengaturan font dan spasi.</p>
    <p class="paragraf-2">Ini paragraf kedua dengan gaya yang berbeda.</p>
</body>
</html>
```

**Langkah 2:** Buat file `tipografi.css`:

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 16px;
    color: #333;
    line-height: 1.6;
}

h1 {
    font-size: 2.5em;
    font-weight: bold;
    color: #2c3e50;
    letter-spacing: 1px;
}

h2 {
    font-size: 1.8em;
    color: #34495e;
}

.paragraf-1 {
    font-style: italic;
    text-align: justify;
}

.paragraf-2 {
    font-weight: bold;
    text-transform: uppercase;
    text-decoration: underline;
}
```

**Langkah 3:** Buka di Live Server dan amati perbedaannya.

**Langkah 4:** Coba ubah nilai `font-size`, `color`, `line-height`, dan `text-align` untuk melihat efeknya.

> **Tips warna:** Gunakan situs seperti [coolors.co](https://coolors.co) atau [colorhunt.co](https://colorhunt.co) untuk memilih palet warna yang serasi.

---

## Latihan Mandiri

Buat halaman profil sederhana dengan ketentuan berikut:

1. Buat file `profil.html` dan `profil.css`.
2. Halaman berisi:
   - Judul "Profil Saya".
   - Satu foto/placeholder gambar (bisa pakai `<img>` dengan gambar apa pun).
   - Nama, NIM, dan program studi.
   - Paragraf singkat tentang diri Anda.
3. Terapkan:
   - Selector tag, class, dan id (minimal masing-masing 1).
   - Box model: padding dan margin pada kartu profil.
   - Border dengan `border-radius` agar sudut membulat.
   - Typography: font berbeda untuk judul dan isi, warna yang serasi.

**Struktur yang disarankan:**

```html
<div class="kartu">
    <img src="foto.jpg" alt="Foto Saya" class="foto">
    <h1 id="nama">Nama Anda</h1>
    <p class="info">NIM: 12345678</p>
    <p class="info">Program Studi: D3 Informatika</p>
    <p class="deskripsi">Tentang saya...</p>
</div>
```

---

## Hasil yang Diharapkan (Expected Output)

Setelah menyelesaikan semua praktikum, Anda memiliki:

- Folder `latihan-css` berisi minimal 4 file: `index.html`, `style.css`, `box.html`, `box.css`, `tipografi.html`, `tipografi.css`.
- Halaman `index.html` dengan judul biru navy di tengah, paragraf hijau, satu paragraf berlatar kuning, satu paragraf merah, dan satu paragraf ungu.
- Halaman `box.html` dengan dua kotak biru muda ber-border navy, berjarak satu sama lain.
- Halaman `tipografi.html` dengan judul besar, sub judul, dan dua paragraf bergaya berbeda.
- Halaman `profil.html` (latihan mandiri) berupa kartu profil yang rapi.

---

## Troubleshooting

| Masalah | Kemungkinan Penyebab | Solusi |
|---|---|---|
| CSS tidak berpengaruh | File CSS tidak terhubung | Pastikan ada `<link rel="stylesheet" href="style.css">` dan nama file benar |
| Perubahan tidak muncul di browser | Browser belum di-refresh | Simpan file (Ctrl+S) dan refresh browser, atau pastikan Live Server aktif |
| Selector tidak bekerja | Nama class/id salah ketik | Periksa penulisan `.nama` (class) vs `#nama` (id) |
| Jarak antar elemen aneh | Margin/padding belum dipahami | Buka DevTools → Computed untuk melihat box model |
| Font tidak berubah | Font tidak tersedia di sistem | Gunakan font umum seperti Arial, sans-serif sebagai fallback |
| Gambar tidak muncul | Path salah | Pastikan file gambar ada di folder yang sama dan nama file benar |

---

## Rangkuman

- CSS mengatur tampilan, HTML mengatur struktur.
- Gunakan **eksternal CSS** untuk proyek nyata.
- Selector: tag, class (`.`), id (`#`), descendant.
- Box model: content → padding → border → margin.
- Typography: atur font, ukuran, warna, dan spasi teks agar mudah dibaca.

---

## Referensi

- MDN Web Docs — CSS Basics: https://developer.mozilla.org/en-US/docs/Learn/CSS
- MDN Web Docs — Box Model: https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model
- W3Schools — CSS Tutorial: https://www.w3schools.com/css/

---

## Screenshot Placeholder

> **📸 Screenshot 1:** Hasil `index.html` setelah menerapkan selector (judul navy, paragraf hijau, highlight kuning, id merah, paragraf ungu di dalam div).
>
> **📸 Screenshot 2:** Hasil `box.html` dengan dua kotak ber-border navy dan jarak antar kotak.
>
> **📸 Screenshot 3:** DevTools → tab Computed yang menampilkan box model salah satu kotak.
>
> **📸 Screenshot 4:** Hasil `tipografi.html` dengan judul, sub judul, dan dua paragraf bergaya berbeda.
>
> **📸 Screenshot 5:** Hasil latihan mandiri `profil.html` (kartu profil).
