# Minggu 1 — Pengantar Web & Setup Lingkungan Kerja

---

| Item | Detail |
|---|---|
| **Minggu ke-** | 1 |
| **Topik** | Pengantar web & workflow design-to-code, instalasi tools |
| **Output** | Lingkungan kerja (VS Code, browser, akun GitHub) siap digunakan |
| **Durasi** | 3 jam kelas: 1 jam teori dan 2 jam praktik |
| **Prasyarat** | Laptop/PC dengan akses internet |
| **Tools** | VS Code, browser (Chrome/Firefox), akun GitHub, Terminal/PowerShell |

---

## Tujuan Pembelajaran

Setelah menyelesaikan modul ini, kamu akan mampu:

1. Menjelaskan secara singkat alur kerja **design-to-code** dalam pengembangan web.
2. Menginstal dan mengonfigurasi VS Code beserta ekstensi yang diperlukan.
3. Membuat akun GitHub dan melakukan **push pertama** ke repository.
4. Membuka file HTML di browser menggunakan **Live Server**.

---

## Bagian A — Pemahaman Singkat: Apa Itu Web dan Alur Kerja Design-to-Code?

### A.1. Web Itu Apa?

Website adalah kumpulan halaman yang diakses melalui browser (Chrome, Firefox, Edge). Setiap halaman terdiri dari tiga lapis utama:

| Lapis | Bahasa | Fungsi |
|---|---|---|
| Struktur | HTML | "Tulang" — menentukan elemen apa yang ada di halaman |
| Tampilan | CSS | "Kulit" — menentukan warna, ukuran, posisi, font |
| Interaksi | JavaScript | "Otot" — menentukan apa yang terjadi saat diklik/di-scroll |

> **Kamu tidak perlu menghafal ini sekarang.** Cukup tahu ada tiga lapis, karena di minggu-minggu berikutnya kita akan belajar satu per satu.

### A.2. Alur Kerja Design-to-Code

```
 Ide / Kebutuhan
      │
      ▼
 ┌─────────┐
 │  Figma   │  ← Kamu mendesain tampilan di sini
 └────┬─────┘
      │ Export / lihat referensi
      ▼
 ┌─────────┐
 │  VS Code │  ← Kamu menulis kode HTML/CSS/JS di sini
 └────┬─────┘
      │ Simpan file
      ▼
 ┌─────────┐
 │ Browser  │  ← Kamu melihat hasilnya di sini
 └────┬─────┘
      │ Push ke GitHub
      ▼
 ┌─────────┐
 │ GitHub   │  ← Kode disimpan & bisa diakses siapa saja
 └─────────┘
```

**Intinya:** Desain dulu di Figma → implementasi di VS Code → lihat hasil di browser → simpan di GitHub.

---

## Bagian B — Live Coding: Instalasi VS Code & Ekstensi

> **Ikuti langkah-langkah berikut secara berurutan.** Pengerjaan bersama dosen.

### B.1. Download & Instal VS Code

1. Buka browser, kunjungi **https://code.visualstudio.com/**.
2. Klik tombol **Download for Windows** (atau sesuai OS kamu).
3. Jalankan installer → klik **Next** di setiap langkah → pastikan opsi berikut **diceklis**:
   - ✅ Add "Open with Code" action to Windows Explorer file context menu
   - ✅ Add "Open with Code" action to Windows Explorer directory context menu
   - ✅ Register Code as an editor for supported file types
4. Klik **Install** → tunggu selesai → klik **Finish**.

### B.2. Instal Ekstensi Penting

1. Buka VS Code.
2. Tekan **Ctrl + Shift + X** untuk membuka panel Extensions.
3. Cari dan instal ekstensi berikut satu per satu:

| # | Nama Ekstensi | Fungsi |
|---|---|---|
| 1 | **Live Server** (Ritwick Dey) | Preview halaman HTML secara otomatis di browser setiap kali file disimpan |
| 2 | **HTML CSS Support** | Autocomplete kelas CSS di file HTML |
| 3 | **Prettier - Code formatter** | Format kode otomatis agar rapi |
| 4 | **VS Code Intellicode** | Saran kode cerdas dari AI |

