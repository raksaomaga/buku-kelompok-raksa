# Minggu 9 — GitHub Kolaborasi: Branch, Pull Request, GitHub Pages

**Mata Kuliah:** Pengenalan Workshop Desain Web
**Program Studi:** D3 Informatika — Semester 1
**Durasi:** 3 jam kelas: 1 jam teori dan 2 jam praktik

---

## Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa diharapkan dapat:

1. Membuat dan berpindah branch di Git.
2. Menggabungkan branch (merge).
3. Membuat pull request (PR) di GitHub.
4. Men-deploy website statis ke GitHub Pages.
5. Menjelaskan alur kerja kolaborasi dasar dengan Git/GitHub.

---

## Alat yang Dibutuhkan

- Laptop dengan **Git** terinstal (dari minggu 8).
- Akun **GitHub**.
- Repository GitHub yang sudah ada (mis. `latihan-css` dari minggu 8).
- VSCode dengan terminal.

---

## Ringkasan Teori (Minimal)

### Apa itu Branch?

Branch adalah **cabang** dari riwayat commit. Branch memungkinkan Anda bekerja pada fitur baru **tanpa mengganggu** kode utama.

```
main:      A --- B --- C
                          \
fitur-navbar:              D --- E
```

- **`main`** (atau `master`) — branch utama, kode yang stabil.
- **Branch fitur** — cabang untuk mengerjakan fitur tertentu, lalu digabungkan kembali ke `main`.

### Apa itu Pull Request (PR)?

Pull request adalah **permintaan untuk menggabungkan** perubahan dari satu branch ke branch lain (biasanya ke `main`). PR memungkinkan orang lain **meninjau** kode sebelum digabung.

### Apa itu GitHub Pages?

GitHub Pages adalah layanan **hosting gratis** dari GitHub untuk website statis (HTML/CSS/JS). Website Anda akan dapat diakses publik melalui URL seperti:

```
https://USERNAME.github.io/NAMA-REPO/
```

---

## Praktikum 1 — Membuat Branch

**Langkah 1:** Buka folder proyek `latihan-css` di VSCode (pastikan sudah menjadi repository Git dari minggu 8).

**Langkah 2:** Periksa branch saat ini:

```bash
git branch
```

Anda akan melihat `* main` (tanda `*` menunjukkan branch aktif).

**Langkah 3:** Buat branch baru bernama `fitur-navbar`:

```bash
git branch fitur-navbar
```

**Langkah 4:** Pindah ke branch baru:

```bash
git checkout fitur-navbar
```

**Langkah 5:** Periksa lagi:

```bash
git branch
```

Sekarang `*` berada di `fitur-navbar`.

> **Cara cepat:** `git checkout -b fitur-navbar` membuat branch **dan** langsung pindah ke sana dalam satu perintah.

---

## Praktikum 2 — Bekerja di Branch Baru

**Langkah 1:** Di branch `fitur-navbar`, buat file baru bernama `navbar.html` (bisa salin dari minggu 6).

**Langkah 2:** Tambahkan dan commit perubahan:

```bash
git add .
git commit -m "Menambahkan halaman navbar"
```

**Langkah 3:** Periksa riwayat:

```bash
git log --oneline
```

**Langkah 4:** Sekarang pindah kembali ke `main`:

```bash
git checkout main
```

**Langkah 5:** Periksa file di folder — `navbar.html` **tidak ada** di branch `main`, karena perubahan hanya ada di branch `fitur-navbar`.

> **Konsep penting:** Setiap branch memiliki riwayat commit sendiri. Perubahan di satu branch tidak terlihat di branch lain sampai digabungkan.

---

## Praktikum 3 — Menggabungkan Branch (Merge)

**Langkah 1:** Pastikan Anda berada di branch `main`:

```bash
git checkout main
```

**Langkah 2:** Gabungkan branch `fitur-navbar` ke `main`:

```bash
git merge fitur-navbar
```

**Langkah 3:** Periksa file — `navbar.html` sekarang ada di `main`.

**Langkah 4:** Periksa riwayat:

```bash
git log --oneline
```

**Langkah 5:** Push `main` ke GitHub:

```bash
git push
```

> **Catatan:** Setelah merge, branch `fitur-navbar` bisa dihapus jika tidak diperlukan: `git branch -d fitur-navbar`.

