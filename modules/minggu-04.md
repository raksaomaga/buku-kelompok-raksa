# Minggu 4 — HTML Lanjutan: Form, Tabel & Multimedia

---

| Item | Detail |
|---|---|
| **Minggu ke-** | 4 |
| **Topik** | HTML form, tabel, elemen multimedia |
| **Output** | Halaman HTML dengan form interaktif, tabel data, dan elemen multimedia |
| **Durasi** | 3 jam kelas: 1 jam teori dan 2 jam praktik |
| **Prasyarat** | Pemahaman HTML dasar & semantic tags (Minggu 3) |
| **Tools** | VS Code, Live Server, browser, W3C Validator |

---

## Tujuan Pembelajaran

Setelah menyelesaikan modul ini, kamu akan mampu:

1. Membuat form HTML dengan berbagai jenis input (text, email, password, checkbox, radio, select, textarea).
2. Menggunakan label, fieldset, dan validasi form dasar.
3. Membuat tabel HTML yang terstruktur dan aksesibel (`<thead>`, `<tbody>`, `scope`).
4. Menyisipkan elemen multimedia (gambar, video, audio) ke halaman HTML.
5. Menggabungkan semua elemen ke dalam satu halaman yang rapi.

---

## Bagian A — Live Coding: Form HTML

> **Form** = cara pengguna mengirim data ke server. Kita fokus pada **struktur form-nya dulu**, pengiriman data (submit) akan dipelajari saat belajar JavaScript.

### A.1. Buat File Baru

1. Di folder `latihan-web-3` (atau buat folder baru `latihan-web-4`), buat file `form.html`.
2. Ketik struktur HTML dasar + hubungkan ke `style.css` (dari Minggu 3, atau buat baru).

### A.2. Live Coding: Form Pendaftaran Akun