### B.3. Verifikasi Instalasi

Lakukan langkah berikut dan pastikan hasilnya sesuai:

1. Buka VS Code.
2. Buat folder baru: **File → Open Folder → New Folder** → beri nama `latihan-web-1`.
3. Di dalam folder itu, buat file baru bernama `index.html`.
4. Ketik `!` lalu tekan **Tab** — VS Code akan mengisi template HTML otomatis (snippets Emmet).
5. Ubah isi `<title>` menjadi `Halo Dunia`.
6. Tambahkan inside `<body>`:

```html
<h1>Halo, Dunia!</h1>
<p>Ini halaman web pertamaku.</p>
```

7. Klik kanan di editor → **Open with Live Server**.
8. Browser akan terbuka secara otomatis menampilkan teks "Halo, Dunia!".

**✅ Ceklis:** Apakah browser menampilkan teks "Halo, Dunia!"?

<!-- Screenshot placeholder: VS Code dengan file index.html terbuka -->
> **📸 Screenshot A1:** VS Code dengan file `index.html` — pastikan panel Explorer (kiri) menunjukkan folder `latihan-web-1` dan file `index.html`.

<!-- Screenshot placeholder: Browser yang menampilkan "Halo, Dunia!" -->
> **📸 Screenshot A2:** Browser yang menampilkan hasil "Halo, Dunia!" — pastikan URL di address bar dimulai dengan `127.0.0.1:5500`.

---

## Bagian C — Live Coding: Membuat Akun GitHub & Repository Pertama

### C.1. Buat Akun GitHub

1. Buka **https://github.com**.
2. Klik **Sign up**.
3. Isi email, password, dan username (gunakan format: `nama-nim` misal: `budi-2301001`).
4. Selesaikan verifikasi.
5. ✅ **Ceklis:** Apakah kamu berhasil masuk ke halaman dashboard GitHub?

<!-- Screenshot placeholder: Dashboard GitHub setelah login -->
> **📸 Screenshot A3:** Dashboard GitHub setelah berhasil login — pastikan username terlihat di pojok kanan atas.

### C.2. Buat Repository Baru

1. Di dashboard GitHub, klik tombol **+** (pojok kanan atas) → **New repository**.
2. Isi form berikut:
   - **Repository name:** `latihan-web-1`
   - **Description:** `Latihan pertama — Halo Dunia`
   - **Public** (pilih ini agar bisa diakses)
   - ✅ **Add a README file** (centang)
3. Klik **Create repository**.

### C.3. Hubungkan Folder Lokal ke GitHub (Push Pertama)

> **Kamu perlu Git terinstal di laptop.** Jika belum, download dari **https://git-scm.com/download/win** dan instal dengan pengaturan default.

