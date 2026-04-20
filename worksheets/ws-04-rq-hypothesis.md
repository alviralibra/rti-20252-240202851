# WS-04: Research Question & Hypothesis

> **Bab 4 — Research Question, Contribution & Hypothesis**

---

## Ringkasan Materi

### RQ Bukan Pertanyaan Biasa

Research Question yang baik secara implisit mengandung cetak biru eksperimen: subjek, baseline, metrik, domain, dataset.

| Kualitas | Contoh |
|----------|--------|
| **Buruk** | "Bagaimana pengaruh deep learning terhadap deteksi malware?" |
| **Baik** | "Apakah CNN menghasilkan F1-Score lebih tinggi dari RF pada CIC-MalMem-2022?" |

Perbedaan: RQ yang baik menyebutkan **metode spesifik**, **metrik terukur**, **baseline**, dan **dataset**.

### Tiga Jenis RQ

| Jenis | Pola | Kebutuhan |
|-------|------|-----------|
| **Comparison** | A vs B → mana lebih baik? | ≥ 2 metode, metrik sama |
| **Improvement** | A' vs A → modifikasi lebih baik? | Pre/post, bukti perbaikan |
| **Exploratory** | Faktor X₁...Xₙ → pengaruh terhadap Y? | Multi-variabel, korelasi/regresi |

### Contribution Statement

Tiga jenis kontribusi: **Improvement** (metode terbukti lebih baik), **Comparison** (perbandingan sistematis yang belum ada), **Novel Approach** (pendekatan baru). Kontribusi harus terhubung langsung dengan gap — kontribusi tanpa gap = klaim tanpa justifikasi.

### Hypothesis H₀ / H₁

- **H₀** (Null) = Tidak ada perbedaan signifikan — asumsi default, harus dibuktikan salah
- **H₁** (Alternative) = Ada perbedaan signifikan — diterima hanya jika H₀ ditolak
- Harus **falsifiable**, mengandung **metrik terukur**, dirumuskan **SEBELUM eksperimen**

### Rantai Operasionalisasi

```
RQ → Variable → Metric → Data → Analysis
```

Jika rantai ini tidak lengkap, RQ belum mature. Bi-directional: RQ yang tidak bisa jadi hipotesis testable harus direvisi mundur.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan pertanyaan | Apa yang harus dibangun? | Apa yang harus dibuktikan? |
| Bentuk jawaban | Sistem yang berfungsi | Bukti empiris terukur |
| Sukses diukur oleh | User satisfaction, uptime | Signifikansi statistik, effect size |
| Jika gagal | Debug dan perbaiki | Laporkan, analisis mengapa |

### Istilah Penting

- **Research Question (RQ)** — Pertanyaan spesifik: variabel terukur + metrik + konteks
- **Contribution Statement** — Apa yang diketahui setelah riset selesai yang sebelumnya belum ada
- **H₀ / H₁** — Null vs Alternative Hypothesis
- **Falsifiability** — Kondisi hipotesis ditolak harus bisa didefinisikan sebelum eksperimen
- **Operationalization** — Proses mewujudkan konsep abstrak menjadi variabel terukur

---

## Template A.4 — RQ-Contribution-Hypothesis

```
RQ-CONTRIBUTION-HYPOTHESIS

Gap Statement  : Minimnya data performa objektif (durasi waktu) dan analisis beban kognitif (RTA) yang membandingkan alur checkout konsumen secara head-to-head antara model Single-Screen (GrabFood) dan Multi-Step (GoFood) dalam riset SOTA 2025-2026.

Research Question:
  Tipe         : [X] Comparison  [ ] Improvement  [ ] Exploratory
  Formulasi    : Apakah alur Single-Screen Checkout pada GrabFood menghasilkan efisiensi kognitif (Time on Task) yang lebih singkat dan skor usability (SUS) yang lebih tinggi dibandingkan alur Multi-Step pada GoFood?
  Variabel IV  : Model User Flow Checkout (Single-Screen vs Multi-Step).
  Variabel DV  : Efisiensi Kognitif dan Kepuasan Pengguna.
  Metrik       : Time on Task (detik) dan Skor SUS (0-100).
  Dataset      : Data primer hasil eksperimen pada 10 partisipan mahasiswa (Gen-Z).
  Baseline     : Skor SUS dan temuan masalah RTA pada ekosistem Grab/Gojek (Handayani, 2025).

Quality Check RQ:
  [X] Variabel spesifik
  [X] Metrik jelas
  [X] Baseline ada
  [X] Konteks disebutkan
  [X] Memerlukan eksperimen (bukan hanya survei literatur)

Contribution Statement:
  Apa yang baru diketahui : Perbandingan empiris efisiensi kognitif antara dua paradigma desain checkout (Single vs Multi-step) pada aplikasi on-demand service di Indonesia tahun 2026.
  Jenis kontribusi        : [ ] Improvement  [X] Comparison  [ ] Novel approach
  Gap yang diisi          : Mengisi keterbatasan riset sebelumnya (Jimmy, 2026; Handayani, 2025) yang belum melakukan pengujian performa waktu secara mikro pada alur checkout konsumen.

Hypothesis Pair:
  H₀ : Tidak ada perbedaan signifikan pada durasi waktu (Time on Task) dan skor SUS antara alur checkout GrabFood dan GoFood.
  H₁ : Alur Single-Screen GrabFood memberikan durasi waktu yang lebih singkat secara signifikan dibandingkan alur Multi-Step GoFood.
  Threshold       : p-value < 0.05 (Independent T-Test).
```

