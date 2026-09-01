# Modul Perkuliahan Desain Web — Buku LaTeX

Dokumen buku (modul) ditulis dengan LaTeX menggunakan template
[ElegantBook](https://github.com/ElegantLaTeX/ElegantBook) (ElegantLaTeX).
Desain visual template dipertahankan; hanya palet warna yang disetel ke
biru/teal yang terkendali sesuai kesepakatan.

> **Baca dulu:** Panduan Git lengkap (fork, clone, branch, commit, push,
> pull request, merge) ada di **README.md di root repositories**. Dokumen ini
> fokus pada alur kerja di dalam folder `book/`.

---

## Alur Kerja Mahasiswa (Ringkas)

Setiap minggu, kelompok Anda mengerjakan satu bab buku. Ikuti urutan berikut:

1. **Baca bab yang relevan** di `chapters/minggu-XX.tex` (mis. `minggu-01.tex`).
   Bab berisi placeholder tangkapan layar dan blok kode yang perlu Anda lengkapi.
2. **Tambahkan tangkapan layar** ke folder `assets/images/minggu-XX/`.
   Gunakan nama deskriptif tanpa spasi, mis. `hasil-halaman-pertama.png`.
3. **Tambahkan kode contoh** (HTML/CSS/JS) ke folder `assets/code/minggu-XX/`.
4. **Ganti placeholder LaTeX** di `chapters/minggu-XX.tex`:
   - Ganti blok `tangkapanlayar` dengan `\includegraphics` (lihat bagian
     [Menyisipkan Tangkapan Layar](#menyisipkan-tangkapan-layar) di bawah).
   - Tampilkan kode contoh dengan lingkungan `lstlisting`.
5. **Kompilasi** `main.tex` **dua kali** dengan XeLaTeX untuk memastikan
   dokumen tidak error (lihat [Cara Kompilasi](#cara-kompilasi)).
6. **Commit dan push** melalui **branch + pull request** — ikuti alur Git
   lengkap di **README.md root repositories**.

> **Penting:** Jangan pernah commit langsung ke branch `master`. Selalu
> kerjakan di branch fitur, lalu buat pull request agar anggota lain bisa
> meninjau sebelum digabung.

---

## Struktur Folder

```
book/
├── main.tex                  # Dokumen utama (kompilasi dimulai dari sini)
├── preamble.tex              # Preamble: bahasa Indonesia + lingkungan pedagogis
├── elegantbook.cls           # (vendor) Kelas ElegantBook v4.7 — diletakkan di root agar ditemukan
├── chapters/
│   ├── minggu-01.tex         # Bab per minggu (01–16)
│   ├── minggu-02.tex
│   └── ... s.d. minggu-16.tex
├── assets/
│   ├── images/               # Tangkapan layar (lihat konvensi aset di bawah)
│   │   ├── minggu-01/
│   │   ├── minggu-02/
│   │   └── ... s.d. minggu-16/
│   └── code/                 # Berkas kode contoh
│       ├── minggu-01/
│       └── ...
└── README.md                 # File ini
```

---

## Prasyarat

- Distribusi TeX dengan **XeLaTeX** (disarankan TeX Live 2025 atau lebih baru).
- Paket yang dibutuhkan (umumnya sudah tersedia di TeX Live penuh):
  `elegantbook`, `tcolorbox`, `ctex`, `newtx`, `tex-gyre`, `listings`,
  `enumitem`, `hyperref`, `graphicx`, `fontspec`.
- Font **TeX Gyre Termes** dan **TeX Gyre Heros** (disertakan TeX Live).

> Kelas `elegantbook.cls` disertakan di root folder ini (vendor) agar
> kompilasi konsisten. Jika TeX Anda sudah memiliki versi ElegantBook,
> berkas lokal ini yang akan dipakai (prioritas folder kerja).

---

## Cara Kompilasi

Kompilasi **wajib** menggunakan XeLaTeX (dua kali untuk referensi silang):

```powershell
# dari dalam folder book/
xelatex -synctex=1 -interaction=nonstopmode main.tex
xelatex -synctex=1 -interaction=nonstopmode main.tex
```

Hasil: `main.pdf` di folder `book/`.

### Jika ada daftar pustaka (reference.bib)

```powershell
xelatex -synctex=1 -interaction=nonstopmode main.tex
biber main
xelatex -synctex=1 -interaction=nonstopmode main.tex
xelatex -synctex=1 -interaction=nonstopmode main.tex
```

### Membersihkan berkas sementara

```powershell
Remove-Item main.aux, main.log, main.out, main.toc, main.lof, main.lot -ErrorAction SilentlyContinue
```

---

## Menyisipkan Tangkapan Layar

Setiap bab berisi **placeholder** tangkapan layar menggunakan lingkungan
`tangkapanlayar`. Lingkungan ini **tidak** menampilkan gambar; ia menampilkan
kotak yang mencantumkan jalur aset yang diharapkan, keterangan, dan instruksi
mahasiswa.

### Contoh placeholder yang harus diganti

```latex
\begin{tangkapanlayar}
  {assets/images/minggu-01/hasil-halaman-pertama.png}
  {Hasil halaman pertama di peramban.}
  {Buka index.html di peramban dan bandingkan hasilnya.}
\end{tangkapanlayar}
```

### Ganti dengan `\includegraphics`

Setelah aset tersedia, hapus blok `tangkapanlayar` di atas dan ganti dengan:

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.85\linewidth]{minggu-01/hasil-halaman-pertama.png}
  \caption{Hasil halaman pertama di peramban.}
  \label{fig:hasil-halaman-pertama}
\end{figure}
```

> **Catatan:** `\graphicspath{{assets/images/}}` sudah disetel di
> `preamble.tex`, sehingga `\includegraphics` cukup menyebut nama folder
> minggu + nama berkas (mis. `minggu-01/hasil-halaman-pertama.png`).

---

## Menampilkan Kode Contoh

Simpan berkas kode di `assets/code/minggu-XX/`, lalu tampilkan isinya di
dokumen dengan lingkungan `lstlisting` (sudah dimuat ElegantBook):

```latex
\begin{lstlisting}[language=HTML, caption={Struktur dasar HTML}, label={lst:html-dasar}]
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Halaman Pertama</title>
</head>
<body>
  <h1>Halo, Dunia!</h1>
</body>
</html>
\end{lstlisting}
```

Bahasa yang didukung di `preamble.tex`: `HTML`, `css`, `JavaScript`, `bash`.

---

## Konvensi Aset

- **Gambar**: simpan di `assets/images/<bab>/<nama>.png` (atau `.jpg`/`.pdf`).
  Gunakan nama deskriptif tanpa spasi, mis. `hasil-halaman-pertama.png`.
- **Kode**: simpan berkas contoh di `assets/code/<bab>/<nama>.html`.
- Referensi gambar di teks gunakan `\figref{label}` (disediakan ElegantBook)
  atau `\ref{fig:label}`.

---

## Lingkungan Pedagogis yang Tersedia

Semua lingkungan didefinisikan di `preamble.tex`:

| Lingkungan        | Fungsi                                   |
|-------------------|------------------------------------------|
| `capaian`         | Capaian pembelajaran bab                  |
| `tujuanpraktik`   | Tujuan sesi praktik                       |
| `langkah`         | Langkah kerja bernomor (enumerate)        |
| `catatan`         | Catatan penting                           |
| `tip`             | Kiat praktis                              |
| `peringatan`      | Peringatan / kesalahan umum               |
| `latihan`         | Latihan bernomor (bab.nomor)              |
| `tangkapanlayar`  | Placeholder non-gambar untuk tangkapan layar |

---

## Menambahkan Bab Baru

1. Salin `chapters/chapter-template.tex` menjadi `chapters/bab-XX.tex`.
2. Isi konten sesuai kerangka (capaian, tujuan praktik, materi, langkah,
   tangkapan layar, catatan/tips/peringatan, latihan, rangkuman).
3. Daftarkan di `main.tex`:
   ```latex
   \input{chapters/bab-XX.tex}
   ```

---

## Palet Warna

Palet biru/teal yang terkendali didefinisikan di `preamble.tex`:

| Peran        | Warna        | RGB            |
|--------------|--------------|----------------|
| Utama        | Biru         | `38, 92, 148`  |
| Sekunder     | Teal         | `0, 128, 128`  |
| Tersier      | Biru tua     | `0, 105, 148`  |
| Peringatan   | Amber        | `176, 130, 20` |

---

## Lisensi

- Template ElegantBook dilisensikan di bawah LPPL-1.3c (lihat
  `vendor/elegantbook.cls` dan repositori ElegantLaTeX).
- Konten modul ini adalah milik institusi/penulis masing-masing.