Buka **Terminal** di VS Code (**Ctrl + `** atau menu **Terminal → New Terminal**), lalu ketik perintah berikut **satu per satu**:

```bash
# 1. Buat file README.md pertama kali
echo "# latihan-web-1" >> README.md

# 2. Inisialisasi Git di folder lokal
git init

# 3. Tambahkan file README.md untuk di-commit
git add README.md

# 4. Buat commit pertama
git commit -m "first commit"

# 5. Ubah nama branch ke main
git branch -M main

# 6. Hubungkan ke remote repository (ganti NAMA_USER dengan username GitHub-mu)
git remote add origin https://github.com/NAMA_USER/latihan-web-1.git

# 7. Push ke GitHub
git push -u origin main
```

**⚠️ Catatan Penting:**
- Jika Git meminta credential (username & password), gunakan **Personal Access Token** sebagai password. Caranya:
  1. Buka **https://github.com/settings/tokens**.
  2. Klik **Generate new token (classic)**.
  3. Beri nama token (misal: `latihan-web`), centang **repo**, lalu klik **Generate**.
  4. Copy token → gunakan sebagai password saat Git meminta.

### C.4. Verifikasi

1. Buka **https://github.com/NAMA_USER/latihan-web-1** di browser.
2. Pastikan file `index.html` terlihat di daftar file.

✅ **Ceklis:** Apakah file `index.html` muncul di halaman repository GitHub-mu?

<!-- Screenshot placeholder: Halaman repository di GitHub yang menunjukkan index.html -->
> **📸 Screenshot A4:** Halaman repository GitHub `latihan-web-1` — pastikan file `index.html` terlihat di daftar file.

---

## Bagian D — Latihan Mandiri

> Kerjakan latihan ini **secara mandiri** tanpa bantuan dosen. Gunakan apa yang sudah kamu praktikkan di Bagian B dan C.

### D.1. Latihan 1 — Perbarui Halaman

1. Buka file `index.html` di VS Code.
2. Tambahkan elemen berikut **di bawah** `<p>` yang sudah ada:

```html
<h2>Tentang Aku</h2>
<p>Nama: [nama lengkap kamu]</p>
<p>NIM: [NIM kamu]</p>
<p>Prodi: D3 Informatika</p>
```

3. Simpan file (**Ctrl + S**).
4. Periksa browser — apakah teks baru muncul di bawah "Halo, Dunia!"?
5. Commit dan push perubahan ke GitHub:

```bash
git add .
git commit -m "Menambahkan informasi diri"
git push
```

### D.2. Latihan 2 — Coba Live Server

1. Matikan Live Server (lihat pojok kanan bawah VS Code, klik **Port: 5500 → Stop**).
2. Buka file `index.html` langsung dari File Explorer Windows (double-click).
3. Perhatikan URL di browser — apakah berbeda dari URL Live Server? (`file:///...` vs `127.0.0.1:5500`)
4. Ubah salah satu teks di VS Code → simpan.
5. Muat ulang (Reload) browser secara manual.
6. Aktifkan kembali Live Server.
7. Ubah teks lagi → simpan → perhatikan apakah browser memperbarui diri **otomatis** tanpa kamu harus reload.

**Pertanyaan refleksi:**
- Mengapa Live Server lebih nyaman daripada membuka file langsung?
- Apa keuntungan menyimpan kode di GitHub?

<!-- Screenshot placeholder: Perbandingan URL Live Server vs file langsung -->
> **📸 Screenshot A5:** Perbandingan URL di browser — kiri: Live Server (`127.0.0.1:5500/index.html`), kanan: file langsung (`file:///C:/.../index.html`).

---

## Bagian E — Ringkasan & Checklist

### Yang sudah kamu pelajari hari ini:

- [ ] Alur kerja design-to-code (Figma → VS Code → Browser → GitHub)
- [ ] Instalasi VS Code + ekstensi (Live Server, Prettier, dsb.)
- [ ] Membuat file HTML pertama dan melihatnya di browser
- [ ] Membuat akun GitHub dan repository pertama
- [ ] Push kode pertama ke GitHub menggunakan Git
- [ ] Live Server: preview otomatis tanpa reload

### Jangan lupa:

- [ ] Semua screenshot sudah diambil.
- [ ] Kode sudah di-push ke GitHub (cek di browser).
- [ ] VS Code dan ekstensi berfungsi dengan baik.

---

## Troubleshooting

| Masalah | Solusi |
|---|---|
| Live Server tidak muncul di menu kanan-klik | Pastikan ekstensi "Live Server" sudah terinstal dan VS Code di-restart |
| Browser menampilkan `This site can't be reached` | Pastikan Live Server sudah berjalan (lihat status bar pojok kanan bawah VS Code) |
| Git menolak push karena "repository not found" | Pastikan URL remote benar: `git remote -v` untuk cek, `git remote set-url origin URL_BARU` untuk perbaiki |
| Git meminta password tapi tidak bisa login | Gunakan **Personal Access Token** (bukan password GitHub biasa). Lihat Bagian C.3 |
| VS Code menampilkan error "command not found: git" | Install Git dari **https://git-scm.com/download/win**, lalu restart VS Code |
| File `index.html` tidak muncul di GitHub | Pastikan sudah menjalankan `git add .`, `git commit`, dan `git push` |

---

## Referensi

- [MDN Web Docs — Your First Website](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web)
- [GitHub Docs — Hello World](https://docs.github.com/en/get-started/quickstart/hello-world)
- [VS Code Documentation — Getting Started](https://code.visualstudio.com/docs/getstarted/intro)
- [Live Server Extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
