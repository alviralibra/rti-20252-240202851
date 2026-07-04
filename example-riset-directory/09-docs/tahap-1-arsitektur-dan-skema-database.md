# Tahap 1 — Perancangan Skenario Uji & Instrumen Kuesioner SUS

**Status:** Selesai

---

## 1. Komponen Evaluasi Usability

1. **Prototipe Antarmuka (Figma)** — Berkas interaksi aktif alur *checkout* GoFood (Model *Single-Screen*) dan GrabFood (Model *Multi-Step*) sebagai objek uji pengguna.
2. **Metrik Efisiensi Kognitif (Kuantitatif)**
   - *Task Completion Time* (TCT): Total waktu (dalam satuan detik) yang dihabiskan responden untuk menyelesaikan tugas transaksi.
   - *Error Rate*: Frekuensi kesalahan klik (*misclick*) atau kebingungan navigasi yang dilakukan responden selama proses uji coba.
3. **Metrik Kepuasan Pengguna (Psikometris)** — Kuesioner kualitatif yang dibakukan menggunakan instrumen standar *System Usability Scale* (SUS) berisi 10 pertanyaan pasca-pengujian.

---

## 2. Alur Pengujian Pengguna (Cross-Over Design)

Skenario dijalankan secara silang kepada responden untuk menghindari bias familiaritas terhadap salah satu aplikasi:
Partisipan Gen Z Masuk → Penjelasan Instruksi Singkat
│
├── Kelompok A: Uji Aplikasi GoFood (Single-Screen) Pertama
│     ├── Rekam Waktu (TCT) & Catat Error Rate selama simulasi checkout
│     ├── Pengisian Kuesioner SUS untuk GoFood
│     └── Beralih ke Aplikasi GrabFood (Multi-Step) → Rekam TCT, Error & Kuesioner SUS
│
└── Kelompok B: Uji Aplikasi GrabFood (Multi-Step) Pertama
├── Rekam Waktu (TCT) & Catat Error Rate selama simulasi checkout
├── Pengisian Kuesioner SUS untuk GrabFood
└── Beralih ke Aplikasi GoFood (Single-Screen) → Rekam TCT, Error & Kuesioner SUS

Mekanisme **Validasi Data**: Jika responden gagal menyelesaikan tugas utama (misalnya aplikasi *crash* atau salah alur yang tidak bisa kembali), maka data berjalan dianggap hangus (*drop*) demi menjaga keakuratan rata-rata metrik komparasi.

---

## 3. Skenario Tugas Responden (Task Scenarios)

Skenario tugas di bawah ini dibuat identik agar perbandingan alur *checkout* bersifat *apple-to-apple*:

1. **Tugas 1 (Pemilihan Menu & Validasi Alamat):** Responden masuk ke halaman keranjang belanja, memeriksa ketepatan alamat pengiriman yang tertera, dan memastikan pesanan makanan sudah sesuai.
2. **Tugas 2 (Penerapan Opsi Promo):** Responden diminta mencari dan memasang voucher diskon/ongkir yang tersedia pada halaman transaksi.
3. **Tugas 3 (Konfigurasi Pembayaran):** Responden mengubah opsi metode pembayaran tunai (*cash*) menjadi saldo dompet digital (GoPay/OVO).
4. **Tugas 4 (Finalisasi Transaksi):** Responden menavigasi pandangan ke ringkasan total biaya dan menekan tombol konfirmasi akhir (*Pesan/Place Order*) sampai muncul animasi proses pemesanan.

---

## 4. Struktur Instrumen Kuesioner SUS

Pengukuran kepuasan pengguna menggunakan 10 butir pertanyaan standar SUS dengan skala Likert 1 (Sangat Tidak Setuju) sampai 5 (Sangat Setuju):

| ID | Pernyataan Kuesioner |
| :--- | :--- |
| **P1** | Saya rasa saya akan menyukai menggunakan alur *checkout* ini lagi. |
| **P2** | Saya merasa alur *checkout* ini rumit tanpa alasan yang jelas. |
| **P3** | Saya rasa alur *checkout* ini sangat mudah digunakan. |
| **P4** | Saya rasa saya membutuhkan bantuan orang lain/teknisi untuk menggunakan alur ini. |
| **P5** | Saya merasa fitur-fitur dalam alur *checkout* ini terintegrasi dengan baik. |
| **P6** | Saya rasa banyak hal yang tidak konsisten pada alur *checkout* ini. |
| **P7** | Saya membayangkan orang lain akan cepat belajar menggunakan alur *checkout* ini. |
| **P8** | Saya merasa alur *checkout* ini sangat membingungkan/ribet saat dijalankan. |
| **P9** | Saya merasa sangat percaya diri saat menggunakan alur *checkout* ini. |
| **P10** | Saya perlu membiasakan diri terlebih dahulu sebelum lancar menggunakan alur ini. |

---

## 5. Keputusan Teknis Prosedur (Final)

1. **Target Responden**: Difokuskan pada 35 responden aktif yang merupakan mahasiswa bagian dari Generasi Z.
2. **Metode Pengumpulan**: Pengujian waktu dilakukan langsung menggunakan *stopwatch* digital, sedangkan skor psikometris dihimpun via Google Form.
3. **Teknis Perhitungan**: Skor SUS dihitung menggunakan rumus baku SUS per responden, lalu diuji signifikansinya secara komparatif untuk menentukan model mana yang memberikan beban kognitif paling rendah bagi pengguna.