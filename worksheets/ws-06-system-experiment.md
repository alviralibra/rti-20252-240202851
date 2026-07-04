# WS-06: System-Experiment Mapping

> **Bab 6 — System Design sebagai Experimental Artifact**

---

## Ringkasan Materi

### Sistem = Instrumen Pengujian, Bukan Produk

Seorang engineer bertanya "apakah sistem bekerja?" — seorang peneliti bertanya "apa yang bisa dibuktikan sistem ini?" Sistem dalam riset adalah **artifact** — objek yang sengaja dibuat untuk menguji klaim spesifik.

### System as Experiment Model

```
RQ → Variable → System Component → Experimental Setup → Output
```

Setiap komponen sistem harus bisa ditelusuri ke variabel riset (top-down), dan setiap pengukuran harus menjawab RQ (bottom-up).

### Mapping Variabel ke Komponen

| Tipe Variabel | Peran di Sistem | Contoh |
|---------------|----------------|--------|
| **IV** (Independent) | Modul yang bisa di-toggle/swap | Algoritma A vs B |
| **DV** (Dependent) | Modul pengukuran | Logger, metrics collector |
| **CV** (Control) | Config yang dikunci | Dataset, parameter tetap |

Jika variabel tidak bisa di-map ke komponen apapun → arsitektur perlu didesain ulang.

### 4 Prinsip Desain Eksperimental

| Prinsip | Pertanyaan Kunci |
|---------|-----------------|
| **Traceability** | Komponen ini melayani variabel yang mana? |
| **Modularity** | Bisakah IV diubah tanpa memengaruhi yang lain? |
| **Controllability** | Apakah CV dieksternalisasi ke config file? |
| **Measurability** | Apakah sistem otomatis menghasilkan data yang dibutuhkan? |

### Variable Isolation melalui Arsitektur

- **Modular architecture** — Pisahkan berdasarkan variabel
- **Configuration-driven** — Ubah config (YAML/JSON), bukan code
- **Feature toggles** — On/off flag untuk ablation study

  Contoh config YAML dengan feature toggles:
  ```yaml
  model:
    type: cnn          # IV: ganti "rf" untuk kondisi baseline
  features:
    use_temporal: true  # toggle komponen temporal
    use_normalization: true  # toggle preprocessing
  experiment:
    seed: 42
    runs: 5
  ```
  Dengan pendekatan ini, berbeda kondisi eksperimen = berbeda satu baris config, **tanpa mengubah kode**.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan sistem | Memenuhi kebutuhan user | Menguji hipotesis, menghasilkan bukti |
| Arsitektur | Optimasi performa & skalabilitas | Optimasi isolasi variabel & reprodusibilitas |
| Konfigurasi | Sering hardcoded | Dieksternalisasi ke config file |
| Fitur tambahan | Menambah nilai user | Menambah noise jika tidak terkait RQ |

### Istilah Penting

- **Artifact** — Objek yang sengaja dibuat untuk memecahkan masalah atau menguji proposisi
- **Traceability** — Kemampuan menelusuri hubungan RQ → variabel → komponen → output
- **Variable Isolation** — Mengubah hanya satu variabel sambil menahan yang lain konstan
- **Ablation Study** — Menguji kontribusi tiap komponen dengan melepasnya satu per satu
- **Configuration-driven Execution** — Semua parameter di config file, bukan hardcoded

---

## Template A.6 — Mapping RQ ke Arsitektur Sistem

