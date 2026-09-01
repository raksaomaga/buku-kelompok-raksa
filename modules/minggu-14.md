# Minggu 14: Workshop Proyek Akhir — Riset UI/UX & Perencanaan Desain

**Topik:** Heuristic evaluation, benchmarking, dan perancangan ulang halaman e-governance di Figma  
**Durasi:** 3 jam kelas: 1 jam teori dan 2 jam praktik
**Format:** Workshop kelompok (3 orang) dengan sesi mentoring

---

## 1. Tujuan Pembelajaran

Di akhir sesi ini, setiap kelompok diharapkan dapat:

1. Melakukan **heuristic evaluation** terhadap halaman website e-governance yang dipilih menggunakan 10 Usability Heuristics (Nielsen Norman Group).
2. Mendokumentasikan **pain point** dan hasil **benchmarking** secara terstruktur.
3. Membuat **wireframe** dan **mockup** desain ulang di Figma berdasarkan temuan riset.
4. Menyusun **rasional desain** yang menghubungkan temuan riset dengan keputusan desain.

---

## 2. Peralatan yang Dibutuhkan

| Tool | Kegunaan | Status |
|---|---|---|
| Browser (Chrome/Firefox) | Akses website target & heuristic checklist | Wajib |
| Figma (akun gratis) | Wireframing & mockup | Wajib |
| VSCode | Persiapan untuk minggu 15 | Opsional |
| GitHub | Repository proyek akhir | Wajib |
| Google Docs / Markdown editor | Dokumentasi hasil riset | Wajib |

---

## 3. Langkah-Langkah Hands-On

### Tahap 1: Persiapan Kelompok (± 10 menit)

1. **Buka repository GitHub** kelompok (yang sudah dibuat dari minggu 8–9 atau buat baru).

2. **Buat branch baru** untuk proyek akhir:
   ```bash
   git checkout -b final-project
   ```

3. **Buat struktur folder** di dalam repo:
   ```
   final-project/
   ├── research/
   │   ├── heuristic-evaluation.md
   │   └── benchmarking.md
   ├── design/
   │   └── (file Figma export nanti)
   ├── src/
   │   ├── index.html
   │   ├── css/
   │   ├── js/
   │   └── assets/
   └── README.md
   ```

4. **Push branch** ke GitHub:
   ```bash
   git add .
   git commit -m "feat: inisialisasi struktur folder proyek akhir"
   git push -u origin final-project
   ```

> **Screenshot placeholder:**
> ```
> [Screenshot: Struktur folder repo di VSCode Explorer]
> ```

---

### Tahap 2: Identifikasi Website Target (± 10 menit)

1. **Pilih satu halaman** dari website e-governance / layanan publik. Contoh yang bisa dipilih:
   - Portal layanan perizinan daerah
   - Halaman pendaftaran online instansi pemerintah
   - Portal informasi desa/kelurahan
   - Halaman pengaduan masyarakat online

2. **Dokumentasikan** di `research/heuristic-evaluation.md`:
   ```markdown
   # Riset UI/UX — Proyek Akhir

   ## Informasi Umum
   - **Nama Website:** [nama website]
   - **URL:** [url]
   - **Halaman yang diriset:** [nama/spesifikasi halaman]
   - **Tanggal Riset:** [tanggal]
   - **Anggota Kelompok:**
     - [Nama 1] — [peran]
     - [Nama 2] — [peran]
     - [Nama 3] — [peran]
   ```

3. **Screenshot halaman asli** dari berbagai ukuran layar (desktop & mobile) untuk dokumentasi:
   - Buka Developer Tools (F12) → toggle device toolbar → pilih ukuran mobile.
   - Ambil screenshot desktop (Ctrl+Shift+S di Firefox, atau klik kanan → "Take screenshot").

> **Screenshot placeholder:**
> ```
> [Screenshot: Tampilan halaman website target — versi desktop]
> [Screenshot: Tampilan halaman website target — versi mobile]
> ```

---

### Tahap 3: Heuristic Evaluation (± 35 menit)

Ikuti langkah-langkah berikut secara berkelompok. Diskusikan setiap heuristik dan catat temuan di `research/heuristic-evaluation.md`.

#### 3a. Buka Heuristic Checklist

Gunakan 10 Usability Heuristics dari Nielsen Norman Group:

