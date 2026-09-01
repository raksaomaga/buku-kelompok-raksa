# Minggu 6 — CSS Layout: Flexbox

**Mata Kuliah:** Pengenalan Workshop Desain Web
**Program Studi:** D3 Informatika — Semester 1
**Durasi:** 3 jam kelas: 1 jam teori dan 2 jam praktik

---

## Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa diharapkan dapat:

1. Menjelaskan konsep flexbox sebagai alat layout satu dimensi.
2. Menggunakan properti `display: flex` pada kontainer.
3. Mengatur arah, pembungkusan, dan perataan item flex.
4. Mengatur ukuran dan urutan item flex.
5. Membangun layout sederhana (navbar, kartu, galeri) dengan flexbox.

---

## Alat yang Dibutuhkan

- Laptop dengan **VSCode** terpasang.
- Extension **Live Server**.
- Browser modern.
- Folder proyek `latihan-flexbox` (buat baru).

---

## Ringkasan Teori (Minimal)

Flexbox (Flexible Box) adalah cara mengatur **tata letak satu dimensi** — baik baris (horizontal) maupun kolom (vertikal). Flexbox sangat berguna untuk menyusun elemen secara sejajar dan merata.

### Konsep Utama

- **Flex container** — elemen induk yang diberi `display: flex`.
- **Flex item** — elemen anak di dalam flex container.

```
+--------------------------------------------------+
|  Flex Container (display: flex)                  |
|  +--------+  +--------+  +--------+             |
|  | item 1 |  | item 2 |  | item 3 |             |
|  +--------+  +--------+  +--------+             |
+--------------------------------------------------+
```

### Properti Penting

| Properti | Fungsi |
|---|---|
| `display: flex` | Mengaktifkan flexbox pada kontainer |
| `flex-direction` | Arah item: `row`, `column`, `row-reverse`, `column-reverse` |
| `justify-content` | Perataan item pada sumbu utama (horizontal untuk row) |
| `align-items` | Perataan item pada sumbu silang (vertikal untuk row) |
| `flex-wrap` | Membolehkan item pindah baris (`wrap`) |
| `gap` | Jarak antar item |
| `flex` | Mengatur ukuran relatif item |

---

## Praktikum 1 — Menyiapkan Proyek

**Langkah 1:** Buat folder `latihan-flexbox` di VSCode.

**Langkah 2:** Buat file `index.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Latihan Flexbox</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
    </div>
</body>
</html>
```

**Langkah 3:** Buat file `style.css`:

```css
.container {
    display: flex;
    background-color: #ddd;
    padding: 10px;
}

.item {
    background-color: lightblue;
    border: 2px solid navy;
    padding: 20px;
    margin: 5px;
    font-size: 20px;
}
```

**Langkah 4:** Buka dengan Live Server. Ketiga item tampil **sejajar horizontal** karena `display: flex`.

---

## Praktikum 2 — Flex Direction

**Langkah 1:** Tambahkan properti berikut pada `.container`:

```css
.container {
    display: flex;
    flex-direction: row;   /* default: sejajar horizontal */
    background-color: #ddd;
    padding: 10px;
}
```

**Langkah 2:** Ubah `row` menjadi `column` dan amati hasilnya (item tersusun vertikal).

**Langkah 3:** Coba juga `row-reverse` dan `column-reverse`. Amati urutan item berubah.

> **Catatan:** `flex-direction` menentukan **sumbu utama**. `row` = sumbu utama horizontal, `column` = sumbu utama vertikal.

---

## Praktikum 3 — Justify Content & Align Items

**Langkah 1:** Kembalikan `flex-direction` menjadi `row`.

**Langkah 2:** Tambahkan `justify-content` dengan berbagai nilai. Coba satu per satu:

```css
.container {
    display: flex;
    justify-content: center;   /* coba: flex-start, flex-end, space-between, space-around, space-evenly */
    background-color: #ddd;
    padding: 10px;
}
```

Amati perbedaan:
- `flex-start` — item di kiri.
- `flex-end` — item di kanan.
- `center` — item di tengah.
- `space-between` — jarak merata, item ujung menempel tepi.
- `space-around` — jarak merata dengan ruang di tepi.
- `space-evenly` — jarak benar-benar merata.

**Langkah 3:** Sekarang atur tinggi kontainer dan coba `align-items`:

```css
.container {
    display: flex;
    height: 200px;
    align-items: center;   /* coba: flex-start, flex-end, stretch */
    background-color: #ddd;
    padding: 10px;
}
```

Amati perbedaan posisi vertikal item.

> **Tips:** `justify-content` mengatur sumbu utama, `align-items` mengatur sumbu silang. Jangan tertukar!

---

## Praktikum 4 — Flex Wrap & Gap

**Langkah 1:** Tambahkan lebih banyak item di HTML (misal 6 item).

