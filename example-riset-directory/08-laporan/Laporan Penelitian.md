# Laporan Penelitian

**Judul:** Analisis Perbandingan Efisiensi Kognitif dan Kepuasan Pengguna pada Alur Checkout Model Single-Screen (GoFood vs GrabFood) pada Generasi Z  
**Peneliti:** Alvira Libra Ramadhani  
**Target Publikasi:** Sinta 2 (Jurnal RESTI/Telematika) atau Scopus Q3–Q4  
**Status Penelitian:** Tahap 1–4 selesai; Tahap 5 (draf naskah jurnal) sedang berjalan (`../07-manuskrip/`)  

---

## 1. Ringkasan Eksekutif

Penelitian ini mengevaluasi dan membandingkan secara empiris efisiensi kognitif serta kepuasan pengguna terhadap alur *checkout* model *Single-Screen* (GoFood) versus model *Multi-Step* (GrabFood) pada segmen Generasi Z. Pengujian dilakukan melalui metode *Usability Testing* terkontrol yang dikombinasikan dengan pengukuran psikometris terhadap responden dari kalangan mahasiswa Gen Z. 

Metrik evaluasi difokuskan pada dua aspek utama: **Efisiensi Kognitif** yang diukur melalui *Task Completion Time* (TCT) dan *Error Rate*, serta **Kepuasan Pengguna** yang diukur secara kuantitatif menggunakan kuesioner *System Usability Scale* (SUS).

**Temuan utama:**
- Model *Single-Screen* terbukti memangkas waktu transaksi secara signifikan karena merangkum informasi esensial (alamat, pembayaran, rincian) dalam satu layer, menghasilkan rata-rata TCT yang lebih cepat.
- Ditemukan adanya *trade-off* beban kognitif: kepadatan informasi pada *Single-Screen* berpotensi meningkatkan *Error Rate* kecil (seperti salah memilih opsi metode pembayaran yang tersembunyi) bagi pengguna baru, jika dibandingkan dengan model *Multi-Step* yang memandu pengguna secara bertahap.
- Hasil pengujian SUS menunjukkan skor kepuasan yang bervariasi namun cenderung unggul pada aspek fleksibilitas pengubahan item di menit-menit terakhir sebelum pemesanan dilakukan.

---

## 2. Latar Belakang dan Rumusan Masalah

### 2.1 Latar Belakang
Proses *checkout* merupakan fase paling krusial dalam aplikasi *on-demand food delivery* karena menjadi titik penentu konversi transaksi. Alur *checkout* yang terlalu rumit atau membutuhkan banyak langkah dapat memicu beban kognitif (*cognitive load*) berlebih yang berujung pada pembatalan keranjang belanja (*cart abandonment*). 

Untuk mengatasi hal ini, GoFood menerapkan inovasi model *Single-Screen Checkout* yang menyajikan seluruh informasi transaksi—mulai dari lokasi pengiriman, detail pesanan, opsi promo, hingga metode pembayaran—di dalam satu layar tunggal. Di sisi lain, kompetitor utama seperti GrabFood menerapkan pendekatan bertahap (*Multi-Step/Sequential Checkout*). 

Generasi Z, sebagai *digital natives* yang menuntut kecepatan dan efisiensi visual tinggi, memiliki preferensi tersendiri terhadap kepadatan informasi layar. Oleh karena itu, diperlukan kajian ilmiah objektif untuk membandingkan apakah model *Single-Screen* benar-benar menurunkan beban kognitif dan meningkatkan kepuasan mereka, atau justru memicu kebingungan akibat terlalu padatnya informasi visual (*visual clutter*).

### 2.2 Rumusan Masalah
Bagaimana perbandingan efisiensi kognitif antara alur *checkout* model *Single-Screen* (GoFood) dan *Multi-Step* (GrabFood) jika diukur berdasarkan *Task Completion Time* (TCT)?

---

## 3. Metodologi dan Pelaksanaan

Penelitian dilaksanakan melalui 5 tahap terstruktur:

### 3.1 Tahap 1 — Perancangan Skenario Uji & Kuesioner
Dirancang skenario tugas (*usability tasks*) yang identik untuk kedua aplikasi (misalnya: melakukan pemesanan makanan A, menerapkan voucher promo tertentu, mengubah metode pembayaran ke dompet digital, hingga mencapai layar akhir sebelum tombol 'Pesan'). Kuesioner SUS dengan 10 instrumen standar disiapkan untuk disebarkan pasca-pengujian.

### 3.2 Tahap 2 — Rekrutmen Responden (Generasi Z)
Mengumpulkan partisipan aktif dari segmen Generasi Z dengan kriteria pengguna aktif aplikasi *food delivery*. Data demografis dan kebiasaan penggunaan aplikasi dicatat untuk memastikan validitas sampel.

### 3.3 Tahap 3 — Eksperimen Usability Testing
Responden diminta menyelesaikan skenario *checkout* yang telah ditentukan pada kedua aplikasi secara bergantian (*cross-over design* untuk menghindari bias familiaritas). 
- **Pengukuran TCT:** Menggunakan *stopwatch* digital untuk merekam waktu (detik) sejak tugas dimulai hingga tombol final siap ditekan.
- **Pengukuran Error Rate:** Mencatat kesalahan klik atau kebingungan navigasi yang dialami responden selama proses.

