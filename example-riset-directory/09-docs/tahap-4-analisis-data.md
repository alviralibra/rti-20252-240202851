# Tahap 4 — Analisis Data & Perhitungan Statistik

**Status:** Selesai — Uji t berpasangan (*Paired Samples T-Test*) atas data 35 responden (70 sesi uji silang) telah dijalankan di SPSS, dengan file luaran visualisasi siap pakai di `06-output/`
**Bergantung pada:** [tahap-3-pelaksanaan-eksperimen.md](tahap-3-pelaksanaan-eksperimen.md)
**Lokasi Skrip & Output:** [../05-kode/analysis](../05-kode/analysis) / `06-output/tables/`

---

## Tujuan

Mengolah data mentah durasi waktu *Time on Task* (ToT) hasil ekstraksi video rekaman layar beserta total skor kuesioner *System Usability Scale* (SUS) dari 35 responden menggunakan analisis statistik inferensial (Uji-t Berpasangan) untuk memvalidasi perbedaan signifikansi performa alur GoFood (*Single-Screen*) vs GrabFood (*Multi-Step*).

---

## Deliverable

- [x] Impor data mentah durasi rekaman video layar dan rekapitulasi Google Form ke lembar kerja analisis (`load_runs.py` / DataSet SPSS).
- [x] Perhitungan statistik deskriptif deskripsi data (*Mean*, *Standard Deviation*, *Std. Error Mean*) untuk kedua aplikasi (Screenshot 2026-06-28 181615.jpg).
- [x] Perhitungan nilai performa efisiensi waktu kognitif ($D_{perf}$) berdasarkan nilai *Mean* ril dari pengujian.
- [x] Analisis korelasi pasangan variabel (*Paired Samples Correlations*) untuk mengukur konsistensi pengerjaan responden (Screenshot 2026-06-28 181615.jpg).
- [x] Pengujian hipotesis komparatif melalui *Paired Samples T-Test* untuk metrik durasi dan kepuasan pengguna (Screenshot 2026-06-28 181630.png).
- [x] Ekstraksi 5 grafik visualisasi perbandingan (`06-output/figures/`) berdasarkan pemetaan distribusi nilai SPSS.

---

## Desain Rumus & Metodologi Statistik

### 1. Definisi Efisiensi Waktu ($D_{perf}$)
Menggunakan analogi persentase penundaan atau percepatan waktu transaksi bersih antara model bertahap (*Multi-Step*) terhadap model satu layar (*Single-Screen*) sebagai baseline:
$$D_{perf} = \frac{\text{Mean ToT}_{\text{GrabFood}} - \text{Mean ToT}_{\text{GoFood}}}{\text{Mean ToT}_{\text{GoFood}}} \times 100\%$$

### 2. Parameter Pengujian Hipotesis (Uji-t)
- **Variabel Pasangan 1:** Durasi Checkout GrabFood vs Durasi Checkout GoFood (satuan detik).
- **Variabel Pasangan 2:** Total Skor SUS GrabFood vs Total Skor SUS GoFood.
- **Tingkat Kepercayaan:** 95% ($\alpha = 0.05$).

---

## Hasil Analisis (Berdasarkan IBM SPSS Output)

### A. Statistik Deskriptif Variabel (*Paired Samples Statistics*)
Berdasarkan berkas data Screenshot 2026-06-28 181615.jpg, berikut adalah ringkasan parameter dasar dari 35 responden mahasiswa kelas 3IKRA:

| Pasangan Uji | Variabel Interaksi | Mean | N | Std. Deviation | Std. Error Mean |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Pair 1** | Durasi Checkout GrabFood (detik) | 19.54 | 35 | 1.945 | 0.329 |
| | Durasi Checkout GoFood (detik) | 13.71 | 35 | 1.506 | 0.255 |
| **Pair 2** | Total Skor SUS GrabFood | 47.423 | 35 | 8.2846 | 1.4004 |
| | Total Skor SUS GoFood | 73.137 | 35 | 11.2196 | 1.8965 |

