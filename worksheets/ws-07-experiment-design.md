# WS-07: Experimental Design & Validity

> **Bab 7 — Experimental Design & Validity**

---

## Ringkasan Materi

### Correlation ≠ Causality

Kausalitas membutuhkan 3 syarat:
1. **Covariance** — X dan Y bergerak bersama
2. **Temporal precedence** — X berubah sebelum Y
3. **Elimination of alternatives** — Tidak ada faktor lain yang menjelaskan Y

Controlled experiment adalah satu-satunya metode yang bisa membuktikan kausalitas.

### Empat Jenis Validitas

| Jenis | Pertanyaan | Ancaman Umum |
|-------|-----------|-------------|
| **Internal** | Apakah hubungan IV→DV nyata? | Confounding variable, selection bias |
| **External** | Apakah bisa digeneralisasi? | Dataset terlalu spesifik |
| **Construct** | Apakah mengukur konsep yang benar? | Metrik tidak sesuai |
| **Conclusion** | Apakah kesimpulan statistik valid? | Sample size kecil, uji salah |

Internal dan external validity sering berkonflik: semakin terkontrol (internal kuat) → semakin artificial (external lemah).

### Tiga Tipe Eksperimen dalam Riset TI

| Tipe | Deskripsi | Kapan Digunakan |
|------|----------|----------------|
| **Comparison Study** | Metode A vs B pada kondisi identik | Membandingkan pendekatan berbeda |
| **Ablation Study** | Full system → lepas komponen satu per satu | Mengukur kontribusi tiap komponen |
| **Parameter Study** | Variasikan satu parameter, amati dampak | Uji sensitifitas/robustness |

### Fairness dalam Perbandingan

Perbandingan yang adil = **kondisi identik** untuk semua metode: dataset sama, preprocessing sama, tuning effort sebanding, environment sama, metrik sama.

Contoh tidak adil: Transformer (30 fitur tambahan + Bayesian optimization) vs RF (default params) → hasilnya misleading.

### Threats to Validity = Diidentifikasi Sebelum Eksperimen

Ancaman validitas harus diidentifikasi **sebelum** eksperimen dan mitigasinya dirancang sebagai bagian dari desain — bukan ditulis sebagai boilerplate setelah selesai.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan testing | Memastikan sistem memenuhi requirement | Membuktikan hubungan kausal antar variabel |
| Baseline | Versi sebelumnya (last release) | Metode tervalidasi dari literatur |
| Kegagalan | Bug → fix → release | H₀ tidak ditolak → tetap kontribusi ilmiah |
| Sukses | 100% test pass | Evidence valid — mendukung atau menolak hipotesis |

### Istilah Penting

- **Causality** — Hubungan sebab-akibat (covariance + temporal + elimination)
- **Controlled Experiment** — Ubah satu variabel, kontrol sisanya, amati efek
- **Fairness** — Semua metode diuji pada kondisi yang benar-benar identik
- **Threats to Validity** — Faktor yang bisa melemahkan kesimpulan jika tidak dimitigasi
- **Conclusion Validity** — Validitas statistik: power, sample size, uji yang tepat

---

## Template A.7 — Desain Eksperimen Lengkap

