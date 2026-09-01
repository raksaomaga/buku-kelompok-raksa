# Minggu 10 — JavaScript Dasar: Variabel, Fungsi, Kondisi & DOM Selection

> **Topik:** Pengenalan JavaScript — dari variabel sampai membaca elemen HTML.
> **Output akhir:** Skrip JavaScript sederhana yang bisa Anda tambahkan ke halaman HTML yang sudah dibuat di minggu-minggu sebelumnya.
> **Durasi:** 3 jam kelas: 1 jam teori dan 2 jam praktik

---

## Daftar Isi

1. [Persiapan](#1-persiapan)
2. [Aktivitas 1 — Menulis Skrip Pertama](#2-aktivitas-1--menulis-skrip-pertama)
3. [Aktivitas 2 — Variabel & Tipe Data](#3-aktivitas-2--variabel--tipe-data)
4. [Aktivitas 3 — Fungsi](#4-aktivitas-3--fungsi)
5. [Aktivitas 4 — Kondisi (If/Else)](#5-aktivitas-4--kondisi-ifelse)
6. [Aktivitas 5 — DOM Selection](#6-aktivitas-5--dom-selection)
7. [Latihan Mandiri](#7-latihan-mandiri)
8. [Troubleshooting](#8-troubleshooting)

---

## 1. Persiapan

### Yang Anda Butuhkan

- VSCode (sudah terinstal dari minggu sebelumnya).
- File HTML dari minggu-minggu sebelumnya (atau buat file baru `index.html`).
- Browser (Chrome atau Firefox).

### Cek Lingkungan

Buka terminal di VSCode (`Ctrl + ``) dan jalankan:

```
node --version
```

Jika muncul versi Node.js, berarti lingkungan sudah siap. Jika belum terinstal, tetap tenang — kita bisa langsung menulis JS di browser tanpa Node.js.

> **Catatan:** Untuk modul ini, kita **tidak** membutuhkan Node.js. Kita menulis JavaScript langsung di dalam file HTML.

---

## 2. Aktivitas 1 — Menulis Skrip Pertama

### Langkah-langkah Ikuti Saya

**Langkah 1:** Buat file baru bernama `minggu10.html` di folder proyek Anda.

**Langkah 2:** Isi dengan kode berikut:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minggu 10 — JavaScript Pertama</title>
</head>
<body>
    <h1 id="judul">Halo, Dunia!</h1>
    <p id="paragraf">Ini adalah paragraf pertama saya.</p>

    <script>
        console.log("JavaScript berhasil dimuat!");
        document.getElementById("judul").style.color = "blue";
    </script>
</body>
</html>
```

**Langkah 3:** Buka file ini di browser — klik kanan pada file di VSCode, pilih **Open with Live Server** (atau buka langsung dengan drag ke browser).

**Langkah 4:** Buka **Console** browser:
- Chrome: tekan `F12` → klik tab **Console**.
- Firefox: tekan `F12` → klik tab **Console**.

<!-- screenshot:console-js -->
> **📸 Screenshot:** Tampilkan console browser dengan pesan "JavaScript berhasil dimuat!".

### Apa yang Terjadi?

- `<script>` di dalam HTML adalah tempat kita menulis kode JavaScript.
- `console.log(...)` mencetak pesan ke console browser — sangat berguna untuk debugging.
- `document.getElementById("judul")` mencari elemen HTML dengan `id="judul"`.
- `.style.color = "blue"` mengubah warna teks menjadi biru.

---

## 3. Aktivitas 2 — Variabel & Tipe Data

### Konsep Singkat

Variabel adalah **wadah** untuk menyimpan data. Di JavaScript modern, kita punya tiga cara mendeklarasikan variabel:

| Kata Kunci | Bisa Diubah? | Kapan Dipakai |
|---|---|---|
| `let` | Ya | Nilai yang mungkin berubah |
| `const` | Tidak | Nilai yang tetap (konstanta) |
| `var` | Ya | HINDARI — cara lama, punya masalah scope |

> **Aturan praktis:** Selalu pakai `const`. Ganti ke `let` hanya jika nilai perlu diubah. Jangan pakai `var`.

### Langkah-langkah Ikuti Saya

**Langkah 1:** Tambahkan script berikut **sebelum** tag `</script>` yang sudah ada:

```javascript
// Variabel dengan const (tidak bisa diubah)
const nama = "Budi";
const umur = 19;

// Variabel dengan let (bisa diubah)
let IPK = 3.5;

console.log("Nama:", nama);
console.log("Umur:", umur);
console.log("IPK:", IPK);

// Mengubah nilai let
IPK = 3.8;
console.log("IPK setelah update:", IPK);
```

**Langkah 2:** Refresh halaman dan lihat hasilnya di Console.

<!-- screenshot:console-variabel -->
> **📸 Screenshot:** Tampilkan console dengan output nama, umur, IPK, dan IPK setelah update.

### Tipe Data Dasar

```javascript
// String (teks) — pakai tanda kutip
const pesan = "Halo Dunia";

// Number (angka) — tanpa tanda kutip
const nilai = 100;

// Boolean (benar/salah)
const lulus = true;

// Array (daftar)
const buku = ["HTML", "CSS", "JavaScript"];

// Object (kumpulan properti)
const mahasiswa = {
    nama: "Budi",
    nim: "12345",
    jurusan: "Informatika"
};

console.log(pesan);       // "Halo Dunia"
console.log(nilai);       // 100
console.log(lulus);       // true
console.log(buku[0]);     // "HTML" (indeks mulai dari 0)
console.log(mahasiswa.nama); // "Budi"
```

<!-- screenshot:console-tipedata -->
> **📸 Screenshot:** Tampilkan console dengan semua output tipe data di atas.

---

## 4. Aktivitas 3 — Fungsi

### Konsep Singkat

Fungsi adalah **bloc kode yang bisa dipanggil berulang kali**. Bayangkan seperti resep masakan — Anda menulis resepnya sekali, lalu bisa dipakai kapan saja.

### Langkah-langkah Ikuti Saya

**Langkah 1:** Tambahkan kode berikut:

```javascript
// Fungsi sederhana — deklarasi
function sapa(nama) {
    console.log("Halo, " + nama + "! Selamat belajar JavaScript.");
}

// Memanggil fungsi
sapa("Budi");
sapa("Ani");
sapa("Andi");

// Fungsi dengan nilai kembali (return)
function hitungLuas(panjang, lebar) {
    const luas = panjang * lebar;
    return luas;
}

const hasil = hitungLuas(10, 5);
console.log("Luas persegi panjang:", hasil);

// Fungsi panah (arrow function) — cara modern
const kalikan = (a, b) => {
    return a * b;
};

console.log("3 × 4 =", kalikan(3, 4));
```

**Langkah 2:** Refresh halaman, lihat hasil di Console.

<!-- screenshot:console-fungsi -->
> **📸 Screenshot:** Tampilkan console dengan output pemanggilan fungsi `sapa()`, `hitungLuas()`, dan `kalikan()`.

### Apa yang Terjadi?

- `function sapa(nama)` — mendefinisikan fungsi bernama `sapa` yang menerima satu parameter `nama`.
- `sapa("Budi")` — memanggil fungsi dengan nilai "Budi" untuk parameter `nama`.
- `return luas` — mengembalikan nilai hasil perhitungan agar bisa digunakan di luar fungsi.
- Arrow function `=>` adalah cara menulis fungsi yang lebih singkat.

---

## 5. Aktivitas 4 — Kondisi (If/Else)

### Konsep Singkat

Kondisi membuat program bisa **mengambil keputusan** — seperti "Jika hujan, bawa payung; jika tidak, bawa topi."

### Langkah-langkah Ikuti Saya

**Langkah 1:** Tambahkan kode berikut:

```javascript
// Kondisi sederhana
const suhu = 32;

if (suhu > 30) {
    console.log("Panas! Minum air yang banyak.");
} else if (suhu >= 20) {
    console.log("Nyaman. Cocok untuk belajar.");
} else {
    console.log("Dingin! Pakai jaket.");
}

// Kondisi dengan string
const namaMahasiswa = "Budi";

if (namaMahasiswa === "Budi") {
    console.log("Halo Budi, selamat datang!");
} else {
    console.log("Siapa kamu?");
}

// Operator perbandingan yang perlu diketahui
// ===  sama dengan (nilai DAN tipe sama)
// !==  tidak sama dengan
// >    lebih besar dari
// <    lebih kecil dari
// >=   lebih besar atau sama dengan
// <=   lebih kecil atau sama dengan

console.log(5 === 5);    // true
console.log(5 === "5");  // false (angka vs string)
console.log(5 == "5");   // true (hati-hati, bisa menyesatkan)
```

**Langkah 2:** Refresh dan lihat output di Console.

<!-- screenshot:console-kondisi -->
> **📸 Screenshot:** Tampilkan console dengan output kondisi if/else dan perbandingan.

---

## 6. Aktivitas 5 — DOM Selection

### Konsep Singkat

**DOM (Document Object Model)** adalah representasi struktur HTML sebagai "pohon" yang bisa diakses oleh JavaScript. DOM Selection adalah cara JavaScript **mencari elemen** di halaman HTML.

### Langkah-langkah Ikuti Saya

**Langkah 1:** Ganti isi file `minggu10.html` dengan versi lengkap berikut:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minggu 10 — DOM Selection</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        .kotak { border: 2px solid #333; padding: 10px; margin: 10px 0; border-radius: 5px; }
        .highlight { background-color: yellow; }
    </style>
</head>
<body>
    <h1 id="judul">Belajar DOM Selection</h1>
    <p class="teks">Paragraf pertama — class="teks"</p>
    <p class="teks">Paragraf kedua — class="teks"</p>
    <p id="paragraf-khusus">Paragraf khusus dengan ID</p>

    <div class="kotak" id="kotak1">Kotak 1</div>
    <div class="kotak" id="kotak2">Kotak 2</div>
    <div class="kotak" id="kotak3">Kotak 3</div>

    <ul id="daftar-mahasiswa">
        <li>Budi</li>
        <li>Ani</li>
        <li>Andi</li>
        <li>Sari</li>
    </ul>

    <script>
        // === Cara 1: getElementById — mencari SATU elemen berdasarkan ID ===
        const judul = document.getElementById("judul");
        console.log("Judul:", judul.textContent);
        judul.style.color = "purple";

        // === Cara 2: querySelector — mencari SATU elemen (pilihan CSS pertama) ===
        const paragrafKhusus = document.querySelector("#paragraf-khusus");
        console.log("Paragraf khusus:", paragrafKhusus.textContent);

        // === Cara 3: querySelectorAll — mencari SEMUA elemen (NodeList) ===
        const semuaTeks = document.querySelectorAll(".teks");
        console.log("Jumlah paragraf .teks:", semuaTeks.length);

        semuaTeks.forEach((el, index) => {
            console.log(`  Teks ${index + 1}:`, el.textContent);
        });

        // === Cara 4: getElementsByClassName — mencari SEMUA elemen ===
        const semuaKotak = document.getElementsByClassName("kotak");
        console.log("Jumlah kotak:", semuaKotak.length);

        // Ubah warna semua kotak
        for (let i = 0; i < semuaKotak.length; i++) {
            semuaKotak[i].style.backgroundColor = "lightblue";
            semuaKotak[i].style.padding = "15px";
        }

        // === Cara 5: querySelector dengan selector campuran ===
        const itemPertama = document.querySelector("#daftar-mahasiswa li:first-child");
        console.log("Mahasiswa pertama:", itemPertama.textContent);
        itemPertama.style.fontWeight = "bold";
        itemPertama.style.color = "red";
    </script>
</body>
</html>
```

**Langkah 2:** Buka dengan Live Server dan lihat hasilnya.

<!-- screenshot:dom-selection-halaman -->
> **📸 Screenshot:** Tampilkan halaman web yang sudah berubah — judul ungu, kotak biru, paragraf pertama daftar mahasiswa berwarna merah tebal.

**Langkah 3:** Buka Console (`F12` → Console) untuk melihat semua log.

<!-- screenshot:dom-selection-console -->
> **📸 Screenshot:** Tampilkan console dengan semua output DOM selection.

### Ringkasan DOM Selection

| Metode | Cari | Return |
|---|---|---|
| `getElementById("id")` | 1 elemen | Element |
| `querySelector("selector")` | 1 elemen (pertama yang cocok) | Element |
| `querySelectorAll("selector")` | Semua elemen | NodeList |
| `getElementsByClassName("class")` | Semua elemen | HTMLCollection |

> **Tips:** `querySelector` dan `querySelectorAll` paling fleksibel — bisa pakai semua selector CSS (id, class, tag, attribute, bahkan `:nth-child`).

---

## 7. Latihan Mandiri

### Latihan 1 — Variabel dan Fungsi (Mandiri)

Buat file baru `latihan10-1.html` dan buatlah:

1. Variabel `const` untuk menyimpan nama lengkap Anda dan NIM.
2. Variabel `let` untuk menyimpan nilai ujian (angka).
3. Fungsi `beriNilai(skor)` yang mencetak ke console:
   - Jika skor >= 85: "Excellent! Nilai Anda: [skor]"
   - Jika skor >= 70: "Bagus! Nilai Anda: [skor]"
   - Jika skor < 70: "Perlu belajar lagi. Nilai Anda: [skor]"
4. Panggil fungsi tersebut dengan tiga nilai berbeda.

**Expected output di console:**
```
Excellent! Nilai Anda: 90
Bagus! Nilai Anda: 75
Perlu belajar lagi. Nilai Anda: 60
```

<!-- screenshot:latihan1-expected -->
> **📸 Screenshot:** Tampilkan console Anda dengan output yang sesuai.

### Latihan 2 — DOM Selection (Mandiri)

Buat file baru `latihan10-2.html` dengan HTML berikut:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Latihan 10-2</title>
</head>
<body>
    <h1 id="sapa">Selamat Datang</h1>
    <p class="info">Mata kuliah: Desain Web</p>
    <p class="info">Dosen: [Nama Dosen]</p>
    <p class="info">Hari: [Hari Kuliah]</p>
    <div class="kartu">Kartu Mahasiswa</div>
    <div class="kartu">Kartu UKT</div>
    <div class="kartu">Kartu Perpustakaan</div>
</body>
</html>
```

Tugas JavaScript:
1. Ambil elemen `#sapa` dan ubah teksnya menjadi nama Anda.
2. Ambil semua elemen `.info` dan ubah warna setiap paragraf menjadi biru.
3. Ambil semua elemen `.kartu` dan tambahkan border 1px solid gray pada setiap kartu.

<!-- screenshot:latihan2-expected -->
> **📸 Screenshot:** Tampilkan halaman setelah JavaScript berjalan — judul berganti nama, paragraf info biru, kartu ada border.

### Latihan 3 — Tantangan (Opsional)

Buat file `latihan10-3.html` yang berisi:
- Sebuah array berisi minimal 5 nama mahasiswa.
- Fungsi `cariMahasiswa(namaArray, namaDicari)` yang mencetak ke console:
  - "[nama] ditemukan di indeks [indeks]!" jika ketemu.
  - "[nama] tidak ditemukan di daftar." jika tidak ketemu.
- Panggil fungsi dengan nama yang ada di array dan nama yang tidak ada.

**Expected output di console:**
```
Budi ditemukan di indeks 0!
Siti tidak ditemukan di daftar.
```

<!-- screenshot:latihan3-expected -->
> **📸 Screenshot:** Tampilkan console dengan output pencarian.

---

## 8. Troubleshooting

### Masalah 1: JavaScript tidak berjalan / Console kosong

| Kemungkinan | Solusi |
|---|---|
| Tag `<script>` salah posisi | Pastikan `<script>` berada **sebelum** `</body>`, bukan di `<head>` |
| Typo pada nama fungsi/variabel | Perhatikan huruf besar-kecil: `judul` ≠ `Judul` |
| File belum disimpan | Tekan `Ctrl + S` sebelum refresh browser |

### Masalah 2: "Uncaught TypeError: Cannot read properties of null"

```
// ❌ Salah — elemen belum ada di DOM
document.getElementById("judul").style.color = "red";

// ✅ Benar — pindahkan script ke akhir body atau pakai DOMContentLoaded
document.addEventListener("DOMContentLoaded", function() {
    document.getElementById("judul").style.color = "red";
});
```

### Masalah 3: Selector tidak menemukan elemen

```javascript
// Pastikan selector benar
document.querySelector("#judul")     // ID → pakai #
document.querySelector(".kotak")     // Class → pakai .
document.querySelector("p")          // Tag → tanpa simbol
document.querySelector("div.kotak")  // Tag + Class
```

Buka **DevTools** → tab **Elements** → periksa apakah elemen yang dicari benar-benar ada di DOM.

### Masalah 4: Console menunjukkan error "is not defined"

Biasanya karena typo nama variabel/fungsi atau urutan pemanggilan yang salah. Perhatikan:
- Nama harus **persis sama** (case-sensitive).
- Fungsi harus dideklarasikan **sebelum** dipanggil (kecuali pakai function declaration).

---

> **⏭️ Selanjutnya:** Minggu 11 — Kita akan belajar **event handling** (klik, input, hover) dan **manipulasi DOM** (membuat/menghapus elemen secara dinamis)!
