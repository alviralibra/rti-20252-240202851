# WS-03: Literature Mapping & Gap

> **Bab 3 — Literature Review, Research Gap & Baseline**

---

## Ringkasan Materi

### Literature Review = Positioning, Bukan Ringkasan

Literature review bukan merangkum paper satu per satu. Pendekatan yang benar adalah **concept-centric** — organisasi berdasarkan tema, metode, atau variabel. Tujuan: menemukan **pola, kontradiksi, dan gap**.

### Empat Jenis Research Gap

| Jenis Gap | Deskripsi | Contoh |
|-----------|----------|--------|
| **Performance Gap** | Performa belum memadai | Akurasi deteksi hanya 78% pada kasus tertentu |
| **Method Gap** | Pendekatan belum diterapkan | Belum ada yang pakai transformer untuk task ini |
| **Data Gap** | Dataset terbatas/tidak representatif | Semua studi pakai dataset sintetis |
| **Context Gap** | Belum diuji pada konteks berbeda | Belum ada evaluasi di negara berkembang |

Gap terkuat = kombinasi 2+ jenis.

### Systematic Search Strategy

1. **Database**: IEEE Xplore, ACM DL, Scopus, Google Scholar
2. **Boolean query** yang terdokumentasi eksplisit
3. **Snowballing**: backward (telusuri referensi) + forward (cari yang mengutip)
4. Klaim "belum ada penelitian" harus didukung **bukti pencarian**

### Baseline Selection — 3 Kriteria

| Kriteria | Pertanyaan |
|----------|-----------|
| **Relevan** | Apakah menyelesaikan masalah yang sama? |
| **Representatif** | Apakah mewakili common practice? |
| **State-of-the-Art** | Apakah terbaru/terbaik? |

Membandingkan deep learning 2024 dengan decision tree sederhana tanpa justifikasi = **straw man comparison** (perbandingan tidak jujur).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan baca literatur | Mencari solusi yang sudah ada | Memahami apa yang belum terjawab |
| Cara membaca paper | Tutorial, how-to | Metode, limitasi, gap |
| Baseline | Framework terpopuler | State-of-the-art yang rigorous |
| Dokumentasi pencarian | Tidak diperlukan | Wajib (reproducible) |

### Istilah Penting

- **Concept-centric** — Organisasi literatur berdasarkan konsep/metode, bukan per penulis
- **Snowballing** — Backward (telusuri referensi) + Forward (cari yang mengutip paper kunci)
- **Research Position** — Pernyataan eksplisit posisi riset terhadap studi sebelumnya
- **Straw man comparison** — Memilih baseline lemah agar metode sendiri terlihat lebih baik

---

## Template A.3 — Literature Mapping & Gap Identification

