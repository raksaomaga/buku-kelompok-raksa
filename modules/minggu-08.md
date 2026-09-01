# Minggu 8 — Git & GitHub Dasar: Init, Commit, Push, Pull

**Mata Kuliah:** Pengenalan Workshop Desain Web
**Program Studi:** D3 Informatika — Semester 1
**Durasi:** 1 pertemuan praktikum (3 jam)

---

## Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa diharapkan dapat:

1. Menjelaskan kegunaan Git dan GitHub.
2. Menginstal dan mengonfigurasi Git di komputer.
3. Menginisialisasi repository Git (`git init`).
4. Melakukan commit dengan pesan yang baik.
5. Membuat repository di GitHub dan menghubungkannya.
6. Melakukan push dan pull.

---

## Alat yang Dibutuhkan

- Laptop dengan **Git** terinstal.
- Akun **GitHub** (sudah dibuat di minggu 1).
- VSCode dengan terminal.
- Folder proyek dari minggu sebelumnya (mis. `latihan-css`).

---

## Ringkasan Teori (Minimal)

### Apa itu Git?

Git adalah **sistem kontrol versi** (version control system). Git melacak setiap perubahan pada file, sehingga Anda bisa:

- Melihat riwayat perubahan.
- Kembali ke versi sebelumnya.
- Bekerja bersama orang lain tanpa menimpa pekerjaan.

### Apa itu GitHub?

GitHub adalah **layanan hosting** untuk repository Git di internet. GitHub memungkinkan Anda menyimpan kode di cloud, berkolaborasi, dan (nanti) men-deploy website.

### Alur Kerja Dasar

```
Working Directory → (git add) → Staging Area → (git commit) → Repository Lokal → (git push) → GitHub
```

- **Working directory** — file yang sedang Anda edit.
- **Staging area** — file yang "dipilih" untuk di-commit.
- **Repository lokal** — riwayat commit di komputer Anda.
- **GitHub** — salinan repository di internet.

---

## Praktikum 1 — Memeriksa Instalasi Git

**Langkah 1:** Buka terminal di VSCode (menu Terminal → New Terminal).

**Langkah 2:** Ketik perintah berikut untuk memeriksa versi Git:

```bash
git --version
```

**Langkah 3:** Jika muncul versi (mis. `git version 2.40.0`), Git sudah terinstal. Jika belum, ikuti langkah instalasi di bawah.

**Langkah 4 (jika belum terinstal):** Unduh Git dari https://git-scm.com/downloads, instal dengan pengaturan default, lalu ulangi Langkah 2.

> **Catatan:** Saat instalasi, pilih editor default sesuai keinginan (mis. VSCode) dan biarkan opsi lain default.

---

## Praktikum 2 — Konfigurasi Git

Sebelum mulai, Git perlu tahu **siapa Anda**. Ini akan tercatat di setiap commit.

**Langkah 1:** Di terminal, ketik (ganti dengan nama dan email Anda):

```bash
git config --global user.name "Nama Anda"
git config --global user.email "email@contoh.com"
```

**Langkah 2:** Gunakan email yang sama dengan akun GitHub Anda.

**Langkah 3:** Periksa konfigurasi:

```bash
git config --list
```

**Langkah 4:** Pastikan `user.name` dan `user.email` muncul dengan benar.

> **Tips:** Konfigurasi `--global` berlaku untuk semua proyek di komputer Anda. Lakukan sekali saja.

---

## Praktikum 3 — Inisialisasi Repository (git init)

**Langkah 1:** Buka folder proyek yang sudah ada, misalnya `latihan-css` dari minggu 5.

**Langkah 2:** Di terminal, pastikan Anda berada di folder proyek. Periksa dengan:

```bash
pwd
```

**Langkah 3:** Inisialisasi repository Git:

```bash
git init
```

**Langkah 4:** Periksa status repository:

```bash
git status
```

Anda akan melihat pesan seperti `On branch master` dan daftar file yang belum di-track (untracked).

> **Catatan:** `git init` membuat folder tersembunyi `.git` yang berisi riwayat versi. Jangan hapus folder ini.

---

## Praktikum 4 — Membuat File .gitignore

**Langkah 1:** Buat file bernama `.gitignore` di folder proyek.

