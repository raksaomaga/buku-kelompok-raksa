# PRD: Modul Perkuliahan "Pengenalan Workshop Desain Web"

**Program Studi:** D3 Informatika
**Semester:** 1
**Durasi:** 1 semester (14–16 pertemuan)
**Status:** Draft

---

## 1. Latar Belakang

Mahasiswa D3 Informatika semester 1 pada umumnya belum memiliki pengalaman pemrograman. Modul ini dirancang sebagai **pengenalan** dunia pengembangan web — mulai dari proses desain (Figma) sampai implementasi dasar (HTML, CSS, JavaScript) dan pengenalan alur kerja profesional (Git/GitHub, VSCode) — dengan sedikit gambaran ke arah tools yang lebih modern (Tailwind, React) tanpa menuntut penguasaan penuh di semester ini.

## 2. Tujuan (Goals)

- Mahasiswa memahami alur kerja *design-to-code*: dari wireframe di Figma menjadi halaman web nyata.
- Mahasiswa mampu membangun halaman web statis (HTML + CSS) yang rapi dan responsif.
- Mahasiswa memahami dasar interaktivitas web dengan JavaScript.
- Mahasiswa terbiasa menggunakan Git/GitHub sebagai alur kerja kolaborasi dan version control.
- Mahasiswa mengenal (bukan mahir) ekosistem modern: Tailwind CSS dan React, sebagai bekal untuk mata kuliah lanjutan.
- Setiap mahasiswa memiliki portofolio nyata (repo GitHub + website yang di-deploy) di akhir semester.

### Non-Goals (di luar cakupan semester ini)

- Mahasiswa **tidak** dituntut mahir membangun aplikasi React dari nol.
- Tidak membahas backend, database, atau API secara mendalam.
- Tidak membahas build tools/bundler tingkat lanjut (Webpack, Vite config, dsb).

## 3. Target Peserta

- Mahasiswa baru D3 Informatika, semester 1.
- Asumsi: mayoritas belum pernah coding sama sekali; sebagian kecil mungkin sudah pernah membuat HTML sederhana secara otodidak.
- Perangkat: laptop pribadi/lab kampus, minimal spesifikasi untuk menjalankan VSCode + browser modern.

## 4. Capaian Pembelajaran

Di akhir semester, mahasiswa diharapkan dapat:

1. Membuat desain UI sederhana di Figma (wireframe → mockup).
2. Menulis struktur halaman web dengan HTML semantik.
3. Menata tampilan dengan CSS (layout, flexbox/grid dasar, responsive design).
4. Menambahkan interaktivitas dasar dengan JavaScript (manipulasi DOM, event handling).
5. Menggunakan Git untuk version control dan GitHub untuk kolaborasi/hosting (GitHub Pages).
6. Menjelaskan konsep dasar utility-first CSS (Tailwind) dan komponen (React) — level pengenalan.
7. Menyelesaikan proyek akhir: website statis multi-halaman dari desain sendiri.

## 5. Tools & Urutan Penguasaan

| Tool | Level Target | Catatan |
|---|---|---|
| Figma | Wajib dikuasai | Wireframing & mockup dasar |
| HTML | Wajib dikuasai | Struktur, semantic tag |
| CSS | Wajib dikuasai | Layout, flexbox, responsive |
| VSCode | Wajib dikuasai | Setup environment, extension dasar |
| Git & GitHub | Wajib dikuasai | Commit, push, pull, branch dasar, GitHub Pages |
| JavaScript | Dasar | DOM manipulation, event, tanpa framework |
| Tailwind CSS | Pengenalan | Konsep utility-first, praktik ringan |
| React | Pengenalan/preview | Konsep komponen & JSX, tanpa proyek mandiri penuh |

**Alasan urutan:** React & Tailwind sengaja ditempatkan di akhir dan pada level "pengenalan" saja, karena melompat langsung ke framework tanpa fondasi HTML/CSS/JS yang kuat berisiko membuat mahasiswa semester 1 kewalahan.

## 6. Struktur Modul (14–16 Pertemuan)

