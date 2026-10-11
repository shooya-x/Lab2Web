# Lab2Web – Latihan HTML Lanjutan

Praktikum **Pemrograman Web** – materi HTML Lanjutan: tabel, form, semantic HTML, multimedia, dan validasi.

## Langkah 1 – Tabel Dasar

**File:** `latihan.html`

Membuat tabel data mahasiswa menggunakan tag `<table>`, `<tr>`, `<th>`, dan `<td>`.

```html
<h1>Data Mahasiswa</h1>
<table border="1">
    <tr>
        <th>NIM</th>
        <th>Nama</th>
        <th>Program Studi</th>
    </tr>
    <tr>
        <td>31241001</td>
        <td>Andi</td>
        <td>Teknik Informatika</td>
    </tr>
    <!-- baris Budi, Cici, Dedi, dan Eka -->
</table>
```

**Penjelasan:**
- `<table>` adalah pembungkus tabel, atribut `border="1"` memberi garis pada tabel.
- `<tr>` (table row) membuat satu baris.
- `<th>` (table header) membuat sel judul kolom yang otomatis tebal dan rata tengah.
- `<td>` (table data) membuat sel isi data.

**Hasil:**

![Langkah 1 - Tabel Data Mahasiswa](screenshots/step1.png)

---

## Langkah 2 – Tabel Lanjutan

**File:** `latihan.html`

Membuat tabel nilai praktikum yang terstruktur dengan `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, dan `colspan`.

```html
<table border="1">
    <caption>Nilai Praktikum</caption>
    <thead>
        <tr>
            <th>No</th>
            <th>Nama</th>
            <th>Nilai</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Andi</td>
            <td>85</td>
        </tr>
        <!-- baris 2 sampai 5 -->
    </tbody>
    <tfoot>
        <tr>
            <td colspan="2">Rata-rata</td>
            <td>88.6</td>
        </tr>
    </tfoot>
</table>
```

**Penjelasan:**
- `<caption>` memberi judul pada tabel.
- `<thead>`, `<tbody>`, `<tfoot>` membagi tabel menjadi bagian kepala, isi, dan kaki sehingga strukturnya lebih jelas dan semantik.
- `colspan="2"` membuat sel "Rata-rata" menggabungkan 2 kolom.

**Hasil:**

![Langkah 2 - Tabel Nilai Praktikum](screenshots/step2.png)

---

## Langkah 3 – Form Registrasi

**File:** `latihan.html`

Membuat form registrasi mahasiswa dengan berbagai tipe `<input>`.

```html
<h1>Form Registrasi Mahasiswa</h1>
<form>
    <label for="nama">Nama Lengkap</label><br>
    <input type="text" id="nama" name="nama"><br><br>

    <label for="email">Email</label><br>
    <input type="email" id="email" name="email"><br><br>

    <label for="password">Password</label><br>
    <input type="password" id="password" name="password"><br><br>

    <label for="tanggal">Tanggal Lahir</label><br>
    <input type="date" id="tanggal" name="tanggal"><br><br>

    <button type="submit">Daftar</button>
    <button type="reset">Reset</button>
</form>
```

**Penjelasan:**
- `<form>` adalah pembungkus seluruh isian form.
- `<label for="...">` dihubungkan dengan `id` pada input, sehingga mengklik label akan memfokuskan input.
- `type="text"`, `email`, `password`, dan `date` menampilkan jenis isian yang berbeda (password disamarkan, date menampilkan pemilih tanggal).
- `type="submit"` mengirim form, `type="reset"` mengosongkan kembali isian.

**Hasil:**

![Langkah 3 - Form Registrasi Mahasiswa](screenshots/step3.png)

---

## Langkah 4 – Radio Button dan Checkbox

**File:** `latihan.html`

Menambahkan pilihan jenis kelamin (radio) dan keahlian (checkbox).

```html
<h2>Jenis Kelamin</h2>
<input type="radio" id="laki" name="jk" value="L">
<label for="laki">Laki-laki</label>
<input type="radio" id="perempuan" name="jk" value="P">
<label for="perempuan">Perempuan</label>

<h2>Keahlian</h2>
<input type="checkbox" id="html" name="skill" value="HTML">
<label for="html">HTML</label>
<input type="checkbox" id="css" name="skill" value="CSS">
<label for="css">CSS</label>
<input type="checkbox" id="js" name="skill" value="JavaScript">
<label for="js">JavaScript</label>
```

**Penjelasan:**
- **Radio** hanya bisa memilih satu opsi. Radio dengan `name` yang sama (`jk`) dianggap satu grup.
- **Checkbox** bisa memilih lebih dari satu opsi.
- `value` adalah nilai yang dikirim ketika opsi dipilih.

**Hasil:**

![Langkah 4 - Radio Button dan Checkbox](screenshots/step4.png)

---

## Langkah 5 – Select dan Textarea

**File:** `latihan.html`

Menambahkan dropdown program studi dan kolom alamat multi-baris.

```html
<label for="prodi">Program Studi</label>
<select id="prodi" name="prodi">
    <option value="">-- Pilih Prodi --</option>
    <option value="ti">Teknik Informatika</option>
    <option value="si">Sistem Informasi</option>
</select>