**Langkah 2:** Atur lebar item agar sempit:

```css
.item {
    width: 150px;
    background-color: lightblue;
    border: 2px solid navy;
    padding: 20px;
    margin: 5px;
}
```

**Langkah 3:** Tanpa `flex-wrap`, item akan menyempit agar muat satu baris. Tambahkan:

```css
.container {
    display: flex;
    flex-wrap: wrap;   /* item pindah ke baris baru jika tidak muat */
    gap: 10px;         /* jarak antar item, menggantikan margin */
    background-color: #ddd;
    padding: 10px;
}
```

**Langkah 4:** Hapus `margin` pada `.item` dan gunakan `gap` pada kontainer. Amati hasilnya lebih rapi.

> **Catatan:** `gap` lebih modern dan rapi daripada `margin` untuk jarak antar item flex.

---

## Praktikum 5 — Properti Flex pada Item

**Langkah 1:** Buat file baru `flex-item.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Flex Item</title>
    <link rel="stylesheet" href="flex-item.css">
</head>
<body>
    <div class="container">
        <div class="item a">A</div>
        <div class="item b">B</div>
        <div class="item c">C</div>
    </div>
</body>
</html>
```

**Langkah 2:** Buat `flex-item.css`:

```css
.container {
    display: flex;
    background-color: #ddd;
    padding: 10px;
}

.item {
    background-color: lightgreen;
    border: 2px solid green;
    padding: 20px;
    margin: 5px;
}

/* Item A mengambil 1 bagian */
.a { flex: 1; }

/* Item B mengambil 2 bagian (dua kali lebih besar dari A) */
.b { flex: 2; }

/* Item C mengambil 1 bagian */
.c { flex: 1; }
```

**Langkah 3:** Buka di Live Server. Item B tampil dua kali lebih lebar dari A dan C.

**Langkah 4:** Coba ubah nilai `flex` pada masing-masing item dan amati perbandingan lebarnya.

> **Tips:** `flex: 1` berarti "ambil ruang yang tersisa secara proporsional". Ini sangat berguna untuk layout yang fleksibel.

---

## Praktikum 6 — Membangun Navbar dengan Flexbox

**Langkah 1:** Buat file `navbar.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Navbar Flexbox</title>
    <link rel="stylesheet" href="navbar.css">
</head>
<body>
    <nav class="navbar">
        <div class="logo">MySite</div>
        <ul class="menu">
            <li><a href="#">Beranda</a></li>
            <li><a href="#">Tentang</a></li>
            <li><a href="#">Kontak</a></li>
        </ul>
        <a href="#" class="btn">Login</a>
    </nav>
</body>
</html>
```

**Langkah 2:** Buat `navbar.css`:

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #2c3e50;
    color: white;
    padding: 15px 30px;
}

.logo {
    font-size: 24px;
    font-weight: bold;
}

.menu {
    display: flex;
    list-style: none;
    gap: 20px;
}

.menu a {
    color: white;
    text-decoration: none;
}

.menu a:hover {
    color: #3498db;
}

.btn {
    background-color: #3498db;
    color: white;
    padding: 8px 16px;
    border-radius: 5px;
    text-decoration: none;
}
```

**Langkah 3:** Buka di Live Server. Anda memiliki navbar dengan logo di kiri, menu di tengah, dan tombol login di kanan.

**Langkah 4:** Coba ubah `justify-content` menjadi `center` dan amati perubahannya.

> **Latihan mandiri:** Tambahkan item menu baru "Layanan" dan "Blog" ke dalam daftar menu.

---

## Praktikum 7 — Galeri Foto dengan Flexbox

**Langkah 1:** Buat file `galeri.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Galeri Flexbox</title>
    <link rel="stylesheet" href="galeri.css">
</head>
<body>
    <h1>Galeri Foto</h1>
    <div class="galeri">
        <div class="foto">Foto 1</div>
        <div class="foto">Foto 2</div>
        <div class="foto">Foto 3</div>
        <div class="foto">Foto 4</div>
        <div class="foto">Foto 5</div>
        <div class="foto">Foto 6</div>
    </div>
</body>
</html>
```

**Langkah 2:** Buat `galeri.css`:

```css
.galeri {
    display: flex;
    flex-wrap: wrap;
    gap: 15px;
    justify-content: center;
}

