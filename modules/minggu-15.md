# Minggu 15: Workshop Proyek Akhir — Implementasi, Deployment & Progress Clinic

**Topik:** Implementasi HTML/CSS/JS sesuai mockup Figma, deployment ke GitHub Pages, dan klinik progress kelompok  
**Durasi:** 1 pertemuan (± 120 menit)  
**Format:** Workshop kelompok (3 orang) dengan sesi mentoring & clinic

---

## 1. Tujuan Pembelajaran

Di akhir sesi ini, setiap kelompok diharapkan dapat:

1. **Mengimplementasikan** halaman web statis (HTML + CSS + JS) sesuai mockup Figma yang sudah dibuat.
2. **Mendeplloys** website ke **GitHub Pages** agar bisa diakses publik.
3. Menyelesaikan **kendala teknis** melalui sesi clinic dengan pengajar.
4. Memastikan **pembagian kerja** berjalan merata dan setiap anggota memahami kode tanggung jawabnya.

---

## 2. Peralatan yang Dibutuhkan

| Tool | Kegunaan | Status |
|---|---|---|
| VSCode | Menulis HTML, CSS, JS | Wajib |
| Live Server (extension VSCode) | Preview halaman secara langsung | Wajib |
| Browser (Chrome/Firefox) | Testing & debugging | Wajib |
| Figma | Referensi desain saat coding | Wajib |
| Git & GitHub | Version control & deployment | Wajib |
| GitHub Copilot / agentic coding tool | Bantuan penulisan kode (opsional) | Opsional |

---

## 3. Langkah-Langkah Hands-On

### Tahap 1: Synchronisasi Repository (± 5 menit)

Sebelum mulai coding, pastikan semua anggota dalam kondisi yang sama.

1. **Buka terminal** di VSCode.

2. **Pastikan berada di branch yang benar:**
   ```bash
   git status
   git checkout final-project
   ```

3. **Ambil perubahan terbaru** dari GitHub (jika ada anggota yang sudah push sebelumnya):
   ```bash
   git pull origin final-project
   ```

4. **Buka file** `index.html` yang sudah ada (atau buat jika belum).

> **Screenshot placeholder:**
> ```
> [Screenshot: Terminal di VSCode — menunjukkan git status branch final-project]
> ```

---

### Tahap 2: Implementasi Halaman Utama (± 50 menit)

Fokuskan waktu pada **satu halaman utama** (landing page / homepage). Multi-halaman bisa ditambahkan jika waktu memungkinkan.

#### 2a. Struktur HTML Dasar

Buka `src/index.html` dan buat struktur dasar:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Nama Website Redesign]</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <!-- Header & Navigasi -->
    <header>
        <nav>
            <!-- Logo + menu navigasi sesuai mockup -->
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <!-- Judul, deskripsi singkat, tombol CTA -->
    </section>

    <!-- Konten Utama -->
    <main>
        <!-- Bagian-bagian konten sesuai mockup -->
    </main>

    <!-- Footer -->
    <footer>
        <!-- Informasi kontak, copyright, tautan -->
    </footer>

    <script src="js/script.js"></script>
</body>
</html>
```

> **Tips:**
> - Gunakan **tag HTML semantik**: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`.
> - Hindari penggunaan `<div>` berlebihan tanpa makna.
> - Tambahkan `lang="id"` di tag `<html>` untuk aksesibilitas.

#### 2b. Pembagian Kerja Kelompok

Agar tidak bentrok, gunakan **branch terpisah per anggota** atau **blok kode terpisah**:

**Opsi A: Branch terpisah (disarankan):**
```bash
# Anggota A
git checkout -b feat/header-navigasi

# Anggota B
git checkout -b feat/konten-utama

# Anggota C
git checkout -b feat/footer-responsive
```

Setiap anggota bekerja di branch sendiri, lalu **merge** ke `final-project` setelah selesai.

