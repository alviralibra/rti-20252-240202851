# WS-09: Implementation & Environment

> **Bab 9 — Implementasi Riset & Kontrol Lingkungan**

---

## Ringkasan Materi

### Implementasi Riset ≠ Coding Biasa

Tujuan implementasi riset bukan membuat software yang berfungsi, melainkan membangun **instrumen pengukuran yang konsisten**. Setiap modul harus di-mapping ke variabel (dari Bab 6), parameter harus config-driven, dan logging aktif dari hari pertama.

### Reproducible Implementation Model

```
Design → Implementation → Environment Setup → Execution Consistency → Reproducibility → Trustworthy Result
```

Setiap transisi memiliki syarat:
- Design → Implementation: kode sesuai mapping variabel-ke-komponen
- Implementation → Environment: versi, dependency, seed, path, OS eksplisit
- Environment → Consistency: seed terkunci, urutan deterministik
- Consistency → Reproducibility: dokumentasi lengkap
- Reproducibility → Trust: siapa pun ikuti dokumentasi → hasil sama/serupa

### Repeatability vs Reproducibility

| Level | Peneliti | Environment | Hasil |
|-------|---------|-------------|-------|
| **Repeatability** | Sama | Sama | Sama persis |
| **Reproducibility** | Berbeda | Berbeda (ikuti docs) | Sama/serupa |

Capai **repeatability** dulu, baru **reproducibility**.

### Engineering vs Research Perspective

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan | Sistem berfungsi untuk user | Instrumen pengukuran konsisten |
| Dependency | Update ke terbaru | Lock di versi spesifik |
| Testing | Unit, integration, E2E | Repeatability test (run ulang → sama?) |
| Dokumentasi | User guide, API docs | Environment spec, execution steps, expected output |
| Config | Default masuk akal | Setiap parameter eksplisit & adjustable |

### Jebakan Kognitif

1. Menunda environment setup → bug sulit dilacak
2. Tidak pakai version control → hasil tidak bisa direkonstruksi
3. Menolak Docker/container → "di laptop saya bisa" saat review
4. 3× hasil sama ≠ repeatable (bisa cache/state tersimpan)

### Istilah Penting

- **Environment Specification** — Deskripsi lengkap: hardware, OS, runtime, library + versi, config, seed
- **Dependency** — Komponen eksternal yang harus di-lock versinya
- **Config-driven** — Parameter dieksternalisasi ke file konfigurasi, bukan hardcode

---

## Template A.9 — Dokumentasi Setup Eksperimen

```
# EXPERIMENT SETUP DOCUMENTATION

Hardware:
  CPU     : Perangkat heterogen (Smartphone milik masing-masing dari 35 responden)
  RAM     : Minimum 4 GB RAM pada perangkat responden
  GPU     : Standar Mobile GPU (Adreno / Mali / Apple GPU) pada perangkat responden
  Storage : Minimum sisa penyimpanan 2 GB untuk kelancaran aplikasi & screen recording

Software:
  OS        : Android OS (Versi 10 ke atas) dan iOS (Versi 15 ke atas)
  Runtime   : Gojek App (Fitur GoFood) & Grab App (Fitur GrabFood) versi stabil terbaru (Mei 2026)
  Framework : Screen Recorder bawaan perangkat / AZ Screen Recorder (untuk perekaman Time on Task)

Dependencies:
| Library | Version | Sumber | Hash/Checksum |
|---------|---------|--------|---------------|
| Gojek App | Versi Terbaru | Google Play / App Store | Official Release |
| Grab App  | Versi Terbaru | Google Play / App Store | Official Release |
| System Usability Scale (SUS) | 10-Item Instrument | Brooke (1996) | Standard Psychometric |

Konfigurasi:
  Config file     : Skenario Tugas Eksperimen Terstandardisasi (Task Scenario Document)
  Random seed     : Counterbalancing (Responden 1-17: GoFood -> GrabFood; Responden 18-35: GrabFood -> GoFood)
  Hyperparameters : Batas waktu maksimal penyelesaian tugas (Cut-off Time) = 180 detik per aplikasi

Reproducibility Check:
  [X] Dependency terdokumentasi (aplikasi Gojek & Grab versi terbaru di perangkat responden)
  [X] Seed ditetapkan di semua level (Urutan pengujian diatur ketat via Counterbalancing)
  [X] Config di version control (Skenario tugas dan kuesioner SUS distandardisasi via Google Form)
  [X] README instruksi reproduksi lengkap
```

---

## Latihan 1 — Environment Specification

Dokumentasikan environment untuk eksperimen Anda (boleh environment saat ini atau yang direncanakan).

