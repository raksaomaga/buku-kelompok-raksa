# Modul Perkuliahan Desain Web — Lembar Kerja Mingguan (Markdown)

Folder ini berisi **16 lembar kerja mingguan** dalam format Markdown
(`minggu-01.md` sampai `minggu-16.md`). Ini adalah **panduan belajar utama**
Anda selama satu semester.

> **Baca dulu:** Panduan Git lengkap (fork, clone, branch, commit, push,
> pull request, merge) ada di **README.md di root repositories**. Dokumen ini
> menjelaskan cara memakai lembar kerja mingguan.

---

## Apa Isi Folder Ini?

```
modules/
├── minggu-01.md    ← Pengantar web & setup lingkungan kerja
├── minggu-02.md    ← Figma dasar: wireframe & mockup
├── minggu-03.md    ← HTML dasar: struktur & semantic tag
├── minggu-04.md    ← HTML lanjutan: form, tabel, multimedia
├── minggu-05.md    ← CSS dasar: selector, box model, typography
├── minggu-06.md    ← CSS layout: flexbox
├── minggu-07.md    ← CSS layout: grid & responsive design
├── minggu-08.md    ← Git & GitHub dasar
├── minggu-09.md    ← GitHub kolaborasi: branch, pull request, GitHub Pages
├── minggu-10.md    ← JavaScript dasar
├── minggu-11.md    ← JavaScript: event handling & manipulasi DOM
├── minggu-12.md    ← Pengenalan Tailwind CSS
├── minggu-13.md    ← Pengenalan React
├── minggu-14.md    ← Workshop proyek akhir (mentoring)
├── minggu-15.md    ← Penyelesaian proyek akhir
└── minggu-16.md    ← Presentasi & evaluasi akhir
```

Setiap file adalah **satu pertemuan** yang berdiri sendiri. Anda bisa membuka
file mana pun tanpa harus membaca file lain terlebih dahulu.

---

## Alokasi Waktu (Seragam untuk Semua Minggu)

Setiap lembar kerja dirancang untuk **3 jam kelas** dengan pembagian:

| Durasi | Kegiatan |
|---|---|
| **1 jam** | **Teori** — penjelasan konsep, contoh, dan demonstrasi |
| **2 jam** | **Praktik** — latihan langsung, live coding, dan tugas mandiri |

> Pembagian ini sama untuk semua minggu, sehingga Anda bisa mengatur ritme
> belajar yang konsisten: pahami konsep di jam pertama, lalu langsung
> praktikkan di dua jam berikutnya.

---

## Cara Memilih dan Membaca Lembar Kerja Mingguan

1. **Tentukan minggu** yang sedang berjalan (mis. minggu ke-5).
2. **Buka file yang sesuai**: `minggu-05.md`.
3. **Baca dari atas ke bawah** — setiap file mengikuti urutan yang sama:
   - **Tujuan Pembelajaran** — apa yang akan Anda kuasai di akhir sesi.
   - **Alat yang Dibutuhkan** — tools yang harus disiapkan.
   - **Ringkasan Teori** — konsep inti (bagian 1 jam).
   - **Langkah Praktik** — instruksi langkah-demi-langkah (bagian 2 jam).
   - **Latihan Mandiri** — tugas untuk dikerjakan sendiri.
   - **Ringkasan & Checklist** — poin penting dan hal yang harus dicek.
   - **Troubleshooting** — solusi masalah umum.
   - **Referensi** — tautan dokumentasi resmi.

> **Tips:** Jangan lompat-lompat. Kerjakan langkah praktik secara berurutan
> agar hasilnya sesuai dengan yang diharapkan.

---

## Kaitan dengan Bab Buku LaTeX

Setiap lembar kerja Markdown **berpasangan dengan satu bab** di buku LaTeX:

| Lembar Kerja | Bab Buku LaTeX |
|---|---|
| `modules/minggu-01.md` | `book/chapters/minggu-01.tex` |
| `modules/minggu-02.md` | `book/chapters/minggu-02.tex` |
| ... | ... |
| `modules/minggu-16.md` | `book/chapters/minggu-16.tex` |

- **Lembar kerja Markdown** = panduan praktis harian (mudah dibaca di GitHub).
- **Bab buku LaTeX** = dokumentasi formal yang dikompilasi menjadi PDF.

Keduanya memuat materi yang sama dan harus **sinkron**. Saat Anda mengerjakan
lembar kerja minggu tertentu, bab LaTeX yang sama adalah tempat Anda
**menyumbangkan hasil kerja** (tangkapan layar dan kode contoh).

---

## Di Mana Anda Menyumbangkan Screenshot & Kode

Lembar kerja Markdown **tidak** menyimpan gambar atau kode — itu hanya panduan.
Hasil kerja Anda disumbangkan ke **buku LaTeX**:

| Hasil Kerja | Lokasi Penyimpanan |
|---|---|
| **Tangkapan layar** | `book/assets/images/minggu-XX/` |
| **Kode contoh** (HTML/CSS/JS) | `book/assets/code/minggu-XX/` |

Contoh:

```
book/assets/images/minggu-01/vs-code-index.html.png
book/assets/code/minggu-05/style-box-model.css
```

Setelah aset tersedia, Anda **mengganti placeholder** di bab LaTeX yang
bersangkutan (blok `tangkapanlayar` → `\includegraphics`, dan menampilkan kode
dengan `lstlisting`). Panduan lengkapnya ada di **`book/README.md`**.

> **Ringkasnya:** Baca lembar kerja Markdown untuk tahu *apa yang harus
> dilakukan*, lalu wujudkan hasilnya di buku LaTeX melalui branch + pull
> request (lihat README root).

---

## Checklist Sebelum Mengumpulkan

- [ ] Semua langkah praktik di lembar kerja sudah dikerjakan.
- [ ] Tangkapan layar sudah disimpan di `book/assets/images/minggu-XX/`.
- [ ] Kode contoh sudah disimpan di `book/assets/code/minggu-XX/`.
- [ ] Placeholder di bab LaTeX sudah diganti dengan gambar/kode yang sebenarnya.
- [ ] Buku LaTeX berhasil dikompilasi (XeLaTeX dua kali) tanpa error.
- [ ] Perubahan sudah di-commit dan di-merge melalui pull request.