```
LITERATURE MAPPING

Topik      : Analisis Efisiensi Kognitif Pengguna dalam Alur Checkout Aplikasi On-Demand Service: Eksperimen Perbandingan User Flow GrabFood vs GoFood
Database   : Google Scholar
Query      : ("usability" OR "efficiency") AND ("on-demand service" OR "m-commerce") AND ("Grab" OR "Gojek")
Tahun      : 2018 – 2025
Hasil awal : 15 paper → Screening → 5 paper final

Literature Matrix (concept-centric):

| Study | Tahun | Method | Data | Result | Limitation |
|-------|-------|--------|------|--------|------------|
|Utami & Gunadi|2023|SUS (System Usability Scale)|30 Responden|GrabFood (76,92) & GoFood (74,83). Keduanya "Good".|Hanya mengukur skor kepuasan, tidak ada data waktu (detik).|
|Hutahaean, dkk.|2025|PLS-SEM & IPMA|149 Pengguna|Learnability & Simplicity sangat krusial bagi loyalitas.|Fokus pada m-commerce umum, bukan layanan pesan-antar makanan.|
|Praditya, dkk.|2018|HCD & QUIS|90 Responden|Perbaikan desain meningkatkan kepuasan navigasi & tampilan.|Fokus pada aplikasi Driver (Mangjek), bukan sisi konsumen.|
|Handayani & Maria|2025|SUS & RTA|5 Expert Users|Menemukan 13 masalah spesifik (notifikasi, stok, promosi).|Fokus pada sisi Penjual (Merchant), bukan alur checkout konsumen.|
|Wicaksono, dkk.|2023|DeLone & McLean|93 Responden|Rute tidak efisien & info kurang tepat pengaruhi kepuasan.|Analisis sistem secara makro, bukan uji coba alur klik (user flow).|

Pola yang ditemukan:
  Metode dominan     : System Usability Scale (SUS) dan kuesioner kepuasan.
  Dataset umum       : Pengguna aktif aplikasi mobile on-demand di Indonesia.
  Limitasi berulang  : Minimnya penggunaan data objektif (waktu) dan belum fokus pada perbandingan alur kerja (user flow) secara mikro.

GAP IDENTIFICATION

Gap 1: [Jenis: Method Gap]
  Deskripsi    : Mayoritas riset menggunakan kuesioner subjektif (SUS) tanpa menggabungkannya dengan data objektif performa waktu (Time on Task).
  Bukti        : Utami & Gunadi (2023) hanya memberikan skor angka tanpa tahu "berapa detik" user bingung di halaman checkout.
  Signifikansi : Tanpa data waktu, kita tidak bisa membuktikan aplikasi mana yang secara teknis lebih cepat menyelesaikan tugas.

Gap 2: [Jenis: Context & Data Gap]
  Deskripsi    : Belum ada perbandingan efisiensi kognitif antara model Single-Screen Checkout (Grab) vs Multi-Step/Wizard Checkout (Gojek).
  Bukti        : Handayani & Maria (2025) fokus pada Merchant; Praditya (2018) pada Driver. Sisi checkout konsumen masih sangat minim.
  Signifikansi : Menemukan alur mana yang paling sedikit memberikan beban pikiran (cognitive load) bagi pengguna yang sedang lapar dan terburu-buru.

Baseline Selection:
| Baseline | Relevansi | Representatif | Source |
|----------|-----------|---------------|--------|
|SUS Score (Grab vs Gojek)|Sebagai pembanding kepuasan psikologis|Sering digunakan dalam riset pembanding|Utami & Gunadi, 2023|
|RTA (Retrospective Think Aloud)|Metode valid untuk gali masalah kognitif|Dipakai untuk bedah masalah usability spesifik|Handayani & Maria, 2025|
```

---

## Latihan 1 — Concept-Centric Literature Table

**Topik riset:** Analisis Efisiensi Kognitif Pengguna dalam Alur Checkout Aplikasi On-Demand Service: Eksperimen Perbandingan User Flow GrabFood vs GoFood
**Query pencarian:** ("usability" OR "efficiency") AND ("on-demand" OR "food delivery") AND ("Grab" OR "Gojek")
**Database:** Google Scholar

| # | Study | Tahun | Method | Dataset | Result | Limitasi |
|---|---|---|---|---|---|---|
| 1 | Utami & Gunadi | 2023 | System Usability Scale (SUS) | 30 Responden | Skor Grab (76,92) & GoFood (74,83) kategori "Good". | Hanya kuesioner persepsi, tidak ada data waktu/detik. |
| 2 | Hutahaean, dkk. | 2025 | PLS-SEM & IPMA | 149 Pengguna | Learnability dominan; Efficiency tidak signifikan di m-commerce. | Fokus pada m-commerce belanja, bukan layanan makanan. |
| 3 | Praditya, dkk. | 2018 | HCD & QUIS | 90 Responden | Perbaikan desain meningkatkan kepuasan navigasi & tampilan. | Fokus pada aplikasi Driver, bukan alur checkout konsumen. |
| 4 | Handayani & Maria | 2025 | SUS & RTA | 5 Expert Users | Menemukan 13 masalah usability spesifik melalui cerita user. | Fokus pada sisi Penjual (Merchant), bukan konsumen. |
| 5 | Wicaksono, dkk. | 2023 | DeLone & McLean | 93 Responden | Rute tidak efisien & info kurang tepat pengaruhi kepuasan. | Analisis sistem makro, tidak menguji user flow mikro. |

**Pola yang terlihat — Metode dominan:** Penggunaan kuesioner subjektif (seperti SUS) dan model statistik untuk mengukur kepuasan pengguna.

**Limitasi yang berulang:** Minimnya penggunaan data performa objektif (seperti durasi waktu dalam detik) dan perbandingan antar model user flow yang berbeda secara mikro.

