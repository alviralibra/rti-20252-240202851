# WS-02: Problem Statement

> **Bab 2 — Problem Formulation & System Context**

---

## Ringkasan Materi

### Problem Formation Model

Masalah riset melewati 5 tahap transformasi. Melompat langsung dari Reality ke Variable adalah kesalahan paling umum.

```
Reality → Observed Issue (Symptom) → Diagnosed Problem (Root Cause)
→ Researchable Problem (Scoped) → Measurable Variable (Operationalized)
```

### Topic ≠ Problem ≠ Research Problem

| Level | Contoh | Status |
|-------|--------|--------|
| **Topik** | Keamanan IoT | Terlalu luas, tidak bisa diuji |
| **Problem** | MQTT tidak terenkripsi | Spesifik tapi belum riset |
| **Research Problem** | Belum ada studi membandingkan overhead TLS 1.3 vs DTLS pada MQTT di IoT RAM < 64KB | Bisa dirancang eksperimennya |

### Symptom vs Root Cause

Apa yang diamati (gejala) ≠ mengapa terjadi (akar masalah). Gunakan **5 Whys** atau **Fishbone Diagram** untuk menggali.

Contoh: "User meninggalkan checkout" (symptom) → "Waktu loading > 8 detik karena API call sequential" (root cause).

### System Thinking

Setiap masalah riset TI harus terikat pada komponen sistem: **Input → Process → Output → Outcome → Constraints → Stakeholders**.

### Problem Quality Check

Masalah riset yang layak harus memenuhi 5 kriteria:
- **Clarity** — Satu orang membaca akan paham
- **Measurability** — Ada metrik kuantitatif
- **Relevance** — Penting untuk domain
- **Testability** — Bisa gagal (falsifiable)
- **Impact** — Ada kontribusi jika terjawab

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Menyelesaikan masalah (*solve*) | Memahami dan membuktikan (*understand & prove*) |
| Masalah | Bug, error, fitur belum ada | Gap dalam pengetahuan |
| Scope | Selesaikan semua yang perlu | Batasi agar bisa dibuktikan |
| Output | Working system | Evidence, paper, replicable findings |

### Istilah Penting

- **Problem Statement** — Formulasi tertulis: konteks sistem + gap + dampak + justifikasi
- **System Context** — Deskripsi lengkap: input, proses, output, outcome, constraints, stakeholders
- **Problem Drift** — Masalah "bermutasi" dari pendahuluan ke metodologi karena statement awal tidak presisi
- **Solution-First Thinking** — Memulai dari solusi tanpa masalah yang jelas — berbahaya dalam riset
- **Operational Definition** — Definisi variabel yang cukup jelas agar peneliti lain bisa mengukur hal yang sama

---

## Template A.2 — Problem Statement Builder

```
PROBLEM STATEMENT BUILDER

Domain & Konteks
  Domain   : Human-Computer Interaction (HCI) / User Experience (UX).
  Konteks  : Proses penyelesaian pesanan (checkout) pada layanan pesan antar makanan (On-Demand Food Delivery) melalui perangkat mobile.

System Context
  Input       : Data keranjang belanja (menu), lokasi pengantaran, dan pilihan promo/voucher.
  Process     : Navigasi antarmuka untuk melakukan konfirmasi pesanan (pilihan alat makan, catatan, hingga metode pembayaran).
  Output      : Status pesanan siap dikirim ke resto/driver.
  Outcome     : Pengguna dapat memesan makanan dengan cepat tanpa merasa bingung (beban kognitif rendah).
  Constraints : Keterbatasan perhatian pengguna (limited attention span) saat lapar atau terburu-buru.
  Stakeholders: Pengguna aplikasi, UX Designer, dan penyedia layanan (Grab/Gojek).

Fenomena → Problem
  Fenomena yang diamati             : Pengguna seringkali ragu atau menghabiskan waktu lama di halaman checkout untuk memastikan pesanan dan promo sudah benar.
  Gejala (symptom) yang terukur     : Variasi waktu penyelesaian tugas (task completion time) yang berbeda signifikan antar aplikasi saat kondisi pengguna tidak fokus.
  Masalah yang didiagnosis          : Beban kognitif yang berbeda akibat desain alur; model Single-Screen (GoFood) yang memusatkan informasi vs model Wizard-Step (GrabFood) yang membagi informasi.
  Masalah riset (researchable)      : Manakah model alur (User Flow) yang memberikan efisiensi kognitif lebih baik bagi pengguna dalam menyelesaikan transaksi checkout?
  Variabel yang terukur             : Waktu penyelesaian (detik) dan skor kegunaan (misalnya melalui kuesioner singkat setelah tes).

Problem Quality Check
  [ ] Clarity — Jelas membandingkan dua alur pada aplikasi populer.
  [ ] Measurability — Menggunakan metrik waktu (detik).
  [ ] Relevance — Sangat relevan untuk industri on-demand service.
  [ ] Testability — Bisa dibuktikan mana yang lebih efisien melalui eksperimen.
  [ ] Impact — Memberikan wawasan desain alur yang paling manusiawi.

Problem Statement (1 paragraf):
  Kompleksitas antarmuka pada tahap checkout aplikasi on-demand service seperti GrabFood dan GoFood seringkali meningkatkan beban kognitif pengguna, yang berdampak pada kecepatan transaksi. Meskipun kedua aplikasi memiliki fungsi yang sama, perbedaan penerapan alur antara Single-Screen dan Wizard-Step menciptakan pengalaman pengguna yang berbeda secara signifikan. Penelitian ini bertujuan untuk menganalisis efisiensi kognitif pengguna melalui eksperimen perbandingan kedua alur tersebut. Hasil dari penelitian ini diharapkan dapat memberikan rekomendasi pola desain navigasi yang paling optimal untuk mendukung efisiensi waktu dan kenyamanan berpikir pengguna dalam menggunakan layanan pesan antar makanan.
```