**Opsi B: Bagian file terpisah (lebih sederhana):**
- Anggota A: kerjakan `index.html` bagian `<header>` dan `<nav>`.
- Anggota B: kerjakan `index.html` bagian `<main>`.
- Anggota C: kerjakan `index.html` bagian `<footer>` + buat `css/style.css`.

> **Screenshot placeholder:**
> ```
> [Screenshot: Struktur branch di GitHub — terlihat branch per anggota]
> [Screenshot: Struktur HTML di VSCode dengan semantic tags]
> ```

#### 2c. Styling dengan CSS

Buka `css/style.css` dan mulai styling berdasarkan mockup Figma:

```css
/* ============================
   Reset & Base Styles
   ============================ */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333;
}

/* ============================
   Header & Navigation
   ============================ */
header {
    background-color: #2c3e50;
    color: white;
    padding: 1rem 2rem;
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
}

/* ============================
   Hero Section
   ============================ */
.hero {
    background-color: #3498db;
    color: white;
    text-align: center;
    padding: 4rem 2rem;
}

/* ============================
   Main Content
   ============================ */
main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

/* ============================
   Footer
   ============================ */
footer {
    background-color: #2c3e50;
    color: white;
    text-align: center;
    padding: 2rem;
    margin-top: 4rem;
}

/* ============================
   Responsive Design
   ============================ */
@media (max-width: 768px) {
    nav {
        flex-direction: column;
        gap: 1rem;
    }

    .hero {
        padding: 2rem 1rem;
    }
}
```

> **Tips:**
> - Selalu referensikan mockup Figma saat menulis CSS — jangan "nebak" ukuran.
> - Gunakan **flexbox** untuk layout (sudah dipelajari di minggu 6).
> - Gunakan **media query** untuk responsif (sudah dipelajari di minggu 7).
> - **Jangan lupa `box-sizing: border-box`** di reset — ini mencegah masalah layout umum.

#### 2d. Interaktivitas JavaScript (Opsional)

Jika mockup memerlukan elemen interaktif (misal: menu hamburger, accordion FAQ, tab navigasi):

```javascript
// js/script.js

// Contoh: Toggle menu mobile
const menuToggle = document.querySelector('.menu-toggle');
const navMenu = document.querySelector('.nav-menu');

if (menuToggle) {
    menuToggle.addEventListener('click', () => {
        navMenu.classList.toggle('active');
    });
}
```

> **Screenshot placeholder:**
> ```
> [Screenshot: Website tampil di browser (Live Server) — versi desktop]
> [Screenshot: Website tampil di browser — versi mobile (toggle responsive)]
> ```

---

### Tahap 3: Sesi Clinic / Mentoring (± 30 menit)

Pengajar berkeliling ke setiap kelompok. Manfaatkan waktu ini untuk:

1. **Review cepat** kode dan struktur repo.
2. **Tanya-jawab** tentang bagian kode yang belum dipahami.
3. **Perbaikan** masalah teknis yang ditemukan.

#### Pertanyaan Clinic yang Perlu Dijawab Setiap Kelompok:

| # | Pertanyaan | Jawaban Kelompok |
|---|---|---|
| 1 | Bagaimana cara website ini mengatasi pain point #1 dari hasil riset? | [Jawaban] |
| 2 | Siapa yang mengerjakan bagian apa? Apakah semua anggota sudah punya tanggung jawab? | [Jawaban] |
| 3 | Apakah website ini responsif di mobile? Bisa didemo? | [Demo] |
| 4 | Apakah ada penggunaan agentic coding tools? Jika ya, bagian mana? | [Jawaban] |

> **Screenshot placeholder:**
> ```
> [Screenshot: Sesi mentoring — pengajar berdiskusi dengan kelompok (opsional)]
> ```

---

### Tahap 4: Deployment ke GitHub Pages (± 15 menit)

Setelah halaman utama cukup lengkap, deploy ke GitHub Pages.

#### 4a. Persiapan Repository

1. **Pastikan file sudah ter-commit:**
   ```bash
   git add .
   git commit -m "feat: implementasi halaman utama sesuai mockup Figma"
   git push
   ```