| Minggu | Topik | Output Mahasiswa |
|---|---|---|
| 1 | Pengantar web & workflow design-to-code, instalasi tools (VSCode, browser, akun GitHub) | Environment siap |
| 2 | Figma dasar: wireframe & mockup, pengantar prinsip dasar UI/UX (heuristik, hierarchy, aksesibilitas) | Wireframe 1 halaman |
| 3 | HTML dasar: struktur & semantic tag | Halaman HTML statis |
| 4 | HTML lanjutan: form, tabel, multimedia | Halaman HTML dengan form |
| 5 | CSS dasar: selector, box model, typography | Styling halaman |
| 6 | CSS layout: flexbox | Layout responsif sederhana |
| 7 | CSS layout: grid & responsive design (media query) | Halaman responsif (mobile-friendly) |
| 8 | Git & GitHub dasar: init, commit, push, pull | Repo pertama di GitHub |
| 9 | GitHub kolaborasi: branch, pull request, GitHub Pages | Website ter-deploy via GitHub Pages |
| 10 | JavaScript dasar: variabel, fungsi, kondisi, DOM selection | Skrip JS sederhana |
| 11 | JavaScript: event handling & manipulasi DOM | Elemen interaktif (misal toggle menu) |
| 12 | Pengenalan Tailwind CSS | Konversi 1 halaman ke Tailwind |
| 13 | Pengenalan React: komponen, JSX, props (konsep) | Demo komponen sederhana |
| 14 | Workshop proyek akhir (mentoring) | Progress proyek akhir |
| 15 | Penyelesaian proyek akhir | Website multi-halaman lengkap |
| 16 | Presentasi & evaluasi akhir | Presentasi portofolio |

## 7. Spesifikasi Proyek Akhir: Re-desain Website E-Governance

**Brief singkat:** Setiap kelompok memilih satu halaman dari website layanan publik/e-governance (mis. portal instansi pemerintah, layanan desa/kota, dsb) untuk diriset dan didesain ulang.

**Format kelompok:** 3 orang per kelompok.

**Tahapan wajib:**

1. **Riset UI/UX** — evaluasi halaman asli menggunakan heuristic evaluation (mis. 10 Usability Heuristics dari Nielsen Norman Group), identifikasi pain point, dan benchmarking singkat dengan situs sejenis. Wawancara/survei ke calon pengguna bersifat opsional (nilai tambah).
2. **Desain ulang di Figma** — wireframe → mockup baru, disertai rasional desain yang mengacu ke temuan riset (bukan sekadar "lebih bagus", tapi "mengatasi masalah X yang ditemukan di riset").
3. **Implementasi di VSCode** — HTML/CSS/JS (boleh menggunakan Tailwind) sesuai mockup Figma.
4. **Deployment** — via GitHub Pages.

**Ketentuan penggunaan agentic coding tools:** Diperbolehkan (mis. GitHub Copilot, Claude Code, atau sejenisnya), dengan syarat:

- Kelompok wajib mendokumentasikan prompt/perintah utama yang digunakan dan bagian mana dari kode yang dibantu AI (dicatat di README).
- Setiap anggota harus bisa menjelaskan bagian kode yang menjadi tanggung jawabnya saat sesi demo/tanya-jawab — ini jadi salah satu alat cek pemahaman, bukan cuma soal etika akademik.
- Karena AI membantu penulisan kode, bobot penilaian proyek akhir digeser lebih ke kualitas riset, ketepatan keputusan desain, dan pemahaman implementasi — bukan semata "kode berjalan".

**Deliverables Proyek Akhir:**

- Dokumen ringkas hasil riset UI/UX (temuan heuristic evaluation/benchmarking).
- File Figma desain ulang lengkap dengan rasional desain.
- Repository GitHub (source code + README: pembagian tugas anggota, catatan penggunaan agentic coding tools bila ada).
- Website hasil redesign yang ter-deploy (GitHub Pages).
- Presentasi kelompok: proses riset → keputusan desain → implementasi.