---

## Latihan 1 — Dari Gap ke RQ

Gunakan gap yang ditemukan di WS-03. Transformasikan menjadi Research Question.

**Gap dari WS-03:** Minimnya penggunaan data performa objektif (durasi detik) dan analisis perbandingan alur kerja mikro antara kompetitor utama dalam riset *usability* terbaru 2025-2026.

**RQ versi pertama (tulis bebas):**
> Mana yang lebih cepat dan mudah digunakan buat bayar makanan, GrabFood atau GoFood?

**Evaluasi RQ:**

| Komponen | Ada? | Isi |
|----------|------|-----|
| Metode spesifik | Ya | Komparasi alur *Single-Screen* vs *Multi-Step* |
| Metrik terukur | Ya | *Time on Task* (detik) dan skor SUS |
| Baseline | Ya | Jurnal evaluasi *usability* tahun 2025 |
| Dataset/konteks | Ya | Pengguna aktif layanan *food delivery* (Gen-Z) |

**Tipe RQ:** [X] Comparison / [ ] Improvement / [ ] Exploratory

**RQ versi revisi (setelah evaluasi):**
> Bagaimana perbandingan efisiensi kognitif berdasarkan metrik *Time on Task* dan skor SUS antara alur *checkout* GrabFood (Single-Screen) dan GoFood (Multi-Step) pada pengguna generasi Z di Indonesia?

---

## Latihan 2 — Hypothesis Pair

Rumuskan pasangan hipotesis dari RQ di Latihan 1.

| Komponen | Isi |
|----------|-----|
| **H₀** | Tidak ada perbedaan signifikan pada durasi waktu (*Time on Task*) dan skor SUS antara alur *checkout* GrabFood dan GoFood. |
| **H₁** | Alur *Single-Screen* GrabFood menghasilkan durasi waktu penyelesaian tugas yang lebih cepat secara signifikan dibandingkan alur GoFood. |
| **Metrik** | *Time on Task* (detik) dan Skor SUS (0-100). |
| **Threshold** | *p-value* < 0.05. |
| **Justifikasi threshold** | Standar baku signifikansi statistik dalam riset HCI (Handayani, 2025) untuk menyatakan adanya perbedaan nyata antar sistem. |

**Apakah hipotesis ini falsifiable?** [X] Ya / [ ] Tidak
> **Bagaimana cara membuktikannya salah?** Dengan melakukan uji statistik (Independent T-Test) pada data hasil eksperimen. Jika nilai *p-value* yang dihasilkan lebih besar dari 0.05, maka hipotesis alternatif (H₁) ditolak dan H₀ dianggap benar (tidak ada perbedaan signifikan).

---

 ## Latihan 3 — Rantai Operasionalisasi

Lengkapi rantai dari RQ hingga metode analisis.

| Tahap | Isi |
|-------|-----|
| **RQ** | Apakah alur *Single-Screen* GrabFood menghasilkan efisiensi kognitif (waktu) yang lebih tinggi dibanding alur *Multi-Step* GoFood? |
| **Variable (IV)** | Model User Flow Checkout (*Single-Screen* vs *Multi-Step*). |
| **Variable (DV)** | Efisiensi Kognitif dan Kepuasan Pengguna. |
| **Metric** | Durasi detik (*Time on Task*) dan Skor SUS (0-100). |
| **Data source** | Rekaman layar eksperimen hingga tahap konfirmasi *checkout* akhir (sebelum klik pesan) dan kuesioner SUS pasca-tugas. |
| **Analysis method** | *Independent T-Test* (Kuantitatif) dan Analisis Temuan Masalah RTA (Kualitatif). |

**Apakah rantai lengkap?** [X] Ya / [ ] Tidak
> **Jika tidak, tahap mana yang perlu direvisi?** (Tahap sudah lengkap dan konsisten dari pertanyaan hingga metode analisis).

---

## Refleksi

> Ambil satu judul skripsi/paper yang pernah dibaca. Coba ekstrak RQ-nya. Apakah RQ tersebut memenuhi semua komponen (metode, metrik, baseline, konteks)? Jika tidak, apa yang hilang?

**Judul:** Usability Aplikasi GrabMerchant: Evaluasi dengan Metode System Usability Scale dan Retrospective Think Aloud (Handayani & Maria, 2025).

**RQ yang diekstrak:** Bagaimana tingkat usability aplikasi GrabMerchant bagi mitra usaha menggunakan metode SUS dan RTA untuk mengidentifikasi hambatan navigasi?

**Komponen yang hilang:** RQ tersebut tidak menyertakan **metrik performa objektif** (seperti durasi waktu/detik) dan tidak memiliki **pembanding (*baseline*)** secara eksplisit terhadap aplikasi kompetitor dalam rumusan pertanyaannya.