2. **Pastikan branch `main` atau `final-project`** berisi kode terbaru.
   - Jika kode di branch lain, **merge** terlebih dahulu:
     ```bash
     git checkout main
     git merge final-project
     git push origin main
     ```

#### 4b. Aktifkan GitHub Pages

1. **Buka repository** di GitHub.
2. Klik tab **"Settings"** → geser ke bagian kiri → klik **"Pages"**.
3. Di bagian **"Source"**:
   - Pilih **"Deploy from a branch"**.
   - Pilih branch: **`main`** (atau `final-project`).
   - Pilih folder: **`/ (root)`** atau **`/docs`** (tergantung struktur).
   - Klik **"Save"**.
4. **Tunggu 1–2 menit**, lalu refresh halaman Settings → Pages.
5. **Klik link** yang muncul di bagian atas (contoh: `https://username.github.io/repo-name/`).

> **Screenshot placeholder:**
> ```
> [Screenshot: GitHub Settings → Pages — konfigurasi source]
> [Screenshot: Website yang sudah ter-deploy di browser — URL GitHub Pages terlihat]
> [Screenshot: Website di mobile view setelah deploy]
> ```

#### 4c. Update Deployment

Setiap kali ada perubahan baru, cukup push ke branch yang sudah di-configure:

```bash
git add .
git commit -m "fix: perbaikan layout header"
git push
```

GitHub Pages akan **otomatis update** dalam ± 1–2 menit.

> **Troubleshooting Deployment:**

| Masalah | Solusi |
|---|---|
| Website tidak muncul setelah deploy | Tunggu 2–3 menit. Jika masih tidak muncul, cek tab **"Actions"** di repo — lihat apakah build berhasil |
| Halaman 404 Not Found | Pastikan file utama bernama `index.html` dan berada di folder root (atau folder yang dipilih di Settings) |
| CSS/JS tidak termuat | Cek path file di HTML — gunakan **relative path** (`css/style.css`), bukan absolute path (`/css/style.css`) |
| Gambar tidak muncul | Pastikan file gambar ada di repo dan path-nya benar. Perhatikan huruf besar/kecil (case-sensitive di GitHub Pages) |
| Deploy dari branch selain `main` | Di Settings → Pages, ganti branch source ke branch yang benar |
| Subfolder tidak terbaca | Pastikan `index.html` ada di root folder yang dipilih di Settings |

---

### Tahap 5: Persiapan Presentasi (± 10 menit)

Mulai siapkan bahan presentasi untuk minggu 16.

#### 5a. Buat Struktur Presentasi

Buat file baru `docs/presentasi-outline.md`:

```markdown
# Outline Presentasi Proyek Akhir

## 1. Pembukaan (1 menit)
- Perkenalan kelompok & nama website yang diriset
- URL website asli vs URL redesign

## 2. Riset UI/UX (3 menit)
- Screenshot halaman asli
- Top 3 pain point dari heuristic evaluation
- Temuan benchmarking (1-2 insight utama)

## 3. Desain Ulang (3 menit)
- Screenshot mockup Figma (desktop & mobile)
- Jelaskan 3 keputusan desain utama dan kaitannya dengan temuan riset

## 4. Implementasi (3 menit)
- Live demo website yang sudah ter-deploy
- Jelaskan teknologi yang digunakan (HTML, CSS, JS)
- Demo responsif (resize browser)

## 5. Pembagian Kerja & Penggunaan AI (2 menit)
- Siapa mengerjakan bagian apa (dengan bukti commit)
- Apakah menggunakan agentic coding tools? Bagian mana?

## 6. Penutup (1 menit)
- Refleksi: apa yang dipelajari, tantangan terbesar
- Q&A
```

#### 5b. Bagikan Peran Presentasi

| Segmen | Penanggung Jawab |
|---|---|
| Pembukaan & Riset | Anggota 1 |
| Desain Ulang | Anggota 2 |
| Implementasi & Demo | Anggota 3 |
| Pembagian Kerja & Penutup | Diskusikan sendiri |

