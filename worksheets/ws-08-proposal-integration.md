# WS-08: Proposal Integration (UTS)

> **Bab 8 — Proposal & Checkpoint**

---

## Ringkasan Materi

### Proposal = Satu Argumen Utuh

Proposal riset bukan kumpulan bab yang independen. Ia adalah **satu argumen** yang mengalir dari masalah ke rencana solusi. Jika satu koneksi putus, seluruh proposal kehilangan koherensi.

### Integration Map — 6 Koneksi Kritis

```
Problem (Bab 2) → Gap (Bab 3) → RQ & H (Bab 4) → Metrik (Bab 5) → Sistem (Bab 6) → Eksperimen (Bab 7)
```

| Koneksi | Pertanyaan Verifikasi |
|---------|----------------------|
| Problem → Gap | Apakah gap muncul dari analisis literatur terhadap masalah? |
| Gap → RQ | Apakah RQ langsung menjawab gap yang teridentifikasi? |
| RQ → Metrik | Apakah setiap variabel di RQ punya metrik terdefinisi? |
| Metrik → Sistem | Apakah setiap metrik bisa diukur oleh komponen sistem? |
| Sistem → Eksperimen | Apakah desain eksperimen menggunakan sistem sebagai instrumen? |

### Koherensi Vertikal + Horizontal

- **Vertikal** — Alur logis atas-ke-bawah (problem → experiment). Setiap section menjawab pertanyaan yang diangkat section sebelumnya dan memunculkan pertanyaan baru.
- **Horizontal** — Konsistensi terminologi (nama variabel di RQ = di hipotesis = di metrik = di desain)

**Operasionalisasi Red Thread** (benang merah):
```
Bab 2 (Problem) → | memperkenalkan masalah X + evidensi |
                          ↓ menimbulkan pertanyaan: "apa akar gap-nya?"
Bab 3 (Gap)     → | menjawab pertanyaan tadi + membuka "lalu apa yang perlu diteliti?" |
                          ↓
Bab 4 (RQ/H)    → | menjawab gap dengan pertanyaan spesifik + prediksi terukur |
                          ↓
Bab 5-7 (Method)→ | menjawab RQ melalui desain eksperimen yang tepat |
```
Jika ada lompatan (section B tidak menjawab pertanyaan section A), red thread putus.

### Jebakan Kognitif

| Jebakan | Deskripsi |
|---------|----------|
| "Selling" Introduction | Menulis promosi, bukan menyajikan data dan gap |
| Copy-paste Methodology | Menyalin deskripsi tekstbook tanpa menyesuaikan ke RQ |
| Optimistic Timeline | Meremehkan waktu implementasi; selalu tambah buffer 30-50% |
| No Possibility of Failure | Mengimplikasikan hasil pasti sukses — proposal jujur mengakui H₀ mungkin tidak ditolak |

### Struktur Proposal

1. **Pendahuluan** — Latar belakang + problem statement (Bab 1-2)
2. **Tinjauan Pustaka** — Literature review + gap + baseline (Bab 3)
3. **RQ / Kontribusi / Hipotesis** — (Bab 4)
4. **Metodologi** — Metrik + sistem + desain eksperimen (Bab 5-7)
5. **Timeline & Output**

### Istilah Penting

- **Integration Map** — Diagram 6 koneksi kritis antar komponen proposal
- **Vertical Coherence** — Alur logis atas-ke-bawah
- **Horizontal Coherence** — Konsistensi terminologi di semua bagian
- **Checkpoint** — Titik self-assessment sebelum transisi dari desain ke eksekusi

---

## Template A.8 — Integration Checklist

```
PROPOSAL INTEGRATION CHECKLIST

Koneksi Vertikal (Flow Atas-Bawah):
  [X] Problem → Gap: masalah terdokumentasi di literatur
  [X] Gap → RQ: pertanyaan menjawab gap spesifik
  [X] RQ → Hypothesis: hipotesis memprediksi jawaban
  [X] Hypothesis → Metric: metrik mengukur variabel dalam hipotesis
  [X] Metric → System: komponen sistem menghasilkan/mengukur metrik
  [X] System → Experiment: desain eksperimen menggunakan sistem

Koneksi Horizontal (Konsistensi):
  [X] Istilah sama di semua bagian
  [X] Variabel di RQ = variabel di hipotesis = metrik di desain
  [X] Scope tidak berubah dari masalah ke eksperimen

Cognitive Trap Checklist:
  [ ] Tidak ada paragraf "promosi" di pendahuluan (hanya data & gap)
  [ ] Metodologi disesuaikan ke RQ, bukan copy-paste textbook
  [ ] Timeline sudah ditambah buffer 30-50% dari estimasi awal
  [ ] Proposal mengakui kemungkinan H0 tidak ditolak (honest uncertainty)
  [ ] Tidak ada klaim "pasti berhasil" atau "meningkatkan signifikan"

Rubrik Self-Assessment:
<<<<<<< HEAD
| Kriteria | 1 (Lemah) | 2 (Cukup) | 3 (Baik) | Skor |
|----------|-----------|-----------|----------|------|
| Koherensi |          |           |   [X]    |  3   |
| Specificity |        |           |   [X]    |  3   |
| Feasibility |        |           |   [X]    |  3   |
| Rigor     |          |           |   [X]    |  3   |
=======
| Kriteria     | 1 (Lemah)                                        | 2 (Cukup)                                     | 3 (Baik)                                           | Skor |
|------------- |--------------------------------------------------|-----------------------------------------------|----------------------------------------------------|------|
| Koherensi    | >2 koneksi vertikal terputus                     | 1-2 koneksi lemah, argumen masih bisa diikuti | Semua 6 koneksi terhubung, red thread jelas        |      |
| Specificity  | Variabel/metrik masih abstrak, tidak ada angka   | Sebagian metrik terdefinisi numerik           | Semua metrik + threshold + unit pengukuran jelas   |      |
| Feasibility  | Timeline >6 bulan tanpa memperhitungkan sumber   | Timeline 3-6 bulan dengan asumsi tertentu     | Timeline 1-3 bulan realistis dengan rencana detail |      |
| Rigor        | Baseline tidak jelas atau straw man              | 1-2 baseline dengan justifikasi partial       | 2+ baseline SOTA + justifikasi pemilihan lengkap   |      |
>>>>>>> ffac99b58491f20c5b78603a2b315eb77ca446fd
```

