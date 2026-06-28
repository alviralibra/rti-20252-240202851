# WS-13: Data Preprocessing

> **Bab 13 — Preprocessing & Persiapan Data untuk Analisis**

---

## Ringkasan Materi

### Data Refinement Pipeline

```
Raw Data → Cleaning → Transformation → Normalization → Processed Data → Analysis Ready
```

Setiap tahap memiliki tujuan berbeda. **Preprocessing bukan langkah teknis biasa** — setiap keputusan preprocessing adalah keputusan riset yang bisa mengubah kesimpulan.

### Empat Prinsip Preprocessing

| Prinsip | Deskripsi |
|---------|----------|
| **Consistency** | Metode sama untuk data yang sama |
| **Transparency** | Setiap langkah terdokumentasi |
| **Reproducibility** | Orang lain bisa mengulang dengan hasil sama |
| **Minimal Distortion** | Ubah sesedikit mungkin; jika normalisasi tidak perlu, jangan lakukan |

### Cleaning Triad

| Masalah | Strategi | Risiko |
|---------|---------|--------|
| **Missing values** | | |
| — Listwise deletion | Missing < 5%, random | Data loss |
| — Mean/median imputation | Sedikit missing, dist. normal | Mengurangi variabilitas |
| — Model-based imputation | Banyak missing, pola sistematis | Introduces dependency |
| — Flag & separate | Missing karena alasan substantif | Kompleksitas analisis |
| **Duplikat** | Identifikasi → verifikasi → hapus | False positive (data mirip ≠ duplikat) |
| **Error format** | Standardisasi tipe, encoding | Kehilangan informasi saat konversi |

### Normalisasi — Kapan & Metode Mana

| Metode | Formula | Output | Sensitif Outlier? |
|--------|---------|--------|-------------------|
| Min-max | (x-min)/(max-min) | [0, 1] | Ya |
| Z-score | (x-mean)/std | Unbounded | Lebih robust |
| Robust scaling | (x-median)/IQR | Unbounded | Paling robust |

**Kunci:** Parameter normalisasi harus dihitung dari **training set saja** — bukan seluruh data. Pelanggaran = **data leakage**.

### Data Leakage Prevention

Data leakage terjadi ketika informasi dari test set "bocor" ke preprocessing:
- Normalisasi parameter dari seluruh dataset ← **SALAH**
- Cross-validation dilakukan sebelum split ← **SALAH**
- Feature selection menggunakan label test set ← **SALAH**

### Jebakan Kognitif

1. "Preprocessing cuma teknis — tidak perlu detail" → bisa ubah kesimpulan
2. "Lebih banyak preprocessing = lebih bersih = lebih baik" → over-processing distorsi data
3. "Normalisasi selalu diperlukan" → belum tentu, tergantung metode analisis
4. "Imputation sama untuk semua situasi" → strategi harus sesuai konteks

---

## Template A.13 — Preprocessing Documentation Log

```
PREPROCESSING LOG

Dataset           : Kuesioner SUS dan Tracking Durasi Checkout (GoFood vs GrabFood)
Jumlah data awal  : 74 responden (37 GoFood, 37 GrabFood)

Cleaning:
| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---------|-------------|------------|-------------|
| Missing | 0 kasus     | -          | Semua field kuesioner diset *required* di Google Form. |
| Duplikat| 2 kasus     | Identifikasi → Verifikasi → Hapus | Terjadi submisi ganda (double-click) oleh responden yang sama pada waktu bersisihan. |
| Error   | 2 kasus     | Pembersihan format waktu | Nilai durasi checkout tercatat dalam format menit (e.g., "1m 15s"), dikonversi penuh ke detik. |

Transformation:
| Transformasi | Variabel | Detail | Alasan |
|-------------|----------|--------|--------|
| Konversi Waktu | Durasi Checkout | Mengubah string "XXm YYs" menjadi total detik numerik | Memudahkan perhitungan statistik deskriptif (mean ± std). |

Normalization:
  Metode    : Tidak perlu normalisasi
  Alasan    : Variabel durasi berskala rasio (detik asli) dan skor SUS sudah memiliki standardisasi baku (skala 0-100).
  Parameter : (dihitung dari: seluruh data)

Leakage Check:
  [✓] Parameter normalisasi dari training set saja
  [✓] Tidak ada informasi test set dalam preprocessing
  [✓] Cross-validation dilakukan setelah split

Jumlah data akhir : 70 responden (35 GoFood, 35 GrabFood)
Script tersedia   : [✓] Ya → path: scripts/preprocessing.py | [ ] Belum
```

---

## Latihan 1 — Cleaning Plan

Periksa dataset Anda (atau dataset contoh) dan dokumentasikan masalah yang ditemukan.

| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---------|-------------|------------|-------------|
| *Contoh: Missing di kolom "label"* | *12 dari 500 (2.4%)* | *Listwise deletion* | *< 5%, distribusi random (MCAR)* |
| Data Duplikat (Double Submit) | 2 dari 74 (2.7%) | Menghapus baris duplikat data kuesioner | Responden tidak sengaja menekan tombol kirim dua kali secara beruntun |
| Error Format Waktu | 2 dari 74 (2.7%) | Parsing string format waktu ke total detik numerik | Standardisasi tipe data agar bisa diproses ke perhitungan nilai mean dan standar deviasi |

**Jumlah data sebelum cleaning:** 74
**Jumlah data setelah cleaning:** 70
**Persentase data yang hilang/berubah:** 5.41%

---

## Latihan 2 — Normalisasi Decision

Tentukan apakah data Anda perlu normalisasi, dan jika ya, metode apa yang tepat.

| Variabel | Range Asli | Distribusi | Outlier? | Metode Normalisasi | Alasan |
|----------|-----------|-----------|----------|-------------------|--------|
| *Contoh: response_time* | *0.1 – 45.2s* | *Right-skewed* | *Ya (45.2s)* | *Robust scaling* | *Ada outlier, perlu robust* |
| *Contoh: accuracy_score* | *0.72 – 0.95* | *Normal, narrow* | *Tidak* | *Tidak perlu* | *Sudah dalam [0,1], metode berbasis distance tidak digunakan* |
| Durasi Checkout | 10.5s – 24.1s | Relatif Normal | Tidak | Tidak perlu | Data menggunakan satuan baku tunggal (detik) dan rentang nilainya tidak jomplang secara ekstrem. |
| Skor SUS | 20 – 100 | Berkelompok | Tidak | Tidak perlu | Skor SUS sudah memiliki standardisasi skala global baku dari 0 hingga 100. |

**Apakah normalisasi diperlukan?** [ ] Ya / [✓] Tidak

**Justifikasi:**
> Normalisasi tidak diperlukan karena kedua variabel (Durasi Checkout dalam detik dan Skor SUS dalam rentang skala 0-100) sudah memiliki unit analisis dan interpretasi standar yang seragam untuk analisis komparatif (uji t atau pengujian hipotesis). Tidak ada perbedaan magnitudo skala antar-fitur yang jomplang secara ekstrem, serta tidak ada model Machine Learning berbasis jarak (seperti KNN atau SVM) yang digunakan dalam pengujian ini.

**Leakage check:**
- [✓] Parameter dihitung dari training set saja (N/A karena seluruh data dipakai langsung untuk uji statistik)
- [✓] Normalisasi diterapkan setelah train-test split

---

## Latihan 3 — Preprocessing Report

Buat ringkasan preprocessing lengkap — dokumentasi yang cukup bagi orang lain untuk mereplikasi.

```
PREPROCESSING SUMMARY

1. Dataset: Kuesioner SUS dan Tracking Durasi Checkout (GoFood vs GrabFood)
2. Data awal: 74 records, 3 features
3. Cleaning:
   - Missing values: 0 kasus, metode: Tidak ada (Semua field Google Form diatur wajib diisi)
   - Duplikat: 2 kasus, tindakan: Identifikasi baris kembar → Verifikasi timestamp → Hapus rekaman ganda
   - Error: 2 kasus, tindakan: Standardisasi penulisan teks catatan waktu ke bentuk detik numerik murni
4. Transformation: Konversi tipe data string berformat waktu (contoh: "1m 15s") menjadi nilai float/integer total detik
5. Normalisasi: Tidak perlu dilakukan normalisasi, parameter dari N/A (Seluruh data)
6. Data akhir: 70 records, 3 features
7. Leakage check: [✓] Lulus / [ ] Ada masalah
```

---

## Refleksi

> Apakah Anda pernah melakukan normalisasi "karena biasa dilakukan" tanpa mempertimbangkan apakah benar-benar diperlukan? Apa risiko over-preprocessing?

> Ya, pada awal-awal belajar analisis data, ada kecenderungan otomatis untuk menerapkan normalisasi (seperti Min-Max atau Z-score) hanya karena metode tersebut selalu ada di dalam tutorial atau *template code*, tanpa memeriksa karakteristik skala asli atau model analisis yang akan digunakan. 
> 
> Risiko dari *over-preprocessing* sangat fatal bagi integritas data. Terlalu banyak memanipulasi atau mengubah bentuk data asli dapat menyebabkan distorsi informasi, menghilangkan variabilitas alami yang berharga, mengaburkan interpretasi kontekstual data asli (misalnya, angka detik riil berubah menjadi nilai pecahan abstrak antar 0 dan 1), serta berpotensi memicu *data leakage* jika batasan pemisahan data tidak dijaga ketat. Alih-alih membuat data menjadi lebih "bersih", *over-preprocessing* justru menjauhkan kita dari realitas pola data yang sebenarnya.