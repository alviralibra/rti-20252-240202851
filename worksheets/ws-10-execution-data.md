# WS-10: Experiment Execution & Data Collection

> **Bab 10 — Eksekusi Eksperimen & Pengumpulan Data**

---

## Ringkasan Materi

### Experiment Execution Pipeline

```
Design → Execution Plan → Controlled Execution → Data Collection → Data Logging → Dataset for Analysis
```

### Multiple Run = Non-Negotiable

Single run **tidak pernah cukup** untuk klaim ilmiah. Minimum 5-10 run per skenario dengan seed berbeda. Multiple run menghasilkan:
- Mean, std, confidence interval
- Distribusi hasil → uji statistik
- Variabilitas → error bar di grafik

### Execution Plan

Setiap eksperimen harus memiliki plan sebelum eksekusi:
- Daftar skenario
- Jumlah run per skenario
- Random seed per run (pre-determined!)
- Urutan eksekusi (randomisasi/counterbalancing)
- Pre-execution checklist

### Data Logging Komprehensif

Setiap run menghasilkan log terstruktur:
1. **Identitas** — Run ID, timestamp, skenario
2. **Konfigurasi** — Semua parameter, seed, code version
3. **Hasil** — Semua metrik, output detail
4. **Metadata** — Waktu eksekusi, resource usage, warning/error

Format: CSV/JSON/database — **bukan stdout yang di-copy-paste**.

### Engineering vs Research Execution

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Run | Sekali (deploy) | Multiple (min 5-10, seed berbeda) |
| Logging | Error log, access log | Semua parameter, metrik, metadata |
| Anomali | Bug → fix → redeploy | Investigasi → dokumentasi → analisis |
| Urutan | Tidak penting | Bisa bias — perlu randomisasi |

### Anomali = Dokumentasi, Bukan Hapus

Run gagal/anomali tidak boleh dihapus tanpa dokumentasi. Bisa jadi:
- **Bug** → fix & re-run (dokumentasikan!)
- **Batas kemampuan metode** → DNF = temuan
- **Data yang bias** jika hanya simpan run "berhasil"

### Jebakan Kognitif

1. "Satu angka cukup" → tanpa distribusi, tidak bisa diuji
2. "Seed tidak penting" → bahkan algoritma deterministik bisa dipengaruhi library stokastik
3. "Run gagal langsung hapus" → kehilangan temuan potensial
4. "Semua run harus hari ini" → thermal throttling, fatigue

---

## Template A.10 — Execution Plan & Data Log

```
# EXECUTION PLAN

| Run # | Skenario | Seed | Parameter | Status | Waktu | Output File |
|-------|----------|------|-----------|--------|-------|-------------|
| 1     | Kelompok A (Responden 1-17) mencoba GoFood terlebih dahulu, kemudian GrabFood. | Counterbalancing A | Batas waktu maks 180 detik per aplikasi; Kuesioner SUS setelah tugas selesai. | Planned | Mei 2026 | data_mentah_kelompok_A.sav |
| 2     | Kelompok B (Responden 18-35) mencoba GrabFood terlebih dahulu, kemudian GoFood. | Counterbalancing B | Batas waktu maks 180 detik per aplikasi; Kuesioner SUS setelah tugas selesai. | Planned | Mei 2026 | data_mentah_kelompok_B.sav |
| 3     | Gabungan seluruh data (35 Responden) untuk analisis statistik akhir di SPSS. | Full Dataset | Uji Normalitas (Shapiro-Wilk) & Paired Samples T-Test dengan tingkat signifikansi 0,05. | Planned | Mei 2026 | analisis_akhir_gofood_grabfood.spv |

Jumlah runs per skenario : 1 Run per kelompok (Kelompok A, Kelompok B, dan Gabungan Total)
Total runs               : 3 Tahap Eksekusi Utama

---

# DATA LOG (Contoh Format per Responden):

  Run ID    : RESP-01 (Contoh data untuk Responden nomor 1)
  Timestamp : Mei 2026, [Waktu Pengujian]
  Skenario  : Kelompok A (GoFood -> GrabFood) via Live Briefing lisan
  Input     : Rekaman Layar Smartphone (.mp4) saat proses checkout makanan bebas
  Output    : Durasi waktu (detik) GoFood = 45s, GrabFood = 55s; Skor SUS GoFood = 80, GrabFood = 75
  Anomali   : Tidak ada / (Contoh jika ada: Koneksi internet responden sempat putus selama 5 detik pada aplikasi GrabFood)
  Catatan   : Responden menyelesaikan kedua tugas dengan lancar dan langsung mengisi kuesioner Google Form tepat setelah uji coba.
```

---

## Latihan 1 — Execution Plan

Susun execution plan untuk eksperimen Anda. Tentukan skenario, jumlah run, dan seed sebelum eksekusi.

| Run # | Skenario | Seed | Parameter Kunci | Status |
|-------|----------|------|----------------|--------|
| 1 | Kelompok A (Responden 1-17): Uji Coba GoFood | Counterbalancing A | Live briefing lisan, Cut-off time 180 detik | Planned |
| 2 | Kelompok A (Responden 1-17): Uji Coba GrabFood | Counterbalancing A | Live briefing lisan, Cut-off time 180 detik, Kuesioner SUS | Planned |
| 3 | Kelompok B (Responden 18-35): Uji Coba GrabFood | Counterbalancing B | Live briefing lisan, Cut-off time 180 detik | Planned |
| 4 | Kelompok B (Responden 18-35): Uji Coba GoFood | Counterbalancing B | Live briefing lisan, Cut-off time 180 detik, Kuesioner SUS | Planned |
| 5 | Gabungan Data 35 Responden: Analisis Akhir | Full Dataset | Input data editor, Uji Normalitas, Paired Samples T-Test | Planned |