| Komponen | Spesifikasi |
|----------|------------|
| CPU | AMD Ryzen 5 5500U (6 Cores, 12 Threads) / Heterogen (Smartphone Responden) |
| RAM | 8 GB DDR4 (Laptop Pengolah Data) / Minimum 4 GB RAM (Smartphone Responden) |
| GPU | AMD Radeon Graphics (Integrated) |
| OS | Windows 11 Home / Android OS (v10+) & iOS (v15+) |
| Runtime | IBM SPSS Statistics Base Runtime |
| Framework | IBM SPSS Statistics v26 |
| Random Seed | Counterbalancing (Urutan variasi pengerjaan tugas responden diatur manual: 17 responden GoFood -> GrabFood, 18 responden GrabFood -> GoFood) |

**Dependencies (minimal 5):**

| Library / Modul | Version | Alasan Dibutuhkan |
|---------|---------|-------------------|
| SPSS Data Editor | v26.0 Core | Modul utama untuk membuat variabel, menginput data mentah (*Time on Task* dalam detik, skor SUS), dan menstrukturkan data dari 35 responden. |
| Descriptive Statistics | v26.0 Built-in | Digunakan untuk menghitung nilai rata-rata (*mean*), standar deviasi, serta nilai minimum dan maksimum dari performa GoFood dan GrabFood. |
| Explore Analytics (Shapiro-Wilk) | v26.0 Built-in | Fitur wajib untuk menguji asumsi normalitas data. Jika data berdistribusi normal ($p > 0.05$), baru kita bisa lanjut ke uji-t parametrik. |
| Paired-Samples T-Test | v26.0 Built-in | Modul inti untuk menguji hipotesis komparatif. Fitur ini yang menghitung apakah perbedaan waktu *checkout* antara GoFood vs GrabFood signifikan secara statistik atau hanya kebetulan. |
| SPSS Chart Builder | v26.0 Built-in | Modul visualisasi data untuk membuat grafik *Boxplot* atau *Bar Chart* standar akademis guna menampilkan perbandingan skor SUS dan efisiensi waktu secara visual. |

---

## Latihan 2 — Repeatability Test Plan

Rancang tes repeatability sederhana: jalankan kode yang sama 3× di environment yang sama.

| Run | Seed / Kontrol | Metrik Utama | Hasil Sama? |
|-----|------|-------------|-------------|
| 1 | Counterbalancing Terstandar | Mean Time on Task & Skor Rata-rata SUS | — |
| 2 | Counterbalancing Terstandar | Mean Time on Task & Skor Rata-rata SUS | [X] Ya / [ ] Tidak |
| 3 | Counterbalancing Terstandar | Mean Time on Task & Skor Rata-rata SUS | [X] Ya / [ ] Tidak |

**Jika hasil berbeda, kemungkinan penyebab:**
> 1. Terjadi kesalahan manusia (*human error*) saat melakukan *input* atau *coding* ulang variabel data mentah responden ke dalam SPSS Data Editor di salah satu sesi *run*.
> 2. Adanya perbedaan dalam pemilihan opsi pembersihan data pencilan (*outliers*) atau penanganan data kosong (*missing values*) di antara ketiga pengujian tersebut.
> 3. Versi *patch* aplikasi SPSS yang digunakan berbeda atau tidak stabil, sehingga algoritma kalkulasi internalnya mengalami *glitch*.

**Checklist kontrol yang sudah diterapkan:**
- [X] Random seed di-set di semua level (Urutan pengerjaan tugas responden diatur konsisten lewat Counterbalancing)
- [X] Tidak ada background process yang mengganggu (Menutup aplikasi berat lain di laptop saat SPSS melakukan kalkulasi)
- [X] Cache dibersihkan antar-run (Memastikan *Output Window* SPSS di-reset atau dibersihkan sebelum pengujian ulang)
- [X] Config file yang sama untuk semua run (Menggunakan berkas dataset `.sav` dan skrip sintaksis SPSS yang sama persis di setiap *run*)

---

## Latihan 3 — README Eksperimen

Tulis README minimum untuk eksperimen Anda (6 komponen wajib).