> **Screenshot placeholder:**
> ```
> [Screenshot: Outline presentasi di Markdown]
> [Screenshot: README.md yang sudah dilengkapi dengan pembagian tugas]
> ```

---

### Tahap 6: Final Commit & Documentation (± 10 menit)

1. **Pastikan README.md** di root repo sudah lengkap:
   ```markdown
   # [Nama Website] — Redesign Proyek Akhir

   ## Anggota Kelompok
   | Nama | NIM | Tugas |
   |---|---|---|
   | [Nama 1] | [NIM] | Header, navigasi, hero section |
   | [Nama 2] | [NIM] | Konten utama, formulir |
   | [Nama 3] | [NIM] | Footer, responsive design |

   ## Tech Stack
   - HTML5
   - CSS3 (Flexbox, Grid, Media Query)
   - JavaScript (vanilla)

   ## Penggunaan Agentic Coding Tools
   - [Jelaskan di sini jika ada, atau tulis "Tidak menggunakan"]

   ## Cara Menjalankan
   1. Clone repository ini
   2. Buka `src/index.html` di browser
   3. Atau kunjungi: [link GitHub Pages]

   ## Hasil Riset
   Lihat folder `research/` untuk dokumen heuristic evaluation dan benchmarking.
   ```

2. **Final commit & push:**
   ```bash
   git add .
   git commit -m "docs: lengkapi README dan siapkan bahan presentasi"
   git push
   ```

> **Screenshot placeholder:**
> ```
> [Screenshot: README.md yang sudah lengkap di GitHub]
> [Screenshot: Commit history — terlihat kontribusi per anggota]
> ```

---

## 4. Output yang Diharapkan

Setelah sesi ini, setiap kelompok harus memiliki:

| # | Output | Lokasi | Status |
|---|---|---|---|
| 1 | Halaman HTML/CSS/JS utama | `src/index.html`, `src/css/`, `src/js/` | ☐ |
| 2 | Website ter-deploy | Link GitHub Pages | ☐ |
| 3 | Responsif di mobile & desktop | Tested di browser | ☐ |
| 4 | README.md lengkap | Root repository | ☐ |
| 5 | Commit history per anggota | GitHub — Insights → Contributors | ☐ |
| 6 | Outline presentasi | `docs/presentasi-outline.md` | ☐ |
| 7 | Semua perubahan ter-push | Branch `final-project` atau `main` | ☐ |

---

## 5. Checklist Kelompok

Sebelum meninggalkan kelas, pastikan semua anggota bisa menjawab:

- [ ] "Apa URL GitHub Pages website kami?"
- [ ] "Bisa tunjukkan website responsif (resize browser)?"
- [ ] "Siapa mengerjakan bagian apa? Bisakah setiap anggota menjelaskan kodenya?"
- [ ] "Apakah README sudah lengkap dengan pembagian tugas?"
- [ ] "Apakah semua anggota sudah commit ke repo?"

---

## 6. Troubleshooting Umum

