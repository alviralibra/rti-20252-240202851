# Tahap 3 — Eksperimen Usability Testing & Pengukuran Time on Task

**Status:** Selesai — Pengujian terhadap seluruh 35 responden (total 70 sesi uji silang) telah dilaksanakan, video rekaman layar berhasil diekstraksi ke satuan detik dan data dimasukkan ke `04-data/`

**Bergantung pada:** [tahap-2-rekrutmen-partisipan.md](tahap-2-rekrutmen-partisipan.md)  
**Lokasi Instrumen:** [../09-docs/](../09-docs/) (Panduan Tugas Skenario & Folder Video Rekaman)

---

## 1. Tujuan

Melaksanakan eksperimen pengujian pengguna (*Usability Testing*) terkontrol untuk membandingkan performa alur *checkout* pada aplikasi **GoFood (Model *Single-Screen*)** sebagai model baseline efisiensi tinggi versus **GrabFood (Model *Multi-Step*)** sebagai model alur bertahap. Pengujian ini mengevaluasi interaksi pengguna Generasi Z berdasarkan tiga tipe kondisi pengerjaan tugas:

- **Tugas Pemilihan & Validasi (Legitimate Flow)** — Responden menyelesaikan pemeriksaan alamat dan item pesanan pada kondisi normal.
- **Tugas Modifikasi Menit Terakhir (Adjustment Flow)** — Responden melakukan perubahan metode pembayaran dan pemasangan promo secara mendadak sebelum konfirmasi akhir, guna menguji ketahanan kognitif terhadap kepadatan informasi layar.
- **Tugas Gabungan Sekaligus (Mixed Flow)** — Responden mengeksekusi seluruh rangkaian manipulasi pesanan dari awal hingga menekan tombol pesanan final secara berurutan untuk diukur total kecepatan kognitifnya.

---

## 2. Deliverable Pelaksanaan

- [x] Berkas video rekaman layar (*Screen Recording*) utuh dari 35 responden saat berinteraksi dengan prototipe.
- [x] Berkas penugasan skenario interaksi yang telah dikalibrasi agar tingkat kesulitan tugas setara pada kedua prototipe aplikasi.
- [x] Sesi pengujian silang (*Cross-Over Sessional Matrix*) penuh untuk 35 responden (Kelompok A memulai dengan GoFood, Kelompok B memulai dengan GrabFood).
- [x] Pencatatan matriks kesalahan klik (*Error Rate Count*) yang divalidasi ulang melalui pemutaran kembali video rekaman.
- [x] Pengisian kuesioner evaluasi kepuasan psikometris SUS sesaat setelah responden menyelesaikan tugas pada masing-masing model aplikasi.
- [x] Ekstraksi data metrik **Time on Task (ToT)** dalam satuan detik dari video rekaman ke dalam draf tabel data mentah di folder `04-data/`.

---

## 3. Desain & Prosedur Eksperimen Di Lapangan

### Protokol Pengujian Pengguna (`09-docs/panduan-ut.md`)

[Mulai Sesi] → Responden Duduk Nyaman → Aktifkan Perekaman Layar (Screen Recording)
│
├── Pembagian Urutan Sesi (Cross-Over)
│
├── [Blok Uji GoFood - Single Screen]
│     ├── Mulai Tugas → Responden mengeksekusi Tugas 1-4 di layar tunggal
│     ├── Selesai Tugas → Matikan perekaman sesi GoFood
│     └── Pengisian 10 Pertanyaan Skor SUS untuk GoFood
│
├── [Blok Uji GrabFood - Multi Step]
│     ├── Mulai Tugas → Responden mengeksekusi Tugas 1-4 secara bertahap
│     ├── Selesai Tugas → Matikan perekaman sesi GrabFood
│     └── Pengisian 10 Pertanyaan Skor SUS untuk GrabFood
│
└── [Pasca Sesi] → Putar Ulang Video → Hitung Detik Bersih Time on Task (ToT)