**Total skenario:** 2 Skenario Kelompok Utama (Kelompok A dan Kelompok B)
**Run per skenario:** 2 Tahap pengujian aplikasi per kelompok
**Total run keseluruhan:** 5 Tahap Eksekusi

---

## Latihan 2 — Data Log Terstruktur

Desain format data log untuk eksperimen Anda. Tentukan field apa saja yang akan dicatat.

**Identitas:**
| Field | Contoh |
|-------|--------|
| Run ID | RESP-001 (Kode ID unik untuk setiap responden) |
| Timestamp | 2026-05-18T16:30:00 (Waktu pelaksanaan pengujian) |
| Kelompok | Kelompok A / Kelompok B (Penanda urutan aplikasi) |

**Konfigurasi:**
| Field | Contoh |
|-------|--------|
| Seed | Counterbalancing A (Metode kontrol urutan lisan) |
| Code version | IBM SPSS Statistics v26 (Versi software pengolah data) |
| Instansi | Generasi Z (Target populasi responden aktif) |

**Hasil:**
| Metrik | Tipe Data | Range Valid |
|--------|----------|-------------|
| Time_on_Task_GoFood | Integer (Detik) | 1 – 180 |
| Time_on_Task_GrabFood | Integer (Detik) | 1 – 180 |
| Skor_SUS_GoFood | Float / Numeric | 0.0 – 100.0 |
| Skor_SUS_GrabFood | Float / Numeric | 0.0 – 100.0 |

**Format output:** [ ] CSV / [ ] JSON / [X] Database / [X] Lainnya: Berkas dataset SPSS (.sav) dan rekaman layar (.mp4)

---

## Latihan 3 — Anomaly Protocol

Rencanakan bagaimana menangani anomali. Untuk setiap jenis, tentukan langkah yang diambil.

| Jenis Anomali | Contoh | Tindakan |
|---------------|--------|----------|
| Run gagal (crash) | Aplikasi GoFood atau GrabFood mendadak *freeze* (hang) atau keluar sendiri (*force close*) di tengah simulasi tugas responden. | Catat di lembar log, bersihkan *cache* aplikasi di HP responden, lakukan *restart* aplikasi, lalu ulangi tugas dari awal. |
| Hasil ekstrem | Responden mengisi kuesioner SUS secara asal-asalan (memberikan nilai 5 semua atau 1 semua untuk semua pertanyaan). | Lakukan pengecekan konsistensi jawaban. Jika terbukti tidak valid (*outlier* parah), data responden tersebut dikeluarkan dari dataset akhir agar tidak merusak rata-rata. |
| Waktu eksekusi anomali | Responden mengalami masalah jaringan (sinyal mendadak hilang atau *buffering* lama) sehingga waktu *checkout* melebihi batas *cut-off* 180 detik. | Hentikan tugas pada detik ke-180, dokumentasikan kendala jaringan di kolom anomali data log, dan tandai data waktu tersebut sebagai data yang tidak tuntas (*incomplete task*). |
| Inkonsistensi dengan run lain | Responden salah menangkap maksud instruksi lisan (*live briefing*) sehingga alur *checkout* yang dilakukan melenceng jauh dari skenario. | Lakukan *investigate* (wawancara singkat setelah tes). Jika kesalahannya fatal akibat salah paham instruksi, batalkan run tersebut dan cari responden pengganti baru agar jumlah sampel tetap 35 orang. |

**Prinsip:** Detect → Investigate → Document → Decide

---

## Refleksi

> Pernahkah Anda melaporkan hasil riset/tugas dari single run? Apa risikonya? Bagaimana multiple run mengubah kepercayaan terhadap hasil?

**Pengalaman sebelumnya:**
Ya, dalam tugas-tugas praktikum awal atau pembuatan prototipe sederhana, kadang saya hanya melakukan pengujian satu atau dua kali (*single run*) untuk memastikan fitur aplikasi berjalan. Risikonya sangat besar untuk riset ilmiah, yaitu munculnya bias dan hasil yang tidak valid. Jika hanya menguji satu orang responden, bisa saja orang tersebut kebetulan sangat mahir (sehingga waktu *checkout* sangat cepat) atau kebetulan gagap teknologi (sehingga waktu *checkout* sangat lama). Hasil *single run* tidak bisa mewakili kelompok Generasi Z secara umum dan rentan terhadap faktor kebetulan.

**Yang akan dilakukan berbeda:**
Pada riset komparasi GoFood dan GrabFood kali ini, saya menerapkan metode *multiple run* dengan mengumpulkan data dari 35 responden berbeda yang dibagi rata lewat urutan *Counterbalancing*. Dengan menguji banyak orang, variasi data individual (seperti kecepatan jari, kondisi sinyal HP, atau tingkat keakraban dengan aplikasi) akan saling menyeimbangkan. Pengujian berulang ini membuat nilai rata-rata (*mean*) yang dihasilkan jauh lebih stabil, objektif, dan dapat dipercaya secara statistik saat diolah menggunakan uji Paired Samples T-Test di SPSS nanti.

### Selesai