---

## Latihan 2 — Gap Identification

Berdasarkan tabel di Latihan 1, identifikasi gap.

| Jenis Gap | Ditemukan? | Gap Statement |
|-----------|-----------|---------------|
| Performance Gap | [ ] Ya / [X] Tidak | - |
| Method Gap | [X] Ya / [ ] Tidak | Mayoritas riset menggunakan kuesioner subjektif (SUS); belum ada yang menggunakan eksperimen objektif "Time on Task" untuk mengukur efisiensi kognitif secara langsung. |
| Data Gap | [X] Ya / [ ] Tidak | Belum tersedia data perbandingan performa antara alur checkout "Single-Screen" (GrabFood) dengan alur "Multi-Step" (GoFood) dalam satuan detik. |
| Context Gap | [X] Ya / [ ] Tidak | Penelitian metode RTA sebelumnya (Handayani & Maria, 2025) baru fokus pada sisi Merchant; belum ada evaluasi mendalam pada sisi Konsumen saat proses checkout. |

**Gap utama yang dipilih:** Method Gap & Data Gap (Kombinasi).

**Mengapa gap ini penting (bukan sekadar "belum ada yang meneliti ini")?**
> Gap ini penting karena efisiensi dalam layanan pesan-antar makanan (*on-demand food delivery*) sangat krusial mengingat kondisi psikologis pengguna yang biasanya sedang lapar atau terburu-buru. Tanpa data performa objektif (durasi waktu) dan analisis beban kognitif (RTA), kita tidak bisa membuktikan secara ilmiah alur mana yang paling optimal bagi pengguna. Riset ini akan memberikan bukti nyata melalui angka (detik) dan narasi user, bukan sekadar skor persepsi angka saja.

---

## Latihan 3 — Baseline Selection

Pilih 2 baseline dari literatur yang sudah dibaca.

| # | Baseline | Mengapa Relevan | Mengapa Representatif | Apakah SOTA? | Sumber |
|---|----------|----------------|----------------------|-------------|--------|
| 1 | System Usability Scale (SUS) Score | Digunakan untuk mengukur kepuasan pengguna pada aplikasi Grab & Gojek. | Merupakan standar industri yang paling sering muncul di literatur usability. | Ya | Utami & Gunadi (2023) |
| 2 | Retrospective Think Aloud (RTA) | Metode untuk menggali kendala spesifik dan beban pikiran pengguna. | Digunakan untuk membedah masalah navigasi pada aplikasi Grab. | Ya | Handayani & Maria (2025) |

**Apakah pemilihan baseline ini bisa dianggap straw man?** [ ] Ya / [X] Tidak
> **Justifikasi:** Pemilihan baseline ini bukan *straw man* karena saya menggunakan metode dan instrumen yang dianggap sebagai standar terbaik (*State-of-the-Art*) dan paling umum digunakan dalam bidang *usability*, bukan membandingkannya dengan metode yang sudah usang atau lemah.

---

## Refleksi

> Apa perbedaan antara "belum ada yang meneliti ini" (klaim tanpa bukti) dengan research gap yang valid? Bagaimana cara membuktikan bahwa sebuah gap benar-benar ada?

**Jawaban:**
> Klaim "belum ada yang meneliti" seringkali bersifat subjektif dan tidak memiliki landasan kuat, sementara **research gap yang valid** adalah pernyataan yang didukung oleh bukti nyata setelah melakukan pemetaan literatur (*literature mapping*). Gap yang valid secara eksplisit menunjukkan bahwa meskipun ada penelitian sebelumnya, terdapat aspek tertentu (metode, data, atau konteks) yang belum terjawab atau memiliki hasil yang kontradiktif. 
> 
> Cara membuktikan sebuah gap benar-benar ada adalah dengan menyusun **Literature Matrix**. Melalui matriks tersebut, kita bisa menunjukkan kolom "Limitasi" dari setiap penelitian sebelumnya. Jika limitasi tersebut muncul berulang kali atau ada celah yang belum tersentuh (misalnya: riset sebelumnya hanya pakai kuesioner, sedangkan kita akan pakai eksperimen waktu), maka gap tersebut terbukti ada secara ilmiah.