**Langkah 2:** Isi dengan file/folder yang **tidak perlu** di-commit:

```
node_modules/
.DS_Store
*.log
```

**Langkah 3:** Simpan file.

> **Catatan:** `.gitignore` memberi tahu Git file mana yang harus diabaikan. Berguna untuk file sementara atau sensitif.

---

## Praktikum 5 — Commit Pertama (git add & git commit)

**Langkah 1:** Tambahkan semua file ke staging area:

```bash
git add .
```

**Langkah 2:** Periksa status:

```bash
git status
```

File yang berwarna hijau (staged) siap di-commit.

**Langkah 3:** Lakukan commit pertama:

```bash
git commit -m "Proyek awal latihan CSS"
```

**Langkah 4:** Periksa riwayat commit:

```bash
git log --oneline
```

Anda akan melihat satu commit dengan pesan "Proyek awal latihan CSS".

> **Tips penulisan pesan commit yang baik:**
> - Singkat dan jelas (maksimal ~50 karakter).
> - Jelaskan **apa** yang diubah, bukan sekadar "update".
> - Contoh: `"Menambahkan halaman profil"`, `"Memperbaiki bug navbar"`, `"Mengubah warna tombol"`.

---

## Praktikum 6 — Membuat Repository di GitHub

**Langkah 1:** Buka https://github.com dan login.

**Langkah 2:** Klik tombol **+** di pojok kanan atas, lalu pilih **New repository**.

**Langkah 3:** Isi:
- **Repository name:** `latihan-css` (atau nama proyek Anda).
- **Description:** (opsional) "Latihan CSS minggu 5".
- **Visibility:** pilih **Public** (agar bisa di-deploy ke GitHub Pages nanti).
- **Jangan centang** "Add a README file" (karena kita sudah punya file).

**Langkah 4:** Klik **Create repository**.

**Langkah 5:** Anda akan melihat halaman berisi perintah untuk menghubungkan repository lokal ke GitHub. Simpan halaman ini — kita akan menggunakannya di praktikum berikutnya.

> **Catatan:** Jangan tutup halaman ini dulu. Perhatikan bagian "…or push an existing repository from the command line".

---

## Praktikum 7 — Menghubungkan dan Push (git remote & git push)

**Langkah 1:** Kembali ke terminal VSCode.

**Langkah 2:** Tambahkan remote (alamat repository GitHub). Ganti `USERNAME` dan `NAMA-REPO` sesuai milik Anda:

```bash
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
```

**Langkah 3:** Periksa remote:

```bash
git remote -v
```

**Langkah 4:** Push commit ke GitHub. Ganti `main` dengan nama branch Anda jika berbeda (lihat `git branch`):

```bash
git branch -M main
git push -u origin main
```

**Langkah 5:** Jika diminta login, ikuti petunjuk (browser akan terbuka untuk autentikasi GitHub).

**Langkah 6:** Buka halaman repository di GitHub dan refresh. File-file Anda sekarang ada di GitHub!

> **Catatan:** `-u` (upstream) membuat Git mengingat bahwa branch `main` terhubung ke `origin/main`, sehingga push berikutnya cukup `git push`.

---

## Praktikum 8 — Mengubah File dan Commit Lagi

**Langkah 1:** Ubah salah satu file di proyek Anda (mis. tambahkan paragraf baru di `index.html`).

**Langkah 2:** Lihat perubahan yang terjadi:

```bash
git status
git diff
```

**Langkah 3:** Tambahkan dan commit perubahan:

```bash
git add .
git commit -m "Menambahkan paragraf baru di index"
```

**Langkah 4:** Push ke GitHub:

```bash
git push
```

**Langkah 5:** Refresh halaman GitHub dan lihat bahwa perubahan sudah masuk.

> **Alur yang benar:** `git add` → `git commit` → `git push`. Ulangi setiap kali selesai mengerjakan sesuatu.

---

## Praktikum 9 — Pull (Mengambil Perubahan)

**Langkah 1:** Buka halaman repository di GitHub.

**Langkah 2:** Klik file `index.html`, lalu klik ikon pensil (edit) di kanan atas.

**Langkah 3:** Ubah sesuatu (mis. ganti judul), lalu klik **Commit changes** di bagian bawah.

**Langkah 4:** Kembali ke terminal VSCode. Ambil perubahan dari GitHub:

