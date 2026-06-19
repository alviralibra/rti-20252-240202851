# WS-11: Data Validation & Integrity

> **Bab 11 — Validasi Data & Integritas**

---

## Ringkasan Materi

### Data Trust Model

```
Raw Data → Data Cleaning → Consistency Check → Validation Process → Trusted Data
```

Data mentah belum bisa dipercaya. Harus melewati pipeline validasi sebelum siap untuk analisis statistik.

### Empat Pilar Data Quality

| Pilar | Deskripsi | Contoh Pelanggaran |
|-------|----------|-------------------|
| **Accuracy** | Nilai dalam range masuk akal | Akurasi = 1.5 (di luar [0,1]) |
| **Consistency** | Format seragam di semua run | Run 1: CSV, Run 2: JSON |
| **Completeness** | Tidak ada data hilang dari plan | 97 dari 100 run tercatat |
| **Validity** | Data sesuai desain eksperimen | Parameter baseline tercampur treatment |

### Proses Validasi Progresif

1. **Format validation** — Tipe file, header, kolom
2. **Range validation** — Nilai dalam batas logis
3. **Consistency validation** — Format seragam antar-run
4. **Logic validation** — Data cocok dengan desain eksperimen

Jika gagal di langkah awal → tidak perlu lanjut.

### Anomaly Detection — 3 Jenis

| Jenis | Deskripsi | Deteksi |
|-------|----------|---------|
| **Statistical outlier** | Nilai di luar distribusi normal | IQR: < Q1-1.5×IQR atau > Q3+1.5×IQR |
| **Contextual anomaly** | Normal absolut, abnormal dalam konteks | Run 1-10: ~91%, Run 11-20: ~88% |
| **Pattern anomaly** | Pola sistematis (bukan random) | Performa menurun berurutan |

**Prinsip:** Detect → Investigate → Document → Decide — **JANGAN langsung hapus.**

### Engineering vs Research Validation

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan | Data sesuai spesifikasi bisnis | Data layak untuk analisis statistik |
| Missing data | Impute / set default | Investigasi penyebab → dokumentasi |
| Outlier | Bug → fix | Mungkin temuan → investigasi |
| Dokumentasi | Minimal (log error) | Komprehensif (anomali + keputusan) |

### Jebakan Kognitif

1. "Logging otomatis ≠ data benar" → bisa ada bug di logger
2. "Outlier = hapus" → bisa jadi temuan penting
3. "Dataset kecil tidak perlu validasi" → justru lebih rentan
4. "Mean normal = data benar" → [94, 95, 93, **44**, 94] → mean 84% terlihat wajar

---

## Template A.11 — Data Validation Checklist

```
DATA VALIDATION CHECKLIST

Completeness:
  [✓] Semua skenario tercakup
  [✓] Jumlah run sesuai rencana
  [✓] Tidak ada file output hilang
  Missing: 0 dari 70 data points

Format Consistency:
  [✓] Semua file format sama (CSV/JSON/...)
  [✓] Header konsisten
  [✓] Tipe data konsisten (numerik tetap numerik)

Range & Logic:
  [✓] Nilai dalam range masuk akal
  [✓] Tidak ada waktu negatif
  [✓] Metrik 0–100%, tidak di luar range
  Anomali ditemukan: Format waktu mentah berbentuk menit:detik (00:17) harus diekstraksi menjadi angka numerik detik murni (17) agar bisa terbaca dan dihitung oleh SPSS.

Cross-Validation:
  [✓] Run identik → hasil mendekati
  [✓] Trend konsisten dengan ekspektasi teori

Keputusan:
  [✓] Data siap analisis
  [ ] Perlu cleaning
  [ ] Perlu re-run (skenario: ____)
```

---

## Latihan 1 — Completeness Check

Verifikasi apakah semua data yang direncanakan sudah terkumpul.

| Skenario | Run Direncanakan | Run Tercatat | Missing | Alasan |
|----------|-----------------|-------------|---------|--------|
| *Contoh: BERT, DS-1* | *10* | *10* | *0* | *—* |
| *LSTM, DS-3* | *10* | *8* | *2* | *OOM pada run 7 & 9* |
| Checkout GrabFood | 35 | 35 | 0 | — |
| Checkout GoFood | 35 | 35 | 0 | — |

**Total expected:** 70 | **Total actual:** 70 | **Missing:** 0

**Keputusan untuk data missing:**
> Tidak ada data yang hilang (missing data = 0). Seluruh data dari 35 responden berhasil terekam secara lengkap untuk kedua skenario aplikasi sehingga data memenuhi syarat aspek completeness dan siap untuk dianalisis.

---

## Latihan 2 — Anomaly Investigation

Periksa data Anda untuk anomali. Gunakan metode IQR atau z-score.

**Dataset sampel (atau data Anda own):**

| Run | Accuracy (%) |
|-----|-------------|
| 1 | 17.0 |
| 2 | 21.0 |
| 3 | 18.0 |
| 4 | 19.0 |
| 5 | 22.0 |

**Deteksi outlier:**
- Q1 = 18.0 | Q3 = 21.0 | IQR = 3.0
- Batas bawah (Q1 - 1.5×IQR) = 13.5
- Batas atas (Q3 + 1.5×IQR) = 25.5
- Outlier terdeteksi: Tidak Ada Outlier

**Investigasi (untuk setiap outlier):**

| Outlier | Nilai | Kemungkinan Penyebab | Keputusan |
|---------|-------|---------------------|-----------|
| *Run 4* | *78.3* | *Contoh: thermal throttling setelah 3 run berturut* | *Re-run dengan cooling interval* |

---

## Latihan 3 — Validation Report

Buat laporan validasi ringkas untuk dataset eksperimen Anda.

**1. Completeness:** 100% data terkumpul
**2. Format:** [✓] Konsisten / [ ] Ada inkonsistensi: —
**3. Range check (anomali):** Tidak ditemukan data durasi bernilai negatif dan tidak ada total skor kuesioner SUS yang berada di luar rentang standar 0–100.
**4. Logic check:** [✓] Parameter sesuai plan / [ ] Ada ketidaksesuaian: —

**Kesimpulan:** [✓] Data siap analisis / [ ] Perlu tindakan: —

---

## Refleksi

> Apa perbedaan antara "data yang benar" dan "data yang dipercaya"? Mengapa proses validasi formal diperlukan meskipun data dikumpulkan secara otomatis?

> "Data yang benar" (raw data) adalah data faktual yang direkam apa adanya oleh instrumen pengumpul data (seperti format menit:detik 00:17 di lembar excel). Sedangkan "data yang dipercaya" (trusted data) adalah data yang telah lolos pipeline validasi formal, dibersihkan dari anomali format, dan disesuaikan sehingga siap diolah secara akurat tanpa memicu bias atau eror logika.
> 
> Proses validasi formal tetap diperlukan meskipun data dikumpulkan otomatis karena sistem perekaman otomatis tidak menjamin data terbebas dari kesalahan tipe data (seperti spasi ilegal atau karakter yang tidak terbaca oleh software statistik) serta tidak mampu mendeteksi keabnormalan logika operasional eksperimen di lapangan. Validasi formal memastikan integritas data benar-benar layak sebelum ditarik kesimpulan ilmiah.