```
EXPERIMENT DESIGN

Research Question : Bagaimana perbandingan efisiensi kognitif alur checkout model Single-Screen (GoFood) dan Multi-Step (GrabFood) pada Generasi Z menggunakan metrik Time on Task dan System Usability Scale (SUS)?
Hypothesis        : Alur checkout model Single-Screen (GoFood) memiliki tingkat efisiensi kognitif (durasi Time on Task lebih cepat) dan skor kepuasan (SUS) yang lebih tinggi secara signifikan dibandingkan alur checkout model Multi-Step (GrabFood) pada responden Generasi Z.
Tipe Eksperimen   : [X] Comparison  [ ] Ablation  [ ] Parameter

Kondisi Eksperimen:
| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| Control | Pengujian usability menggunakan alur checkout model Single-Screen | GoFood (Single-Screen) | Skenario tugas belanja identik, rentang usia responden 18-26 tahun (Gen Z), koneksi internet stabil (>10 Mbps), tipe OS smartphone setara. |
| Treatment | Pengujian usability menggunakan alur checkout model Multi-Step | GrabFood (Multi-Step) | Skenario tugas belanja identik, rentang usia responden 18-26 tahun (Gen Z), koneksi internet stabil (>10 Mbps), tipe OS smartphone setara. |

Fairness Checklist:
  [X] Dataset identik untuk semua kondisi
  [X] Preprocessing setara
  [X] Tuning effort setara
  [X] Environment identik
  [X] Metrik evaluasi sama

Threat Analysis:
| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| Internal    | *Learning Effect*: Responden menyelesaikan tugas pada aplikasi kedua lebih cepat karena sudah mempelajari polanya dari aplikasi pertama. | Menerapkan teknik *counterbalancing* (sebagian responden memulai dengan GoFood terlebih dahulu, sebagian lainnya memulai dengan GrabFood). |
| External    | Demografi responden terlalu spesifik (hanya Generasi Z), sehingga hasil pengujian sulit digeneralisasi untuk kelompok usia lain (misal Lansia). | Membatasi ruang lingkup klaim penelitian secara eksplisit bahwa hasil studi ini hanya berlaku untuk kelompok demografis Generasi Z di Indonesia. |
| Construct   | Metrik *Time on Task* bias karena kendala teknis jaringan internet lambat (*system delay*), bukan karena hambatan efisiensi kognitif pengguna. | Melakukan pemotongan durasi waktu tunggu loading sistem (*trimming*) melalui analisis hasil rekaman layar (*screen recording*). |
| Conclusion  | Ukuran sampel responden terlalu kecil sehingga kekuatan uji statistik lemah (*low statistical power*) untuk menarik kesimpulan yang valid. | Menetapkan jumlah sampel (35 responden) untuk menjamin representasi data pengujian usability komparatif skala kecil. |

Statistical Plan:
  Uji statistik   : Paired t-test (jika data terdistribusi normal) atau Wilcoxon Signed-Rank Test (jika data tidak berdistribusi normal)
  Justifikasi      : Eksperimen membandingkan dua kondisi/perlakuan berbeda (GoFood vs GrabFood) pada kelompok subjek yang sama (paired/related samples).
  Alpha            : 0.05
  Effect size min  : Cohen's d >= 0.5 (efek berukuran sedang/medium)
```

---

## Latihan 1 — Desain Eksperimen

Susun desain eksperimen berdasarkan RQ, variabel, dan sistem dari WS-04 sampai WS-06.

**RQ:** Bagaimana perbandingan efisiensi kognitif alur checkout model Single-Screen (GoFood) dan Multi-Step (GrabFood) pada Generasi Z menggunakan metrik Time on Task dan System Usability Scale (SUS)?
**Tipe eksperimen:** [X] Comparison / [ ] Ablation / [ ] Parameter

| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| **Control** | Pengujian usability menggunakan alur checkout model Single-Screen sebagai baseline dasar. | GoFood (Single-Screen) | Skenario tugas belanja identik, rentang usia responden 18-26 tahun (Gen Z), koneksi internet stabil (>10 Mbps), tipe OS smartphone setara . |
| **Treatment** | Pengujian usability menggunakan alur checkout model Multi-Step sebagai perlakuan pembanding. | GrabFood (Multi-Step) | Skenario tugas belanja identik, rentang usia responden 18-26 tahun (Gen Z), koneksi internet stabil (>10 Mbps), tipe OS smartphone setara . |

---

## Latihan 2 — Fairness Checklist

Evaluasi apakah desain eksperimen di Latihan 1 sudah fair.

| Kriteria | Status | Detail |
|----------|--------|--------|
| **Dataset identik** | ✅ Terpenuhi | Skenario belanja yang diuji (pilihan menu makanan, jumlah porsi, hingga detail alamat pengiriman) dibuat persis sama di kedua aplikasi (GoFood dan GrabFood). |
| **Preprocessing setara** | ✅ Terpenuhi | Kedua aplikasi dipastikan sudah diperbarui ke versi stabil paling mutakhir dari Google Play Store / App Store, dan akun uji coba diposisikan dalam keadaan siap pakai (*logged-in*). |
| **Tuning effort setara** | ✅ Terpenuhi | Pengujian dilakukan menggunakan pengaturan bawaan (*default*) dari masing-masing aplikasi, tanpa memberikan perlakuan promo atau penyesuaian khusus yang bisa memicu bias visual. |
| **Environment identik** | ✅ Terpenuhi | Pengujian dilakukan di ruangan tenang yang sama secara tatap muka (*offline*), menggunakan jaringan Wi-Fi/seluler dengan kecepatan stabil setara (>10 Mbps), serta perangkat smartphone berspesifikasi seimbang. |
| **Metrik evaluasi sama** | ✅ Terpenuhi | Efisiensi kognitif diukur menggunakan satuan waktu yang sama (*Time on Task* dalam detik) dan tingkat kepuasan diukur menggunakan kuesioner kualitatif yang sama (skor numerik *System Usability Scale*). |