Ketik kode berikut di dalam `<body>`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Pendaftaran — Latihan HTML Lanjutan</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            line-height: 1.6;
        }
        h1 { color: #2c3e50; }
        form { background: #f9f9f9; padding: 20px; border-radius: 8px; }
        label { display: block; margin-top: 12px; font-weight: bold; }
        input, select, textarea {
            width: 100%; padding: 8px; margin-top: 4px;
            border: 1px solid #ccc; border-radius: 4px;
            box-sizing: border-box;
        }
        fieldset {
            border: 1px solid #ccc; border-radius: 8px;
            padding: 12px; margin-top: 16px;
        }
        legend { font-weight: bold; padding: 0 8px; }
        .radio-group label, .checkbox-group label {
            display: inline; font-weight: normal;
        }
        button {
            margin-top: 16px; padding: 10px 20px;
            background: #2c3e50; color: white;
            border: none; border-radius: 4px;
            font-size: 16px; cursor: pointer;
        }
        button:hover { background: #34495e; }
    </style>
</head>
<body>

    <h1>Form Pendaftaran Akun</h1>
    <p>Isi form berikut untuk mendaftar. Tanda <span style="color:red;">*</span> wajib diisi.</p>

    <form action="#" method="post">

        <!-- FIELDSET 1: Data Diri -->
        <fieldset>
            <legend>Data Diri</legend>

            <label for="nama">Nama Lengkap <span style="color:red;">*</span></label>
            <input type="text" id="nama" name="nama"
                   placeholder="Masukkan nama lengkap"
                   required>

            <label for="email">Email <span style="color:red;">*</span></label>
            <input type="email" id="email" name="email"
                   placeholder="contoh@email.com"
                   required>

            <label for="password">Password <span style="color:red;">*</span></label>
            <input type="password" id="password" name="password"
                   placeholder="Minimal 8 karakter"
                   minlength="8" required>

            <label for="tanggal">Tanggal Lahir</label>
            <input type="date" id="tanggal" name="tanggal">

            <label for="jk">Jenis Kelamin <span style="color:red;">*</span></label>
            <div class="radio-group">
                <input type="radio" id="laki" name="jk" value="laki-laki" required>
                <label for="laki">Laki-laki</label>

                <input type="radio" id="perempuan" name="jk" value="perempuan">
                <label for="perempuan">Perempuan</label>
            </div>
        </fieldset>

        <!-- FIELDSET 2: Informasi Akademik -->
        <fieldset>
            <legend>Informasi Akademik</legend>

            <label for="prodi">Program Studi <span style="color:red;">*</span></label>
            <select id="prodi" name="prodi" required>
                <option value="">-- Pilih Prodi --</option>
                <option value="d3-informatika">D3 Informatika</option>
                <option value="d3-multimedia">D3 Multimedia</option>
                <option value="d3-akuntansi">D3 Akuntansi</option>
                <option value="d3-administrasi">D3 Administrasi Bisnis</option>
            </select>

            <label for="angkatan">Angkatan</label>
            <input type="number" id="angkatan" name="angkatan"
                   min="2020" max="2030" placeholder="Contoh: 2026">

            <label>Hobi / Minat (boleh pilih lebih dari 1):</label>
            <div class="checkbox-group">
                <input type="checkbox" id="hobi-web" name="hobi" value="web-design">
                <label for="hobi-web">Desain Web</label><br>

                <input type="checkbox" id="hobi-mobile" name="hobi" value="mobile-app">
                <label for="hobi-mobile">Mobile App</label><br>

                <input type="checkbox" id="hobi-ai" name="hobi" value="ai">
                <label for="hobi-ai">AI / Machine Learning</label><br>

                <input type="checkbox" id="hobi-network" name="hobi" value="networking">
                <label for="hobi-network">Jaringan</label>
            </div>
        </fieldset>

        <!-- FIELDSET 3: Pesan -->
        <fieldset>
            <legend>Catatan Tambahan</legend>

            <label for="pesan">Tulis pesan / motivasi kamu:</label>
            <textarea id="pesan" name="pesan" rows="5"
                      placeholder="Tulis di sini..."></textarea>
        </fieldset>

        <!-- Tombol Submit -->
        <button type="submit">Daftar Sekarang</button>

    </form>

</body>
</html>
```

**Simpan → buka dengan Live Server.**

### A.3. Penjelasan Jenis-Jenis Input

| Jenis Input | Fungsi | Contoh Penggunaan |
|---|---|---|
| `type="text"` | Teks biasa (satu baris) | Nama, judul |
| `type="email"` | Teks + validasi format email | Alamat email |
| `type="password"` | Teks tersembunyi (bullet) | Password |
| `type="number"` | Hanya angka + tombol naik/turun | Usia, tahun |
| `type="date"` | Date picker (kalender) | Tanggal lahir |
| `type="radio"` | Pilih **satu** dari beberapa opsi | Jenis kelamin |
| `type="checkbox"` | Pilih **beberapa** opsi | Hobi, minat |
| `type="tel"` | Nomor telepon | No. HP |
| `type="url"` | Teks + validasi format URL | Website |
| `type="file"` | Upload file | Upload foto profil |
| `<select>` | Dropdown (daftar pilihan) | Program studi |
| `<textarea>` | Teks panjang (multi-baris) | Pesan, komentar |

### A.4. Pentingnya `<label>`

```html
<!-- ✅ Benar: label terhubung ke input via "for" = id -->
<label for="nama">Nama Lengkap</label>
<input type="text" id="nama" name="nama">

<!-- ❌ Salah: label tidak terhubung -->
<label>Nama Lengkap</label>
<input type="text">
```

**Kenapa harus pakai label?**
1. **Aksesibilitas:** Screen reader bisa membaca "Nama Lengkap" saat input difokuskan.
2. **UX:** Klik pada label akan memfokuskan cursor ke input yang sesuai.
3. **Validasi:** Browser menampilkan pesan error yang lebih informatif.

### A.5. Atribut Validasi Dasar

| Atribut | Fungsi | Contoh |
|---|---|---|
| `required` | Input wajib diisi | Semua field penting |
| `minlength` / `maxlength` | Batas panjang teks | Password minimal 8 karakter |
| `min` / `max` | Batas angka | Tahun 2020–2030 |
| `placeholder` | Teks petunjuk di dalam input | "Masukkan email" |
| `pattern` | Pola regex untuk validasi | Format telepon tertentu |
| `disabled` | Nonaktifkan input | Field yang belum tersedia |
| `readonly` | Boleh dilihat, tidak bisa diedit | Field otomatis |

### A.6. Verifikasi Form

Coba:
1. Klik tombol **Daftar Sekarang** tanpa mengisi apapun → browser harus menampilkan pesan error "Please fill out this field" pada field `required`.
2. Isi email dengan format salah (misal: `bukanemail`) → tekan Submit → browser harus menampilkan pesan error tentang format email.
3. Isi password kurang dari 8 karakter → browser harus menolak.

<!-- Screenshot placeholder: Form di browser dengan pesan error validasi -->
> **📸 Screenshot D1:** Form pendaftaran di browser — pastikan terlihat semua field (Data Diri, Info Akademik, Pesan) dan tombol "Daftar Sekarang".

---

## Bagian B — Live Coding: Tabel HTML

> **Tabel** digunakan untuk menampilkan data berbentuk baris dan kolom. Penting untuk data terstruktur seperti jadwal, perbandingan harga, statistik, dsb.

### B.1. Live Coding: Tabel Sederhana

Buat file baru: `tabel.html`. Ketik kode berikut:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tabel Data — Latihan HTML Lanjutan</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 800px; margin: 20px auto; }
        table { width: 100%; border-collapse: collapse; margin: 20px 0; }
        th, td { border: 1px solid #ddd; padding: 10px 12px; text-align: left; }
        thead { background-color: #2c3e50; color: white; }
        tbody tr:nth-child(even) { background-color: #f2f2f2; }
        caption { font-size: 1.2em; font-weight: bold; margin-bottom: 10px; }
    </style>
</head>
<body>

    <h1>Data Mahasiswa D3 Informatika</h1>

    <!-- TABLE 1: Tabel Dasar -->
    <table>
        <caption>Jadwal Kuliah Semester 1</caption>
        <thead>
            <tr>
                <th scope="col">No</th>
                <th scope="col">Mata Kuliah</th>
                <th scope="col">Hari</th>
                <th scope="col">Jam</th>
                <th scope="col">SKS</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Desain Web</td>
                <td>Senin</td>
                <td>08:00 – 10:00</td>
                <td>3</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Algoritma Pemrograman</td>
                <td>Selasa</td>
                <td>10:00 – 12:00</td>
                <td>3</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Basis Data</td>
                <td>Rabu</td>
                <td>13:00 – 15:00</td>
                <td>3</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Matematika Diskrit</td>
                <td>Kamis</td>
                <td>08:00 – 10:00</td>
                <td>3</td>
            </tr>
            <tr>
                <td>5</td>
                <td>Bahasa Inggris Teknik</td>
                <td>Jumat</td>
                <td>10:00 – 12:00</td>
                <td>2</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="4"><strong>Total SKS</strong></td>
                <td><strong>14</strong></td>
            </tr>
        </tfoot>
    </table>

    <hr>

    <!-- TABLE 2: Tabel dengan colspan -->
    <h2>Perbandingan Nilai UTS</h2>
    <table>
        <thead>
            <tr>
                <th rowspan="2" scope="col">Mata Kuliah</th>
                <th colspan="3" scope="colgroup">Nilai Per Kelompok</th>
            </tr>
            <tr>
                <th scope="col">Kelompok A</th>
                <th scope="col">Kelompok B</th>
                <th scope="col">Kelompok C</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Desain Web</td>
                <td>85</td>
                <td>78</td>
                <td>90</td>
            </tr>
            <tr>
                <td>Algoritma</td>
                <td>72</td>
                <td>88</td>
                <td>81</td>
            </tr>
            <tr>
                <td>Basis Data</td>
                <td>91</td>
                <td>76</td>
                <td>85</td>
            </tr>
        </tbody>
    </table>

</body>
</html>
```

**Simpan → buka dengan Live Server.**

### B.2. Penjelasan Struktur Tabel

```
<table>
    <caption>   → Judul tabel (wajib ada untuk aksesibilitas)
    <thead>     → Bagian kepala tabel (baris judul kolom)
        <tr>    → Table row (baris)
        <th>    → Table header (judul kolom/baris)
    <tbody>     → Bagian isi tabel (data)
        <tr>
        <td>    → Table data (sel data)
    <tfoot>     → Bagian kaki tabel (total, ringkasan)
        <tr>
        <td>
</table>
```

### B.3. Atribut Penting Tabel untuk Aksesibilitas

| Atribut | Fungsi | Contoh |
|---|---|---|
| `scope="col"` | Menandai header sebagai kolom | `<th scope="col">Nama</th>` |
| `scope="row"` | Menandai header sebagai baris | `<th scope="row">Senin</th>` |
| `colspan="N"` | Sel melebar N kolom | `<td colspan="3">Gabungan</td>` |
| `rowspan="N"` | Sel melebar N baris | `<th rowspan="2">Header</th>` |

**📌 Catatan:** `scope` membantu screen reader menavigasi tabel dengan benar.

### B.4. Verifikasi

✅ **Ceklis:**
- [ ] Tabel 1 menampilkan 5 mata kuliah dengan kolom: No, MK, Hari, Jam, SKS.
- [ ] Tabel 1 memiliki `caption`, `thead`, `tbody`, dan `tfoot`.
- [ ] Tabel 2 menggunakan `colspan` dan `rowspan`.
- [ ] Warna header tabel berbeda dari isi (mudah dibedakan).

<!-- Screenshot placeholder: Tabel data di browser -->
> **📸 Screenshot D2:** Tabel data mahasiswa di browser — pastikan terlihat 2 tabel: Jadwal Kuliah dan Perbandingan Nilai, dengan styling yang rapi.

---

## Bagian C — Live Coding: Multimedia (Gambar, Video, Audio)

### C.1. Gambar — Review & Lanjutan

Kita sudah belajar `<img>` di Minggu 3. Sekarang tambahkan **figure**:

```html
<figure>
    <img src="https://placehold.co/600x400"
         alt="Pemandangan gunung saat matahari terbit"
         width="600" height="400"
         loading="lazy">
    <figcaption>Gambar 1 — Pemandangan alam sebagai contoh konten visual</figcaption>
</figure>
```

**Atribut tambahan `loading="lazy"`:** Gambar hanya dimuat saat user scroll ke bagian tersebut (hemat bandwidth & mempercepat loading halaman pertama).

### C.2. Video (HTML5)

```html
<!-- Video dari URL langsung -->
<video width="640" height="360" controls>
    <source src="video-tutorial.mp4" type="video/mp4">
    Browser kamu tidak mendukung elemen video.
</video>
```

**Jika tidak punya file video lokal**, gunakan contoh video publik:

```html
<video width="640" height="360" controls poster="https://placehold.co/640x360">
    <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
    Browser kamu tidak mendukung elemen video.
</video>
```

**Atribut video:**

| Atribut | Fungsi |
|---|---|
| `controls` | Menampilkan tombol play/pause/volume |
| `autoplay` | Video otomatis dimuat (hindari — mengganggu user) |
| `loop` | Video diulang terus-menerus |
| `muted` | Video tanpa suara |
| `poster` | Gambar thumbnail sebelum video dimainkan |
| `width` / `height` | Ukuran tampilan video |

### C.3. Audio (HTML5)

```html
<audio controls>
    <source src="https://www.w3schools.com/html/horse.mp3" type="audio/mpeg">
    Browser kamu tidak mendukung elemen audio.
</audio>
```

**Atribut audio:**

| Atribut | Fungsi |
|---|---|
| `controls` | Menampilkan tombol play/pause/volume |
| `autoplay` | Audio otomatis dimainkan (sangat tidak disarankan) |
| `loop` | Audio diulang terus-menerus |
| `muted` | Audio tanpa suara |

### C.4. Iframe — Embed Konten Eksternal

```html
<!-- Embed YouTube video -->
<iframe width="560" height="315"
    src="https://www.youtube.com/embed/dQw4w9WgXcQ"
    title="Contoh video YouTube"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
</iframe>
```

**⚠️ Penting:** Selalu isi atribut `title` pada `<iframe>` untuk aksesibilitas.

---

## Bagian D — Live Coding: Gabungkan Semua ke Satu Halaman

### D.1. Buat Halaman Lengkap

Buat file `praktikum-minggu-4.html` yang menggabungkan semua elemen yang sudah dipelajari. Struktur:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Praktikum Minggu 4 — Form, Tabel & Multimedia</title>
    <style>
        * { box-sizing: border-box; }
        body { font-family: Arial, sans-serif; max-width: 900px; margin: 0 auto; padding: 20px; line-height: 1.6; color: #333; }
        h1 { color: #2c3e50; border-bottom: 2px solid #2c3e50; padding-bottom: 8px; }
        h2 { color: #34495e; margin-top: 40px; }
        nav { background: #2c3e50; padding: 12px; border-radius: 8px; margin-bottom: 20px; }
        nav a { color: white; text-decoration: none; margin: 0 12px; }
        nav a:hover { text-decoration: underline; }
        table { width: 100%; border-collapse: collapse; margin: 16px 0; }
        th, td { border: 1px solid #ddd; padding: 8px 12px; text-align: left; }
        thead { background: #2c3e50; color: white; }
        caption { font-weight: bold; margin-bottom: 8px; }
        form { background: #f9f9f9; padding: 20px; border-radius: 8px; }
        label { display: block; margin-top: 10px; font-weight: bold; }
        input, select, textarea { width: 100%; padding: 8px; margin-top: 4px; border: 1px solid #ccc; border-radius: 4px; }
        button { margin-top: 14px; padding: 10px 24px; background: #2c3e50; color: white; border: none; border-radius: 4px; cursor: pointer; font-size: 16px; }
        button:hover { background: #34495e; }
        figure { margin: 20px 0; text-align: center; }
        figcaption { font-style: italic; margin-top: 6px; color: #666; }
        footer { background: #2c3e50; color: white; text-align: center; padding: 12px; border-radius: 8px; margin-top: 40px; }
    </style>
</head>
<body>

    <!-- HEADER & NAV -->
    <header>
        <h1>Praktikum Minggu 4</h1>
        <nav>
            <a href="#form">Form</a>
            <a href="#tabel">Tabel</a>
            <a href="#multimedia">Multimedia</a>
        </nav>
    </header>

    <main>

        <!-- SECTION: FORM -->
        <section id="form">
            <h2>1. Form Pendaftaran</h2>
            <!-- Salin isi form dari Bagian A, lengkap dengan fieldset -->
            <form action="#" method="post">
                <label for="p-nama">Nama Lengkap <span style="color:red;">*</span></label>
                <input type="text" id="p-nama" name="nama" placeholder="Nama kamu" required>

                <label for="p-email">Email <span style="color:red;">*</span></label>
                <input type="email" id="p-email" name="email" placeholder="email@contoh.com" required>

                <label for="p-prodi">Program Studi</label>
                <select id="p-prodi" name="prodi">
                    <option value="">-- Pilih --</option>
                    <option value="d3-informatika">D3 Informatika</option>
                    <option value="d3-multimedia">D3 Multimedia</option>
                </select>

                <label for="p-pesan">Pesan</label>
                <textarea id="p-pesan" name="pesan" rows="4" placeholder="Tulis pesan..."></textarea>

                <button type="submit">Kirim</button>
            </form>
        </section>

        <!-- SECTION: TABEL -->
        <section id="tabel">
            <h2>2. Tabel Perbandingan</h2>
            <table>
                <caption>Perbandingan Framework CSS</caption>
                <thead>
                    <tr>
                        <th scope="col">Fitur</th>
                        <th scope="col">CSS Biasa</th>
                        <th scope="col">Tailwind CSS</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Cara penulisan</td>
                        <td>File terpisah (.css)</td>
                        <td>Class inline di HTML</td>
                    </tr>
                    <tr>
                        <td>Learning curve</td>
                        <td>Rendah</td>
                        <td>Sedang</td>
                    </tr>
                    <tr>
                        <td>Ukuran file akhir</td>
                        <td>Terkontrol manual</td>
                        <td>Di-browse otomatis</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <!-- SECTION: MULTIMEDIA -->
        <section id="multimedia">
            <h2>3. Multimedia</h2>

            <figure>
                <img src="https://placehold.co/600x300"
                     alt="Contoh gambar placeholder untuk demonstrasi elemen img"
                     width="600" height="300" loading="lazy">
                <figcaption>Gambar 1 — Demonstrasi elemen &lt;img&gt; dengan &lt;figure&gt;</figcaption>
            </figure>

            <h3>Video</h3>
            <video width="100%" controls poster="https://placehold.co/640x360">
                <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
                Browser kamu tidak mendukung elemen video.
            </video>

            <h3>Audio</h3>
            <audio controls style="width:100%;">
                <source src="https://www.w3schools.com/html/horse.mp3" type="audio/mpeg">
                Browser kamu tidak mendukung elemen audio.
            </audio>
        </section>

    </main>

    <footer>
        <p>&copy; 2026 — Praktikum Minggu 4 | D3 Informatika</p>
    </footer>

</body>
</html>
```

### D.2. Verifikasi

**Cek halaman di browser dan pastikan:**

✅ **Ceklis:**
- [ ] Navigasi anchor (#form, #tabel, #multimedia) berfungsi (klik → scroll ke section).
- [ ] Form bisa diisi dan menampilkan pesan error jika field required kosong.
- [ ] Tabel muncul dengan benar (3 kolom, 3 baris data).
- [ ] Gambar muncul dengan caption.
- [ ] Video bisa diputar (play/pause).
- [ ] Audio bisa diputar.
- [ ] Footer muncul di bagian bawah.

<!-- Screenshot placeholder: Halaman praktikum minggu 4 — section form -->
> **📸 Screenshot D3:** Section Form di halaman praktikum — pastikan terlihat label, input field, select dropdown, textarea, dan tombol submit.

<!-- Screenshot placeholder: Halaman praktikum minggu 4 — section tabel dan multimedia -->
> **📸 Screenshot D4:** Section Tabel dan Multimedia — pastikan terlihat tabel perbandingan, gambar dengan caption, video player, dan audio player.

---

## Bagian E — Validasi & Push ke GitHub

### E.1. Validasi HTML

1. Buka **https://validator.w3.org/#validate_by_input**.
2. Copy-paste isi `praktikum-minggu-4.html` → klik **Check**.
3. Perbaiki semua error hingga hasilnya bersih.

### E.2. Push ke GitHub

```bash
# Inisialisasi (jika folder baru)
git init
git remote add origin https://github.com/NAMA_USER/latihan-web-4.git

# Commit dan push
git add .
git commit -m "Latihan HTML minggu 4: form, tabel, multimedia"
git branch -M main
git push -u origin main
```

---

## Bagian F — Latihan Mandiri

> Kerjakan latihan ini **secara mandiri**.

### F.1. Latihan 1 — Form "Survei Kepuasan"

Buat halaman `survei.html` yang berisi form survei kepuasan mahasiswa terhadap layanan kampus. Syarat:

**Field yang wajib ada:**

| # | Field | Jenis Input | Validasi |
|---|---|---|---|
| 1 | Nama | `text` | `required` |
| 2 | NIM | `number` | `required`, `minlength="8"` |
| 3 | Email | `email` | `required` |
| 4 | Fakultas | `select` (dropdown) | `required`, minimal 4 pilihan |
| 5 | Semestersaat ini | `number` | `min="1"` `max="8"` |
| 6 | Tingkat kepuasan | `radio` (1-5) | `required`, gunakan `fieldset` + `legend` |
| 7 | Saran/klasuhan | `textarea` | `rows="5"`, placeholder berisi contoh |
| 8 | Setuju dihubungi | `checkbox` | — |

**Persyaratan tambahan:**
- Gunakan minimal **2 fieldset** untuk mengelompokkan field.
- Setiap field harus punya `<label>` yang terhubung (attribute `for` = `id`).
- Gunakan `<main>`, `<header>`, `<footer>` (semantic HTML).
- Tambahkan sedikit CSS inline atau file terpisah agar form rapi.

### F.2. Latihan 2 — Tabel "Data Buku"

Buat halaman `buku.html` yang berisi tabel daftar buku. Spesifikasi:

| Kolom | Isi |
|---|---|
| No | Nomor urut |
| Judul Buku | Judul (string) |
| Pengarang | Nama pengarang |
| Tahun | Tahun terbit |
| Harga | Harga dalam Rupiah |

- Minimal **8 baris data** (buku).
- Gunakan `<thead>`, `<tbody>`, `<tfoot>` (tfoot untuk total rata-rata harga).
- Gunakan `scope="col"` pada header kolom.
- Gunakan `colspan` di footer untuk kolom "Total".
- Tambahkan `<caption>` pada tabel.
- Sertakan minimal 1 gambar (misal: sampul buku placeholder) di atas tabel dengan `<figure>` + `<figcaption>`.

### F.3. Latihan 3 — Push & Screenshot

1. Push semua file ke GitHub.
2. Ambil screenshot hasil latihan (form & tabel).
3. Pastikan tidak ada warning di W3C Validator.

**✅ Final Checklist:**
- [ ] `survei.html` valid di W3C Validator.
- [ ] `buku.html` valid di W3C Validator.
- [ ] Semua `<label>` terhubung ke `<input>` (for = id).
- [ ] Semua field required berfungsi (validasi browser).
- [ ] Tabel menggunakan `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`.
- [ ] Semua file sudah di-push ke GitHub.

---

## Bagian G — Ringkasan & Checklist

### Yang sudah kamu pelajari hari ini:

- [ ] Membuat form HTML dengan berbagai jenis input.
- [ ] Menggunakan `<label>`, `<fieldset>`, `<legend>` untuk form yang rapi & aksesibel.
- [ ] Atribut validasi: `required`, `minlength`, `min`, `max`, `placeholder`.
- [ ] Membuat tabel dengan `<table>`, `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`.
- [ ] Atribut tabel: `scope`, `colspan`, `rowspan`.
- [ ] Menyisipkan multimedia: `<img>`, `<figure>`, `<video>`, `<audio>`, `<iframe>`.

### Cheat Sheet Form Input Types:

```
text     → Teks biasa
email    → Email (validasi format)
password → Teks tersembunyi
number   → Angka + tombol +/-/↓
date     → Date picker (kalender)
tel      → Nomor telepon
url      → URL (validasi format)
radio    → Pilih 1 dari beberapa
checkbox → Pilih beberapa
file     → Upload file
color    → Color picker
range    → Slider
hidden   → Tersembunyi (data tersembunyi)
submit   → Tombol submit (default sudah ada)
reset    → Tombol reset form
```

---

## Troubleshooting

| Masalah | Solusi |
|---|---|
| Form tidak melakukan apa-apa saat submit | `action="#"` hanya placeholder — tidak ada backend. Validasi browser tetap berjalan meskipun tidak ada server |
| Radio button bisa dipilih semua | Pastikan semua radio button punya **nama yang sama** (`name="jk"`), sehingga hanya satu yang bisa dipilih |
| Label tidak memfokuskan input saat diklik | Pastikan atribut `for` pada `<label>` = `id` pada `<input>` (harus sama persis) |
| Tampilan tabel berantakan di mobile | Tabel memang tidak responsif secara default — akan dipelajari cara membuatnya responsif di CSS (Minggu 7) |
| Video/audio tidak muncul | Cek URL/path file. Jika dari URL eksternal, pastikan URL masih aktif. Gunakan file dari w3schools sebagai fallback |
| `<caption>` tidak terlihat | Pastikan `<caption>` adalah anak langsung `<table>` dan berada **sebelum** `<thead>` |
| Tombol submit reload halaman | Normal — karena `action="#"`. Saat belajar JavaScript (Minggu 10-11), kita akan mencegah reload dengan `event.preventDefault()` |

---

## Referensi

- [MDN Web Docs — HTML Forms Guide](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [MDN Web Docs — HTML Tables Guide](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables)
- [MDN Web Docs — Using HTML Audio and Video](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
- [W3C HTML Validator](https://validator.w3.org/)
- [HTML5 Form Input Types — MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