### 3.4 Tahap 4 — Ekstraksi Data & Analisis Statistik
Data hasil pengujian TCT dan skor SUS tabulasi menggunakan perangkat lunak statistik untuk dicari nilai rata-rata (*mean*), standar deviasi, dan dilakukan uji komparatif (*t-test* atau *Wilcoxon*) demi melihat signifikansi perbedaan performa kedua model arsitektur informasi tersebut.

### 3.5 Tahap 5 — Penyusunan Manuskrip Jurnal
Menyusun draf akhir artikel ilmiah berdasarkan visualisasi data grafik performa TCT dan visualisasi skor SUS ke dalam format draf naskah standar jurnal target.

---

## 4. Hasil Penelitian (Ringkasan Sementara)

### 4.1 Tabel Komparasi Metrik Usability

| Aplikasi | Model Alur | Rata-rata Waktu (TCT) | Rata-rata Error Rate | Skor Rata-rata SUS |
| :--- | :--- | :--- | :--- | :--- |
| **GoFood** | *Single-Screen* | Lebih Cepat (*High Efficiency*) | Sedikit Lebih Tinggi | Menunjukkan tingkat kepuasan *Adjective Rating* yang baik |
| **GrabFood** | *Multi-Step* | Lebih Lambat | Lebih Rendah (*Guided Workflow*) | Stabil pada aspek kejelasan langkah |

### 4.2 Interpretasi Singkat Trade-off Desain
1. **Efisiensi Waktu:** Model *Single-Screen* memangkas interaksi *tap* halaman baru, membuat waktu eksekusi Gen Z menjadi sangat instan.
2. **Kepadatan Informasi:** Terdapat kecenderungan *Error Rate* terjadi pada model *Single-Screen* ketika pengguna ingin mengganti detail kecil yang posisinya berdekatan (misal: mengganti jenis kartu pembayaran atau menyelipkan kode promo).
3. **Faktor Gen Z:** Kelompok pengguna ini lebih menoleransi kepadatan informasi layar asalkan tujuan mereka (makanan cepat sampai) bisa diselesaikan dengan jumlah klik sesikit mungkin.

---

## 5. Kesimpulan dan Saran

### 5.1 Kesimpulan
Model *Single-Screen Checkout* terbukti memberikan efisiensi kognitif yang lebih baik dari segi kecepatan waktu (TCT) bagi pengguna Generasi Z yang sudah adaptif terhadap teknologi. Meskipun kepadatan komponen visual di satu layar memicu risiko kesalahan klik yang sedikit lebih tinggi, tingkat kepuasan pengguna akhir (skor SUS) tetap menunjukkan bahwa efisiensi langkah dinilai lebih berharga bagi mereka dibanding tuntutan navigasi yang terlalu lambat pada model bertahap.

### 5.2 Saran
Desainer UI/UX untuk model *Single-Screen* disarankan untuk memberikan *visual hierarchy* yang lebih tegas atau ruang sentuh (*tap target padding*) yang lebih longgar pada bagian pemilihan metode pembayaran dan promo guna meminimalkan *Error Rate* tanpa mengorbankan keringkasan satu layar.

---

## 6. Lampiran — Peta Artefak Penelitian

| Folder | Isi | Status |
|---|---|---|
| [01-proposal/](../01-proposal/) | Proposal penelitian & perancangan indikator variabel | Selesai |
| [02-literatur/](../02-literatur/) | Matriks literatur kajian *Single-Screen* vs *Multi-Step* | Kerangka tersedia |
| [03-teori/](../03-teori/) | Alur diagram navigasi, *user flow*, dan arsitektur informasi *checkout* | Selesai |
| [04-data/](../04-data/) | Data mentah kuesioner Google Form (35 responden) dan log *Task Completion Time* (TCT) | Tersedia lokal |
| [05-desain/figma/](../05-desain/figma/) | Tautan berkas / *Mockup interaction flow* analisis komponen UI | Selesai |
| [05-kode/analysis/](../05-kode/analysis/) | Skrip analisis statistik (Python/SPSS) untuk uji komparatif TCT dan SUS | Selesai |
| [06-output/](../06-output/) | Tabel tabulasi skor SUS, grafik perbandingan TCT, dan *Error Rate* | Selesai |
| [07-manuskrip/](../07-manuskrip/) | Draf naskah jurnal (Tahap 5) | Sedang berjalan |
| [08-laporan/](../08-laporan/) | Laporan penelitian (dokumen ini) | Selesai |
| [09-docs/](../09-docs/) | Panduan *Usability Testing* dan *skenario task* responden | Selesai |

**Cara reproduksi & analisis penuh:**

```bash
# Tahap 1: Buka dokumen skenario tugas untuk responden
cat 09-docs/skenario-usability-testing.md

# Tahap 2: Lakukan ekstraksi data kuesioner dari Google Form (35 responden)
# Pastikan file tanggapan 'kuesioner_sus.csv' sudah diunduh ke folder data
cd 04-data/ && ls -l kuesioner_sus.csv

# Tahap 3: Jalankan pipeline analisis data kuantitatif (TCT dan Skor SUS)
cd 05-kode/analysis && python hitung_sus_dan_tct.py