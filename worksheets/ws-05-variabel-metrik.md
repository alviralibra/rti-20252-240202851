# WS-05: Variabel & Metrik

> **Bab 5 — Metric, Measurement & Data**

---

## Ringkasan Materi

### Measurement Alignment Model

Setiap pengukuran yang valid harus bisa ditelusuri melalui rantai ini tanpa lompatan logis:

```
Problem → Concept → Variable → Metric → Data → Result
```

### Operationalization = Keputusan Desain

Menerjemahkan konsep abstrak menjadi variabel terukur bukan proses mekanis. "Code quality" yang diukur via SonarQube code smells membawa asumsi implisit. Setiap operasionalisasi harus didokumentasikan dan dijustifikasi.

### Empat Tipe Data (NOIR)

| Tipe | Ciri | Contoh | Operasi Valid |
|------|------|--------|---------------|
| **Nominal** | Kategori, tanpa urutan | Jenis algoritma (RF, SVM, CNN) | Modus, chi-square |
| **Ordinal** | Urutan, interval tidak sama | Skala Likert (1-5) | Median, Spearman |
| **Interval** | Jarak bermakna, tanpa nol absolut | Suhu Celsius | Mean, Pearson, t-test |
| **Ratio** | Jarak bermakna + nol absolut | Waktu eksekusi (ms) | Semua operasi |

Tipe data menentukan uji statistik yang valid. Kebanyakan metrik performa TI = ratio; persepsi pengguna = ordinal.

### Kriteria Pemilihan Metrik

- **Representative** — Mewakili konsep yang diteliti
- **Sensitive** — Cukup peka menangkap perbedaan bermakna (hindari ceiling effect)
- **Feasible** — Bisa dikumpulkan dalam batasan waktu dan biaya

### Pre-registration

Metrik harus ditentukan **sebelum** eksperimen. Memilih metrik setelah melihat data = **p-hacking**. Metrik tambahan yang ditemukan kemudian dilaporkan sebagai *exploratory*, bukan *confirmatory*.

### Primary vs Secondary Metric

- **Primary Metric** — Langsung terikat ke hipotesis, menentukan kesimpulan
- **Secondary Metric** — Pendukung, dilaporkan di samping primary; statusnya suplementer

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Pemilihan metrik | Berdasarkan kebiasaan/tool yang ada | Berdasarkan construct validity |
| Anomali | Dihapus untuk laporan bersih | Diinvestigasi — bisa jadi temuan |
| Kapan dipilih | Setelah sistem jadi (monitoring) | Sebelum eksperimen (by design) |

### Istilah Penting

- **Operationalization** — Transformasi konsep abstrak menjadi variabel terukur
- **Construct Validity** — Sejauh mana pengukuran benar-benar mengukur konsep yang dimaksud
- **Measurement Scale** — Klasifikasi data (NOIR) yang menentukan analisis valid
- **Multi-metric Evaluation** — Menggunakan beberapa metrik untuk menangkap konsep kompleks

---

## Template A.5 — Definisi Variabel, Metrik & Justifikasi

```
VARIABLE & METRIC DEFINITION

**Research Question:**
Bagaimana perbandingan efisiensi kognitif (Time on Task) dan kepuasan pengguna (SUS) antara alur checkout Single-Screen (GoFood) dan Multi-Step (GrabFood) pada generasi Z?

| Variabel | Tipe | Konsep | Metrik | Skala | Satuan | Cara Mengukur | Justifikasi |
|----------|------|--------|--------|-------|--------|---------------|-------------|
| User Flow Design | IV | Strategi penyajian informasi di layar | Tipe Alur (Single vs Multi) | Nominal | - | Observasi struktur halaman checkout Gojek & Grab | Variabel bebas yang dimanipulasi untuk melihat perbedaan hasil. |
| Cognitive Efficiency | DV | Kecepatan proses berpikir & bertindak | Time on Task | Ratio | Detik | Rekaman layar dari klik keranjang sampai tombol bayar | Indikator objektif paling valid untuk mengukur efisiensi sistem. |
| Internet Stability | CV | Kecepatan transmisi data | Kecepatan Bandwidth | Ratio | Mbps | Melakukan Speedtest sebelum eksperimen dimulai | Memastikan perbedaan waktu bukan karena loading aplikasi yang lambat. |

Alignment Check:
  RQ → Concept → Variable → Metric → Data → Result
  [X] Setiap langkah terdokumentasi
  [X] Tidak ada "lompatan logis"
  [X] Metrik mengukur apa yang dimaksud (construct validity)
```