### B. Korelasi Pasangan Variabel (*Paired Samples Correlations*)
Berdasarkan analisis korelasi pada berkas Screenshot 2026-06-28 181615.jpg:
- **Korelasi Durasi (Pair 1):** Diperoleh nilai koefisien korelasi sebesar **0.847** dengan nilai signifikansi **0.000**. Hal ini menunjukkan hubungan linier positif yang sangat kuat dan signifikan; responden yang secara alami lambat di aplikasi baseline juga cenderung mengalami perlambatan konstan di alur pembanding.
- **Korelasi Kepuasan SUS (Pair 2):** Diperoleh nilai koefisien korelasi sebesar **0.008** dengan nilai signifikansi **0.965** ($p > 0.05$). Menandakan perubahan penilaian subyektif skor kepuasan antar-aplikasi bersifat independen dan tidak dipengaruhi oleh urutan pengerjaan responden.

### C. Hasil Uji Signifikansi Parsial (*Paired Samples Test*)
Berdasarkan perhitungan komparasi pada berkas Screenshot 2026-06-28 181630.png, diperoleh kesimpulan statistik sebagai berikut:

#### 1. Analisis Komparasi Durasi Checkout (Pair 1)
- **Nilai Selisih Performa ($D_{perf}$):** 
  $$D_{perf} = \frac{19.54 - 13.71}{13.71} \times 100\% = \mathbf{+42.52\%}$$
- **Hasil Uji-t:** Nilai perbedaan rata-rata (*Mean Paired Differences*) adalah **5.829 detik** dengan $t(34) = 33.068$ dan nilai $p = 0.000$ (Sig. 2-tailed). 
- **Kesimpulan:** Karena $p < 0.05$, terdapat perbedaan durasi yang sangat signifikan. Alur *Multi-Step* (GrabFood) terbukti menimbulkan *overhead* penundaan waktu kognitif sebesar **42.52%** lebih lama dibandingkan alur *Single-Screen* (GoFood).

#### 2. Analisis Komparasi Kepuasan Usability SUS (Pair 2)
- **Nilai Perubahan Kepuasan ($D_{perf}$ SUS):**
  $$D_{perf} = \frac{47.423 - 73.137}{73.137} \times 100\% = \mathbf{-35.16\%}$$
- **Hasil Uji-t:** Nilai perbedaan rata-rata adalah **-25.7143** dengan $t(34) = -10.948$ dan nilai $p = 0.000$ (Sig. 2-tailed).
- **Kesimpulan:** Terdapat perbedaan skor kepuasan yang sangat signifikan. Model satu layar (GoFood) memperoleh penilaian rata-rata jauh lebih tinggi (**73.137**, Kategori: *Acceptable / Good*) dibandingkan alur bertahap GrabFood yang anjlok ke angka **47.423** (Kategori: *Not Acceptable / Poor*), mengalami degradasi tingkat kepuasan user sebesar **35.16%**.

---

## Visualisasi Grafik Hasil (`06-output/figures/`)

Seluruh visualisasi diproduksi otomatis oleh `charts.py` menggunakan sebaran parameter deviasi dari SPSS:
1. `fig_latency_p95.png`: Grafik batang rata-rata waktu pengerjaan tugas (*Time on Task*) yang menonjolkan batas efisiensi GoFood pada 13.71 detik vs GrabFood pada 19.54 detik (Screenshot 2026-06-28 181615.jpg).
2. `fig_dperf.png`: Grafik visualisasi persentase lonjakan beban interaksi waktu tambahan ($D_{perf} = +42.52\%$) pada model bertahap (Screenshot 2026-06-28 181630.png).
3. `fig_postgres_cpu.png`: Diagram kotak (*Box Plot*) visualisasi sebaran skor kepuasan SUS antara GoFood (Mean: 73.137) vs GrabFood (Mean: 47.423) untuk memperlihatkan rentang deviasi data (Screenshot 2026-06-28 181615.jpg).

---

## Catatan Penting untuk Bab Pembahasan (Tahap 5)

* **Validitas Empiris Beban Kognitif:** Dengan nilai $t$ hitung durasi yang sangat besar ($33.068$), riset ini sukses membuktikan bahwa pemecahan halaman transaksi ke dalam skema *Multi-Step* justru menjadi *bottleneck* utama yang membebani memori jangka pendek pengguna Gen Z.
* **Paradoks Kerapian Navigasi:** Meskipun niat awal model bertahap adalah menyederhanakan interface, nilai rata-rata skor SUS yang jatuh di bawah batas kelayakan baku ($47.423 < 68.0$) mengonfirmasi bahwa responden menganggap perpindahan halaman yang berulang merupakan sebuah hambatan proses transaksi yang mengesalkan.