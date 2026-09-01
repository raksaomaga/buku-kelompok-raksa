# Minggu 13 — Pengenalan React: Komponen, JSX & Props

> **Topik:** Berkenalan dengan React — framework JavaScript terpopuler. Kita memahami **konsep** komponen, JSX, dan props secara teori ringan + demo visual, **tanpa** membuat aplikasi React yang berjalan penuh.
> **Output akhir:** Pemahaman konseptual tentang bagaimana React bekerja, kemampuan membaca kode React sederhana, dan gambaran apa yang akan dipelajari di semester lanjut.
> **Durasi:** 3 jam kelas: 1 jam teori dan 2 jam praktik

---

## Daftar Isi

1. [Persiapan](#1-persiapan)
2. [Konsep: Mengapa React?](#2-konsep-mengapa-react)
3. [Aktivitas 1 — Membaca Kode React (Tanpa Menjalankan)](#3-aktivitas-1--membaca-kode-react-tanpa-menjalankan)
4. [Aktivitas 2 — JSX: HTML yang "Bisa Dikode"](#4-aktivitas-2--jsx-html-yang-bisa-dikode)
5. [Aktivitas 3 — Komponen: Blok Bangunan UI](#5-aktivitas-3--komponen-blok-bangunan-ui)
6. [Aktivitas 4 — Props: Mengirim Data ke Komponen](#6-aktivitas-4--props-mengirim-data-ke-komponen)
7. [Aktivitas 5 — Demo Lengkap: Membaca & Memahami Kode React](#7-aktivitas-5--demo-lengkap-membaca--memahami-kode-react)
8. [Latihan Mandiri](#8-latihan-mandiri)
9. [Troubleshooting & Catatan](#9-troubleshooting--catatan)

---

## 1. Persiapan

### Yang Anda Butuhkan

- Pemahaman dari minggu 10–11 (JavaScript dasar, variabel, fungsi, DOM).
- Pemahaman dari minggu 12 (Tailwind CSS — karena React sering dipasangkan dengan Tailwind).
- Browser untuk melihat demo visual.
- VSCode untuk membaca dan mengedit file kode.

### Yang Kita TIDAK Akan Lakukan Hari Ini

- Instalasi React (tidak perlu `npx create-react-app` atau `npm create vite`).
- Menjalankan aplikasi React lokal.
- Menggunakan build tools (Vite, Webpack, dll).

> **Tujuan minggu ini:** Membaca, memahami, dan "merasakan" kode React. Agar ketika Anda belajar React di semester lanjutan, konsepnya sudah tidak asing.

---

## 2. Konsep: Mengapa React?

### React dalam Satu Kalimat

> **React** adalah JavaScript library untuk membangun **antarmuka (UI) berbasis komponen** — artinya, Anda memecah halaman web menjadi potongan-potongan kecil yang bisa digunakan ulang.

### Perbandingan: Tanpa React vs Dengan React

**Tanpa React (vanilla JavaScript):**
```javascript
// Anda harus secara manual mencari elemen dan mengubahnya
const daftar = document.getElementById("daftar-mahasiswa");
const item = document.createElement("li");
item.textContent = "Budi";
daftar.appendChild(item);
// Jika data berubah → Anda harus menulis ulang kode manipulasi DOM
```

**Dengan React:**
```jsx
// Anda cukup mendeskripsikan APA yang ingin ditampilkan
function DaftarMahasiswa({ mahasiswa }) {
    return (
        <ul>
            {mahasiswa.map((nama, index) => (
                <li key={index}>{nama}</li>
            ))}
        </ul>
    );
}

// React yang mengurus bagaimana update DOM saat data berubah
```

### React Populer Karena:

| Alasan | Penjelasan |
|---|---|
| **Komponen** | UI dipecah jadi blok kecil, bisa digunakan ulang |
| **Deklaratif** | Anda tulis "apa" yang ingin ditampilkan, bukan "bagaimana" cara update DOM |
| **Ekosistem besar** | Banyak library pendukung (routing, state management, UI kit) |
| **Industry standard** | Banyak perusahaan tech menggunakan React |

---

## 3. Aktivitas 1 — Membaca Kode React (Tanpa Menjalankan)

### Tujuan

Melihat kode React secara utuh agar Anda terbiasa dengan sintaksnya. Kita **tidak menjalankan** kode ini — kita membaca dan memahaminya.

**Langkah 1:** Buat file baru `react-preview.html`:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Preview Kode React</title>
    <style>
        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background-color: #1e1e2e;
            color: #cdd6f4;
            margin: 0;
            padding: 20px;
        }
        h1 { color: #89b4fa; text-align: center; margin-bottom: 10px; }
        .subtitle { text-align: center; color: #6c7086; margin-bottom: 30px; }
        .code-block {
            background-color: #181825;
            border: 1px solid #313244;
            border-radius: 8px;
            padding: 20px;
            margin: 15px 0;
            overflow-x: auto;
        }
        .code-block h3 { color: #f38ba8; margin-top: 0; }
        pre { margin: 0; white-space: pre-wrap; }
        code { font-family: 'Fira Code', 'Consolas', monospace; font-size: 14px; line-height: 1.6; }
        .comment { color: #6c7086; }
        .keyword { color: #cba6f7; }
        .string { color: #a6e3a1; }
        .comp { color: #89dceb; }
        .prop { color: #fab387; }
        .annotation { background: #313244; color: #f9e2af; padding: 8px 12px; border-radius: 5px; font-size: 13px; margin-top: 10px; }
        .note { background: #1e1e2e; border-left: 4px solid #89b4fa; padding: 12px 16px; margin: 15px 0; border-radius: 0 8px 8px 0; }
    </style>
</head>
<body>

<h1>Preview Kode React</h1>
<p class="subtitle">Membaca &amp; memahami kode React — tanpa menjalankan</p>
```

**Langkah 2:** Tambahkan bagian kode React satu per satu. Berikut urutan penjelasannya (paste ke file setelah tag `</p>` yang sudah ada):

### Kode 1 — Komponen Paling Sederhana

```html
    <div class="code-block">
        <h3>Komponen 1 — "Halo Dunia" Paling Sederhana</h3>
        <pre><code><span class="comment">// Dalam React, UI ditulis sebagai FUNCTION yang mengembalikan JSX</span>
<span class="keyword">function</span> <span class="comp">Sapa</span>() {
    <span class="keyword">return</span> (
        &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"container"</span>&gt;
            &lt;<span class="comp">h1</span>&gt;Halo, Dunia React!&lt;/<span class="comp">h1</span>&gt;
            &lt;<span class="comp">p</span>&gt;Ini adalah komponen React pertama saya.&lt;/<span class="comp">p</span>&gt;
        &lt;/<span class="comp">div</span>&gt;
    );
}</code></pre>
    </div>

    <div class="annotation">
        <strong>Catatan:</strong>
        JSX mirip HTML, tapi ada perbedaan kecil — misal: <code>class</code> menjadi <code>className</code>.<br>
        Komponen harus diawali huruf KAPITAL (misal: <code>Sapa</code>, bukan <code>sapa</code>).
    </div>
```

### Kode 2 — Komponen dengan Props

```html
    <div class="code-block">
        <h3>Komponen 2 — Menerima Data dengan Props</h3>
        <pre><code><span class="comment">// Props = "parameter" untuk komponen React</span>
<span class="keyword">function</span> <span class="comp">KartuProfil</span>({ <span class="prop">nama</span>, <span class="prop">jurusan</span>, <span class="prop">angkatan</span> }) {
    <span class="keyword">return</span> (
        &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"bg-white rounded-lg shadow-md p-6"</span>&gt;
            &lt;<span class="comp">h2</span> <span class="prop">className</span>=<span class="string">"text-xl font-bold"</span>&gt;{<span class="prop">nama</span>}&lt;/<span class="comp">h2</span>&gt;
            &lt;<span class="comp">p</span> <span class="prop">className</span>=<span class="string">"text-gray-600"</span>&gt;Jurusan: {<span class="prop">jurusan</span>}&lt;/<span class="comp">p</span>&gt;
            &lt;<span class="comp">p</span> <span class="prop">className</span>=<span class="string">"text-gray-600"</span>&gt;Angkatan: {<span class="prop">angkatan</span>}&lt;/<span class="comp">p</span>&gt;
        &lt;/<span class="comp">div</span>&gt;
    );
}

<span class="comment">// Cara menggunakan (memanggil) komponen:</span>
<span class="comment">// &lt;KartuProfil nama="Budi" jurusan="Informatika" angkatan="2025" /&gt;</span>
<span class="comment">// &lt;KartuProfil nama="Ani" jurusan="Informatika" angkatan="2025" /&gt;</span></code></pre>
    </div>

    <div class="note">
        <strong>Yang terjadi:</strong> Fungsi <code>KartuProfil</code> menerima tiga props (<code>nama</code>, <code>jurusan</code>, <code>angkatan</code>) dan menggunakannya di dalam JSX.<br>
        Komponen yang sama bisa digunakan berulang kali dengan data berbeda — itulah kekuatan komponen!
    </div>
```

### Kode 3 — Komponen dengan List (Map)

```html
    <div class="code-block">
        <h3>Komponen 3 — Menampilkan Daftar (List)</h3>
        <pre><code><span class="keyword">function</span> <span class="comp">DaftarMahasiswa</span>({ <span class="prop">mahasiswa</span> }) {
    <span class="keyword">return</span> (
        &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"bg-white rounded-lg shadow p-4"</span>&gt;
            &lt;<span class="comp">h2</span> <span class="prop">className</span>=<span class="string">"text-lg font-bold mb-2"</span>&gt;Daftar Mahasiswa&lt;/<span class="comp">h2</span>&gt;
            &lt;<span class="comp">ul</span>&gt;
                {<span class="prop">mahasiswa</span>.map((<span class="prop">nama</span>, <span class="prop">index</span>) =&gt; (
                    &lt;<span class="comp">li</span> <span class="prop">key</span>={<span class="prop">index</span>} <span class="prop">className</span>=<span class="string">"py-1 border-b"</span>&gt;
                        {<span class="prop">index</span> + 1}. {<span class="prop">nama</span>}
                    &lt;/<span class="comp">li</span>&gt;
                ))}
            &lt;/<span class="comp">ul</span>&gt;
        &lt;/<span class="comp">div</span>&gt;
    );
}

<span class="comment">// Cara menggunakan:</span>
<span class="comment">// &lt;DaftarMahasiswa mahasiswa={["Budi", "Ani", "Andi", "Sari"]} /&gt;</span></code></pre>
    </div>

    <div class="annotation">
        <strong>Catatan:</strong> <code>map()</code> dalam JSX mirip seperti <code>forEach()</code> di JavaScript biasa — tetapi mengembalikan nilai (return).<br>
        <code>key</code> diperlukan oleh React untuk mengidentifikasi setiap elemen dalam daftar.
    </div>
```

### Kode 4 — Komponen Bersarang (Nested)

```html
    <div class="code-block">
        <h3>Komponen 4 — Komponen di Dalam Komponen</h3>
        <pre><code><span class="comment">// Komponen kecil — tombol</span>
<span class="keyword">function</span> <span class="comp">Tombol</span>({ <span class="prop">teks</span>, <span class="prop">warna</span> }) {
    <span class="keyword">return</span> (
        &lt;<span class="comp">button</span> <span class="prop">className</span>={<span class="string">`px-4 py-2 rounded text-white font-bold ${</span><span class="prop">warna</span><span class="string">}`</span>}&gt;
            {<span class="prop">teks</span>}
        &lt;/<span class="comp">button</span>&gt;
    );
}

<span class="comment">// Komponen besar — menggunakan Tombol</span>
<span class="keyword">function</span> <span class="comp">HalamanUtama</span>() {
    <span class="keyword">return</span> (
        &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"p-6"</span>&gt;
            &lt;<span class="comp">h1</span> <span class="prop">className</span>=<span class="string">"text-2xl font-bold mb-4"</span>&gt;Selamat Datang&lt;/<span class="comp">h1</span>&gt;
            &lt;<span class="comp">p</span> <span class="prop">className</span>=<span class="string">"mb-4"</span>&gt;Pilih aksi berikut:&lt;/<span class="comp">p</span>&gt;

            <span class="comment">{/* Menggunakan komponen Tombol */}</span>
            &lt;<span class="comp">Tombol</span> <span class="prop">teks</span>=<span class="string">"Mulai"</span> <span class="prop">warna</span>=<span class="string">"bg-blue-500"</span> /&gt;
            &lt;<span class="string"> </span>&gt;
            &lt;<span class="comp">Tombol</span> <span class="prop">teks</span>=<span class="string">"Batal"</span> <span class="prop">warna</span>=<span class="string">"bg-red-500"</span> /&gt;
        &lt;/<span class="comp">div</span>&gt;
    );
}</code></pre>
    </div>

    <div class="note">
        <strong>Yang terjadi:</strong> <code>HalamanUtama</code> menggunakan komponen <code>Tombol</code> dua kali dengan data berbeda.<br>
        Ini seperti menggunakan fungsi dalam fungsi — komponen React bisa dipanggil berkali-kali dengan data berbeda.
    </div>
```

**Langkah 3:** Tutup file HTML yang benar:

```html
</body>
</html>
```

**Langkah 4:** Buka `react-preview.html` di browser untuk melihat tampilan kode yang sudah diberi warna syntax highlighting.

<!-- screenshot:react-preview-kode -->
> **📸 Screenshot:** Tampilkan halaman preview kode React dengan syntax highlighting yang rapi.

---

## 4. Aktivitas 2 — JSX: HTML yang "Bisa Dikode"

### Apa Itu JSX?

**JSX (JavaScript XML)** adalah sintaks yang mirip HTML tapi ditulis **di dalam JavaScript**. React menggunakan JSX sebagai cara mendeskripsikan tampilan UI.

### Perbedaan JSX vs HTML

| Aspek | HTML | JSX |
|---|---|---|
| Class | `class="..."` | `className="..."` |
| For (label) | `for="..."` | `htmlFor="..."` |
| Style | `style="color: red;"` | `style={{ color: 'red' }}` |
| Self-closing | `<br>`, `<img>` | `<br />`, `<img />` |
| Expression | Tidak bisa | Bisa pakai `{}` |
| Comment | `<!-- ... -->` | `{/* ... */}` |

### JSX Adalah Ekspresi JavaScript

```jsx
// Anda bisa menulis JavaScript Dalam JSX menggunakan {}

function Profil({ nama, umur }) {
    return (
        <div>
            <h2>Nama: {nama}</h2>
            <p>Umur: {umur} tahun</p>
            <p>Status: {umur >= 17 ? 'Dewasa' : 'Anak-anak'}</p>
            <p>Tahun Lahir: {2025 - umur}</p>
        </div>
    );
}

// {} di JSX = "masukkan hasil ekspresi JavaScript di sini"
```

**Bandingkan dengan JavaScript biasa:**

```javascript
// JavaScript biasa
const nama = "Budi";
const html = "<h2>Nama: " + nama + "</h2>";

// JSX
// <h2>Nama: {nama}</h2>  → lebih bersih dan mudah dibaca
```

---

## 5. Aktivitas 3 — Komponen: Blok Bangunan UI

### Konsep Mental: Komponen = LEGO

Bayangkan setiap komponen React adalah **bata LEGO**:
- Setiap bata punya bentuk dan warna tersendiri (props & style).
- Anda bisa menyusun bata-bata menjadi struktur yang lebih besar.
- Bata yang sama bisa digunakan berulang kali di tempat berbeda.

### Struktur Dasar Komponen

```jsx
// 1. Komponen tanpa props (self-contained)
function Header() {
    return (
        <nav className="bg-blue-600 text-white p-4">
            <h1 className="text-xl font-bold">My Website</h1>
        </nav>
    );
}

// 2. Komponen dengan props
function Card({ title, description, buttonText }) {
    return (
        <div className="bg-white rounded-lg shadow p-4">
            <h2 className="text-lg font-bold">{title}</h2>
            <p className="text-gray-600 mb-3">{description}</p>
            <button className="bg-blue-500 text-white px-4 py-2 rounded">
                {buttonText}
            </button>
        </div>
    );
}

// 3. Komponen menyusun komponen lain (Komposisi)
function App() {
    return (
        <div>
            <Header />
            <Card title="Tentang Kami" description="Kami adalah..." buttonText="Selengkapnya" />
            <Card title="Layanan" description="Kami menyediakan..." buttonText="Lihat" />
        </div>
    );
}
```

### Perbandingan dengan Cara Tradisional

```html
<!-- Tanpa komponen: mengulang kode yang sama -->
<div class="card">
    <h2>Tentang Kami</h2>
    <p>Kami adalah...</p>
    <button>Selengkapnya</button>
</div>
<div class="card">
    <h2>Layanan</h2>
    <p>Kami menyediakan...</p>
    <button>Lihat</button>
</div>
<!-- Jika ingin mengubah struktur card, harus mengubah SEMUA card secara manual -->

<!-- Dengan komponen: cukup ganti definisi Card -->
<!-- Perubahan di satu tempat berlaku untuk semua Card -->
```

---

## 6. Aktivitas 4 — Props: Mengirim Data ke Komponen

### Apa Itu Props?

**Props (properties)** adalah cara mengirim data **dari luar ke dalam** komponen — seperti parameter fungsi.

```jsx
function Greeting({ nama }) {
    return <h1>Halo, {nama}!</h1>;
}

// Menggunakan komponen:
<Greeting nama="Budi" />   // → render: <h1>Halo, Budi!</h1>
<Greeting nama="Ani" />    // → render: <h1>Halo, Ani!</h1>
```

### Analogi Fungsi JavaScript

```javascript
// JavaScript biasa
function sapa(nama) {
    return "Halo, " + nama + "!";
}

sapa("Budi");  // "Halo, Budi!"
sapa("Ani");   // "Halo, Ani!"

// React = konsep yang sama, tapi output-nya JSX (UI)
// <Greeting nama="Budi" /> = sapa("Budi") dalam konteks UI
```

### Props Bisa Berisi Apa Saja

```jsx
function ProductCard({ name, price, inStock, rating, image }) {
    return (
        <div className="bg-white rounded-lg shadow p-4">
            <img src={image} alt={name} className="w-full h-48 object-cover rounded" />
            <h2 className="text-lg font-bold mt-2">{name}</h2>
            <p className="text-green-600 font-semibold">
                Rp {price.toLocaleString('id-ID')}
            </p>
            <p className="text-sm text-gray-500">
                {inStock ? 'Tersedia' : 'Habis'}
            </p>
            <p className="text-sm">{rating}/5</p>
        </div>
    );
}

// Menggunakan:
<ProductCard
    name="Laptop ASUS"
    price={8500000}
    inStock={true}
    rating={4.5}
    image="/laptop.jpg"
/>
```

### Props — Aturan Penting

```jsx
// 1. Props bersifat READ-ONLY — komponen TIDAK BOLEH mengubah props
function Avatar({ nama }) {
    // ❌ nama = "Hacker";  // JANGAN! Props tidak boleh diubah
    // ✅ Gunakan variabel baru jika perlu
    const namaBesar = nama.toUpperCase();
    return <div>{namaBesar}</div>;
}

// 2. Default props
function Button({ text = "Klik", color = "blue" }) {
    return <button className={`bg-${color}-500 text-white p-2`}>{text}</button>;
}

// 3. Children props — konten di antara tag pembuka dan penutup
function Container({ children }) {
    return <div className="max-w-md mx-auto bg-white p-6 rounded-lg shadow">{children}</div>;
}

// Menggunakan children:
<Container>
    <h1>Judul</h1>
    <p>Paragraf di dalam container</p>
</Container>
```

---

## 7. Aktivitas 5 — Demo Lengkap: Membaca & Memahami Kode React

### Tujuan

Membaca kode React yang **lebih realistis** — seperti yang mungkin Anda temui di proyek nyata.

**Langkah 1:** Tambahkan kode berikut ke `react-preview.html` (setelah kode-kode sebelumnya):

```html
    <div class="code-block">
        <h3>Kode Lengkap — Halaman Profil Mahasiswa (React)</h3>
        <pre><code><span class="comment">// =========================================</span>
<span class="comment">// File: App.jsx — Halaman Profil Mahasiswa</span>
<span class="comment">// =========================================</span>

<span class="comment">// 1. Komponen kecil: badge status</span>
<span class="keyword">function</span> <span class="comp">StatusBadge</span>({ <span class="prop">aktif</span> }) {
    <span class="keyword">if</span> (<span class="prop">aktif</span>) {
        <span class="keyword">return</span> &lt;<span class="comp">span</span> <span class="prop">className</span>=<span class="string">"bg-green-100 text-green-800 px-3 py-1 rounded-full text-sm"</span>&gt;
            Aktif
        &lt;/<span class="comp">span</span>&gt;;
    }
    <span class="keyword">return</span> &lt;<span class="comp">span</span> <span class="prop">className</span>=<span class="string">"bg-red-100 text-red-800 px-3 py-1 rounded-full text-sm"</span>&gt;
        Tidak Aktif
    &lt;/<span class="comp">span</span>&gt;;
}

<span class="comment">// 2. Komponen medium: kartu profil</span>
<span class="keyword">function</span> <span class="comp">KartuProfil</span>({ <span class="prop">nama</span>, <span class="prop">nim</span>, <span class="prop">jurusan</span>, <span class="prop">ipk</span>, <span class="prop">aktif</span> }) {
    <span class="keyword">return</span> (
        &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"bg-white rounded-xl shadow-lg p-6 max-w-sm"</span>&gt;
            <span class="comment">{/* Avatar */}</span>
            &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"w-20 h-20 rounded-full bg-blue-500
                        flex items-center justify-center text-white text-2xl
                        font-bold mx-auto mb-4"</span>&gt;
                {<span class="prop">nama</span>.charAt(0)}
            &lt;/<span class="comp">div</span>&gt;

            <span class="comment">{/* Info */}</span>
            &lt;<span class="comp">h2</span> <span class="prop">className</span>=<span class="string">"text-xl font-bold text-center mb-1"</span>&gt;
                {<span class="prop">nama</span>}
            &lt;/<span class="comp">h2</span>&gt;
            &lt;<span class="comp">p</span> <span class="prop">className</span>=<span class="string">"text-gray-500 text-center mb-3"</span>&gt;NIM: {<span class="prop">nim</span>}&lt;/<span class="comp">p</span>&gt;
            &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"text-center mb-3"</span>&gt;
                &lt;<span class="comp">StatusBadge</span> <span class="prop">aktif</span>={<span class="prop">aktif</span>} /&gt;
            &lt;/<span class="comp">div</span>&gt;

            <span class="comment">{/* Detail */}</span>
            &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"border-t pt-3 mt-3 space-y-1 text-sm"</span>&gt;
                &lt;<span class="comp">p</span>&gt;&lt;<span class="comp">strong</span>&gt;Jurusan:&lt;/<span class="comp">strong</span>&gt; {<span class="prop">jurusan</span>}&lt;/<span class="comp">p</span>&gt;
                &lt;<span class="comp">p</span>&gt;&lt;<span class="comp">strong</span>&gt;IPK:&lt;/<span class="comp">strong</span>&gt;
                    &lt;<span class="comp">span</span> <span class="prop">className</span>={<span class="prop">ipk</span> &gt;= 3.5 ? <span class="string">"text-green-600"</span> : <span class="string">"text-red-600"</span>}&gt;
                        {<span class="prop">ipk</span>}
                    &lt;/<span class="comp">span</span>&gt;
                &lt;/<span class="comp">p</span>&gt;
            &lt;/<span class="comp">div</span>&gt;
        &lt;/<span class="comp">div</span>&gt;
    );
}

<span class="comment">// 3. Komponen utama: halaman</span>
<span class="keyword">function</span> <span class="comp">HalamanProfil</span>() {
    <span class="keyword">const</span> daftarMahasiswa = [
        { <span class="prop">nama</span>: <span class="string">"Budi Santoso"</span>, <span class="prop">nim</span>: <span class="string">"2401001"</span>,
          <span class="prop">jurusan</span>: <span class="string">"Informatika"</span>, <span class="prop">ipk</span>: 3.8, <span class="prop">aktif</span>: <span class="keyword">true</span> },
        { <span class="prop">nama</span>: <span class="string">"Ani Wijaya"</span>, <span class="prop">nim</span>: <span class="string">"2401002"</span>,
          <span class="prop">jurusan</span>: <span class="string">"Informatika"</span>, <span class="prop">ipk</span>: 3.2, <span class="prop">aktif</span>: <span class="keyword">true</span> },
        { <span class="prop">nama</span>: <span class="string">"Andi Pratama"</span>, <span class="prop">nim</span>: <span class="string">"2401003"</span>,
          <span class="prop">jurusan</span>: <span class="string">"Sistem Informasi"</span>, <span class="prop">ipk</span>: 2.9, <span class="prop">aktif</span>: <span class="keyword">false</span> },
    ];

    <span class="keyword">return</span> (
        &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"min-h-screen bg-gray-100 py-10"</span>&gt;
            &lt;<span class="comp">h1</span> <span class="prop">className</span>=<span class="string">"text-3xl font-bold text-center mb-8"</span>&gt;
                Daftar Profil Mahasiswa
            &lt;/<span class="comp">h1</span>&gt;

            &lt;<span class="comp">div</span> <span class="prop">className</span>=<span class="string">"flex flex-wrap justify-center gap-6 px-4"</span>&gt;
                {<span class="prop">daftarMahasiswa</span>.map((<span class="prop">mhs</span>) =&gt; (
                    &lt;<span class="comp">KartuProfil</span>
                        <span class="prop">key</span>={<span class="prop">mhs</span>.nim}
                        <span class="prop">nama</span>={<span class="prop">mhs</span>.nama}
                        <span class="prop">nim</span>={<span class="prop">mhs</span>.nim}
                        <span class="prop">jurusan</span>={<span class="prop">mhs</span>.jurusan}
                        <span class="prop">ipk</span>={<span class="prop">mhs</span>.ipk}
                        <span class="prop">aktif</span>={<span class="prop">mhs</span>.aktif}
                    /&gt;
                ))}
            &lt;/<span class="comp">div</span>&gt;
        &lt;/<span class="comp">div</span>&gt;
    );
}</code></pre>
    </div>
```

**Langkah 2:** Buka file di browser dan baca kode dengan seksama. Coba identifikasi:

<!-- screenshot:react-kode-lengkap -->
> **📸 Screenshot:** Tampilkan kode lengkap di browser dengan syntax highlighting.

**Checklist pemahaman** — centang jika sudah bisa menjawab:

- [ ] Komponen `StatusBadge` menerima props apa?
- [ ] Di mana `StatusBadge` digunakan (disebut)?
- [ ] Bagaimana cara menentukan warna IPK (hijau/merah)?
- [ ] Bagaimana `HalamanProfil` membuat daftar kartu?
- [ ] Apa fungsi `key` pada `KartuProfil`?

<!-- screenshot:react-checklist -->
> **📸 Screenshot:** Tampilkan checklist yang sudah diisi.

---

## 8. Latihan Mandiri

### Latihan 1 — Membaca Kode React (Mandiri)

Baca kode React berikut dan jawab pertanyaan di bawahnya:

```jsx
function TodoItem({ text, completed }) {
    return (
        <div className="flex items-center gap-2 p-2">
            <input type="checkbox" checked={completed} readOnly />
            <span className={completed ? "line-through text-gray-400" : ""}>
                {text}
            </span>
        </div>
    );
}

function TodoList() {
    const todos = [
        { text: "Belajar HTML", completed: true },
        { text: "Belajar CSS", completed: true },
        { text: "Belajar JavaScript", completed: false },
        { text: "Belajar React", completed: false },
    ];

    return (
        <div className="max-w-md mx-auto bg-white p-4 rounded-lg shadow">
            <h2 className="text-xl font-bold mb-3">To-Do List</h2>
            {todos.map((todo, index) => (
                <TodoItem
                    key={index}
                    text={todo.text}
                    completed={todo.completed}
                />
            ))}
        </div>
    );
}
```

**Pertanyaan:**

1. Komponen `TodoItem` menerima props apa saja?
2. Apa yang terjadi pada teks jika `completed === true`?
3. Berapa banyak `TodoItem` yang akan ditampilkan?
4. Berapa banyak item yang sudah selesai (centang)?
5. Jika Anda ingin menambah item baru, bagian mana yang perlu diubah?

<!-- screenshot:latihan1-expected -->
> **📸 Screenshot:** Tuliskan jawaban Anda (boleh di file teks atau di comment di dalam file HTML).

### Latihan 2 — Menulis Pseudo-Code React (Mandiri)

Bayangkan Anda diminta membuat komponen `KartuProduk` untuk toko online. **Tanpa menjalankan kode**, tuliskan (dalam bentuk pseudo-code atau kode JSX mentah) komponen yang:

1. Menerima props: `nama`, `harga`, `gambar` (URL), `diskon` (persen, bisa 0).
2. Menampilkan gambar, nama produk, harga asli, dan harga setelah diskon (jika diskon > 0).
3. Menggunakan Tailwind CSS untuk styling (minimal: rounded, shadow, padding).

**Expected output (kira-kira tampilan yang Anda bayangkan):**

```
+------------------------+
|   [Gambar Produk]      |
|                        |
|   Laptop ASUS          |
|   Rp 8.500.000         |
|   ~~Rp 10.000.000~~    |  <-- hanya muncul jika diskon > 0
|   (hemat 15%)          |
+------------------------+
```

<!-- screenshot:latihan2-expected -->
> **📸 Screenshot:** Tampilkan kode JSX pseudo-code yang Anda tulis.

### Latihan 3 — Peta Pemahaman (Opsional)

Buat daftar 5 konsep React yang sudah Anda pahami dan 5 konsep yang masih ingin dipelajari lebih lanjut. Ini akan menjadi acuan saat Anda belajar React di semester lanjutan.

**Contoh format:**

| Sudah Dipahami | Ingin Dipelajari |
|---|---|
| Komponen adalah fungsi | State (useState hook) |
| Props = parameter komponen | useEffect (side effects) |
| JSX mirip HTML tapi ada bedanya | React Router (navigasi) |
| Komponen bisa bersarang | API calls di React |
| map() untuk membuat list | Context API (state global) |

<!-- screenshot:latihan3-expected -->
> **📸 Screenshot:** Tampilkan daftar pemahaman Anda.

---

## 9. Troubleshooting & Catatan

### FAQ Umum tentang React

**Q: Apakah saya harus menguasai React sekarang?**
> Tidak. Modul ini hanya pengenalan. Anda akan belajar React secara mendalam di semester lanjutan. Yang penting sekarang adalah **membaca dan memahami konsep dasarnya**.

**Q: Kenapa ada banyak simbol aneh di kode React (`{}`, `()`, `=>`, `className`)?**
> - `{}` = ekspresi JavaScript di dalam JSX
> - `() => {}` = arrow function (sudah dipelajari di minggu 10)
> - `className` = nama attribute di JSX untuk menetapkan class CSS (karena `class` adalah kata kunci JavaScript)

**Q: React vs Vue vs Angular — mana yang terbaik?**
> Tidak ada yang "terbaik" secara mutlak. React paling banyak digunakan di industri global. Vue lebih populer di beberapa region. Angular untuk aplikasi enterprise. Untuk kuliah, React adalah pilihan yang aman karena ekosistemnya paling besar.

### Kosa Kata React

| Istilah | Arti |
|---|---|
| **Component** | Blok bangunan UI — fungsi yang mengembalikan JSX |
| **JSX** | JavaScript XML — sintaks HTML-like di dalam JavaScript |
| **Props** | Data yang dikirim ke komponen (read-only) |
| **State** | Data internal komponen yang bisa berubah (akan dipelajari di semester lanjutan) |
| **Virtual DOM** | Representasi DOM di memori — React update DOM secara efisien |
| **Hook** | Fitur khusus React (useState, useEffect) — akan dipelajari nanti |

### Pengingat: Apa yang Sudah Anda Miliki

Setelah mengikuti minggu 10–13, Anda sudah memiliki fondasi untuk melangkah ke topik lanjutan:

| Minggu | Topik | Skill yang Didapat |
|---|---|---|
| 10 | JavaScript dasar | Variabel, fungsi, kondisi, DOM selection |
| 11 | JavaScript interaktif | Event handling, manipulasi DOM |
| 12 | Tailwind CSS | Utility-first CSS, layout responsive |
| 13 | React preview | Membaca kode komponen, JSX, props |

> **Next step (semester lanjutan):** Anda akan membangun aplikasi React yang sebenarnya — menggunakan state, effect, routing, dan API. Fondasi dari minggu 10–13 akan membuat proses itu jauh lebih mudah!

---

> **Selamat menyelesaikan modul pengenalan workshop desain web!** Semoga ini menjadi awal yang baik untuk perjalanan Anda di dunia web development.
