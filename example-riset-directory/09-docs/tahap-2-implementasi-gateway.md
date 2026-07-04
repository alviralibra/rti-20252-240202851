# Tahap 2 — Penyusunan Kuesioner & Rekrutmen Responden Gen Z

**Status:** Selesai  
**Acuan Prosedur:** [tahap-1-skenario-dan-instrumen.md](tahap-1-skenario-dan-instrumen.md)  
**Lokasi Instrumen:** [../09-docs/](../09-docs/) (Panduan & Kuesioner Google Form)

---

## Tujuan

Menyiapkan instrumen pengumpulan data digital berupa kuesioner psikometris *System Usability Scale* (SUS) dan menyebarkannya guna merekrut serta mengumpulkan data dari sampel target Generasi Z. Pengumpulan data dirancang untuk mendukung pengujian dua model alur operasi *checkout*:
- **Model A (Single-Screen / GoFood)** — Menguji respons terhadap halaman ringkasan padat satu layar tunggal.
- **Model B (Multi-Step / GrabFood)** — Menguji respons terhadap halaman transaksi bertahap (sekuensial).

---

## Deliverable Berkas & Administrasi

- [x] **Struktur Formulir Digital** — Penyusunan kuesioner elektronik via Google Form yang terbagi menjadi bagian Demografi, Evaluasi GoFood (10 Pertanyaan SUS), dan Evaluasi GrabFood (10 Pertanyaan SUS).
- [x] **Lembar Persetujuan (*Informed Consent*)** — Pernyataan persetujuan partisipasi responden di bagian awal kuesioner yang menjamin kerahasiaan data pribadi.
- [x] **Matriks Karakteristik Sampel** — Kriteria inklusi responden: mahasiswa aktif, termasuk dalam rentang usia Generasi Z, dan memiliki pengalaman bertransaksi pada aplikasi *food delivery*.
- [x] **Daftar Periksa Pengujian (*Usability Checklist*)** — Panduan operasional bagi peneliti untuk memastikan responden memahami batasan tugas simulasi tanpa memberikan intervensi jawaban.
- [x] **Format Tabulasi Data Mentah** — Penyiapan struktur file spreadsheet (`.csv`/`.xlsx`) untuk memisahkan skor Likert ganjil (pernyataan positif) dan genap (pernyataan negatif) sesuai rumus baku SUS.
- [x] **Validasi Pengisian** — Pengaktifan fitur *required fields* pada Google Form untuk mencegah adanya data kosong (*missing values*) dari responden.

---

## Hasil Rekrutmen & Karakteristik Sampel Akhir

Proses rekrutmen partisipan dilakukan secara luring dan daring di lingkungan kampus, menghasilkan basis data empiris yang valid:

- **Jumlah Responden Layak:** Berhasil mengumpulkan data lengkap dari **35 responden** mahasiswa Generasi Z setelah melalui proses penyaringan kelayakan kriteria sampel.
- **Karakteristik Demografis:** Seluruh responden terverifikasi berada pada segmen usia Generasi Z (mahasiswa aktif kelas 3IKRA) yang terbiasa menggunakan ponsel pintar untuk pemesanan makanan sehari-hari.
- **Validasi Kualitas Data:** Tidak ditemukan data duplikat atau pengisian tidak lengkap. Seluruh 35 baris data dinyatakan bersih (*clean data*) dan siap dimasukkan ke dalam *pipeline* analisis kuantitatif pada Tahap 4.

---

## Catatan Pelaksanaan Lapangan

- **Koreksi Sampel:** Jumlah responden akhir ditetapkan secara presisi sebanyak 35 orang, disesuaikan dari catatan evaluasi kemajuan riset di lapangan.
- **Teknis Pengkondisian:** Untuk meminimalkan bias eksternal (seperti kendala sinyal internet operator responden), seluruh proses pengujian simulasi alur *checkout* prototipe dilakukan menggunakan koneksi Wi-Fi yang sama di area pengujian terkontrol.
- **Ketertelusuran Berkas:** Data mentah hasil ekspor Google Form telah diarsipkan secara lokal pada direktori `04-data/kuesioner_sus.csv` dengan anotasi yang jelas untuk mempermudah proses audit data atau bimbingan laporan.