```
SYSTEM-EXPERIMENT MAPPING

Research Question: Bagaimana perbandingan efisiensi kognitif alur checkout model Single-Screen (GoFood) dan Multi-Step (GrabFood) pada Generasi Z menggunakan metrik Time on Task dan System Usability Scale (SUS)?

Variable → Component Mapping:
| Variabel | Tipe | Komponen Sistem | Cara Manipulasi/Pengukuran |
|----------|------|-----------------|---------------------------|
| Model Alur Checkout (Single-Screen vs Multi-Step) | IV   | Antarmuka Aplikasi (GoFood & GrabFood) | Meminta responden menyelesaikan tugas transaksi pada masing-masing jenis alur antarmuka secara bergantian |
| Efisiensi Kognitif dan Kepuasan Pengguna | DV   | Instrumen Evaluasi (Screen Recorder & Kuesioner SUS) | Mengukur durasi pengerjaan tugas (Time on Task dalam detik) via rekaman video dan menghitung skor SUS pasca-tes |
| Lingkungan Pengujian dan Karakteristik Responden | CV   | Protokol Eksperimen & Spesifikasi Device | Menyamakan instruksi tugas, menyamakan rentang usia responden (Gen Z), serta mengunci jenis koneksi internet dan OS smartphone |

4 Prinsip Desain:
  [X] Traceability — Setiap komponen bisa ditelusuri ke variabel
  [X] Variable Isolation — IV bisa diubah tanpa mengubah CV
  [X] Measurement Integration — Pengukuran DV built-in
  [X] Reproducibility — Setup bisa direkonstruksi

Experimental Setup:
  Input data     : Skenario tugas (task scenario) checkout pembelian menu makanan yang seragam pada kedua aplikasi
  Parameter      : Responden Gen Z aktif, koneksi internet stabil (>10 Mbps), versi aplikasi terbaru yang digunakan pada smartphone
  Output format  : Catatan waktu penyelesaian tugas (file .xlsx) dan tabulasi skor SUS (skala 0-100)
```

---

## Latihan 1 — Variable-to-Component Mapping

Gunakan RQ dan variabel dari WS-05. Petakan ke komponen sistem.

**RQ:** Bagaimana perbandingan efisiensi kognitif alur checkout model Single-Screen (GoFood) dan Multi-Step (GrabFood) pada Generasi Z menggunakan metrik Time on Task dan System Usability Scale (SUS)?

| Variabel | Tipe | Komponen Sistem | Cara Manipulasi / Pengukuran |
|----------|------|-----------------|---------------------------|
| Model Alur Checkout (Single-Screen vs Multi-Step) | IV | Antarmuka Aplikasi (GoFood & GrabFood) | Meminta responden menyelesaikan tugas transaksi pada masing-masing jenis alur antarmuka secara bergantian |
| Efisiensi Kognitif dan Kepuasan Pengguna | DV | Instrumen Evaluasi (Screen Recorder & Kuesioner SUS) | Mengukur durasi pengerjaan tugas (Time on Task dalam detik) via rekaman video dan menghitung skor SUS pasca-tes |
| Lingkungan Pengujian dan Karakteristik Responden | CV | Protokol Eksperimen & Spesifikasi Device | Menyamakan instruksi tugas, menyamakan rentang usia responden (Gen Z), serta mengunci jenis koneksi internet dan OS smartphone |

**Apakah semua variabel bisa di-map?** [X] Ya / [ ] Tidak
> Jika tidak, komponen apa yang perlu ditambahkan? Semua variabel penelitian sudah berhasil dipetakan ke dalam komponen pengujian dengan lengkap.

---

## Latihan 2 — 4 Prinsip Desain

Evaluasi desain sistem terhadap 4 prinsip.

| Prinsip | Status | Bukti / Penjelasan |
|---------|--------|-------------------|
| Traceability | ✅ Terpenuhi | Setiap data yang dikumpulkan (durasi detik dan nilai kuesioner) secara langsung ditujukan untuk mengukur variabel efisiensi kognitif (Time on Task) dan tingkat kepuasan (SUS). |
| Modularity | ✅ Terpenuhi | Antarmuka aplikasi yang diuji (IV) dapat diswap atau diganti tanpa memengaruhi instrumen kuesioner evaluasi (DV) maupun lembar perhitungan statistik yang digunakan. |
| Controllability | ✅ Terpenuhi | Variabel kontrol (CV) dikunci menggunakan instruksi pengujian (test script) yang seragam, pembatasan spesifikasi sistem operasi handphone, serta standar koneksi internet yang ditentukan. |
| Measurability | ✅ Terpenuhi | Pengukuran menghasilkan data kuantitatif yang objektif berupa angka durasi waktu penyelesaian (detik) dan skor numerik SUS yang presisi. |