```
# Judul Eksperimen: Analisis Usability dan Efisiensi Kognitif Proses Checkout pada Aplikasi GoFood dan GrabFood untuk Generasi Z

## 1. Environment
| Komponen | Spesifikasi |
|----------|------------|
| CPU | AMD Ryzen 5 5500U (6 Cores, 12 Threads) / Heterogen (Smartphone Responden) |
| RAM | 8 GB DDR4 (Laptop Pengolah Data) / Minimum 4 GB RAM (Smartphone Responden) |
| GPU | AMD Radeon Graphics (Integrated) |
| OS | Windows 11 Home / Android OS (v10+) & iOS (v15+) |
| Runtime | IBM SPSS Statistics Base Runtime |
| Framework | IBM SPSS Statistics v26 |
| Random Seed | Counterbalancing (Urutan pengerjaan tugas dibedakan manual: 17 responden GoFood -> GrabFood, 18 responden GrabFood -> GoFood) |

## 2. Installation
1. Siapkan laptop yang sudah ter-install perangkat lunak IBM SPSS Statistics (minimal versi 26).
2. Di sisi responden, pastikan aplikasi Gojek (fitur GoFood) dan Grab (fitur GrabFood) versi stabil terbaru sudah terpasang di smartphone masing-masing.
3. Siapkan aplikasi Screen Recorder bawaan smartphone atau pihak ketiga (seperti AZ Screen Recorder) untuk merekam jalannya eksperimen.

## 3. Data
* **Sumber Data:** Data primer yang diperoleh langsung dari hasil pengujian langsung (eksperimen mandiri) terhadap 35 responden Generasi Z.
* **Format Data:** * Data kualitatif/waktu: Rekaman video layar smartphone (.mp4) untuk menghitung *Time on Task*.
  * Data kuantitatif: Berkas kuesioner kuesioner psikometrik digital via Google Form (.xlsx / .csv) yang kemudian diimpor menjadi format dataset SPSS (.sav).
* **Ukuran Data:** 35 baris data responden dengan variabel utama berupa: `Waktu_GoFood`, `Waktu_GrabFood`, `Skor_SUS_GoFood`, dan `Skor_SUS_GrabFood`.

## 4. Execution
1. **Pengumpulan Data (Lapangan):** Intruksikan responden untuk membuka aplikasi rekam layar, lalu berikan dokumen skenario tugas untuk melakukan *checkout* makanan di GoFood dan GrabFood sesuai urutan metode *Counterbalancing*.
2. **Ekstraksi Waktu:** Analisis hasil rekaman video (.mp4) lalu catat durasi penyelesaian tugas dalam satuan detik (*Time on Task*).
3. **Analisis Statistik (SPSS):** * Buka aplikasi IBM SPSS Statistics -> Impor data ke SPSS Data Editor.
   * Jalankan uji normalitas: Pilih menu `Analyze` -> `Descriptive Statistics` -> `Explore` -> Centang `Normality plots with tests`.
   * Jalankan uji komparasi: Pilih menu `Analyze` -> `Compare Means` -> `Paired-Samples T-Test` -> Masukkan variabel GoFood dan GrabFood -> Klik `OK`.

## 5. Configuration
* **Berkas Konfigurasi:** Dokumen Skenario Tugas Terstandardisasi (Task Scenario) dan Kuesioner Evaluasi SUS di Google Form.
* **Parameter Kunci:**
  * Tingkat Signifikansi (alpha): 0.05 (Kepercayaan 95%).
  * Batas Waktu Maksimal (*Cut-off Time*): 180 detik per tugas alur *checkout*.
  * Aturan Penilaian SUS: Menggunakan rumus konversi standar skala Likert 1-5 ke skor total SUS skala 0-100 milik John Brooke (1996).

## 6. Expected Output
Output yang diharapkan berupa lembar keluaran dokumen statistik (*SPSS Output Window* dengan format `.spv` atau ekspor ke `.pdf` / `.docx`) yang berisi tabel-tabel utama:
1. **Table Paired Samples Statistics:** Menampilkan nilai rata-rata (*mean*) waktu *checkout* dan skor SUS untuk membandingkan mana aplikasi yang lebih efisien dan memuaskan.
2. **Tabel Paired Samples Test:** Menampilkan nilai *t-value*, derajat kebebasan (*df*), dan nilai signifikansi pada kolom **Sig. (2-tailed)**. Jika nilai pada kolom **Sig. (2-tailed)** menunjukkan angka di bawah 0,05, maka hipotesis penelitian diterima. Hal tersebut membuktikan bahwa terdapat perbedaan efisiensi kognitif (waktu checkout) yang signifikan secara statistik antara aplikasi GoFood dan GrabFood pada Generasi Z. Jika nilai p < 0.05, maka hipotesis diterima, yang berarti terdapat perbedaan efisiensi kognitif yang signifikan antara GoFood dan GrabFood.
```

---

## Refleksi

> Apakah eksperimen Anda saat ini bisa direproduksi oleh orang lain tanpa bantuan Anda? Komponen apa yang masih hilang?
Eksperimen ini bisa direproduksi oleh orang lain dengan bantuan dokumentasi tambahan berupa panduan ucapan lisan. Karena instruksi tugas diberikan secara langsung atau lisan (Live Briefing) kepada responden tanpa lembar skenario tertulis, peneliti lain membutuhkan teks transkrip ucapan (Script Briefing) yang sama agar instruksi yang diterima responden di luar sana tidak berbeda-beda dan tetap adil.

**Level saat ini:** [X] Repeatability / [ ] Reproducibility / [ ] Belum keduanya

**Komponen yang belum terdokumentasi:**
> 1. Teks panduan instruksi lisan (Briefing Script) yang berisi kalimat standar yang dibacakan saat menyuruh responden melakukan checkout di HP masing-masing.
> 2. Berkas tautan Google Form kosong untuk pengisian kuesioner SUS oleh responden.
> 3. Dataset mentah akhir berbasis SPSS (.sav) karena pengambilan data lapangan dan pengisian kuesioner baru direncanakan berjalan pada bulan Mei 2026 ini.