<label for="alamat">Alamat</label><br>
<textarea id="alamat" name="alamat" rows="5" cols="40"></textarea>
```

**Penjelasan:**
- `<select>` membuat dropdown, dan setiap pilihan ditulis dengan `<option>`.
- `<textarea>` untuk teks panjang; `rows` mengatur tinggi (jumlah baris) dan `cols` mengatur lebar (jumlah karakter).

**Hasil:**

![Langkah 5 - Textarea Alamat](screenshots/step5.png)

---

## Langkah 6 – Validasi Form

**File:** `latihan.html`

Menambahkan validasi bawaan HTML5 tanpa JavaScript.

```html
<form>
    <label for="nama">Nama</label>
    <input type="text" id="nama" name="nama" required minlength="3">
    <label for="email">Email</label>
    <input type="email" id="email" name="email" required>
    <label for="umur">Umur</label>
    <input type="number" id="umur" name="umur" min="17" max="60" required>
    <button type="submit">Kirim</button>
</form>
```

**Penjelasan:**

| Atribut | Fungsi |
|---------|--------|
| `required` | Isian wajib diisi, form tidak terkirim jika kosong |
| `minlength="3"` | Nama minimal 3 karakter |
| `type="email"` | Harus berformat email yang valid |
| `min="17"` `max="60"` | Umur harus di antara 17 sampai 60 |

**Hasil:**

![Langkah 6 - Form dengan Validasi](screenshots/step6.png)

---

## Langkah 7 – Semantic HTML

**File:** `index.html`

Membuat halaman Portal Mahasiswa dengan elemen semantik agar struktur halaman jelas bagi browser, mesin pencari, dan pembaca layar.

```html
<header>
    <h1>Portal Mahasiswa</h1>
</header>
<nav>
    <a href="#">Beranda</a>
    <a href="#">Profil</a>
    <a href="#">Kontak</a>
</nav>
<main>
    <section>
        <h2>Informasi Akademik</h2>
        <article>
            <h3>Praktikum HTML Lanjutan</h3>
            <p>Mahasiswa mempelajari tabel, form, semantic HTML,
                multimedia, dan validasi.</p>
        </article>
    </section>
    <aside>Informasi tambahan mahasiswa.</aside>
</main>
<footer>
    <p>&copy; 2026 Teknik Informatika</p>
</footer>
```

**Penjelasan:**

| Tag | Fungsi |
|-----|--------|
| `<header>` | Bagian kepala halaman |
| `<nav>` | Menu navigasi |
| `<main>` | Konten utama halaman |
| `<section>` | Pengelompokan konten berdasarkan tema |
| `<article>` | Konten mandiri (artikel/berita) |
| `<aside>` | Konten pendukung/tambahan |
| `<footer>` | Bagian kaki halaman |

**Hasil:**

![Langkah 7 - Halaman Portal Mahasiswa](screenshots/step7.png)

---

## Langkah 8 – Multimedia (Audio dan Video)

**File:** `index.html`

Menambahkan pemutar audio dan video dari folder `media/`.

```html
<h2>Audio</h2>
<audio controls>
    <source src="media/audio.mp3" type="audio/mpeg">
    Browser tidak mendukung audio.
</audio>

<h2>Video</h2>
<video controls width="480">
    <source src="media/video.mp4" type="video/mp4">
    Browser tidak mendukung video.
</video>
```

**Penjelasan:**
- `<audio>` dan `<video>` menampilkan pemutar media bawaan browser.
- Atribut `controls` memunculkan tombol play, pause, volume, dan fullscreen.
- `<source>` menentukan file media (`src`) beserta formatnya (`type`).
- Teks di dalam tag hanya tampil jika browser tidak mendukung elemen tersebut (fallback).
- Atribut `width="480"` mengatur lebar video.

**Hasil:**

![Langkah 8 - Audio dan Video](screenshots/step8.png)

---

## Langkah 9 – Halaman Biodata

**File:** `biodata.html`

Menggabungkan semantic HTML, tabel, dan form dalam satu halaman biodata mahasiswa, lengkap dengan navigasi antarhalaman dan antarbagian.

```html
<nav>
    <a href="index.html">Beranda</a>
    <a href="#biodata">Biodata</a>
    <a href="#form">Form</a>
</nav>
<main>
    <section id="biodata">
        <h2>Data Mahasiswa</h2>
        <table border="1">
            <tr>
                <th>Data</th>
                <th>Keterangan</th>
            </tr>
            <tr>
                <td>NIM</td>
                <td>31251024</td>
            </tr>
            <tr>
                <td>Nama</td>
                <td>Surya Septa Pratama</td>
            </tr>
            <tr>
                <td>Program Studi</td>
                <td>Teknik Informatika</td>
            </tr>
        </table>
    </section>

    <section id="form">
        <h2>Form Biodata</h2>
        <form>
            <label for="nama">Nama</label>
            <input type="text" id="nama" name="nama" required>
            <!-- input email, select prodi, textarea alamat -->
            <button type="submit">Simpan</button>
            <button type="reset">Reset</button>
        </form>
    </section>
</main>
```

**Penjelasan:**
- Link `href="index.html"` berpindah ke halaman lain, sedangkan `href="#biodata"` dan `href="#form"` melompat ke bagian dengan `id` yang sama di halaman ini.
- Semua isian form memakai atribut `required` sehingga wajib diisi sebelum disimpan.

**Hasil:**

![Langkah 9 - Halaman Biodata Mahasiswa](screenshots/step9.png)

---

## Cara Menjalankan

1. Clone repository ini:
   ```bash
   git clone https://github.com/shooya-x/Lab2Web.git
   ```
2. Buka folder `Lab2Web`.
3. Buka file `index.html`, `biodata.html`, atau `latihan.html` langsung di browser (klik dua kali atau gunakan Live Server di VS Code).

## Kesimpulan

Pada praktikum ini telah dipelajari pembuatan tabel (termasuk `thead`, `tbody`, `tfoot`, dan `colspan`), berbagai elemen form (input, radio, checkbox, select, textarea), validasi form bawaan HTML5, elemen semantic HTML, serta penyisipan multimedia audio dan video.