---

## Praktikum 4 — Push Branch ke GitHub

**Langkah 1:** Buat branch baru lagi:

```bash
git checkout -b fitur-kontak
```

**Langkah 2:** Buat file `kontak.html` sederhana dan commit:

```bash
git add .
git commit -m "Menambahkan halaman kontak"
```

**Langkah 3:** Push branch baru ke GitHub:

```bash
git push -u origin fitur-kontak
```

**Langkah 4:** Buka halaman repository di GitHub. Klik dropdown **branch** (biasanya bertuliskan `main`). Anda akan melihat branch `fitur-kontak` di daftar.

> **Catatan:** `-u origin fitur-kontak` membuat branch lokal terhubung ke branch di GitHub.

---

## Praktikum 5 — Membuat Pull Request (PR)

**Langkah 1:** Di halaman repository GitHub, setelah push branch `fitur-kontak`, akan muncul banner kuning "Compare & pull request". Klik banner tersebut.

**Langkah 2:** Jika banner tidak muncul, klik tab **Pull requests**, lalu tombol **New pull request**.

**Langkah 3:** Atur:
- **base:** `main` (tujuan penggabungan).
- **compare:** `fitur-kontak` (sumber perubahan).

**Langkah 4:** Isi judul PR, misalnya: `"Menambahkan halaman kontak"`.

**Langkah 5:** Isi deskripsi PR, misalnya:

```
Menambahkan halaman kontak sederhana dengan form.
- Form nama, email, dan pesan
- Styling dasar dengan CSS
```

**Langkah 6:** Klik **Create pull request**.

**Langkah 7:** Amati halaman PR. Anda bisa melihat:
- **Files changed** — perbedaan kode yang diusulkan.
- **Commits** — daftar commit dalam PR.
- **Conversation** — diskusi/review.

> **Tips:** PR adalah tempat untuk **review** sebelum kode digabung. Rekan tim bisa memberi komentar pada baris kode tertentu.

---

## Praktikum 6 — Merge Pull Request

**Langkah 1:** Di halaman PR yang sudah dibuat, klik tombol **Merge pull request**.

**Langkah 2:** Klik **Confirm merge**.

**Langkah 3:** Klik **Delete branch** untuk membersihkan branch `fitur-kontak` di GitHub (opsional).

**Langkah 4:** Kembali ke terminal VSCode. Ambil perubahan yang sudah di-merge:

```bash
git checkout main
git pull
```

**Langkah 5:** Periksa bahwa `kontak.html` sekarang ada di `main` lokal.

> **Alur kolaborasi lengkap:**
> 1. Buat branch fitur.
> 2. Kerjakan dan commit.
> 3. Push branch ke GitHub.
> 4. Buat PR.
> 5. Review & merge.
> 6. `git pull` di lokal.

---

## Praktikum 7 — Menyiapkan GitHub Pages

**Langkah 1:** Pastikan Anda berada di branch `main` dan semua perubahan sudah di-push.

**Langkah 2:** Buka halaman repository di GitHub.

**Langkah 3:** Klik tab **Settings**.

**Langkah 4:** Di menu kiri, klik **Pages**.

**Langkah 5:** Pada bagian **Build and deployment**:
- **Source:** pilih **Deploy from a branch**.
- **Branch:** pilih `main` dan folder `/ (root)`.
- Klik **Save**.

**Langkah 6:** Tunggu beberapa saat (1–2 menit) hingga proses build selesai.

**Langkah 7:** Refresh halaman. Akan muncul URL website Anda, misalnya:

```
https://USERNAME.github.io/latihan-css/
```

**Langkah 8:** Klik URL tersebut atau buka di browser. Website Anda sekarang **live di internet**!

> **Catatan:** URL GitHub Pages mengikuti format `https://USERNAME.github.io/NAMA-REPO/`. Pastikan ada file `index.html` di root repository agar website menampilkan halaman utama.

---

## Praktikum 8 — Memperbarui Website di GitHub Pages

**Langkah 1:** Ubah salah satu file di proyek (mis. ganti judul di `index.html`).

**Langkah 2:** Commit dan push:

```bash
git add .
git commit -m "Memperbarui judul halaman"
git push
```

**Langkah 3:** Tunggu beberapa saat, lalu refresh website Anda. Perubahan otomatis muncul.

