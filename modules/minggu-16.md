# Minggu 16: Presentasi, Refleksi & Finalisasi Proyek Akhir

**Topik:** Presentasi hasil proyek redesign, sesi tanya-jawab individual, refleksi pembelajaran semester  
**Durasi:** 1 pertemuan (± 120 menit)  
**Format:** Presentasi kelompok + tanya-jawab + refleksi individu

---

## 1. Tujuan Pembelajaran

Di akhir sesi ini, setiap mahasiswa diharapkan dapat:

1. **Mempresentasikan** proses proyek redesign dari riset → desain → implementasi → deployment.
2. **Menjawab pertanyaan** tentang kode dan keputusan desain secara individual.
3. **Merefleksikan** perkembangan diri selama semester dalam mata kuliah ini.
4. **Menyelesaikan** seluruh deliverable proyek akhir.

---

## 2. Peralatan yang Dibutuhkan

| Tool | Kegunaan | Status |
|---|---|---|
| Browser | Live demo website | Wajib |
| GitHub | Menunjukkan repository, commit history | Wajib |
| Figma | Menunjukkan file desain | Wajib |
| Slide presentasi | Pembukaan & penutup (Google Slides / MD) | Wajib |
| VSCode | Menunjukkan kode saat tanya-jawab | Wajib |

---

## 3. Langkah-Langkah Hands-On

### Tahap 1: Persiapan Sebelum Presentasi (± 10 menit)

#### 1a. Cek Kesiapan Teknis

Setiap kelompok memastikan:

- [ ] Website bisa diakses via GitHub Pages — **buka di browser dan coba navigasi**.
- [ ] Website responsif — **resize browser** dari desktop ke mobile.
- [ ] Repository GitHub bersih — **tidak ada file temporary** atau file yang tidak perlu.
- [ ] README.md sudah lengkap.
- [ ] Semua anggota bisa mengakses repository dari laptop masing-masing.

#### 1b. Buka Semua Tab yang Dibutuhkan

Siapkan di browser sebelum giliran presentasi:

1. **Tab 1:** Website hasil redesign (GitHub Pages).
2. **Tab 2:** Repository GitHub (terlihat commit history & README).
3. **Tab 3:** File desain Figma.
4. **Tab 4:** File heuristic evaluation di GitHub (atau VSCode).

> **Screenshot placeholder:**
> ```
> [Screenshot: Persiapan presentasi — browser dengan 4 tab terbuka]
> ```

#### 1c. Urutan Presentasi

| Urutan | Kelompok | Topik Redesign |
|---|---|---|
| 1 | Kelompok 1 | [nama website] |
| 2 | Kelompok 2 | [nama website] |
| 3 | Kelompok 3 | [nama website] |
| ... | ... | ... |

---

### Tahap 2: Presentasi Kelompok (± 8–10 menit per kelompok)

Gunakan outline yang sudah disiapkan di minggu 15. Berikut panduan waktu:

#### 2a. Pembukaan (± 1 menit)

- Perkenalan anggota kelompok.
- Nama website yang diriset dan URL-nya.
- URL website redesign (GitHub Pages).

> **Screenshot placeholder:**
> ```
> [Screenshot: Slide pembukaan — nama kelompok, nama website]
> ```

#### 2b. Riset UI/UX (± 2–3 menit)

Tampilkan:

1. **Screenshot halaman asli** website yang diriset.
2. **Top 3 pain point** dari heuristic evaluation — jelaskan **apa masalahnya** dan **mengapa itu masalah bagi pengguna**.
   - Contoh: *"Di halaman asli, tombol 'Ajukan Permohonan' tidak terlihat karena warnanya menyatu dengan background. Ini melanggar heuristic #1 — Visibility of System Status."*
3. **1–2 temuan benchmarking** — apa yang dipelajari dari website lain.

> **Screenshot placeholder:**
> ```
> [Screenshot: Tampilan slide riset — pain point utama]
> ```

#### 2c. Desain Ulang (± 2–3 menit)

Tampilkan:

1. **Mockup Figma** (desktop & mobile) — tunjukkan langsung di Figma.
2. **3 keputusan desain utama**, masing-masing dijelaskan:
   - *"Keputusan 1: Kami memindahkan tombol CTA ke posisi lebih prominent. Ini karena di riset ditemukan bahwa tombol utama sulit ditemukan (pain point #1)."*
   - *"Keputusan 2: Menambahkan breadcrumb navigasi. Ini mengatasi masalah pengguna yang tersesat (pain point #2)."*
   - *"Keputusan 3: Mengubah warna menjadi lebih kontras untuk aksesibilitas (insight dari heuristic #8)."*

> **Screenshot placeholder:**
> ```
> [Screenshot: Mockup Figma — tampilan desktop]
> [Screenshot: Mockup Figma — tampilan mobile]
> [Screenshot: Anotasi rasional desain di Figma]
> ```

#### 2d. Live Demo (± 2 menit)

1. **Buka website** di browser (GitHub Pages).
2. **Tunjukkan fitur utama:**
   - Navigasi.
   - Konten utama.
   - Responsif (resize browser dari desktop ke mobile).
3. **Tunjukkan commit history** di GitHub — siapa mengerjakan apa.

> **Screenshot placeholder:**
> ```
> [Screenshot: Live demo website — tampilan desktop]
> [Screenshot: Live demo website — tampilan mobile]
> [Screenshot: Commit history di GitHub]
> ```

#### 2e. Pembagian Kerja & Penggunaan AI (± 1 menit)

- **Tabel pembagian tugas:**

  | Anggota | Tugas | Jumlah Commit |
  |---|---|---|
  | [Nama 1] | Header, navigasi | X commit |
  | [Nama 2] | Konten utama, formulir | X commit |
  | [Nama 3] | Footer, responsive | X commit |

- **Penggunaan agentic coding tools:** Jelaskan tools apa yang dipakai, di bagian mana, dan tunjukkan dokumentasi prompt-nya.

#### 2f. Penutup (± 1 menit)

- **Satu hal terpenting** yang dipelajari dari proyek ini.
- **Satu tantangan terbesar** yang dihadapi.

---

### Tahap 3: Sesi Tanya-Jawab Individual (± 5 menit per kelompok)

Setelah presentasi, pengajar mengajukan pertanyaan kepada **setiap anggota secara individual**.

#### Contoh Pertanyaan yang Mungkin Ditanyakan

| Untuk Anggota yang Mengerjakan Header/Navigasi | Untuk Anggota yang Mengerjakan Konten Utama | Untuk Anggota yang Mengerjakan Footer/Responsive |
|---|---|---|
| "Bagaimana cara kerja navigasi di website ini? Jelaskan HTML-nya." | "Kenapa formulir ini diletakkan di posisi ini?" | "Bagaimana cara media query bekerja di CSS ini?" |
| "Apa heuristik yang paling relevan dengan perubahan di header?" | "Bagaimana website ini mengatasi pain point #2?" | "Apa bedanya `flex-direction: row` dan `column` di kode ini?" |
| "Jika saya ingin mengubah warna header, baris CSS mana yang perlu diubah?" | "Bisakah kamu menjelaskan alur pengguna mengisi formulir ini?" | "Di mana batas breakpoint untuk mobile di CSS ini?" |

> **Tips untuk mahasiswa:**
> - **Buka VSCode** saat sesi tanya-jawab — tunjukkan kode langsung.
> - **Jujur** jika tidak tahu, tapi tunjukkan usaha untuk mencari tahu.
> - **Hubungkan jawaban dengan riset** — misal: "Ini kami buat karena di riset ditemukan..."

> **Screenshot placeholder:**
> ```
> [Screenshot: Sesi tanya-jawab — anggota menjelaskan kode di VSCode]
> ```

---

### Tahap 4: Refleksi Individu (± 15 menit)

Setelah semua kelompok selesai presentasi, setiap mahasiswa mengisi **refleksi diri**.

#### 4a. Isi Formulir Refleksi

Buka file `reflection.md` di repo (atau gunakan form online yang disediakan pengajar) dan jawab:

```markdown
# Refleksi Akhir Semester — [Nama Mahasiswa]

## NIM: [NIM]
## Kelompok: [Nomor/Nama Kelompok]
## Website yang Diredesign: [Nama Website]

---

### 1. Perkembangan Skill

| Skill | Awal Semester | Akhir Semester | Keterangan |
|---|---|---|---|
| HTML | ☐ Belum bisa | ☐ Bisa | |
| CSS | ☐ Belum bisa | ☐ Bisa | |
| JavaScript | ☐ Belum bisa | ☐ Bisa | |
| Figma | ☐ Belum bisa | ☐ Bisa | |
| Git/GitHub | ☐ Belum bisa | ☐ Bisa | |
| Heuristic Evaluation | ☐ Belum bisa | ☐ Bisa | |

### 2. Refleksi Proyek Akhir

**Apa yang paling menantang dari proyek ini?**
> [Jawaban]

**Apa yang paling memuaskan dari hasil kerja kelompok?**
> [Jawaban]

**Jika bisa mengulang, apa yang akan dilakukan berbeda?**
> [Jawaban]

**Bagian mana dari kode yang paling dipahami dan bisa dijelaskan dengan baik?**
> [Jawaban]

**Bagian mana yang masih perlu dipelajari lebih lanjut?**
> [Jawaban]

### 3. Refleksi Pembelajaran

**Satu hal terpenting yang dipelajari di mata kuliah ini:**
> [Jawaban]

**Bagaimana mata kuliah ini mengubah cara pandang terhadap web development?**
> [Jawaban]

**Apakah ada topik yang ingin dipelajari lebih lanjut?**
> [Jawaban]
```

> **Screenshot placeholder:**
> ```
> [Screenshot: Formulir refleksi yang sudah diisi]
> ```

#### 4b. Commit Refleksi

```bash
git add reflection.md
git commit -m "docs: refleksi akhir semester — [nama]"
git push
```

---

### Tahap 5: Finalisasi Repository (± 10 menit)

Pastikan repository dalam kondisi final dan siap untuk portofolio.

#### 5a. Review Checklist Final

| # | Item | Cek |
|---|---|---|
| 1 | `index.html` berfungsi dengan benar | ☐ |
| 2 | CSS responsive (desktop & mobile) | ☐ |
| 3 | JavaScript berfungsi (jika ada) | ☐ |
| 4 | Gambar & aset semua tampil | ☐ |
| 5 | `README.md` lengkap | ☐ |
| 6 | Folder `research/` berisi heuristic evaluation & benchmarking | ☐ |
| 7 | File Figma sudah di-share (link di README) | ☐ |
| 8 | Website ter-deploy di GitHub Pages | ☐ |
| 9 | Commit history mencerminkan kontribusi per anggota | ☐ |
| 10 | Tidak ada file temporary (`.DS_Store`, `Thumbs.db`, dll) | ☐ |

#### 5b. Tambahkan File `.gitignore` (Jika Belum Ada)

Buat `.gitignore` di root repository:

```gitignore
# OS files
.DS_Store
Thumbs.db

# Editor files
.vscode/settings.json
*.swp
*.swo

# Node modules (jika menggunakan Tailwind)
node_modules/

# Build output
dist/
```

#### 5c. Final Commit

```bash
git add .
git commit -m "chore: finalisasi repository proyek akhir"
git push
```

> **Screenshot placeholder:**
> ```
> [Screenshot: Repository GitHub — tampilan root yang bersih dan lengkap]
> [Screenshot: Commit history akhir — terlihat kontribusi merata per anggota]
> ```

---

### Tahap 6: Penutup Semester (± 10 menit)

Pengajar menutup sesi dengan:

1. **Ringkasan pencapaian** kelas secara keseluruhan.
2. **Highlight** proyek-proyek yang menonjol.
3. **Pengumuman** terkait nilai akhir (jika sudah tersedia).
4. **Motivasi** untuk melanjutkan belajar web development di semester selanjutnya.

---

## 4. Deliverable Akhir Proyek

Pastikan seluruh deliverable berikut sudah selesai:

| # | Deliverable | Lokasi | Status |
|---|---|---|---|
| 1 | Dokumen hasil riset UI/UX | `research/heuristic-evaluation.md` | ☐ |
| 2 | Dokumen benchmarking | `research/benchmarking.md` | ☐ |
| 3 | File Figma (wireframe + mockup) | Link di README | ☐ |
| 4 | Repository GitHub (source code + README) | GitHub | ☐ |
| 5 | Website ter-deploy (GitHub Pages) | Link di README | ☐ |
| 6 | Pembagian tugas di README | `README.md` | ☐ |
| 7 | Dokumentasi penggunaan agentic coding (jika ada) | `README.md` atau file terpisah | ☐ |
| 8 | Refleksi individu | `reflection.md` | ☐ |