**Ada yang tidak fair?** [ ] Ya / [X] Tidak
> Jika ya, bagaimana cara memperbaikinya? Seluruh aspek pengujian telah dirancang secara seimbang agar perbandingan performa murni dipengaruhi oleh perbedaan alur antarmuka (*checkout*), bukan karena faktor eksternal lainnya.
---

## Latihan 3 — Threat Analysis

Identifikasi ancaman validitas untuk desain eksperimen ini.

| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| **Internal** | *Learning Effect*: Responden menyelesaikan tugas pada aplikasi kedua lebih cepat karena sudah mempelajari alur tugas dari aplikasi pertama. | Menerapkan teknik *counterbalancing* (sebagian responden memulai dengan GoFood terlebih dahulu, sebagian lainnya memulai dengan GrabFood). |
| **External** | Karakteristik responden yang terlalu homogen (hanya berfokus pada Generasi Z) membuat hasil riset ini sulit diterapkan pada kelompok usia lain (misal Lansia). | Membatasi ruang lingkup klaim penelitian secara eksplisit bahwa hasil dan kesimpulan studi ini hanya berlaku untuk kelompok Generasi Z. |
| **Construct** | Metrik *Time on Task* terganggu oleh waktu tunggu loading sistem/jaringan internet (*system delay*), sehingga tidak mencerminkan efisiensi kognitif murni responden. | Melakukan pemotongan (*trimming*) durasi waktu tunggu sistem melalui analisis hasil rekaman layar (*screen recording*) untuk mendapatkan waktu interaksi murni. |
| **Conclusion** | Jumlah responden yang terlalu sedikit membuat variansi data sangat tinggi dan hasil uji statistik kehilangan kekuatannya (*low statistical power*). | Menetapkan jumlah sampel  (35 responden) untuk memastikan data yang dikumpulkan memenuhi syarat analisis statistik deskriptif dan komparatif. |

**Ancaman mana yang paling sulit dimitigasi?** Internal (Learning Effect)
**Mengapa?**
> Karena memori manusia tidak bisa dihapus setelah melakukan pengujian pertama. Meskipun urutan pengujian aplikasi sudah diacak (*counterbalancing*), responden secara alami tetap memiliki gambaran mental tentang bagaimana cara menyelesaikan tugas belanja makanan pada percobaan kedua.

---

## Refleksi

> Sebuah paper melaporkan "metode kami mengalahkan semua baseline." Apa 3 pertanyaan pertama yang harus diajukan untuk mengevaluasi klaim ini?

**Jawaban:**
1. **Apakah perbandingannya sudah adil (*fairness*)?** Apakah metode yang diusulkan dan seluruh metode pembanding (*baseline*) diuji pada lingkungan, dataset, dan *tuning effort* (hyperparameter) yang benar-benar identik, ataukah metode *baseline* sengaja dijalankan dengan parameter bawaan (*default*) yang tidak optimal?
2. **Apakah peningkatan performa tersebut signifikan secara statistik?** Apakah paper menyertakan uji signifikansi statistik (seperti uji hipotesis *p-value* atau estimasi *effect size*) untuk membuktikan bahwa keunggulan tersebut nyata dan konsisten, bukan sekadar kebetulan atau variasi acak (*noise*) saat eksperimen?
3. **Bagaimana dengan ancaman terhadap validitas (*threats to validity*)?** Apakah ada bias internal tersembunyi—seperti kebocoran data (*data leakage*) antara data latih dan uji, atau manipulasi pemilihan sampel—yang secara tidak sengaja menguntungkan metode yang diusulkan oleh penulis?