### Matriks Pengumpulan Data Eksperimen

| Dimensi Pengujian | Objek Komparasi Alur | Target Jumlah Sampel | Metode Pengukuran |
| :--- | :--- | :--- | :--- |
| **Model Antarmuka** | *Single-Screen* (GoFood) vs *Multi-Step* (GrabFood) | 2 Aplikasi per Partisipan | Prototipe Interaktif Figma |
| **Metrik Kognitif** | **Time on Task (ToT)** & Frekuensi *Error Rate* | Diukur langsung lewat observasi | **Analisis Detikan Video Rekaman** |
| **Replikasi Data** | 35 Responden Mahasiswa (Gen Z) | Total 70 data poin interaksi utuh | Eksportasi Log Google Form & MP4 |

---

## 4. Hasil Kalibrasi Awal (Pre-Test/Smoke Test)

Sebelum pengujian penuh terhadap 35 responden dijalankan, dilakukan sesi uji coba awal (*pre-test*) kepada 2 responden untuk menguji efektivitas perhitungan detikan untuk metrik *Time on Task*:

- **Temuan Iterasi Pertama:** Jika perekaman layar digabung dari awal penjelasan instruksi, peneliti kesulitan memisahkan mana waktu berpikir responden membaca teks tugas dan mana waktu interaksi riil di aplikasi. Hasil *Time on Task* menjadi tidak objektif.
- **Perbaikan Prosedur:** Penanda waktu awal (*ToT Start*) baru dihitung tepat pada detik saat responden melakukan sentuhan/klik pertama pada elemen prototipe, dan waktu akhir (*ToT End*) dihitung tepat pada detik saat tombol konfirmasi final "Pesan" selesai ditekan.
- **Hasil Iterasi Kedua:** Penentuan durasi *Time on Task* menjadi sangat presisi (murni merekam efisiensi kognitif user di dalam sistem). Prosedur perekaman ini dinyatakan valid untuk diaplikasikan ke seluruh responden.

---

## 5. Hasil Pengumpulan Data Penuh (35 Responden)

Seluruh rangkaian pengujian terhadap 35 partisipan mahasiswa Generasi Z (termasuk rekan-rekan dari kelas 3IKRA) berhasil diselesaikan tanpa ada berkas video yang rusak (*zero corrupted video file*).

- **Volume Data Terhimpun:** Didapatkan 46 video rekaman alur (17 GoFood, 18 GrabFood) yang kemudian ditonton ulang untuk dicatat durasi detiknya ke dalam file `04-data/time_on_task.csv`, serta 46 entri jawaban kuesioner SUS di file `04-data/kuesioner_sus.csv`.
- **Kondisi Awal Pengujian:** Responden diberikan jeda istirahat ringan (*distractor task*) selama 2 menit di antara pergantian aplikasi agar memori jangka pendek dari alur aplikasi pertama tidak memengaruhi kecepatan pengerjaan (*Time on Task*) di aplikasi kedua.
- **Kesiapan Tahap Lanjutan:** Basis data angka detikan *Time on Task* dari 35 responden ini telah dikunci (*freeze*) dan siap masuk ke pemrosesan analisis statistik (mencari nilai rata-rata *mean* dan uji signifikansi) pada Tahap 4.

---

## 6. Catatan Lingkungan Pengujian

- **Konsistensi Perangkat Perekam:** Aplikasi perekam layar disetel pada resolusi dan *frame rate* yang sama (1080p @30fps) di semua perangkat uji guna memastikan pergerakan detik saat di-pause atau di-review oleh peneliti berjalan konstan dan adil.
- **Isolasi Gangguan:** Selama proses perekaman layar, notifikasi pesan masuk, panggilan, atau *pop-up* sistem pada ponsel dinonaktifkan (*Do Not Disturb* mode) agar tidak mengalihkan perhatian kognitif responden ataupun mengganggu jalannya perhitungan *Time on Task* responden.