---

## Latihan 1 — Kompilasi Proposal Mini

Kumpulkan hasil dari WS-02 sampai WS-07 menjadi satu ringkasan proposal.

| Komponen | Sumber | Isi (1-2 kalimat) |
|----------|--------|-------------------|
| Problem Statement | WS-02 | Pengguna Generasi Z sering mengalami hambatan efisiensi kognitif dan ketidakpuasan saat melakukan proses *checkout* akibat antarmuka *super-app* yang terlalu padat informasi. Celah mengenai aplikasi mana yang lebih optimal antara GoFood dan GrabFood untuk kelompok usia ini belum diteliti secara komparatif. |
| Gap | WS-03 | Belum ada studi empiris yang membandingkan efisiensi kognitif secara objektif (*Time on Task*) dan kepuasan secara subjektif (Skor SUS) pada fitur *checkout* GoFood vs GrabFood khusus untuk populasi Generasi Z. |
| RQ | WS-04 | Apakah terdapat perbedaan signifikansi pada efisiensi kognitif (*Time on Task*) dan tingkat kepuasan pengguna (*System Usability Scale*) antara proses *checkout* GoFood dan GrabFood pada Generasi Z? |
| Hipotesis | WS-04 | H₁: Terdapat perbedaan rata-rata waktu transaksi (*Time on Task*) dan skor kepuasan (*SUS*) yang signifikan antara fitur *checkout* GoFood dan GrabFood pada pengguna Generasi Z. |
| Variabel & Metrik | WS-05 | IV = jenis antarmuka aplikasi (*GoFood vs GrabFood*); DV = efisiensi kognitif (*Time on Task* dalam detik) + kepuasan pengguna (Skor global SUS skala 0-100). |
| Sistem | WS-06 | Sistem yang diuji adalah alur antarmuka dan arsitektur informasi fitur *checkout* pada aplikasi GoFood dan GrabFood versi terbaru. Komponen sistem ini memproses tugas pencarian menu hingga halaman ringkasan pesanan akhir. |
| Desain Eksperimen | WS-07 | Desain eksperimen menggunakan *Within-Subject Design* dengan teknik *Counterbalancing* pada 35 responden Generasi Z. Responden mengeksekusi skenario tugas belanja makanan yang identik pada kedua aplikasi secara bergantian. |

---

## Latihan 2 — Integration Checklist

Verifikasi 6 koneksi kritis. Isi dengan merujuk tabel di Latihan 1.

| Koneksi | Status | Bukti |
|---------|--------|-------|
| Problem → Gap | ✅ | Gap muncul langsung dari kajian 14 literatur bab sebelumnya yang menunjukkan belum adanya penelitian komparatif empiris mengenai efisiensi kognitif proses checkout khusus untuk populasi Generasi Z di Indonesia. |
| Gap → RQ | ✅ | RQ secara linier menanyakan apakah terdapat perbedaan signifikansi pada efisiensi kognitif (Time on Task) dan tingkat kepuasan pengguna (SUS) antara proses checkout GoFood dan GrabFood. |
| RQ → Hypothesis | ✅ | Hipotesis (H₁) secara terukur memprediksi adanya perbedaan nilai rata-rata (mean) performa waktu transaksi dan skor kepuasan yang signifikan secara statistik di antara kedua aplikasi tersebut. |
| Hypothesis → Metric | ✅ | Variabel dalam hipotesis diturunkan secara operasional menjadi metrik kuantitatif, yaitu durasi kecepatan dalam satuan detik (Time on Task) dan skor kuesioner psikometrik global standar (SUS Score). |
| Metric → System | ✅ | Metrik yang ditentukan diukur langsung melalui interaksi pengguna pada komponen riil sistem, yaitu alur tata letak antarmuka, arsitektur informasi, hingga halaman ringkasan pesanan akhir (checkout page) GoFood dan GrabFood. |
| System → Experiment | ✅ | Pengujian komponen sistem tersebut diimplementasikan ke dalam desain eksperimen Within-Subject dengan membandingkan performa 35 responden yang sama pada kedua aplikasi lewat skenario tugas yang identik. |