**Penilaian kontribusi individu (kelompok 3 orang):** Gunakan kombinasi commit history per anggota, pembagian tugas eksplisit di README, dan sesi tanya-jawab individual saat demo, supaya nilai tidak semata berdasarkan hasil akhir kelompok.

## 8. Deliverables Peserta (Portofolio Akhir — Keseluruhan Modul)

- File desain Figma (wireframe + mockup).
- Repository GitHub berisi source code.
- Website statis (HTML/CSS/JS) yang ter-deploy via GitHub Pages.
- Dokumentasi singkat (README) tentang proses desain ke kode.
- (Khusus proyek akhir) Lihat Bagian 7 untuk deliverable tambahan.

## 9. Metode Pembelajaran

- Praktikum langsung (hands-on) tiap pertemuan, porsi teori minim.
- Live coding oleh pengajar, diikuti latihan mandiri.
- Project-based learning menuju proyek akhir.
- Peer review sederhana (mahasiswa saling melihat repo/desain teman).

## 10. Penilaian

| Komponen | Bobot |
|---|---|
| Tugas mingguan/praktikum | 25% |
| UTS (mini project pertengahan, mis. hasil minggu 1–8) | 20% |
| Partisipasi & progress GitHub | 10% |
| Proyek akhir (riset UI/UX + desain + implementasi + presentasi) | 45% |

Rincian bobot proyek akhir (dari 45% di atas, disarankan):
- Riset UI/UX: 10%
- Kualitas desain ulang di Figma (rasional desain): 10%
- Implementasi & deployment: 15%
- Presentasi & pemahaman individual saat tanya-jawab: 10%

## 11. Metrik Keberhasilan Modul

- % mahasiswa yang berhasil deploy website ke GitHub Pages.
- % kelompok yang menyelesaikan proyek akhir sesuai brief (riset + desain + implementasi).
- Kualitas commit history (indikator pemahaman Git, bukan cuma 1 commit besar di akhir).
- Kedalaman temuan riset UI/UX (bukan sekadar checklist heuristik, tapi ada kaitan jelas ke keputusan desain).
- Survei kepercayaan diri mahasiswa terhadap dasar web development di akhir semester.

## 12. Risiko & Mitigasi

| Risiko | Mitigasi |
|---|---|
| Mahasiswa kewalahan di materi JS/Tailwind/React (minggu 10–13) | Porsi materi tetap ringan/konseptual, latihan terpandu, tidak ada tugas berat di topik ini |
| Kendala perangkat (laptop tidak memadai) | Sediakan alternatif lab kampus, gunakan tools ringan (VSCode + Live Server) |
| Kesulitan penggunaan Git di awal | Sesi khusus troubleshooting Git di minggu 8–9, cheat sheet perintah dasar |
| Kesenjangan skill awal antar mahasiswa | Modul suplemen/tutorial tambahan untuk yang tertinggal |
| Kelompok terlalu bergantung pada agentic coding tools sehingga tidak paham kode sendiri | Wajib sesi tanya-jawab individual saat demo; bobot penilaian digeser ke riset & keputusan desain, bukan hanya kode jadi |
| Riset UI/UX dikerjakan asal-asalan (checklist tanpa analisis) | Berikan contoh/template heuristic evaluation yang baik di minggu 2, minta kaitan eksplisit antara temuan riset dan keputusan desain di laporan |
| Pembagian kerja kelompok tidak merata | Commit history per anggota + pembagian tugas eksplisit di README sebagai syarat penilaian |

## 13. Referensi & Bahan Ajar (usulan)

- Dokumentasi resmi MDN Web Docs (HTML, CSS, JS).
- Tailwind CSS docs (bagian "Getting Started").
- React docs (bagian pengantar konsep, bukan advanced).
- GitHub Skills / GitHub Docs untuk latihan Git dasar.
- Figma Community templates untuk referensi wireframe.
- Nielsen Norman Group — 10 Usability Heuristics for User Interface Design (untuk riset UI/UX).
- Contoh website e-governance publik sebagai objek studi (mis. portal layanan pemerintah daerah/pusat yang dapat diakses publik).
