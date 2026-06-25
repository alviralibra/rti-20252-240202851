# WS-12: Result Presentation & Visualization

> **Bab 12 — Penyajian Hasil & Visualisasi**

---

## Ringkasan Materi

### Data → Insight Model

```
Validated Data → Structured Presentation → Visualization → Pattern Recognition → Insight
```

Penyajian **mendahului** analisis. Tabel dan grafik membantu peneliti "melihat" data sebelum menghitung. Langsung ke uji statistik tanpa visualisasi berisiko kesimpulan yang secara teknis benar tapi kontekstual salah (Anscombe's Quartet, 1973).

### Tabel = Presisi, Grafik = Pola

Keduanya **saling melengkapi**:
- Tabel: angka presisi, self-contained (dipahami tanpa teks), sortable
- Grafik: pola visual, tren, perbandingan cepat

### Jenis Grafik Berdasarkan Tujuan

| Tujuan | Jenis Grafik |
|--------|-------------|
| Perbandingan antar-skenario | Bar chart (grouped/stacked) |
| Distribusi per-skenario | Box plot / violin plot |
| Tren temporal | Line chart |
| Korelasi dua variabel | Scatter plot |
| Proporsi (total = 100%) | Pie chart (hati-hati!) |

### Contoh Tabel Hasil yang Baik

| Model | Accuracy (%) | F1-Score (%) | Training Time (min) |
|-------|-------------|-------------|---------------------|
| BERT | 88.4 ± 1.2 | 87.1 ± 1.4 | 45.2 ± 3.1 |
| LSTM | 86.1 ± 1.8 | 84.5 ± 2.0 | 12.8 ± 1.2 |
| SVM | 82.3 ± 0.9 | 80.7 ± 1.1 | 0.3 ± 0.1 |

*N=10 per model. Mean ± std. Diurutkan berdasarkan Accuracy.*

### Visualization Bias — Yang Harus Dihindari

| Bias | Deskripsi | Dampak |
|------|----------|--------|
| Truncated axis | Y tidak dari 0 | Memperbesar perbedaan kecil |
| Inconsistent scale | Dua grafik skala beda | Perbandingan menyesatkan |
| Cherry-picked data | Hanya tampilkan yang "menang" | Selektif, tidak jujur |
| 3D effects | Efek 3D tanpa dimensi data ke-3 | Distorsi tanpa informasi |
| Missing error bar | Tidak ada variabilitas | Menyembunyikan ketidakpastian |

### Engineering vs Research Presentation

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan grafik | Dashboard monitoring | Mendukung argumen ilmiah |
| Informasi wajib | KPI, threshold | Mean, std, CI, N, p-value |
| Bias handling | Less critical | Wajib dihindari (peer-review) |

---

## Template A.12 — Result Presentation Plan

```
RESULT PRESENTATION PLAN

Research Question : Apakah terdapat perbedaan yang signifikan pada efisiensi durasi checkout dan tingkat kepuasan SUS antara GoFood dan GrabFood pada Gen Z?
Metrik Utama      : Durasi Checkout (detik) dan Skor SUS (0-100)

Tabel Hasil:
| Skenario | Metrik 1 (mean ± std) | Metrik 2 (mean ± std) | n |
|----------|----------------------|----------------------|---|
| GoFood   | 13.71 ± 1.51 detik   | 73.13 ± 12.38        | 35|
| GrabFood | 19.34 ± 1.94 detik   | 47.41 ± 8.16         | 35|

Visualisasi yang Direncanakan:
| # | Jenis Grafik | Pesan Utama | Metrik |
|---|-------------|-------------|--------|
| 1 | Bar chart + error bar | GoFood memiliki rata-rata durasi checkout yang lebih cepat secara signifikan dibandingkan GrabFood | Mean Durasi ± Std |
| 2 | Box plot | Distribusi sebaran nilai SUS GoFood secara konsisten berada di rentang yang lebih tinggi daripada GrabFood | Seluruh run Skor SUS |

Bias Check:
  [✓] Y-axis mulai dari 0 (atau dijustifikasi)
  [✓] Error bar/CI ditampilkan
  [✓] Semua data disertakan (tidak cherry-picked)
  [✓] Tidak menggunakan 3D tanpa alasan
```

---

## Latihan 1 — Tabel Hasil

Buat tabel hasil eksperimen Anda (boleh dengan data simulasi jika belum punya data riil).

| Skenario | Metrik 1 (mean ± std) | Metrik 2 (mean ± std) | n |
|----------|----------------------|----------------------|---|
| *Contoh: BERT-base* | *88.4 ± 1.2%* | *45.2 ± 3.1 min* | *10* |
| GoFood   | 13.71 ± 1.51 detik   | 73.13 ± 12.38        | 35 |
| GrabFood | 19.34 ± 1.94 detik   | 47.41 ± 8.16         | 35 |

**Checklist tabel:**
- [✓] Self-contained (judul jelas, satuan ada, N tercantum)
- [✓] Mean ± std (bukan single number)
- [✓] Diurutkan berdasarkan metrik utama
- [✓] Format konsisten di semua baris

---

## Latihan 2 — Rencana Visualisasi

Rencanakan 2-3 grafik untuk menyajikan data dari Latihan 1. Setiap grafik = satu pesan.

| # | Jenis Grafik | Pesan | Data yang Digunakan |
|---|-------------|-------|---------------------|
| 1 | Bar chart + error bar | GoFood memiliki rata-rata durasi checkout yang lebih cepat secara signifikan dibandingkan GrabFood | Mean durasi ± std |
| 2 | Box plot | Distribusi sebaran nilai kepuasan SUS GoFood secara konsisten berada di rentang yang lebih tinggi daripada GrabFood | Seluruh run Skor SUS |
| 3 | Scatter plot | Korelasi trade-off antara durasi checkout dengan total skor kepuasan SUS | Nilai Durasi vs Skor SUS |

---

## Latihan 3 — Bias Detection

Evaluasi visualisasi berikut untuk bias (skenario dari contoh):

**Skenario:** Metode A = 91.2%, Metode B = 90.8%. Bar chart dengan Y-axis mulai dari 90%.

| Pertanyaan | Jawaban |
|-----------|---------|
| Apakah Y-axis menyesatkan? | Contoh: Ya — A terlihat 2× B padahal beda 0.4% |
| Apakah error bar ditampilkan? | Tidak ditampilkan, sehingga variabilitas data dan ketidakpastian kedua metode menjadi tersembunyi. |
| Apakah semua kondisi ditampilkan? | Ya, semua kondisi (Metode A dan Metode B) sudah dicantumkan dalam grafik. |
| Apa solusinya? | Mengubah Y-axis agar dimulai dari angka 0% dan menambahkan error bar pada masing-masing bar chart untuk menunjukkan variabilitas data. |

**Evaluasi grafik Anda sendiri dari Latihan 2:**
- [✓] Semua bias check lulus
- [ ] Ada yang perlu diperbaiki: ____

---

## Refleksi

> Mengapa tabel dan grafik keduanya diperlukan — tidak cukup salah satu saja? Pernahkah Anda membuat grafik yang (tanpa sengaja) menyesatkan?

> Tabel dan grafik keduanya diperlukan karena saling melengkapi dalam penyajian ilmiah. Tabel menyediakan aspek presisi tingkat tinggi di mana pembaca bisa melihat nilai numerik eksak secara mendetail (akurasi data). Sementara itu, grafik memberikan pemahaman instan mengenai pola, tren, sebaran distribusi, dan perbandingan cepat antar-skenario yang sulit ditangkap secara visual jika hanya berupa deretan angka di dalam tabel.
> 
> Kelemahan visualisasi tanpa landasan pilar data quality bisa memicu bias. Pengalaman membuat grafik yang tidak sengaja menyesatkan adalah saat sumbu Y (Y-axis) terpotong otomatis oleh sistem pengolah grafik (*truncated axis*), sehingga perbedaan tipis antar-variabel terlihat sangat drastis dan melompat jauh, yang dapat mengecoh pembaca jika tidak diperiksa skala angkanya secara teliti.
