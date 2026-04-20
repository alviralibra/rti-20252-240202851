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
Database   : Google Scholar, ResearchGate, Portal Garuda
Query      : ("usability" OR "efficiency") AND ("RTA" OR "Retrospective Think Aloud") AND ("Grab" OR "Gojek")
Tahun      : 2025 – 2026
Hasil awal : 12 paper → Screening → 5 paper final

Literature Matrix (concept-centric):

| Study | Tahun | Method | Data | Result | Limitation |
|-------|-------|--------|------|--------|------------|
|Jimmy & Suhardi|2026|Kuantitatif (Regresi)|204 Pengguna Gojek|Persepsi kemudahan dan kepuasan secara parsial membangun loyalitas.|Fokus pada variabel psikologis makro, bukan bedah alur (flow) teknis.|
|Hutahaean, dkk.|2025|IPMA (Importance Performance Matrix)|149 Pengguna|Efisiensi dan kemudahan adalah prioritas utama untuk loyalitas m-commerce.|Belum menggunakan metode kualitatif (RTA) untuk mendeteksi beban kognitif spesifik.|
|Handayani & Maria|2025|SUS & RTA|5 Expert Users|Menemukan 13 masalah kritis pada navigasi, stok, dan promosi.|Fokus pada sisi Mitra (GrabMerchant), bukan pada alur checkout konsumen.|
|Bimantari Dewi, dkk.|2025|RTA, SUS, & Heuristic Evaluation|Pengguna App XYZ|RTA berhasil menemukan hambatan kognitif pada alur transaksi yang tidak terdeteksi SUS.|Fokus pada satu aplikasi fintech tunggal, bukan studi komparatif antar kompetitor.|
|Ruzaini & Rafiah|2025|Analisis Deskriptif & Verifikatif|100 Pengguna Go-Food|User Experience (UX) memiliki pengaruh positif kuat terhadap minat beli.|Data diambil secara umum (makro), tidak spesifik menguji efisiensi per alur klik.|

Pola yang ditemukan:
  Metode dominan     : Penggunaan kuesioner (SUS) dikombinasikan dengan validasi kualitatif (RTA).
  Dataset umum       : Pengguna aktif layanan on-demand service dan m-commerce di Indonesia.
  Limitasi berulang  : Belum ada riset SOTA (2025-2026) yang melakukan komparasi langsung alur checkout antara dua kompetitor utama (Grab vs Gojek) dari sisi konsumen.

GAP IDENTIFICATION

Gap 1: [Jenis: Method Gap]
  Deskripsi    : Meskipun riset terbaru (Jimmy, 2026; Ruzaini, 2025) sudah membahas UX, mayoritas masih menggunakan data persepsi subjektif tanpa pengukuran beban kognitif yang mendalam.
  Bukti        : Hutahaean, dkk. (2025) menyatakan efisiensi penting namun hanya diukur lewat matriks kepentingan, bukan observasi langsung hambatan kognitif saat checkout.
  Signifikansi : Menggabungkan RTA dengan analisis komparatif akan memberikan bukti objektif di mana letak "mental block" pengguna pada masing-masing aplikasi.

Gap 2: [Jenis: Context Gap]
  Deskripsi    : Riset RTA paling mutakhir (Handayani, 2025) baru menyentuh sisi Merchant (penjual). Konteks checkout pembeli (paling kritis bagi profit) belum dibedah secara komparatif.
  Bukti        : Bimantari Dewi, dkk. (2025) membuktikan RTA efektif untuk alur transaksi, namun belum diterapkan pada persaingan pasar GrabFood vs GoFood.
  Signifikansi : Memberikan rekomendasi desain berdasarkan alur mana yang paling efisien secara kognitif bagi konsumen yang memiliki beban waktu (lapar/terburu-buru).