---

## 5. Contoh Struktur Repository Final

```
nama-repo/
├── README.md                    ← Pembagian tugas, tech stack, link deploy
├── .gitignore
├── research/
│   ├── heuristic-evaluation.md  ← 10 heuristik + temuan + skor
│   ├── benchmarking.md          ← Perbandingan dengan website lain
│   └── rasional-desain.md       ← Kaitan riset → keputusan desain
├── src/
│   ├── index.html               ← Halaman utama
│   ├── css/
│   │   └── style.css            ← Semua styling
│   ├── js/
│   │   └── script.js            ← Interaktivitas (jika ada)
│   └── assets/
│       ├── logo.png
│       └── ...
├── design/
│   └── figma-link.txt           ← Link ke file Figma
├── docs/
│   └── presentasi-outline.md    ← Outline presentasi
└── reflection.md                ← Refleksi (opsional per repo)
```

---

## 6. Troubleshooting

| Masalah | Solusi |
|---|---|
| **Website tidak bisa diakses saat presentasi** | Buka file `index.html` langsung dari VSCode (Live Server) sebagai backup. Atau unduh repo dan buka secara lokal |
| **Figma tidak bisa dibuka** | Pastikan akun Figma sudah login. Jika di lab kampus, minta bantuan admin untuk install Figma desktop |
| **Lupa commit bagian tertentu** | Cek `git status` → jika ada file yang belum ter-commit, lakukan commit sekarang. Jangan lupa push |
| **Tidak sempat mengisi refleksi** | Refleksi bisa diisi dan di-push setelah kelas. Deadline: 1×24 jam setelah presentasi |
| **Koneksi internet mati saat presentasi** | Gunakan versi lokal (Live Server) sebagai cadangan. Pastikan sudah download repo sebelumnya |
| **Anggota tidak bisa hadir** | Hubungi pengajar sebelum kelas. Kemungkinan presentasi dijadwalkan ulang atau dilakukan remote |
| **Website deploy expired/blank** | Cek Settings → Pages di GitHub. Pastikan branch source masih aktif. Push ulang jika perlu |
| **Merge conflict di final commit** | Selesaikan conflict: buka file → pilih versi yang benar → hapus marker `<<<<<<<` → commit |

---

## 7. Tautan Referensi

| Sumber | URL | Keterangan |
|---|---|---|
| GitHub Pages | https://docs.github.com/en/pages | Panduan deployment |
| Nielsen Norman Group | https://www.nngroup.com/articles/ten-usability-heuristics/ | Referensi heuristic evaluation |
| Figma | https://www.figma.com | Tool desain |
| MDN Web Docs | https://developer.mozilla.org | Referensi HTML, CSS, JavaScript |
| GitHub Skills | https://skills.github.com | Latihan Git lanjutan |

---

## 8. Catatan untuk Pengajar

### Acara Presentasi

- **Waktu per kelompok:** 8–10 menit presentasi + 5 menit tanya-jawab.
- **Jumlah kelompok:** Sesuaikan dengan jumlah kelas (misal: 6 kelompok × 15 menit = 90 menit).
- **Urutan presentasi:** Acak secara adil (undi atau alphabetis).
- **Penilaian tanya-jawab:** Fokus pada pemahaman individual, bukan hafalan. Berikan pertanyaan yang menguji **kemampuan menjelaskan**, bukan sekadar menyebutkan nama teknologi.

### Panduan Tanya-Jawab Individual

- **Mulai dari kode yang dikerjakan** anggota tersebut.
- **Tanyakan "mengapa"** bukan hanya "apa" — misal: "Mengapa kamu memilih flexbox untuk layout ini?"
- **Jika anggota menjawab "ini dari Copilot/Claude"**, lanjutkan: "Boleh jelaskan bagaimana kode ini bekerja?"
- **Berikan ruang untuk berkembang** — jika jawaban belum lengkap, bantu dengan pertanyaan leading.

### Setelah Presentasi

- **Kumpulkan refleksi** dari semua mahasiswa.
- **Review commit history** untuk memastikan kontribusi merata.
- **Dokumentasikan** proyek-proyek terbaik sebagai contoh untuk semester depan.
