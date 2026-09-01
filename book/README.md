# Modul Perkuliahan Desain Web — Buku LaTeX

Dokumen buku (modul) ditulis dengan LaTeX menggunakan template
[ElegantBook](https://github.com/ElegantLaTeX/ElegantBook) (ElegantLaTeX).
Desain visual template dipertahankan; hanya palet warna yang disetel ke
biru/teal yang terkendali sesuai kesepakatan.

## Struktur Folder

```
book/
├── main.tex                  # Dokumen utama (kompilasi dimulai dari sini)
├── preamble.tex              # Preamble: bahasa Indonesia + lingkungan pedagogis
├── elegantbook.cls           # (vendor) Kelas ElegantBook v4.7 — diletakkan di root agar ditemukan
├── chapters/
│   └── chapter-template.tex  # Kerangka bab — salin untuk bab baru
├── assets/
│   ├── images/               # Gambar (lihat konvensi aset di bawah)
│   └── code/                 # Berkas kode contoh
└── README.md                 # File ini
```

## Prasyarat

- Distribusi TeX dengan **XeLaTeX** (disarankan TeX Live 2025 atau lebih baru).
- Paket yang dibutuhkan (umumnya sudah tersedia di TeX Live penuh):
  `elegantbook`, `tcolorbox`, `ctex`, `newtx`, `tex-gyre`, `listings`,
  `enumitem`, `hyperref`, `graphicx`, `fontspec`.
- Font **TeX Gyre Termes** dan **TeX Gyre Heros** (disertakan TeX Live).

> Kelas `elegantbook.cls` disertakan di root folder ini (vendor) agar
> kompilasi konsisten. Jika TeX Anda sudah memiliki versi ElegantBook,
> berkas lokal ini yang akan dipakai (prioritas folder kerja).

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

## Menambahkan Bab Baru

1. Salin `chapters/chapter-template.tex` menjadi `chapters/bab-XX.tex`.
2. Isi konten sesuai kerangka (capaian, tujuan praktik, materi, langkah,
   tangkapan layar, catatan/tips/peringatan, latihan, rangkuman).
3. Daftarkan di `main.tex`:
   ```latex
   \input{chapters/bab-XX.tex}
   ```

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

### Contoh penggunaan `tangkapanlayar`

```latex
\begin{tangkapanlayar}
  {assets/images/bab-01/hasil-halaman-pertama.png}
  {Hasil halaman pertama di peramban.}
  {Buka index.html di peramban dan bandingkan hasilnya.}
\end{tangkapanlayar}
```

Lingkungan ini **tidak** menampilkan gambar; ia menampilkan kotak placeholder
yang mencantumkan jalur aset yang diharapkan, keterangan, dan instruksi
mahasiswa. Ganti blok tersebut dengan `\includegraphics` setelah aset tersedia.

## Konvensi Aset

- **Gambar**: simpan di `assets/images/<bab>/<nama>.png` (atau `.jpg`/`.pdf`).
  Gunakan nama deskriptif tanpa spasi, mis. `hasil-halaman-pertama.png`.
- **Kode**: simpan berkas contoh di `assets/code/<bab>/<nama>.html`.
- Referensi gambar di teks gunakan `\figref{label}` (disediakan ElegantBook)
  atau `\ref{fig:label}`.

## Palet Warna

Palet biru/teal yang terkendali didefinisikan di `preamble.tex`:

| Peran        | Warna        | RGB            |
|--------------|--------------|----------------|
| Utama        | Biru         | `38, 92, 148`  |
| Sekunder     | Teal         | `0, 128, 128`  |
| Tersier      | Biru tua     | `0, 105, 148`  |
| Peringatan   | Amber        | `176, 130, 20` |

## Lisensi

- Template ElegantBook dilisensikan di bawah LPPL-1.3c (lihat
  `vendor/elegantbook.cls` dan repositori ElegantLaTeX).
- Konten modul ini adalah milik institusi/penulis masing-masing.