**Koneksi mana yang paling lemah?** Koneksi Metric → System (WS-05 ke WS-06)

**Bagaimana cara memperkuatnya?**
> Untuk memperkuat koneksi tersebut, peneliti harus memastikan secara spesifik bagian komponen sistem atau elemen antarmuka (*user interface*) mana saja pada *checkout page* kedua aplikasi yang paling memengaruhi fluktuasi metrik *Time on Task*. Hal ini dilakukan dengan memetakan secara detail setiap tahapan alur sistem (seperti pemuatan menu, penentuan alamat, hingga penyeleksian opsi pembayaran) ke dalam bentuk variabel kontrol yang terstandardisasi, sehingga rekaman *screen recording* dapat menangkap dengan tepat komponen sistem mana yang memicu tingginya beban kognitif atau penundaan waktu.

**Konsistensi horizontal — apakah istilah dan scope konsisten?** [X] Ya / [ ] Tidak
> Jika tidak, di bagian mana terjadi inkonsistensi? Seluruh istilah utama (seperti "Efisiensi Kognitif", "Kepuasan Pengguna", "Time on Task", "SUS Score", dan "Generasi Z") serta ruang lingkup penelitian (proses pencarian menu hingga *checkout page* makanan) sudah terjaga secara konsisten dari penentuan masalah hingga desain eksperimen tanpa adanya pergeseran makna atau cakupan riset.

---

## Latihan 3 — Rubrik Self-Assessment

Evaluasi proposal mini menggunakan rubrik.

| Kriteria | Skor (1-3) | Justifikasi |
|----------|-----------|-------------|
| Koherensi | 3 | Seluruh elemen dari penentuan masalah beban kognitif hingga desain eksperimen komparatif terhubung secara logis, runtut, dan membentuk kesatuan alur penelitian yang utuh (*seamless*). |
| Specificity | 3 | Setiap metrik pengujian telah didefinisikan secara numerik dan spesifik, yaitu *Time on Task* dalam satuan detik dan tingkat kepuasan menggunakan nilai indeks global *System Usability Scale* (0-100). |
| Feasibility | 3 | Penelitian sangat layak dijalankan karena pengujian menggunakan aplikasi yang sudah matang di pasar (*GoFood* dan *GrabFood*) serta dijalankan langsung pada perangkat pengujian mandiri milik peneliti tanpa biaya produksi sistem baru. |
| Rigor | 3 | Metodologi penelitian sangat ketat karena menggunakan rancangan *Within-Subject Design* dengan teknik *Counterbalancing* untuk mengeliminasi bias, serta didukung analisis statistik parametrik uji *Paired Samples T-Test*. |

**Skor total:** 12 / 12

**Apakah proposal siap untuk fase eksekusi?** [X] Ya / [ ] Belum
> Jika belum, apa yang perlu diperbaiki? Proposal sudah sepenuhnya terintegrasi, koheren, dan memenuhi seluruh parameter metodologi ilmiah yang ketat, sehingga siap untuk langsung dilanjutkan ke fase eksekusi pengumpulan data di lapangan.

---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-08, bagian mana yang paling mudah dan paling sulit? Mengapa? Apa yang akan dilakukan berbeda jika mengulang dari awal?

**Bagian termudah:** Bagian termudah adalah WS-02 (Problem Statement) dan WS-04 (Formulasi RQ & Hipotesis). Hal ini dikarena fenomena masalah beban kognitif pada aplikasi *food delivery* sangat dekat dengan kehidupan sehari-hari Generasi Z, sehingga perumusan masalah, pertanyaan penelitian, dan penentuan arah dugaan hipotesis dapat dikembangkan secara intuitif dan lancar berdasarkan observasi awal.

**Bagian tersulit:** Bagian tersulit adalah WS-07 (Desain Eksperimen) dan WS-08 (Proposal Integration Checklist). Kesulitannya terletak pada kewajiban untuk menjaga validitas internal eksperimen agar benar-benar ketat (*rigorous*), memformulasikan teknik *Counterbalancing* yang tepat untuk mengeliminasi efek belajar (*learning effect*), serta memastikan seluruh komponen dari awal hingga akhir mengalir secara koheren tanpa ada pergeseran *scope*.

**Yang akan dilakukan berbeda:**
> Jika mengulang dari awal, peneliti akan melakukan studi literatur dan pemetaan metrik antarmuka (*UI metrics*) secara lebih mendalam dan spesifik di tahap awal sebelum menyusun skenario tugas eksperimen. Dengan demikian, peneliti dapat mengidentifikasi komponen-komponen mikro pada fitur *checkout* (seperti penempatan tombol, kejelasan informasi biaya, atau jumlah langkah interaksi) yang berpotensi menjadi variabel pengganggu sejak dini, sehingga struktur instrumen pengujian dan integrasi sistem dapat dirancang dengan jauh lebih efisien dan matang.