.foto {
    width: 200px;
    height: 150px;
    background-color: #3498db;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 8px;
    font-size: 18px;
}
```

**Langkah 3:** Buka di Live Server. Foto-foto tersusun rapi dan otomatis pindah baris saat jendela dipersempit.

**Langkah 4:** Persempit jendela browser dan amati bagaimana item berpindah baris (karena `flex-wrap: wrap`).

> **Latihan mandiri:** Ganti teks "Foto 1" dst dengan gambar nyata menggunakan `<img>`.

---

## Latihan Mandiri

Buat halaman **kartu produk** dengan flexbox. Ketentuan:

1. Buat file `produk.html` dan `produk.css`.
2. Halaman berisi judul "Produk Kami" dan 3 kartu produk sejajar.
3. Setiap kartu berisi:
   - Nama produk.
   - Harga.
   - Tombol "Beli".
4. Gunakan:
   - `display: flex` untuk menyusun kartu sejajar.
   - `justify-content: space-between` atau `center`.
   - `gap` untuk jarak antar kartu.
   - `flex-direction: column` di dalam kartu agar isi tersusun vertikal.
   - `align-items: center` untuk menengahkan isi kartu.

**Struktur yang disarankan:**

```html
<div class="produk-list">
    <div class="kartu">
        <h3>Produk A</h3>
        <p class="harga">Rp 50.000</p>
        <button>Beli</button>
    </div>
    <div class="kartu">
        <h3>Produk B</h3>
        <p class="harga">Rp 75.000</p>
        <button>Beli</button>
    </div>
    <div class="kartu">
        <h3>Produk C</h3>
        <p class="harga">Rp 100.000</p>
        <button>Beli</button>
    </div>
</div>
```

---

## Hasil yang Diharapkan (Expected Output)

Setelah menyelesaikan semua praktikum, Anda memiliki:

- Folder `latihan-flexbox` berisi file: `index.html`, `style.css`, `flex-item.html`, `flex-item.css`, `navbar.html`, `navbar.css`, `galeri.html`, `galeri.css`.
- Halaman `index.html` dengan 3 item sejajar yang bisa diubah arah dan perataannya.
- Halaman `flex-item.html` dengan item B dua kali lebih lebar dari A dan C.
- Halaman `navbar.html` dengan navbar rapi: logo kiri, menu tengah, tombol kanan.
- Halaman `galeri.html` dengan foto-foto yang otomatis pindah baris saat jendela dipersempit.
- Halaman `produk.html` (latihan mandiri) dengan 3 kartu produk sejajar.

---

## Troubleshooting

| Masalah | Kemungkinan Penyebab | Solusi |
|---|---|---|
| Item tidak sejajar | `display: flex` belum ditambahkan | Pastikan properti `display: flex` ada di kontainer, bukan di item |
| `justify-content` tidak berpengaruh | Salah sumbu | `justify-content` bekerja pada sumbu utama; jika `flex-direction: column`, ia mengatur vertikal |
| Item menyempit saat jendela kecil | `flex-wrap` belum diaktifkan | Tambahkan `flex-wrap: wrap` pada kontainer |
| Jarak antar item tidak muncul | Menggunakan `margin` tapi `gap` tidak ada | Gunakan `gap` pada kontainer untuk jarak yang konsisten |
| Item tidak menengahkan teks | `align-items`/`justify-content` belum diatur | Untuk menengahkan, atur keduanya menjadi `center` |
| Layout berantakan | Ada margin/padding default browser | Tambahkan `* { margin: 0; padding: 0; box-sizing: border-box; }` di awal CSS |

---

## Rangkuman

- Flexbox mengatur layout **satu dimensi** (baris atau kolom).
- `display: flex` pada kontainer mengaktifkan flexbox.
- `flex-direction` menentukan sumbu utama.
- `justify-content` mengatur sumbu utama, `align-items` mengatur sumbu silang.
- `flex-wrap: wrap` memungkinkan item pindah baris.
- `gap` mengatur jarak antar item.
- `flex: 1` membuat item mengambil ruang secara proporsional.

---

## Referensi

- MDN Web Docs — Flexbox: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox
- CSS-Tricks — A Complete Guide to Flexbox: https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- Flexbox Froggy (game latihan): https://flexboxfroggy.com/

---

## Screenshot Placeholder

> **📸 Screenshot 1:** Hasil `index.html` dengan 3 item sejajar horizontal (`flex-direction: row`).
>
> **📸 Screenshot 2:** Hasil `index.html` setelah `flex-direction: column` (item tersusun vertikal).
>
> **📸 Screenshot 3:** Hasil `justify-content: space-between` (item ujung menempel tepi).
>
> **📸 Screenshot 4:** Hasil `flex-wrap: wrap` dengan 6 item yang pindah baris.
>
> **📸 Screenshot 5:** Hasil `flex-item.html` dengan item B lebih lebar (flex: 2).
>
> **📸 Screenshot 6:** Hasil `navbar.html` (logo kiri, menu tengah, tombol kanan).
>
> **📸 Screenshot 7:** Hasil `galeri.html` dengan foto-foto tersusun rapi.
>
> **📸 Screenshot 8:** Hasil latihan mandiri `produk.html` (3 kartu produk sejajar).
