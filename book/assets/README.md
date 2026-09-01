# Konvensi Aset (Placeholder)

Folder ini menampung aset yang dirujuk dari dokumen LaTeX. Semua jalur
bersifat **relatif terhadap folder `book/`**.

## Struktur

```
assets/
├── images/
│   └── <bab>/
│       └── <nama>.png        # atau .jpg / .pdf
└── code/
    └── <bab>/
        └── <nama>.html       # atau .css / .js
```

## Aturan Penamaan

- Gunakan nama deskriptif **tanpa spasi**, huruf kecil, pisahkan kata dengan
  tanda hubung (`-`). Contoh: `hasil-halaman-pertama.png`.
- Kelompokkan per bab: `assets/images/bab-01/`, `assets/images/bab-02/`, dst.
- Untuk tangkapan layar, gunakan akhiran yang jelas, mis.
  `tampilan-form-login.png`, `hasil-validasi-html.png`.

## Placeholder Tangkapan Layar

Gunakan lingkungan `tangkapanlayar` di `preamble.tex` untuk menandai lokasi
gambar yang belum tersedia. Lingkungan ini menerima tiga argumen:

1. **Jalur aset yang diharapkan** — mis. `assets/images/bab-01/hasil.png`
2. **Keterangan (caption)** — teks yang akan menjadi keterangan gambar
3. **Instruksi mahasiswa** — apa yang harus dilakukan/diamati mahasiswa

Contoh:

```latex
\begin{tangkapanlayar}
  {assets/images/bab-01/hasil-halaman-pertama.png}
  {Hasil halaman pertama di peramban.}
  {Buka index.html di peramban dan bandingkan hasilnya dengan gambar.}
\end{tangkapanlayar}
```

Saat aset tersedia, ganti blok tersebut dengan:

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.8\linewidth]{bab-01/hasil-halaman-pertama.png}
  \caption{Hasil halaman pertama di peramban.}
  \label{fig:hasil-halaman-pertama}
\end{figure}
```

> Catatan: `\graphicspath{{assets/images/}}` sudah disetel di `preamble.tex`,
> sehingga `\includegraphics` cukup menyebut nama bab + berkas.

## Berkas Kode

Berkas kode contoh disimpan di `assets/code/<bab>/`. Untuk menampilkan isi
berkas di dokumen, gunakan lingkungan `lstlisting` (sudah dimuat ElegantBook):

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

## Checklist Sebelum Kompilasi

- [ ] Semua `\includegraphics` merujuk berkas yang benar-benar ada.
- [ ] Semua placeholder `tangkapanlayar` mencantumkan jalur aset yang valid.
- [ ] Nama berkas tidak mengandung spasi atau karakter khusus.