---

## Latihan 1 — Operationalization Chain

Gunakan RQ dari WS-04. Definisikan variabel dan metriknya.

**RQ:** Bagaimana perbandingan efisiensi kognitif berdasarkan metrik Time on Task dan skor SUS antara alur checkout GoFood (Single-Screen) dan GrabFood (Multi-Step) pada pengguna generasi Z di Indonesia?

| Variabel | Tipe | Konsep Abstrak | Metrik Konkret | Skala (NOIR) | Satuan |
|----------|------|----------------|----------------|--------------|--------|
| Model Alur | IV | Strategi Desain UI | Single-Screen vs Multi-Step | Nominal | — |
| Efisiensi & Kepuasan | DV | Performa & Persepsi | Time on Task & Skor SUS | Ratio & Ordinal | Detik & Skor |
| Koneksi Internet | CV | Stabilitas Sistem | Bandwidth Kecepatan | Ratio | Mbps |

**Apakah ada lompatan logis dalam rantai?** [ ] Ya / [X] Tidak
> Jika ya, di mana? —

---

## Latihan 2 — Evaluasi Metrik

Evaluasi metrik DV yang dipilih di Latihan 1 menggunakan 3 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Representative | 5 | Time on Task secara langsung mewakili konsep efisiensi kognitif dalam menyelesaikan tugas checkout. |
| Sensitive | 4 | Metrik ini sangat peka dalam menangkap perbedaan kecepatan navigasi sekecil apapun dalam satuan detik. |
| Feasible | 5 | Data sangat mudah dikumpulkan melalui fitur screen recording pada smartphone responden tanpa alat tambahan. |

**Apakah perlu secondary metric?** [X] Ya / [ ] Tidak
> Jika ya, apa dan mengapa? Analisis Temuan RTA (Retrospective Think Aloud), karena angka waktu saja tidak bisa menjelaskan alasan kualitatif mengapa pengguna mengalami hambatan di titik tertentu.

**Contoh kasus ceiling effect untuk metrik ini:**
Jika tugas yang diberikan terlalu sederhana (misal: hanya menekan satu tombol), semua responden akan menyelesaikannya dalam waktu yang hampir sama cepatnya, sehingga perbedaan efisiensi antar desain tidak akan terlihat.

---

## Latihan 3 — Data Quality Check

Bayangkan data yang akan dikumpulkan dari eksperimen. Evaluasi 4 dimensi kualitas data.

| Dimensi | Pertanyaan | Jawaban | Strategi Mitigasi |
|---------|-----------|---------|------------------|
| Completeness | Apakah semua data point terkumpul? | Ya | Memastikan setiap sesi dari 23 responden menghasilkan video rekaman yang utuh dan kuesioner SUS yang terisi lengkap sebelum sesi berakhir. |
| Consistency | Apakah ada kontradiksi internal? | Tidak | Menggunakan skenario tugas (Task Scenario) yang sama persis dan instruksi yang seragam untuk setiap responden. |
| Validity | Apakah benar-benar mengukur yang dimaksud? | Ya | Memulai penghitungan waktu (Time on Task) tepat saat responden masuk ke halaman checkout untuk menjaga fokus pengukuran pada alur kerja mikro. |
| Representativeness | Apakah sampel mewakili populasi target? | Ya | Melakukan screening ketat untuk memastikan 23 responden adalah pengguna aktif layanan food delivery yang masuk dalam kategori generasi Z. |

---

## Refleksi

> Mengapa memilih metrik setelah melihat data dianggap p-hacking? Apa bedanya dengan eksplorasi data yang sah?

**Jawaban:**
Memilih metrik setelah melihat data dianggap *p-hacking* karena peneliti cenderung melakukan manipulasi dengan hanya memilih variabel yang memberikan hasil signifikan (mendukung hipotesis) dan membuang data yang tidak mendukung agar penelitian terlihat "berhasil". Hal ini mencederai objektivitas dan kejujuran ilmiah. Perbedaannya dengan eksplorasi data yang sah adalah eksplorasi bertujuan untuk mencari wawasan atau pola baru dari data tanpa mengubah atau mengklaim hasil hipotesis utama yang sudah ditetapkan di awal eksperimen secara *pre-registered*.