Baseline Selection:
| Baseline | Relevansi | Representatif | Source |
|----------|-----------|---------------|--------|
|Analisis Loyalitas & Kemudahan|Pembanding standar kepuasan pengguna Gojek terbaru|Mewakili tren riset on-demand service 2026|Jimmy & Suhardi, 2026|
|RTA & SUS Evaluation|Metode standar untuk deteksi hambatan kognitif|Dipakai pada evaluasi aplikasi ekosistem Grab|Handayani & Maria, 2025|
```

---

## Latihan 1 — Concept-Centric Literature Table

**Topik riset:** Analisis Efisiensi Kognitif Pengguna dalam Alur Checkout GrabFood vs GoFood.
**Query pencarian:** ("usability" OR "efficiency") AND ("RTA") AND ("Grab" OR "Gojek")
**Database:** Google Scholar

| # | Study | Tahun | Method | Dataset | Result | Limitasi |
|---|---|---|---|---|---|---|
| 1 | Jimmy & Suhardi | 2026 | Kuantitatif | User Gojek | Usability pengaruhi loyalitas | Tidak bedah alur mikro |
| 2 | Handayani & Maria | 2025 | SUS & RTA | GrabMerchant | Skor 61,5 (Grade D) | Fokus sisi Penjual |
| 3 | Ruzaini & Rafiah | 2025 | Kuantitatif | User Go-Food | UX pengaruhi minat beli | Tidak ada uji efisiensi alur |
| 4 | Hutahaean, dkk. | 2025 | IPMA | User M-commerce | Efisiensi adalah prioritas | Fokus pada fitur makro |
| 5 | Bimantari Dewi, dkk. | 2025 | RTA & HE | User App XYZ | Masalah kognitif terdeteksi | Bukan studi perbandingan |

**Pola yang terlihat — Metode dominan:** Penggunaan System Usability Scale (SUS) sebagai data kuantitatif yang divalidasi dengan Retrospective Think Aloud (RTA) untuk menemukan akar masalah.

**Limitasi yang berulang:** Minimnya data performa objektif dan analisis beban kognitif pada perbandingan model user flow yang berbeda (seperti Single-Screen vs Multi-Step checkout).

---

## Latihan 2 — Gap Identification

Berdasarkan tabel di Latihan 1, identifikasi gap.

| Jenis Gap | Ditemukan? | Gap Statement |
|-----------|-----------|---------------|
| **Performance Gap** | [X] Ya | Hasil evaluasi pada beberapa platform (GrabMerchant & XYZ) di tahun 2025 menunjukkan skor usability masih di kategori "Marginal". |
| **Method Gap** | [X] Ya | Belum ada penelitian yang secara simultan menggabungkan metode RTA untuk membandingkan dua model user flow yang berbeda secara kompetitif. |
| **Data Gap** | [ ] Tidak | - |
| **Context Gap** | [X] Ya | Riset RTA tahun 2025 (Handayani) baru fokus pada sisi Merchant; konteks checkout sisi Konsumen (customer-facing) masih sangat minim dibahas secara mendalam. |

**Gap utama yang dipilih:** Context Gap & Methodological Application.

**Mengapa gap ini penting?**
> Alur checkout adalah titik kritis konversi. Tanpa analisis beban kognitif (RTA), perusahaan tidak dapat memetakan bagian alur mana yang paling melelahkan secara mental bagi pengguna. Riset ini mengisi celah dengan membandingkan model desain GrabFood vs GoFood untuk menentukan standar efisiensi terbaik.

---

## Latihan 3 — Baseline Selection

Pilih 2 baseline dari literatur yang sudah dibaca sebagai acuan pembanding dalam penelitian ini.

| # | Baseline | Mengapa Relevan | Mengapa Representatif | Apakah SOTA? | Sumber |
|---|----------|----------------|----------------------|-------------|--------|
| 1 | **Integrasi Metode SUS & Retrospective Think Aloud (RTA)** | Baseline ini relevan karena menguji aplikasi dalam ekosistem layanan *on-demand* yang serupa (Grab) untuk mendeteksi hambatan kognitif spesifik. | Mewakili standar terbaru dalam evaluasi *usability* yang tidak hanya mengandalkan angka, tapi juga narasi hambatan pengguna. | Ya (2025) | Handayani & Maria (2025) |
| 2 | **Importance Performance Matrix Analysis (IPMA)** | Relevan untuk memetakan bahwa variabel efisiensi dan kemudahan adalah prioritas utama (high importance) dalam loyalitas pengguna *m-commerce*. | Merupakan teknik analisis mutakhir yang digunakan untuk menentukan fokus perbaikan pada aplikasi layanan digital terbaru. | Ya (2025) | Hutahaean, dkk. (2025) |

**Apakah pemilihan baseline ini bisa dianggap straw man?** [ ] Ya / [X] Tidak

> **Justifikasi:** > Pemilihan baseline ini bukan merupakan *straw man comparison* karena kedua referensi tersebut adalah penelitian *State-of-the-Art* (SOTA) yang diterbitkan pada tahun 2025. Metode yang digunakan (RTA dan IPMA) merupakan metode yang *rigorous* dan sedang menjadi tren dalam riset sistem informasi saat ini. Dengan membandingkan penelitian saya terhadap standar yang kuat ini, hasil analisis efisiensi kognitif pada alur *checkout* GrabFood dan GoFood akan memiliki validitas ilmiah yang tinggi.

---

## Refleksi

> Apa perbedaan antara "belum ada yang meneliti ini" (klaim tanpa bukti) dengan research gap yang valid? Bagaimana cara membuktikan bahwa sebuah gap benar-benar ada?

**Jawaban:**
Klaim "belum ada yang meneliti" seringkali bersifat subjektif dan tidak memiliki landasan kuat, sementara **research gap yang valid** adalah pernyataan yang didukung oleh bukti nyata setelah melakukan pemetaan literatur (*literature mapping*). Gap yang valid secara eksplisit menunjukkan bahwa meskipun ada penelitian sebelumnya (seperti studi SOTA tahun 2025-2026), terdapat aspek tertentu—baik dari sisi metode, data, maupun konteks—yang belum terjawab secara tuntas atau memiliki hasil yang masih bisa dikembangkan.

Cara membuktikan sebuah gap benar-benar ada adalah dengan menyusun **Literature Matrix**. Melalui matriks tersebut, kita dapat memetakan kolom **Limitasi** dari setiap penelitian terbaru. Jika limitasi tersebut muncul berulang kali atau terdapat celah yang belum tersentuh—seperti riset sebelumnya yang hanya fokus pada sisi *merchant* (Handayani, 2025) atau loyalitas makro (Jimmy, 2026)—sedangkan riset kita masuk ke analisis mikro beban kognitif alur *checkout* pembeli, maka gap tersebut terbukti ada secara ilmiah dan valid untuk diteliti.