---

## Latihan 1 — Dari Topik ke Masalah Riset

Pilih satu topik di bidang TI yang diminati. Transformasikan melalui 5 tahap Problem Formation Model.

**Topik awal:** Efisiensi navigasi pada aplikasi food delivery.

| Tahap | Hasil |
|-------|-------|
| Reality |Pengguna sering merasa bingung atau "stuck" saat ingin memasang promo di halaman checkout. |
| Observed Issue (Symptom) |Durasi rata-rata pengguna di halaman checkout mencapai lebih dari 15 detik sebelum klik "Order". |
| Diagnosed Problem (Root Cause) |Informasi yang terlalu menumpuk di satu layar meningkatkan beban berpikir (cognitive load). |
| Researchable Problem |Eksperimen perbandingan efisiensi alur Single-Screen (Gojek) vs Wizard-Step (Grab). |
| Measurable Variable |Time on Task (detik) dan jumlah kesalahan klik pengguna. |

**Apakah terjebak solution-first thinking?** [ ] Ya / [x] Tidak
> 

---

## Latihan 2 — System Context Decomposition

Gambarkan konteks sistem dari masalah riset di Latihan 1.

| Komponen | Deskripsi |
|----------|----------|
| Input |Pemilihan menu, penentuan alamat, dan pemilihan voucher diskon. |
| Process |Interaksi pengguna dengan elemen antarmuka (tombol, dropdown, pop-up konfirmasi). |
| Output |Pesanan terkunci dan siap diproses ke sistem pembayaran. |
| Outcome |Terciptanya pengalaman pemesanan yang cepat dan intuitif bagi pengguna. |
| Constraints |Gangguan eksternal (distraction) dan keterbatasan memori jangka pendek pengguna. |
| Stakeholders |Pelanggan lapar (pengguna utama) dan pengembang aplikasi. |

**Komponen mana yang paling relevan dengan masalah riset?** Process

---

## Latihan 3 — Problem Quality Check

Evaluasi problem statement yang sudah dibuat menggunakan 5 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Clarity |5 |Sangat jelas karena membandingkan dua aplikasi yang sudah dikenal luas. |
| Measurability |5 |Menggunakan detik sebagai satuan waktu yang sangat objektif. |
| Relevance |5 |Sangat penting bagi perkembangan industri aplikasi di Indonesia. |
| Testability |5 |Sangat mudah diuji dengan meminta responden mencoba aplikasi secara langsung. |
| Impact |4 |Memberikan kontribusi pada standar desain UX yang lebih baik. |

**Skor total:** 24 / 25

**Problem statement versi final (1 paragraf):**
> Kompleksitas antarmuka pada tahap checkout aplikasi on-demand service seperti GrabFood dan GoFood seringkali meningkatkan beban kognitif pengguna, yang berdampak pada kecepatan transaksi. Meskipun kedua aplikasi memiliki fungsi yang sama, perbedaan penerapan alur antara Single-Screen dan Wizard-Step menciptakan pengalaman pengguna yang berbeda secara signifikan. Penelitian ini bertujuan untuk menganalisis efisiensi kognitif pengguna melalui eksperimen perbandingan kedua alur tersebut. Hasil dari penelitian ini diharapkan dapat memberikan rekomendasi pola desain navigasi yang paling optimal untuk mendukung efisiensi waktu dan kenyamanan berpikir pengguna dalam menggunakan layanan pesan antar makanan.


---

## Refleksi

> Bandingkan "masalah" yang biasa ditemui saat coding (bug, error) dengan masalah riset. Apa perbedaan fundamental dalam cara mendefinisikan dan mendekati keduanya?

**Jawaban:**
> Perbedaan fundamentalnya adalah pada tujuan dan cakupannya. Masalah saat coding (bug/error) adalah masalah teknis operasional yang bersifat mendesak untuk diselesaikan agar sistem berfungsi (Engineering). Solusinya biasanya sudah pasti (misal: memperbaiki sintaks). Sedangkan masalah riset adalah upaya untuk mencari kebenaran atau pola tertentu melalui data (Understanding). Masalah riset tidak selalu berarti sistemnya "rusak", melainkan kita ingin membuktikan mana sistem yang "lebih baik" berdasarkan bukti empiris. Riset membutuhkan metodologi yang sistematis (seperti eksperimen tadi) agar hasilnya bisa dipertanggungjawabkan secara ilmiah, bukan sekadar memperbaiki kode yang eror.