| # | Heuristik | Pertanyaan Panduan |
|---|---|---|
| 1 | **Visibility of System Status** | Apakah pengguna tahu apa yang sedang terjadi di halaman? |
| 2 | **Match Between System and Real World** | Apakah bahasa dan istilah yang digunakan sesuai dengan dunia nyata pengguna? |
| 3 | **User Control and Freedom** | Apakah pengguna bisa membatalkan aksi atau navigasi dengan mudah? |
| 4 | **Consistency and Standards** | Apakah tampilan dan interaksi konsisten di seluruh halaman? |
| 5 | **Error Prevention** | Apakah ada perlindungan untuk mencegah pengguna melakukan kesalahan? |
| 6 | **Recognition Rather Than Recall** | Apakah pengguna perlu mengingat informasi dari satu bagian ke bagian lain? |
| 7 | **Flexibility and Efficiency of Use** | Apakah ada cara cepat untuk pengguna yang sudah terbiasa? |
| 8 | **Aesthetic and Minimalist Design** | Apakah antarmuka bebas dari elemen yang tidak perlu? |
| 9 | **Help Users Recognize, Diagnose, and Recover from Errors** | Apakah pesan error jelas dan membantu? |
| 10 | **Help and Documentation** | Apakah ada panduan atau bantuan jika pengguna kebingungan? |

#### 3b. Evaluasi Setiap Heuristik

Untuk setiap heuristik, catat di dalam file Markdown:

```markdown
## Heuristic #1: Visibility of System Status

**Skor Pelanggaran (0–4):** [0 = tidak ada masalah, 4 = masalah kritis]

**Temuan:**
- [Deskripsi temuan — apa yang terlihat/ditemukan di halaman]
- [Tambah temuan jika ada]

**Screenshot Bukti:**
![Screenshot](../assets/heuristic-1.png)

**Dampak ke Pengguna:**
- [Penjelasan singkat bagaimana ini mempengaruhi pengalaman pengguna]

**Kaitan dengan Rekomendasi Desain:**
- [Saran perbaikan yang akan diterapkan di desain ulang]
```

> **Tips:**
> - Jangan khawatir soal skor yang "benar" — yang penting adalah **kemampuan menjelaskan** mengapa suatu masalah muncul.
> - Satu heuristik bisa memiliki **0 atau lebih** temuan. Jika tidak ada masalah, tulis "Tidak ditemukan pelanggaran signifikan."

#### 3c._ringkasan Temuan

Buat ringkasan di bagian bawah file:

```markdown
## Ringkasan Heuristic Evaluation

| # | Heuristik | Skor | Jumlah Temuan |
|---|---|---|---|
| 1 | Visibility of System Status | X | X |
| 2 | Match Between System and Real World | X | X |
| ... | ... | ... | ... |
| **Total** | | **XX** | **XX** |

### Top 3 Pain Point Terbesar:
1. [Pain point — dari heuristic ke-...]
2. [Pain point — dari heuristic ke-...]
3. [Pain point — dari heuristic ke-...]
```

> **Screenshot placeholder:**
> ```
> [Screenshot: Dokumentasi heuristic evaluation di Markdown — tampilan di VSCode atau GitHub]
> [Screenshot: Tabel ringkasan temuan]
> ```

---

### Tahap 4: Benchmarking Singkat (± 15 menit)

Bandinkan halaman target dengan **2–3 website sejenis** yang memiliki fitur serupa.

1. **Pilih minimal 2 website** untuk dibandingkan (contoh: website pemerintah daerah lain, website layanan publik modern seperti JKN, dsb).

2. **Buat file** `research/benchmarking.md`:

```markdown
# Benchmarking

## Website yang Dibandingkan

### Website A: [Nama]
- **URL:** [url]
- **Halaman sejenis:** [deskripsi]
- **Kelebihan:**
  - [kelebihan 1]
  - [kelebihan 2]
- **Kekurangan:**
  - [kekurangan 1]
- **Screenshot:**
  ![Website A](../assets/benchmark-a.png)

### Website B: [Nama]
- **URL:** [url]
- **Halaman sejenis:** [deskripsi]
- **Kelebihan:**
  - [kelebihan 1]
  - [kelebihan 2]
- **Kekurangan:**
  - [kekurangan 1]
- **Screenshot:**
  ![Website B](../assets/benchmark-b.png)

## Perbandingan Fitur

| Fitur | Website Target | Website A | Website B | Desain Ulang Kami |
|---|---|---|---|---|
| [Fitur 1] | ❌ Tidak ada | ✅ Ada | ⚠️ Sebagian | ✅ (Rencana) |
| [Fitur 2] | ... | ... | ... | ... |

## Pelajaran dari Benchmarking:
1. [Insight 1 — fitur/praktik terbaik yang ingin diadopsi]
2. [Insight 2 — apa yang perlu dihindari]
3. [Insight 3 — kesempatan untuk berbeda/diferensiasi]
```