| Masalah | Solusi |
|---|---|
| **CSS tidak terapply** | Cek `<link>` di HTML — pastikan path benar (`css/style.css`). Cek juga apakah file CSS benar-benar ada di folder yang tepat |
| **Gambar tidak tampil** | Cek path gambar. Gunakan path relatif: `assets/gambar.png`, bukan `/assets/gambar.png` atau URL absolut. Pastikan nama file tepat (case-sensitive) |
| **Layout pecah di mobile** | Pastikan `<meta name="viewport">` ada di `<head>`. Cek media query di CSS. Gunakan DevTools → Toggle Device Toolbar |
| **JavaScript tidak jalan** | Buka Console di DevTools (F12 → Console). Cek error message. Pastikan file JS sudah di-link di HTML sebelum `</body>` |
| **Git merge conflict** | Buka file yang conflict → cari `<<<<<<<` → pilih versi yang benar → hapus marker conflict → commit |
| **GitHub Pages 404** | Pastikan `index.html` di root. Cek Settings → Pages → source branch & folder. Tunggu 2 menit setelah push |
| **Flexbox tidak bekerja** | Pastikan parent element punya `display: flex`. Cek apakah ada `width` atau `height` yang membatasi. Gunakan DevTools untuk inspect |
| **Font tidak sesuai mockup** | Import Google Fonts di `<head>`: `<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">` → `font-family: 'Roboto', sans-serif;` |
| **Anggota tidak bisa push** | Cek `git remote -v`. Pastikan remote URL benar. Jika clone via SSH, pastikan SSH key sudah terdaftar di GitHub |
| **Tidak sempat deploy hari ini** | Tidak masalah — deploy bisa dilakukan malam ini atau besok. Yang penting kode sudah ter-push ke GitHub |

---

## 7. Panduan Agentic Coding Tools (Opsional)

Jika kelompok menggunakan GitHub Copilot, Claude Code, atau tools serupa:

### Dokumentasi yang Wajib Dicatat

```markdown
## Penggunaan Agentic Coding Tools

| # | Prompt / Perintah | Bagian Kode | Anggota |
|---|---|---|---|
| 1 | "Buatkan responsive navbar dengan flexbox..." | `index.html` bagian `<nav>` | Anggota A |
| 2 | "Buat CSS untuk hero section dengan gradient..." | `css/style.css` bagian hero | Anggota B |
| 3 | "Buat JavaScript untuk toggle menu mobile..." | `js/script.js` | Anggota C |
```

### Tips Penggunaan yang Bertanggung Jawab

1. **Selalu review kode** yang dihasilkan — jangan langsung copy-paste.
2. **Pahami setiap baris** — siapkan diri untuk menjelaskan saat sesi tanya-jawab minggu 16.
3. **Gunakan sebagai bantuan**, bukan pengganti — anggota harus bisa memodifikasi kode sendiri.
4. **Dokumentasikan** semua prompt di README atau file terpisah.

---

## 8. Tautan Referensi

| Sumber | URL | Keterangan |
|---|---|---|
| GitHub Pages Docs | https://docs.github.com/en/pages | Panduan lengkap deployment |
| MDN: HTML Semantics | https://developer.mozilla.org/en-US/docs/Guide/HTML/Sections_and_outlines_of_an_HTML5_document | Penggunaan tag semantik |
| CSS Flexbox Guide | https://css-tricks.com/snippets/css/a-guide-to-flexbox/ | Referensi flexbox |
| CSS Media Queries | https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries | Responsive design |
| Figma to Code | https://www.figma.com/best-practices/from-design-to-code/ | Tips konversi Figma ke kode |

---

## 9. Persiapan untuk Minggu 16 (Presentasi)

Sebelum pertemuan minggu depan, pastikan:

1. **Website sudah ter-deploy** dan bisa diakses semua orang.
2. **Semua anggota bisa menjelaskan kode** bagian masing-masing.
3. **Outline presentasi sudah final** dan semua anggota tahu siapa bicara kapan.
4. **Siapkan demo langsung** — buka website di browser, siap untuk resize dan navigasi.
5. **Latihan presentasi** — coba presentasikan dalam waktu ± 10 menit.

> **Catatan untuk Pengajar:**
> Sesi ini adalah **workshop intensif**. Pengajar berkeliling memberikan bantuan teknis. Fokus mentoring:
> - Pastikan setiap kelompok sudah punya minimal **1 halaman utama** yang bisa di-deploy.
> - Bantu kelompok yang mengalami **merge conflict** atau masalah Git lainnya.
> - Tekankan: **"setiap anggota harus bisa menjelaskan kodenya"** — ini kunci penilaian minggu depan.
> - Jika ada kelompok yang sangat tertinggal, bantu mereka fokus ke **1 halaman sederhana** yang bisa di-deploy, daripada mengejar multi-halaman.