```bash
git pull
```

**Langkah 5:** Buka `index.html` di VSCode — perubahan yang Anda buat di GitHub sekarang ada di komputer lokal.

> **Catatan:** `git pull` mengambil perubahan terbaru dari GitHub ke komputer Anda. Lakukan ini sebelum mulai bekerja jika bekerja bersama tim.

---

## Latihan Mandiri

1. Buat repository baru di GitHub bernama `latihan-flexbox`.
2. Hubungkan folder `latihan-flexbox` (dari minggu 6) ke repository tersebut.
3. Lakukan commit dengan pesan yang jelas untuk semua file.
4. Push ke GitHub.
5. Ubah satu file, commit, dan push lagi.
6. Buat perubahan di GitHub (edit langsung), lalu `git pull` di komputer.
7. Periksa `git log --oneline` dan pastikan semua commit tercatat.

---

## Hasil yang Diharapkan (Expected Output)

Setelah menyelesaikan semua praktikum, Anda memiliki:

- Git terinstal dan terkonfigurasi dengan nama dan email Anda.
- Repository lokal `latihan-css` dengan minimal 2 commit.
- Repository di GitHub bernama `latihan-css` berisi semua file proyek.
- Kemampuan untuk melakukan `git add`, `git commit`, `git push`, dan `git pull`.
- Riwayat commit yang bisa dilihat di `git log --oneline` dan di halaman GitHub.

---

## Troubleshooting

| Masalah | Kemungkinan Penyebab | Solusi |
|---|---|---|
| `git` bukan perintah yang dikenali | Git belum terinstal / tidak di PATH | Instal Git dari git-scm.com, restart terminal/VSCode |
| `git push` meminta password terus | Autentikasi belum diatur | Gunakan login browser saat diminta, atau atur Personal Access Token |
| `fatal: remote origin already exists` | Remote sudah pernah ditambahkan | Gunakan `git remote set-url origin <URL>` untuk mengganti |
| `fatal: not a git repository` | Bukan di folder proyek | Pastikan berada di folder yang sudah `git init` (periksa dengan `pwd`) |
| Push ditolak (rejected) | Remote punya commit yang tidak ada di lokal | Jalankan `git pull` dulu, lalu `git push` lagi |
| File tidak muncul di GitHub | Belum di-commit / di-push | Jalankan `git add .`, `git commit -m "..."`, lalu `git push` |
| Commit tidak tercatat | Belum `git add` | Jalankan `git add .` sebelum `git commit` |
| Branch bernama `master` bukan `main` | Versi Git lama | Jalankan `git branch -M main` sebelum push |

---

## Rangkuman

- Git = kontrol versi lokal; GitHub = hosting repository di internet.
- `git init` — mulai repository.
- `git add .` — pindahkan file ke staging area.
- `git commit -m "pesan"` — simpan snapshot perubahan.
- `git push` — kirim commit ke GitHub.
- `git pull` — ambil perubahan dari GitHub.
- `git status` — lihat kondisi repository.
- `git log --oneline` — lihat riwayat commit.
- Tulis pesan commit yang jelas dan singkat.

---

## Referensi

- Git Documentation: https://git-scm.com/doc
- GitHub Docs — Getting Started with Git: https://docs.github.com/en/get-started
- GitHub Skills: https://skills.github.com/
- Pro Git Book (gratis): https://git-scm.com/book/en/v2

---

## Screenshot Placeholder

> **📸 Screenshot 1:** Hasil `git --version` di terminal (menunjukkan versi Git terinstal).
>
> **📸 Screenshot 2:** Hasil `git config --list` (menampilkan user.name dan user.email).
>
> **📸 Screenshot 3:** Hasil `git status` setelah `git init` (file untracked).
>
> **📸 Screenshot 4:** Hasil `git status` setelah `git add .` (file staged, berwarna hijau).
>
> **📸 Screenshot 5:** Hasil `git log --oneline` (riwayat commit).
>
> **📸 Screenshot 6:** Halaman repository di GitHub setelah push pertama (berisi file proyek).
>
> **📸 Screenshot 7:** Halaman GitHub yang menampilkan riwayat commit.
>
> **📸 Screenshot 8:** Hasil `git pull` yang berhasil mengambil perubahan dari GitHub.