> **Catatan:** GitHub Pages otomatis men-deploy ulang setiap kali ada push ke branch `main`. Tidak perlu konfigurasi tambahan.

---

## Latihan Mandiri

1. Buat branch baru bernama `fitur-tentang`.
2. Buat file `tentang.html` berisi halaman "Tentang" sederhana.
3. Commit dan push branch ke GitHub.
4. Buat pull request dari `fitur-tentang` ke `main`.
5. Merge PR tersebut.
6. `git pull` di komputer lokal.
7. Pastikan GitHub Pages menampilkan halaman terbaru.
8. Buka website Anda di ponsel dan pastikan tampil dengan baik.

---

## Hasil yang Diharapkan (Expected Output)

Setelah menyelesaikan semua praktikum, Anda memiliki:

- Kemampuan membuat, berpindah, dan menggabungkan branch.
- Pengalaman membuat dan merge pull request di GitHub.
- Website statis yang **ter-deploy** di GitHub Pages dengan URL publik.
- Pemahaman alur kerja kolaborasi: branch → commit → push → PR → merge → pull.
- Repository GitHub dengan riwayat commit yang rapi dan terstruktur.

---

## Troubleshooting

| Masalah | Kemungkinan Penyebab | Solusi |
|---|---|---|
| `git checkout` gagal | Ada perubahan yang belum di-commit | Commit atau stash perubahan dulu: `git stash` |
| Merge conflict | Dua branch mengubah file yang sama | Buka file yang konflik, pilih perubahan yang benar, hapus penanda `<<<<<<<`, lalu commit |
| PR tidak muncul | Branch belum di-push | Jalankan `git push -u origin NAMA-BRANCH` |
| GitHub Pages 404 | Tidak ada `index.html` di root | Pastikan file `index.html` ada di root repository |
| GitHub Pages belum muncul | Proses build masih berjalan | Tunggu 1–2 menit, lalu refresh |
| Website tidak update | Push belum dilakukan / build berjalan | Pastikan `git push` berhasil, tunggu build selesai |
| URL tidak bisa diakses | Repository private | GitHub Pages hanya untuk repository **public** (atau akun Pro) |
| Merge conflict saat `git pull` | Perubahan lokal dan remote bentrok | Commit perubahan lokal dulu, lalu `git pull` |

---

## Rangkuman

- **Branch** memungkinkan bekerja pada fitur tanpa mengganggu `main`.
- `git branch` — lihat branch; `git checkout -b nama` — buat & pindah branch.
- `git merge nama-branch` — gabungkan branch ke branch aktif.
- **Pull request** adalah permintaan penggabungan yang bisa direview.
- **GitHub Pages** men-deploy website statis secara gratis.
- Alur kolaborasi: branch → commit → push → PR → merge → pull.
- GitHub Pages otomatis update setiap push ke `main`.

---

## Referensi

- GitHub Docs — About Branches: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches
- GitHub Docs — About Pull Requests: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests
- GitHub Docs — GitHub Pages: https://docs.github.com/en/pages
- Git Branching (Pro Git): https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell

---

## Screenshot Placeholder

> **📸 Screenshot 1:** Hasil `git branch` yang menampilkan branch `main` dan `fitur-navbar`.
>
> **📸 Screenshot 2:** Hasil `git log --oneline` di branch `fitur-navbar` (menampilkan commit tambahan).
>
> **📸 Screenshot 3:** Hasil `git merge fitur-navbar` yang berhasil.
>
> **📸 Screenshot 4:** Halaman GitHub yang menampilkan dropdown branch (ada `fitur-kontak`).
>
> **📸 Screenshot 5:** Halaman pembuatan pull request (base: main, compare: fitur-kontak).
>
> **📸 Screenshot 6:** Halaman PR yang menampilkan tab Conversation, Commits, dan Files changed.
>
> **📸 Screenshot 7:** Halaman PR setelah di-merge (tombol "Merged").
>
> **📸 Screenshot 8:** Halaman Settings → Pages yang menampilkan konfigurasi deploy dari branch main.
>
> **📸 Screenshot 9:** Website yang ter-deploy di GitHub Pages (tampil di browser).
>
> **📸 Screenshot 10:** Website di GitHub Pages diakses dari ponsel (tampilan responsif).