**Prinsip mana yang paling sulit dipenuhi?** Controllability (Kontrol terhadap lingkungan pengujian responden)
**Strategi untuk mengatasinya:**
> Menyusun panduan instruksi tertulis yang sangat jelas dan ringkas (test script) yang wajib dibaca responden sebelum memulai pengujian, serta melakukan sesi pengujian di ruangan yang tenang guna meminimalisir distraksi eksternal.

---

## Latihan 3 — Ablation Study Planning

Jika sistem memiliki 3 komponen utama, rencanakan ablation study.

> **Panduan jumlah kondisi:** Untuk 3 komponen (A, B, C), kondisi minimal yang direkomendasikan:
> Full + (-A) + (-B) + (-C) = **4 kondisi dasar**. Jika waktu memungkinkan, tambahkan kombinasi ganda: (-A,-B), (-A,-C), (-B,-C) = **7 kondisi**. Sesuaikan dengan *computational cost* dan tenggat waktu penelitian.

| Kondisi | Komponen A | Komponen B | Komponen C | Hasil yang Diharapkan |
|---------|-----------|-----------|-----------|----------------------|
| Full | ✅ Alur Checkout (GoFood & GrabFood) | ✅ Pengukuran Waktu (Time on Task) | ✅ Kuesioner Kepuasan (SUS) | Evaluasi usability komprehensif yang membandingkan performa objektif (kecepatan) dan kepuasan subjektif pengguna. |
| – A | ❌ (Tanpa alur pembanding/hanya satu alur) | ✅ | ✅ | Tidak didapatkan data komparasi efisiensi antarmuka, hanya berupa evaluasi aplikasi tunggal. |
| – B | ✅ | ❌ (Tanpa pengukur waktu) | ✅ | Hanya mendapatkan data kepuasan subjektif responden tanpa pembuktian efisiensi kecepatan nyata (detik). |
| – C | ✅ | ✅ | ❌ (Tanpa kuesioner SUS) | Hanya mendapatkan data durasi kecepatan interaksi tanpa mengetahui kenyamanan dan persepsi kepuasan pengguna. |

**Komponen mana yang diprediksi paling berkontribusi?** Komponen A (Alur Checkout)
**Mengapa?**
> Karena alur checkout (Single-Screen vs Multi-Step) merupakan variabel bebas (IV) yang menjadi objek utama penelitian. Tanpa adanya manipulasi atau perbedaan pada komponen alur antarmuka ini, eksperimen komparatif tidak memiliki dasar pembanding untuk menguji hipotesis efisiensi kognitif.

---

## Refleksi

> Apa risiko jika sistem dibangun seperti produk (monolitik, fitur lengkap) lalu baru dilakukan eksperimen? Mengapa arsitektur modular penting untuk riset?

**Jawaban:**
> Risiko terbesar jika sistem dibangun seperti produk monolitik yang lengkap sebelum eksperimen dilakukan adalah munculnya bias variabel (*confounding variables* atau *noise*). Ketika seluruh fitur digabungkan menjadi satu kesatuan yang rumit, kita akan sangat kesulitan untuk mengidentifikasi dan membuktikan fitur atau komponen spesifik mana yang sebenarnya memengaruhi perilaku pengguna atau performa sistem. Selain itu, jika terjadi kegagalan atau kesalahan dalam satu modul, seluruh sistem pengujian dapat terganggu sehingga membuang waktu dan sumber daya yang besar.
> 
> Arsitektur modular sangat penting untuk riset karena memungkinkan adanya **isolasi variabel** yang bersih. Melalui modularitas, peneliti dapat dengan mudah mengganti, mematikan, atau memodifikasi komponen tertentu (seperti menukar alur antarmuka atau instrumen pengukuran) secara independen tanpa harus merusak atau mendesain ulang keseluruhan arsitektur eksperimen. Hal ini menjamin bahwa pengujian tetap efisien, valid secara ilmiah, dan mudah untuk direproduksi kembali (*reproducible*).