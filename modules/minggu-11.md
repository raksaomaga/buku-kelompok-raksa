# Minggu 11 — JavaScript: Event Handling & Manipulasi DOM

> **Topik:** Membuat halaman web interaktif — merespons klik, input pengguna, dan mengubah isi halaman secara dinamis.
> **Output akhir:** Halaman web interaktif (misal: toggle menu, form sederhana, atau daftar tugas yang bisa ditambah/dihapus).
> **Durasi:** 3 jam kelas: 1 jam teori dan 2 jam praktik

---

## Daftar Isi

1. [Persiapan](#1-persiapan)
2. [Aktivitas 1 — Event Handling: onclick & addEventListener](#2-aktivitas-1--event-handling-onclick--addeventlistener)
3. [Aktivitas 2 — Event Pada Form & Input](#3-aktivitas-2--event-pada-form--input)
4. [Aktivitas 3 — Manipulasi DOM: Mengubah Konten](#4-aktivitas-3--manipulasi-dom-mengubah-konten)
5. [Aktivitas 4 — Manipulasi DOM: Membuat & Menghapus Elemen](#5-aktivitas-4--manipulasi-dom-membuat--menghapus-elemen)
6. [Aktivitas 5 — Mini Proyek: Toggle Menu Mobile](#6-aktivitas-5--mini-proyek-toggle-menu-mobile)
7. [Latihan Mandiri](#7-latihan-mandiri)
8. [Troubleshooting](#8-troubleshooting)

---

## 1. Persiapan

### Yang Anda Butuhkan

- File dari minggu 10 (atau buat file baru).
- Browser dengan DevTools (`F12`).
- VSCode dengan Live Server.

> **Pengingat cepat minggu 10:** `getElementById`, `querySelector`, `querySelectorAll`, `let`, `const`, `if/else`, fungsi.

---

## 2. Aktivitas 1 — Event Handling: onclick & addEventListener

### Konsep Singkat

**Event** adalah sesuatu yang terjadi pada halaman web — misal: pengguna mengklik tombol, mengetik di input, atau menggerakkan mouse. Kita bisa **mendengarkan** event ini dan menjalankan JavaScript sebagai respons.

### Langkah-langkah Ikuti Saya

**Langkah 1:** Buat file baru `minggu11.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minggu 11 — Event Handling</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        button { padding: 10px 20px; font-size: 16px; cursor: pointer; margin: 5px; }
        .aktif { background-color: #4CAF50; color: white; }
        .output { background-color: #f0f0f0; padding: 15px; margin: 10px 0; border-radius: 5px; min-height: 30px; }
    </style>
</head>
<body>
    <h1>Event Handling</h1>

    <!-- Cara 1: onclick langsung di HTML -->
    <h2>Cara 1: onclick di HTML</h2>
    <button onclick="sapa()">Klik Saya!</button>

    <!-- Cara 2: addEventListener di JavaScript -->
    <h2>Cara 2: addEventListener</h2>
    <button id="tombol-hitung">Hitung Klik</button>
    <span id="tampil-klik">0</span> kali diklik

    <div class="output" id="area-output">Output akan muncul di sini...</div>

    <script>
        // === Cara 1: onclick ===
        function sapa() {
            document.getElementById("area-output").textContent = "Halo! Anda baru saja mengklik tombol sapa.";
        }

        // === Cara 2: addEventListener (cara yang lebih disarankan) ===
        let jumlahKlik = 0;

        document.getElementById("tombol-hitung").addEventListener("click", function() {
            jumlahKlik++;
            document.getElementById("tampil-klik").textContent = jumlahKlik;

            if (jumlahKlik >= 5) {
                document.getElementById("area-output").textContent = "Wah, Anda sudah mengklik " + jumlahKlik + " kali!";
            } else {
                document.getElementById("area-output").textContent = "Klik ke-" + jumlahKlik + ". Coba terus!";
            }
        });
    </script>
</body>
</html>
```

**Langkah 2:** Buka dengan Live Server, klik kedua tombol, dan amati perubahan.

<!-- screenshot:event-basic -->
> **📸 Screenshot:** Tampilkan halaman dengan tombol "Hitung Klik" yang sudah diklik beberapa kali dan angka penghitung.

### Mengapa `addEventListener` Lebih Baik dari `onclick`?

| Aspek | `onclick` | `addEventListener` |
|---|---|---|
| Jumlah event handler | Hanya 1 | Banyak sekaligus |
| Pemisahan kode | JS tercampur di HTML | JS terpisah di `<script>` |
| Fleksibilitas | Terbatas | Bisa add/remove listener |

> **Aturan praktis:** Gunakan `addEventListener` untuk semua kebutuhan.

### Event Populer yang Perlu Diketahui

| Event | Kapan Terjadi |
|---|---|
| `click` | Elemen diklik |
| `dblclick` | Elemen diklik dua kali |
| `mouseover` | Mouse masuk ke elemen |
| `mouseout` | Mouse keluar dari elemen |
| `keydown` | Tombol keyboard ditekan |
| `keyup` | Tombol keyboard dilepas |
| `input` | Nilai input berubah |
| `submit` | Form dikirim |
| `load` | Halaman selesai dimuat |

---

## 3. Aktivitas 2 — Event Pada Form & Input

### Langkah-langkah Ikuti Saya

**Langkah 1:** Tambahkan kode berikut **sebelum** `</body>` (ganti atau tambahkan script baru):

```html
    <!-- Tambahan untuk Aktivitas 2 -->
    <h2>Form Sederhana</h2>
    <form id="form-mahasiswa">
        <label for="input-nama">Nama:</label><br>
        <input type="text" id="input-nama" placeholder="Masukkan nama"><br><br>

        <label for="input-email">Email:</label><br>
        <input type="email" id="input-email" placeholder="contoh@email.com"><br><br>

        <button type="submit">Kirim</button>
    </form>

    <div class="output" id="hasil-form">Data form akan muncul di sini...</div>

    <script>
        // Event pada form submit
        document.getElementById("form-mahasiswa").addEventListener("submit", function(event) {
            // Mencegah halaman refresh (default behavior form)
            event.preventDefault();

            const nama = document.getElementById("input-nama").value;
            const email = document.getElementById("input-email").value;

            // Validasi sederhana
            if (nama === "" || email === "") {
                document.getElementById("hasil-form").textContent = "⚠️ Semua field wajib diisi!";
                document.getElementById("hasil-form").style.backgroundColor = "#ffe0e0";
                return;
            }

            document.getElementById("hasil-form").textContent =
                "✅ Data diterima — Nama: " + nama + ", Email: " + email;
            document.getElementById("hasil-form").style.backgroundColor = "#e0ffe0";

            // Kosongkan form
            document.getElementById("input-nama").value = "";
            document.getElementById("input-email").value = "";
        });

        // Event pada input — real-time feedback
        document.getElementById("input-nama").addEventListener("input", function(event) {
            const panjang = event.target.value.length;
            if (panjang > 0) {
                document.getElementById("hasil-form").textContent = "Anda mengetik " + panjang + " karakter...";
                document.getElementById("hasil-form").style.backgroundColor = "#f0f0f0";
            } else {
                document.getElementById("hasil-form").textContent = "Data form akan muncul di sini...";
            }
        });
    </script>
```

**Langkah 2:** Coba isi form dan submit. Amati:
- Jika field kosong → muncul pesan error.
- Saat mengetik di field nama → muncul penghitung karakter real-time.
- Setelah submit berhasil → form terkosongkan.

<!-- screenshot:event-form -->
> **📸 Screenshot:** Tampilkan form yang sudah diisi dengan data valid, dan pesan sukses di area output.

<!-- screenshot:event-form-validasi -->
> **📸 Screenshot:** Tampilkan form yang dikosongkan lalu disubmit — muncul pesan validasi error.

---

## 4. Aktivitas 3 — Manipulasi DOM: Mengubah Konten

### Langkah-langkah Ikuti Saya

**Langkah 1:** Tambahkan kode berikut:

```html
    <h2>Mengubah Konten DOM</h2>
    <button id="btn-ubah-teks">Ubah Teks</button>
    <button id="btn-ubah-html">Ubah HTML</button>
    <button id="btn-ubah-style">Ubah Gaya</button>
    <button id="btn-ubah-class">Toggle Class</button>

    <div id="target-konten" class="output">
        Ini adalah elemen yang akan diubah.
    </div>

    <script>
        // 1. Mengubah teks (textContent)
        document.getElementById("btn-ubah-teks").addEventListener("click", function() {
            document.getElementById("target-konten").textContent = "Teks sudah berubah!";
        });

        // 2. Mengubah HTML (innerHTML)
        document.getElementById("btn-ubah-html").addEventListener("click", function() {
            document.getElementById("target-konten").innerHTML =
                "<strong>Teks tebal</strong> dan <em>text miring</em> — semua dari innerHTML!";
        });

        // 3. Mengubah gaya langsung (style)
        document.getElementById("btn-ubah-style").addEventListener("click", function() {
            const el = document.getElementById("target-konten");
            el.style.backgroundColor = "#4CAF50";
            el.style.color = "white";
            el.style.padding = "20px";
            el.style.borderRadius = "10px";
            el.style.fontSize = "18px";
        });

        // 4. Toggle class (cara paling rapi untuk styling)
        document.getElementById("btn-ubah-class").addEventListener("click", function() {
            document.getElementById("target-konten").classList.toggle("aktif");
        });
    </script>
```

**Langkah 2:** Klik setiap tombol satu per satu dan amati perubahan.

<!-- screenshot:manipulasi-konten -->
> **📸 Screenshot:** Tampilkan area output setelah diklik — tampilan berubah sesuai tombol yang ditekan.

### Cara Mengubah DOM

| Metode | Fungsi | Contoh |
|---|---|---|
| `textContent` | Mengubah teks mentah | `el.textContent = "Halo"` |
| `innerHTML` | Mengubah isi HTML | `el.innerHTML = "<b>Halo</b>"` |
| `style.properti` | Mengubah gaya CSS langsung | `el.style.color = "red"` |
| `classList.toggle()` | Tambah/hapus class CSS | `el.classList.toggle("aktif")` |

> **Catatan keamanan:** Hindari `innerHTML` untuk konten dari pengguna (bisa menyebabkan XSS). Untuk teks biasa, pakai `textContent`.

---

## 5. Aktivitas 4 — Manipulasi DOM: Membuat & Menghapus Elemen

### Langkah-langkah Ikuti Saya

**Langkah 1:** Tambahkan kode berikut:

```html
    <h2>Membuat & Menghapus Elemen</h2>
    <input type="text" id="input-item" placeholder="Ketik item baru...">
    <button id="btn-tambah">Tambah</button>
    <button id="btn-hapus-terakhir">Hapus Terakhir</button>
    <button id="btn-hapus-semua">Hapus Semua</button>

    <ul id="daftar-item" style="list-style: none; padding: 0;">
    </ul>

    <script>
        // Fungsi membuat elemen baru
        function buatItem(teksItem) {
            const li = document.createElement("li");
            li.textContent = teksItem;
            li.style.padding = "8px 12px";
            li.style.margin = "5px 0";
            li.style.backgroundColor = "#e8f4f8";
            li.style.borderRadius = "4px";
            li.style.display = "flex";
            li.style.justifyContent = "space-between";

            // Tombol hapus per item
            const tombolHapus = document.createElement("button");
            tombolHapus.textContent = "✕";
            tombolHapus.style.backgroundColor = "#ff6b6b";
            tombolHapus.style.color = "white";
            tombolHapus.style.border = "none";
            tombolHapus.style.padding = "2px 8px";
            tombolHapus.style.cursor = "pointer";
            tombolHapus.style.borderRadius = "3px";

            tombolHapus.addEventListener("click", function() {
                li.remove(); // Hapus elemen dari DOM
            });

            li.appendChild(tombolHapus);
            return li;
        }

        // Tambah item
        document.getElementById("btn-tambah").addEventListener("click", function() {
            const input = document.getElementById("input-item");
            const teks = input.value.trim();

            if (teks === "") {
                alert("Masukkan teks terlebih dahulu!");
                return;
            }

            const itemBaru = buatItem(teks);
            document.getElementById("daftar-item").appendChild(itemBaru);
            input.value = ""; // Kosongkan input
            input.focus();    // Fokus kembali ke input
        });

        // Tambah item dengan Enter
        document.getElementById("input-item").addEventListener("keydown", function(event) {
            if (event.key === "Enter") {
                document.getElementById("btn-tambah").click();
            }
        });

        // Hapus item terakhir
        document.getElementById("btn-hapus-terakhir").addEventListener("click", function() {
            const daftar = document.getElementById("daftar-item");
            if (daftar.lastElementChild) {
                daftar.lastElementChild.remove();
            }
        });

        // Hapus semua item
        document.getElementById("btn-hapus-semua").addEventListener("click", function() {
            document.getElementById("daftar-item").innerHTML = "";
        });
    </script>
```

**Langkah 2:** Coba tambahkan beberapa item, hapus satu per satu, dan hapus semua.

<!-- screenshot:manipulasi-elemen -->
> **📸 Screenshot:** Tampilkan daftar item yang sudah ditambahkan beberapa item, dengan tombol hapus per item.

### Cara Membuat & Menambah Elemen

```javascript
// 1. Buat elemen baru
const elemenBaru = document.createElement("div");

// 2. Isi konten
elemenBaru.textContent = "Ini elemen baru";
elemenBaru.className = "kartu";

// 3. Masukkan ke DOM (sebagai anak dari elemen lain)
document.getElementById("induk").appendChild(elemenBaru);

// Atau sisipkan di posisi tertentu
document.getElementById("induk").insertBefore(elemenBaru, referensiElemen);

// Hapus elemen
elemenBaru.remove();
```

---

## 6. Aktivitas 5 — Mini Proyek: Toggle Menu Mobile

### Tujuan

Membuat tombol hamburger sederhana yang membuka/menutup menu navigasi — seperti yang sering Anda lihat di website di hp.

### Langkah-langkah Ikuti Saya

**Langkah 1:** Buat file baru `mini-proyek-menu.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mini Proyek — Toggle Menu</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: Arial, sans-serif; }

        /* Navbar */
        .navbar {
            background-color: #333;
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .navbar .logo { color: white; font-size: 20px; font-weight: bold; }

        /* Tombol hamburger */
        .hamburger {
            display: none; /* Tersembunyi di desktop */
            background: none;
            border: none;
            color: white;
            font-size: 24px;
            cursor: pointer;
            padding: 5px 10px;
        }

        /* Menu navigasi */
        .nav-menu {
            list-style: none;
            display: flex; /* Horizontal di desktop */
            gap: 15px;
        }
        .nav-menu a {
            color: white;
            text-decoration: none;
            padding: 5px 10px;
            border-radius: 3px;
        }
        .nav-menu a:hover { background-color: #555; }

        /* Mobile: tampilkan hamburger, sembunyikan menu */
        @media (max-width: 600px) {
            .hamburger { display: block; }
            .nav-menu {
                display: none; /* Sembunyikan dulu */
                flex-direction: vertical;
                position: absolute;
                top: 60px;
                left: 0;
                right: 0;
                background-color: #444;
                padding: 10px 20px;
            }
            .nav-menu.tampil { display: flex; } /* Tampilkan jika ada class tampil */
        }

        /* Konten halaman */
        .konten { padding: 20px; }
        .konten h2 { margin-bottom: 10px; }
        .konten p { line-height: 1.6; }
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="logo">MyWeb</div>
        <button class="hamburger" id="hamburger">☰</button>
        <ul class="nav-menu" id="nav-menu">
            <li><a href="#">Beranda</a></li>
            <li><a href="#">Tentang</a></li>
            <li><a href="#">Portofolio</a></li>
            <li><a href="#">Kontak</a></li>
        </ul>
    </nav>

    <div class="konten">
        <h2>Selamat Datang!</h2>
        <p>Coba ubah ukuran browser ke bawah 600px (atau buka di hp) untuk melihat menu hamburger muncul. Klik tombol ☰ untuk membuka/menutup menu.</p>
    </div>

    <script>
        // Toggle menu saat tombol hamburger diklik
        const tombolHamburger = document.getElementById("hamburger");
        const navMenu = document.getElementById("nav-menu");

        tombolHamburger.addEventListener("click", function() {
            navMenu.classList.toggle("tampil");

            // Ganti simbol tombol
            if (navMenu.classList.contains("tampil")) {
                tombolHamburger.textContent = "✕";
            } else {
                tombolHamburger.textContent = "☰";
            }
        });

        // Tutup menu jika diklik di luar area menu
        document.addEventListener("click", function(event) {
            if (!navMenu.contains(event.target) && !tombolHamburger.contains(event.target)) {
                navMenu.classList.remove("tampil");
                tombolHamburger.textContent = "☰";
            }
        });
    </script>
</body>
</html>
```

**Langkah 2:** Buka dengan Live Server, lalu **resize browser ke bawah 600px** untuk melihat tampilan mobile.

**Langkah 3:** Klik tombol ☰ dan amati menu terbuka. Klik ✕ untuk menutup.

<!-- screenshot:miniproject-desktop -->
> **📸 Screenshot:** Tampilan desktop — menu horizontal, tombol hamburger tersembunyi.

<!-- screenshot:miniproject-mobile -->
> **📸 Screenshot:** Tampilan mobile (browser < 600px) — tombol hamburger terlihat, menu terbuka ke bawah.

---

## 7. Latihan Mandiri

### Latihan 1 — Kalkulator Sederhana (Mandiri)

Buat file `latihan11-1.html` yang berisi:
1. Dua input angka (`<input type="number">`).
2. Empat tombol: Tambah, Kurang, Kalikan, Bagi.
3. Area output untuk menampilkan hasil.
4. JavaScript yang menghitung sesuai tombol yang diklik.

**Expected output:**
- Jika input 10 dan 5, klik "Kalikan" → output menampilkan "Hasil: 50".
- Jika input 10 dan 0, klik "Bagi" → output menampilkan "Error: Tidak bisa dibagi nol!".

<!-- screenshot:latihan1-expected -->
> **📸 Screenshot:** Tampilkan kalkulator berfungsi dengan hasil perhitungan.

### Latihan 2 — Daftar Tugas dengan Checkbox (Mandiri)

Buat file `latihan11-2.html` yang berisi:
1. Input untuk menambah tugas baru + tombol "Tambah".
2. Setiap tugas memiliki checkbox dan tombol "Hapus".
3. Saat checkbox dicentang, teks tugas dicoret (strikethrough).
4. Total tugas dan tugas selesai ditampilkan di bawah daftar.

**Expected output:**
- Menambah 3 tugas → "Total: 3, Selesai: 0".
- Mencentang 1 tugas → "Total: 3, Selesai: 1", teks tugas tercoret.

<!-- screenshot:latihan2-expected -->
> **📸 Screenshot:** Tampilkan daftar tugas dengan satu tugas tercentang dan counter yang benar.

### Latihan 3 — Light/Dark Mode Toggle (Opsional)

Buat file `latihan11-3.html` yang berisi:
1. Tombol "🌙 Dark Mode" / "☀️ Light Mode".
2. Saat diklik, halaman berganti antara background terang dan gelap.
3. Preferensi diingat selama sesi (boleh pakai `localStorage` jika sudah tahu, atau cukup toggle CSS class).

<!-- screenshot:latihan3-expected -->
> **📸 Screenshot:** Tampilkan halaman dalam mode gelap dan mode terang.

---

## 8. Troubleshooting

### Masalah 1: Event tidak merespons

| Cek | Solusi |
|---|---|
| Elemen sudah ada di DOM saat script dijalankan? | Pindahkan script ke akhir `<body>` atau pakai `DOMContentLoaded` |
| ID/class selector benar? | Buka DevTools → Elements → pastikan ID/class cocok |
| Typo nama event? | Pastikan ejaan benar: `"click"`, bukan `"clicl"` |

### Masalah 2: `event.preventDefault()` lupa ditulis

```javascript
// ❌ Form akan refresh halaman saat dikirim
form.addEventListener("submit", function() {
    // proses data...
});

// ✅ Mencegah refresh
form.addEventListener("submit", function(event) {
    event.preventDefault();
    // proses data...
});
```

### Masalah 3: Elemen baru tidak muncul di DOM

```javascript
// Pastikan Anda memanggil appendChild atau prepend
const parent = document.getElementById("induk");
const child = document.createElement("div");
child.textContent = "Baru!";

// ❌ Lupa append — elemen tidak akan muncul
document.createElement("div");

// ✅ Elemen akan muncul
parent.appendChild(child);
```

### Masalah 4: `classList.toggle` tidak berfungsi

```javascript
// Pastikan nama class tidak ada typo
element.classList.toggle("aktif");  // ✅
element.classList.toggle("Aktif");  // ❌ case-sensitive!
```

### Masalah 5: Toggle menu tidak menutup saat klik di luar

Pastikan pengecekan menggunakan `event.target` dan logika `contains()` benar. Perhatikan juga urutan pengecekan — elemen yang diklik mungkin masih "di dalam" parent dari sudut pandang DOM.

---

> **⏭️ Selanjutnya:** Minggu 12 — Kita akan berkenalan dengan **Tailwind CSS**, framework CSS utility-first yang sangat populer dan mempercepat styling!
