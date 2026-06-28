# WS-14: Analysis, Interpretation & Failure Analysis

> **Bab 14 — Analisis Data, Interpretasi & Failure Analysis**

---

## Ringkasan Materi

### Data → Knowledge Model

```
Data → Analysis → Interpretation → Explanation → Knowledge
```

Tiga level yang berbeda:
- **Analysis** — "Apa yang terjadi?" (deskriptif + inferensial)
- **Interpretation** — "Apa artinya?" (konteks RQ + literatur)
- **Failure Analysis** — "Mengapa tidak berhasil?" (boundary conditions)

### Beyond p-value

**Statistical significance ≠ practical significance.** Selalu laporkan:
1. p-value (signifikansi statistik)
2. Effect size (besarnya efek)
3. Confidence interval (rentang ketidakpastian)

| Effect Size (Cohen's d) | Interpretasi |
|-------------------------|-------------|
| < 0.2 | Small |
| 0.2 – 0.8 | Medium |
| > 0.8 | Large |

### Pemilihan Uji Statistik

| Kondisi | Uji yang Tepat |
|---------|---------------|
| 2 grup, normal, paired | Paired t-test |
| 2 grup, non-normal | Wilcoxon signed-rank |
| > 2 grup, normal | One-way ANOVA + post-hoc |
| > 2 grup, non-normal | Kruskal-Wallis + post-hoc |
| 2 variabel kontinu | Pearson (normal) / Spearman (rank) |

### Failure Analysis as Contribution

Hipotesis yang ditolak adalah **temuan yang berharga**:

| Dataset | New (F1) | Baseline (F1) | p-value | Cohen's d |
|---------|---------|--------------|---------|-----------|
| DS-1 (small, clean) | 94.2±1.1 | 89.3±1.5 | <0.001 | **3.7** |
| DS-4 (medium, noisy) | 78.3±3.2 | 82.1±2.8 | 0.008 | **-1.3** |
| DS-5 (large, noisy) | 71.6±4.1 | 80.5±3.0 | <0.001 | **-2.5** |

**Insight:** Metode baru unggul di data bersih tapi gagal di data noisy → asumsi Gaussian dilanggar → **boundary condition** ditemukan → hybrid approach direkomendasikan.

**Partial failure + deep analysis = kontribusi lebih kaya daripada full success tanpa analisis.**

### Limitation Types

| Jenis | Contoh |
|-------|--------|
| Internal validity | Confounders yang tidak dikontrol |
| External validity | Generalisasi ke domain lain |
| Construct validity | Metrik mengukur apa yang dimaksud? |
| Statistical limitation | Sample size, asumsi distribusi |

### Jebakan Kognitif

1. "Signifikan statistik = penting secara praktis" → cek effect size
2. "Hipotesis tidak didukung → cari sudut baru" → p-hacking
3. "Kegagalan tidak perlu dilaporkan detail" → missed insight
4. "Limitasi cukup disebutkan, tidak perlu dianalisis" → kedalaman hilang

---

## Template A.14 — Analysis & Interpretation Report

```
ANALYSIS & INTERPRETATION

1. Statistik Deskriptif:
   | Skenario | Mean | Std | Median | Min | Max | n |
   |----------|------|-----|--------|-----|-----|---|
   | Durasi Checkout Grab | 19.54 | 1.945 | 19.50 | 15.50 | 23.40 | 35 |
   | Durasi Checkout GoFood | 13.71 | 1.506 | 13.50 | 11.20 | 16.80 | 35 |
   | Total Skor SUS Grab | 47.42 | 8.285 | 47.50 | 30.00 | 65.00 | 35 |
   | Total Skor SUS GoFood | 73.14 | 11.220 | 75.00 | 50.00 | 95.00 | 35 |

2. Uji Hipotesis:
   Uji yang digunakan  : Paired Samples t-test
   Justifikasi          : Membandingkan rata-rata dari dua kondisi interaksi yang berbeda (Grab vs GoFood) pada kelompok subjek pengguna Gen Z yang sama (data berpasangan).
   Hasil: 
   - Durasi Checkout : p = .000 (p < 0.001), effect size (Cohen's d) = 3.82
   - Total Skor SUS  : p = .000 (p < 0.001), effect size (Cohen's d) = -2.60
   CI 95%               : [5.470, 6.187] (Durasi) dan [-30.487, -20.941] (Skor SUS)

3. Keputusan:
   [✓] H₀ ditolak → H₁ diterima
   [ ] H₀ tidak ditolak

4. Interpretasi:
   Hubungan ke RQ       : Terbukti secara statistik bahwa terdapat perbedaan efisiensi kognitif (durasi) dan tingkat kepuasan (skor SUS) yang signifikan antara proses checkout GoFood dan GrabFood pada Gen Z.
   Practical significance: Proses checkout GoFood secara riil ~5.83 detik lebih cepat daripada GrabFood. Di sisi lain, pengalaman pengguna (UX) GoFood masuk kategori "Good/Acceptable" (73.14), sementara GrabFood tertinggal di kategori "Poor/Not Acceptable" (47.42).
   Perbandingan literatur: Hasil ini selaras dengan Hick's Law dan Aesthetic-Usability Effect, di mana minimalisasi langkah interaksi dan kejelasan visual pada GoFood berhasil memangkas *cognitive load* pengguna dibandingkan alur GrabFood.

5. Limitation:
   | Jenis | Ancaman | Dampak | Mitigasi |
   |-------|---------|--------|----------|
   | External Validity | Karakteristik sampel homogen (mahasiswa IT) | Pola pengujian berisiko kurang merepresentasikan Gen Z non-teknis | Menambah variasi sebaran latar belakang responden non-IT pada riset mendatang |
   | Construct Validity | Pengukuran durasi manual via screen recording | Risiko deviasi minor hitungan waktu akibat delay respons manusia | Menggunakan tools *event-logger* otomatis yang tertanam di sistem |

6. Failure Analysis (jika H₀ tidak ditolak):
   Penyebab potensial  : N/A (Hipotesis didukung penuh dan terbukti signifikan)
   Boundary condition   : N/A
   Insight              : N/A
```

---

## Latihan 1 — Pemilihan Uji Statistik

## Latihan 1 — Pemilihan Uji Statistik

Tentukan uji statistik yang tepat untuk eksperimen Anda.

| Pertanyaan | Jawaban |
|-----------|---------|
| Berapa grup yang dibandingkan? | 2 kondisi aplikasi (GoFood vs GrabFood) |
| Apakah data berpasangan (paired)? | Ya (Responden yang sama menguji kedua aplikasi) |
| Apakah distribusi normal? (uji normalitas) | Ya (Hasil uji normalitas SPSS menunjukkan data berdistribusi normal) |
| **Uji yang dipilih:** | Paired Samples t-test |
| **Justifikasi:** | Digunakan karena penelitian membandingkan nilai rata-rata dari dua variabel/kondisi yang saling berhubungan (berpasangan) pada satu kelompok subjek yang sama. |

**Effect size yang akan dilaporkan:** [✓] Cohen's d / [ ] Eta-squared / [ ] Lainnya: ____

---

## Latihan 2 — Interpretasi Hasil

Gunakan data berikut (atau data riil Anda) untuk berlatih interpretasi.

**Data:**
| Kondisi Aplikasi / Metrik | Mean ± Std | n |
|---------------------------|------------|---|
| Durasi Checkout Grab | 19.54 ± 1.95s | 35 |
| Durasi Checkout GoFood | 13.71 ± 1.51s | 35 |
| Total Skor SUS Grab | 47.42 ± 8.28 | 35 |
| Total Skor SUS GoFood | 73.14 ± 11.22 | 35 |

p < 0.001, Cohen's d = 3.82 (Durasi) & -2.60 (SUS), CI 95% = [5.47, 6.19] & [-30.49, -20.94]

| Aspek | Interpretasi |
|-------|-------------|
| Signifikansi statistik | *p < 0.001 → Kedua metrik (Durasi dan SUS) menunjukkan perbedaan yang sangat signifikan secara statistik pada α=0.05.* |
| Effect size | *d = 3.82 (Durasi) & -2.60 (SUS) → Keduanya memiliki efek yang sangat besar (ekstrem).* |
| Practical significance | Secara praktis, GoFood memotong waktu transaksi ~5.83 detik lebih cepat. Dari sisi kepuasan, GoFood masuk kategori "Good/Acceptable" (73.14), sedangkan GrabFood berada di kategori "Poor/Not Acceptable" (47.42), menandakan masalah UX yang nyata pada alur GrabFood. |
| Hubungan ke RQ | Menjawab Research Question (RQ) secara menyeluruh bahwa terdapat perbedaan efisiensi kognitif (durasi) sekaligus kenyamanan aplikasi (skor SUS) yang masif antara kedua platform pada pengguna Gen Z. |
| Perbandingan literatur | Hasil ini selaras dengan *Hick's Law* dan *Aesthetic-Usability Effect*, di mana pengurangan langkah pemrosesan informasi (durasi lebih pendek) berkorelasi positif dengan tingginya persepsi kegunaan sistem (skor SUS lebih tinggi). |

---

## Latihan 3 — Failure Analysis

Latih kemampuan failure analysis: hipotesis TIDAK didukung. Apa yang bisa dipelajari?

**Skenario:** Metode baru Anda mendapat F1 = 83.2%, baseline = 84.7%. p = 0.12 (tidak signifikan).

| Pertanyaan | Jawaban |
|-----------|---------|
| Apakah ini "gagal"? | Bukan gagal total — hipotesis tidak terdukung adalah temuan eksperimental yang valid dan objektif, serta tetap dihitung sebagai kontribusi ilmiah ilmiah. |
| Kemungkinan penyebab? | Arsitektur metode baru memperkenalkan parameter yang terlalu kompleks (*over-parameterization*), memicu fenomena *overfitting* ringan pada dataset pengujian yang digunakan. |
| Boundary condition? | Metode baru ini kurang optimal jika diimplementasikan pada dataset berskala kecil dengan sebaran fitur yang padat; metode baseline terbukti jauh lebih kokoh (*robust*). |
| Insight yang bisa diambil? | Terdapat *trade-off* kritis antara kompleksitas arsitektur model dengan volume data latih. Penyederhanaan komponen regularisasi atau beralih ke pendekatan hibrida sangat direkomendasikan. |
| Apakah layak dilaporkan? Mengapa? | Ya, sangat layak — Pelaporan *negative result* dan batas kondisi operasional (*boundary condition*) membantu komunitas peneliti menghindari replikasi galat yang sama dan memberikan arahan optimasi yang benar. |

**Limitation terkait:**
| Jenis | Ancaman | Dampak |
|-------|---------|--------|
| Statistical | Hanya menjalankan 5 kali *running* per skenario pengujian | *Statistical power* menjadi rendah dan rentang ketidakpastian analisis melebar |
| External Validity | Pengujian terbatas pada satu repositori dataset yang homogen | Generalisasi model baru pada variasi domain data lain belum teruji dengan kuat |
| Construct Validity | Evaluasi performa hanya bersandar penuh pada metrik F1-score | Dimensi efisiensi penggunaan memori dan beban komputasi belum terukur secara berimbang |

---

## Refleksi

> Apakah "failure" dalam riset benar-benar gagal, atau justru kontribusi? Bagaimana failure analysis mengubah cara Anda melihat hasil negatif?

> *Failure* atau kegagalan dalam riset—seperti hipotesis yang ditolak atau metode baru yang performanya di bawah *baseline*—bukanlah sebuah kegagalan total, melainkan sebuah kontribusi ilmiah yang sangat berharga. Dalam dunia penelitian, mengetahui "apa yang tidak berhasil" dan "di mana batas kemampuan suatu metode" (*boundary conditions*) memiliki derajat kepentingan yang sama dengan menemukan keberhasilan. 
> 
> *Failure analysis* mengubah cara pandang terhadap hasil negatif dari yang semula dianggap sebagai "produk cacat/salah" menjadi sebuah *insight* objektif. Analisis kegagalan yang mendalam memaksa peneliti untuk membedah anomali data, menguji kembali asumsi dasar, serta memetakan batasan sistem secara jujur. Melaporkan hasil negatif beserta analisisnya justru menyelamatkan peneliti lain dari jebakan duplikasi riset yang sia-sia, sekaligus membuka jalan bagi pengembangan pendekatan hibrida atau solusi baru yang lebih adaptif di masa depan.