> **Screenshot placeholder:**
> ```
> [Screenshot: Perbandingan visual antara website target dan website A/B]
> ```

---

### Tahap 5: Perencanaan Desain di Figma (± 40 menit)

Buka **Figma** (desktop app atau browser) dan mulai mendesain.

#### 5a. Buat Frame Wireframe (± 15 menit)

1. **Buka file Figma** yang sudah ada atau buat file baru:
   - Klik **"New design file"** di dashboard Figma.

2. **Buat frame** untuk wireframe:
   - Tekan `F` → pilih ukuran frame (Desktop: 1440×900, Mobile: 375×812).
   - Beri nama frame: "Wireframe — Desktop" dan "Wireframe — Mobile".

3. **Buat wireframe** — sketsa tata letak **tanpa warna**, hanya:
   - Kotak untuk area konten.
   - Garis/garis putus untuk teks placeholder.
   - Ikon sederhana untuk elemen navigasi.
   - Anotasi singkat di sebelah setiap elemen.

> **Tips wireframe:**
> - Gunakan hanya warna abu-abu, hitam, putih.
> - Jangan tambahkan warna, gambar, atau font khusus.
> - Fokus pada **struktur** dan **alur pengguna**, bukan visual.
>
> **Screenshot placeholder:**
> ```
> [Screenshot: Wireframe desktop di Figma — tampilan keseluruhan]
> [Screenshot: Wireframe mobile di Figma — tampilan keseluruhan]
> ```

#### 5b. Buat Mockup (± 20 menit)

1. **Duplikat frame** wireframe → rename menjadi "Mockup — Desktop" dan "Mockup — Mobile".

2. **Terapkan visual** pada mockup:
   - Warna merek (maks. 3–4 warna).
   - Font yang sudah dipilih (Google Fonts atau font system).
   - Gambar/ikon asli.
   - Spasi dan tipografi yang konsisten.

3. **Pastikan konsistensi** antar halaman:
   - Header/footer identik.
   - Tipografi konsisten (heading, body, caption).
   - Spasi antar elemen konsisten.

> **Screenshot placeholder:**
> ```
> [Screenshot: Mockup desktop di Figma — tampilan keseluruhan]
> [Screenshot: Mockup desktop di Figma — zoom ke area header/navigasi]
> [Screenshot: Mockup mobile di Figma — tampilan keseluruhan]
> ```

#### 5c. Tulis Rasional Desain (± 5 menit)

Di file `research/rasional-desain.md` atau langsung di README:

```markdown
## Rasional Desain

### Kaitan Temuan Riset → Keputusan Desain

| # | Temuan Riset | Keputusan Desain | Penjelasan |
|---|---|---|---|
| 1 | [Pain point dari heuristic ke-X] | [Apa yang didesain ulang] | [Mengapa keputusan ini diambil, berdasarkan temuan riset] |
| 2 | [Temuan dari benchmarking] | [Apa yang diadopsi/diubah] | [Rasionalnya] |
| 3 | ... | ... | ... |

### Prinsip Desain yang Diterapkan:
1. [Prinsip 1 — misal "Consistency" dari heuristic #4]
2. [Prinsip 2 — misal "Minimalism" dari heuristic #8]
3. [Prinsip 3 — misal "Error Prevention" dari heuristic #5]
```

> **Screenshot placeholder:**
> ```
> [Screenshot: Anotasi rasional desain di Figma (gunakan fitur komentar/text annotation)]
> ```

---

### Tahap 6: Commit & Push (± 5 menit)

1. **Kembali ke VSCode** → buka terminal.

2. **Pastikan semua file sudah tersimpan** di folder yang benar.

3. **Commit dan push:**
   ```bash
   git add .
   git commit -m "feat: hasil riset heuristic evaluation, benchmarking, dan wireframe/mockup"
   git push
   ```

4. **Buka pull request** (opsional, tapi disarankan):
   - Buka repository di GitHub.
   - Klik **"Compare & pull request"**.
   - Tambahkan deskripsi: "Riset UI/UX dan desain awal proyek akhir — re-desain [nama website]".
   - Klik **"Create pull request"**.

> **Screenshot placeholder:**
> ```
> [Screenshot: Commit history di GitHub — terlihat branch final-project]
> [Screenshot: Pull request yang sudah dibuat]
> ```

---

## 4. Output yang Diharapkan

Setelah sesi ini, setiap kelompok harus memiliki:

| # | Output | Lokasi | Status |
|---|---|---|---|
| 1 | Dokumen heuristic evaluation | `research/heuristic-evaluation.md` | ☐ |
| 2 | Dokumen benchmarking | `research/benchmarking.md` | ☐ |
| 3 | Wireframe (desktop & mobile) | File Figma | ☐ |
| 4 | Mockup (desktop & mobile) | File Figma | ☐ |
| 5 | Rasional desain | `research/rasional-desain.md` atau README | ☐ |
| 6 | Screenshot halaman asli | `assets/` atau folder `research/` | ☐ |
| 7 | Commit di GitHub | Branch `final-project` | ☐ |

---

## 5. Checklist Kelompok

Sebelum meninggalkan kelas, pastikan semua anggota bisa menjawab:

- [ ] "Apa 3 pain point terbesar yang ditemukan di website target?"
- [ ] "Mengapa desain kami berubah dari versi asli?"
- [ ] "Di mana file Figma bisa diakses oleh semua anggota?"
- [ ] "Bagaimana cara setiap anggota mengklaim tugas implementasi di minggu 15?"
- [ ] "Apakah semua anggota sudah bisa mengakses repository GitHub?"

---

## 6. Troubleshooting

| Masalah | Solusi |
|---|---|
| Website target tidak bisa diakses | Gunakan **Wayback Machine** (web.archive.org) untuk versi terakhir yang bisa diakses, atau pilih website lain |
| Tidak yakin bagaimana mengisi heuristic evaluation | Lihat contoh di [Nielsen Norman Group](https://www.nngroup.com/articles/ten-usability-heuristics/) — fokus pada kemampuan menjelaskan, bukan skor sempurna |
| Figma tidak bisa dibuka di browser | Gunakan **Figma desktop app** (download dari figma.com), atau pastikan browser sudah versi terbaru |
| Anggota kelompok berbeda kampus/hari | Semua file riset di GitHub — akses dari mana saja. Desain Figma bisa di-share via link Figma |
| Sulit menentukan website target | Pilih website pemerintah daerah (contoh: portal layanan disdukcapil, BPJS, atau website desa). Hindari website yang sudah sangat modern |
| Tidak bisa membuat branch di Git | Pastikan sudah meng-clone repository ke lokal. Jika masih gagal, cek `git status` untuk memastikan tidak ada perubahan yang belum di-commit |
| Merasa pekerjaan terlalu banyak untuk 1 pertemuan | Fokus pada **heuristic evaluation** dan **wireframe** dulu. Mockup bisa dilanjutkan di minggu 15, tapi idealnya sudah selesai hari ini |
| Perbedaan pendapat antar anggota dalam menilai heuristic | Gunakan voting sederhana. Catat semua pendapat, lalu pilih yang paling banyak didukung. Catat alasan di dokumentasi |

---

## 7. Tautan Referensi

| Sumber | URL | Keterangan |
|---|---|---|
| 10 Usability Heuristics (NNGroup) | https://www.nngroup.com/articles/ten-usability-heuristics/ | Daftar heuristik lengkap dengan contoh |
| Figma Getting Started | https://help.figma.com/hc/en-us/articles/360040319993 | Panduan dasar Figma |
| Heuristic Evaluation Template | https://www.nngroup.com/articles/how-to-conduct-a-heuristic-evaluation/ | Cara melakukan heuristic evaluation |
| Wayback Machine | https://web.archive.org | Akses versi lama website |
| Contoh Website E-Governance | https://www.go.id, https://jakartasatu.jakarta.go.id | Contoh website pemerintah untuk diriset |

---

## 8. Persiapan untuk Minggu 15

Sebelum pertemuan minggu depan, pastikan:

1. Semua dokumen riset sudah **ter-commit dan ter-push** ke GitHub.
2. Desain Figma sudah **selesai** (wireframe + mockup).
3. Anggota kelompok sudah **berbagi peran** untuk implementasi:
   - **Anggota A:** Header, navigasi, hero section.
   - **Anggota B:** Bagian tengah (konten utama, formulir, informasi).
   - **Anggota C:** Footer, bagian bawah, optimasi responsif.
   - *(Atur sendiri sesuai kebutuhan kelompok)*
4. File `index.html` sudah **mulai disiapkan** (kosong atau skeleton HTML sudah ada di branch `final-project`).

---

> **Catatan untuk Pengajar:**
> Sesi ini sebagian besar berupa **mentoring mandiri**. Pengajar berkeliling memantau progress kelompok dan memberikan bantuan teknis. Fokus mentoring:
> - Pastikan heuristic evaluation dilakukan dengan analisis, bukan sekadar checklist.
> - Bantu kelompok yang kesulitan menentukan website target.
> - Tekankan pentingnya **kaitan antara temuan riset dan keputusan desain**.
