# WS-01: Distorsi & Paradigma

> **Bab 1 — Research Mindset in IT**

---

## Ringkasan Materi

### Research Trust Model

Pengetahuan ilmiah tidak muncul langsung dari kenyataan. Ia melewati **6 tahap transformasi** yang masing-masing rawan distorsi:

```
Reality → Data → Processing → Analysis → Inference → Knowledge
```

Etika mencegah distorsi yang disengaja (fabrikasi, cherry-picking). Validitas mendeteksi distorsi yang tidak disengaja (confounding variable, sampling bias).

### Tiga Jenis Validitas

| Jenis | Pertanyaan | Contoh Ancaman |
|-------|-----------|----------------|
| **Internal Validity** | Apakah hubungan kausal benar ada? | Confounding variable |
| **External Validity** | Apakah bisa digeneralisasi? | Dataset terlalu homogen |
| **Construct Validity** | Apakah mengukur hal yang benar? | Metrik tidak sesuai klaim |

### Paradigma Riset

Mata kuliah ini menggunakan pendekatan **Positivist** (fenomena TI bisa diukur objektif melalui eksperimen terkontrol) diperkuat **Design Science Research** (DSR). Penting untuk membedakan keduanya:

| Paradigma | Cara Kerja | Contoh di TI |
|-----------|-----------|---------------|
| **Positivis** | Uji hipotesis dengan eksperimen terkontrol | Apakah CNN lebih akurat dari RF pada dataset X? |
| **Design Science Research** | Bangun artefak (sistem/model/framework) untuk menguji proposisi | Dapatkah arsitektur hybrid CNN+LSTM membuktikan peningkatan recall ≥5%? |
| **Interpretivis** | Pahami makna melalui konteks & kualitatif | Bagaimana peneliti manafsirkan anomali data sensor IoT? |

Dalam DSR, artefak **bukan tujuan akhir** — ia adalah instrumen untuk menghasilkan pengetahuan. Pertanyaan riset tetap harus difalsifikasi.

### Mode Berpikir Peneliti

**Curious** (mempertanyakan fenomena) → **Critical** (mengevaluasi klaim berdasarkan bukti) → **Systematic** (merancang investigasi terstruktur dan reproducible).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Membuat sistem yang bekerja | Menghasilkan pengetahuan yang valid |
| Pertanyaan khas | "Bagaimana membuatnya jalan?" | "Apakah klaim ini benar?" |
| Ukuran sukses | Sistem berfungsi, client puas | Hipotesis terjawab, temuan tervalidasi |
| Kegagalan | Harus dihindari | Harus dilaporkan (negative result = kontribusi) |

### Istilah Penting

- **Research Mindset** — Pola pikir yang menuntut bukti dan mempertanyakan asumsi
- **Research Ethics** — Prinsip perilaku: kejujuran, objektivitas, keterbukaan, akuntabilitas
- **HARKing** — Hypothesizing After Results are Known — merumuskan hipotesis setelah melihat data
- **Falsifiability** — Hipotesis harus bisa dibuktikan salah

---

## Template A.1 — Research Mindset Self-Assessment

```
Nama Peneliti    : Alvira Libra Ramadhani
Tanggal          : 06 April 2026

1. Ketika membaca klaim "metode X 95% akurat":
   - Pertanyaan pertama saya:
   Bagaimana profil 20 responden tersebut dan apakah mereka memiliki keterikatan emosional/profesional yang memengaruhi penilaian?
   - Data yang dibutuhkan untuk verifikasi:
   Deskripsi demografi responden (pengalaman kerja, usia) dan skor mentah kuesioner sebelum dikonversi.

2. Posisi paradigma:
   - Pendekatan: [ ] Positivis  [ ] Interpretivis  [x] Design Science  [x] Mixed
   - Alasan: 
   Penelitian ini menggunakan pendekatan Mixed (kombinasi kuantitatif SUS dan kualitatif wawancara) serta Design Science karena melibatkan rancang bangun sistem menggunakan metode Waterfall.

3. Identifikasi distorsi:
   - Asumsi tersembunyi:
   Seluruh kasir dianggap sudah memiliki standar kemampuan operasional komputer yang sama.
   - Sumber bias potensial:
   Sampling Bias (responden hanya 20 pegawai Alfamart yang mungkin sudah terbiasa dengan sistem).
   - Langkah mitigasi:
   Menambahkan jumlah responden dari berbagai cabang gerai dengan tingkat pengalaman yang bervariasi.

4. Komitmen etika:
   - Data yang tidak akan dimanipulasi:
   Skor jawaban asli dari 10 pertanyaan SUS yang diberikan responden.
   - Batasan yang diakui sejak awal:
   Penelitian hanya dilakukan pada sampel terbatas (20 orang) di wilayah tertentu (Karawang).
```

---

## Latihan 1 — Identifikasi Distorsi

Pilih satu paper riset di bidang TI yang mengklaim "metode X meningkatkan performa." Telusuri setiap tahap Research Trust Model.

> **Panduan pencarian paper:** Gunakan [IEEE Xplore](https://ieeexplore.ieee.org), [ACM Digital Library](https://dl.acm.org), atau Google Scholar. Pilih paper **tahun 2020 ke atas**, di topik yang Anda minati: deteksi anomali, klasifikasi citra, NLP, keamanan siber, IoT, dsb.
>
> **Contoh domain TI:** "Deteksi anomali lalu-lintas jaringan menggunakan CNN — akurasi meningkat 94% vs baseline SVM 87%." Distorsi potensial: apakah dataset normal/anomali seimbang? Apakah hanya diuji pada satu vendor traffic?

**Paper yang dipilih:**
<<<<<<< HEAD
> Judul: 
PENGGUNAAN SISTEM INFORMASI POS (POINT OF SALE) DALAM MENINGKATKAN AKTIVITAS TRANSAKSI KASIR PADA PT SUMBER ALFARIA TRIJAYA ТВК
> Penulis (Tahun): 
Melawati Purwasih, dkk. (2023)
=======
> Judul: _______________________________________________
> Penulis (Tahun): ______________________________________
> Sumber/Link DOI: _____________________________________
>>>>>>> ffac99b58491f20c5b78603a2b315eb77ca446fd

| Tahap | Apa yang Dilakukan | Potensi Distorsi |
|-------|-------------------|-----------------|
| Reality → Data |Mengumpulkan data menggunakan metode deskriptif kuantitatif dengan sampel 20 responden pegawai Alfamart. |Sampling Bias: Jumlah 20 responden sangat kecil untuk skala perusahaan nasional, sehingga mungkin tidak mewakili kondisi seluruh kasir. |
| Data → Processing |Mengonversi jawaban kuesioner menjadi skor SUS dengan rumus: (Skor-1) untuk item ganjil dan (5-Skor) untuk item genap. |Manual Calculation Error: Risiko kesalahan manusia saat menghitung balik skor pada pertanyaan negatif (nomor genap). |
| Processing → Analysis |Melakukan uji validitas (Bivariate Pearson) dan reliabilitas (Cronbach's Alpha) menggunakan software SPSS. |Pearson) dan reliabilitas (Cronbach's Alpha) menggunakan software SPSS.
	

Tool Dependency: Mengandalkan statistik tanpa melihat apakah ada pola jawaban seragam (straightlining) dari responden yang jenuh. |
| Analysis → Inference |Menghasilkan skor rata-rata SUS sebesar 95,7 yang masuk kategori acceptable. |Halo Effect: Skor yang sangat tinggi (95,7) bisa jadi muncul karena responden merasa sungkan memberi nilai buruk pada sistem kantornya sendiri. |
| Inference → Knowledge |Menyimpulkan bahwa aplikasi POS ini dapat membantu tugas pihak terkait dan meningkatkan pelayanan secara sistematis. |Overgeneralization: Menganggap kesuksesan di satu titik pengamatan sebagai kebenaran mutlak untuk semua implementasi POS di berbagai kondisi gerai. |

**Distorsi paling besar di tahap:** Reality → Data

**Dua distorsi spesifik yang teridentifikasi:**
1. Sampling Bias: Peneliti hanya menggunakan 20 responden, yang mana angka ini sangat kecil untuk menjamin validitas eksternal pada sistem yang digunakan secara masif di banyak cabang.Sampling Bias: Peneliti hanya menggunakan 20 responden, yang mana angka ini sangat kecil untuk menjamin validitas eksternal pada sistem yang digunakan secara masif di banyak cabang.
2. Social Desirability Bias: Karena responden adalah pegawai internal PT Sumber Alfaria Trijaya Tbk, ada kecenderungan mereka memberikan jawaban yang "aman" atau positif agar terlihat mendukung kebijakan perusahaan, sehingga skor SUS menjadi sangat tinggi (95,7).

---

## Latihan 2 — Analisis Kasus Etika

Skenario: Seorang peneliti menemukan bahwa jika 3 data point outlier dihapus, hasil eksperimennya menjadi signifikan. Dengan outlier, hasilnya tidak signifikan.

| Perspektif | Analisis |
|------------|---------|
| Kejujuran ilmiah |Peneliti harus melaporkan temuan apa adanya tanpa memanipulasi data demi mendapatkan hasil signifikan, karena menyembunyikan outlier tanpa alasan teknis merupakan bentuk ketidakjujuran akademik. |
| Transparansi |Peneliti wajib menjelaskan alasan penghapusan outlier secara terbuka (misalnya karena kesalahan alat atau prosedur) dan menyajikan perbandingan hasil data sebelum serta sesudah dihapus agar pembaca dapat menilai objektivitasnya. |
| Peer review |Peneliti harus membiarkan penelaah (reviewer) mengevaluasi apakah penghapusan tersebut valid secara metodologi atau hanya upaya untuk memaksakan hipotesis agar diterima. |

**Keputusan akhir dan justifikasi:**
> Peneliti harus melaporkan kedua versi data (dengan dan tanpa outlier) atau tetap menyertakan outlier jika tidak ada bukti kuat bahwa data tersebut cacat secara teknis.
> Justifikasi: Dalam riset, hasil yang tidak signifikan (negative results) tetap merupakan kontribusi pengetahuan yang valid. Menghapus data hanya agar hasil terlihat "bagus" atau signifikan melanggar prinsip objektivitas dan kejujuran dalam Research Trust Model. Terutama pada sistem krusial seperti POS, data yang tidak biasa (outlier) bisa jadi mencerminkan error sistem yang justru penting untuk dilaporkan.

---

## Latihan 3 — Posisi Paradigma

**Topik riset:** Evaluasi Usability dan Implementasi Sistem Informasi Point of Sale (POS) pada PT Sumber Alfaria Trijaya Tbk.

> **Skala 1–5:** 1 = tidak sesuai sama sekali dengan topik ini, 5 = sangat sesuai dan dominan digunakan pada riset bertopik serupa.

| Kriteria | Positivis | Interpretivis | Design Science |
|----------|-----------|---------------|----------------|
<<<<<<< HEAD
| Kesesuaian dengan topik (1–5) | 4 | 2 | 5 |
| Jenis data yang dikumpulkan |Data kuantitatif berupa skor kuesioner System Usability Scale (SUS) dan hasil uji validitas/reliabilitas SPSS. |Data kualitatif berupa hasil wawancara mengenai faktor-faktor yang mempengaruhi kepuasan pengguna. |Artefak perangkat lunak (Sistem POS) , diagram alir, dan hasil pengujian BlackBox. |
| Limitasi paradigma |Cenderung kaku dan mungkin mengabaikan pengalaman emosional subjektif pengguna di luar angka statistik. |Hasil riset sangat subjektif dan sulit untuk digeneralisasikan ke seluruh gerai Alfamart secara nasional |Terlalu fokus pada efektivitas fungsional sistem (apakah sistem jalan) daripada memahami fenomena sosial di lingkungan kerja. |
=======
| Kesesuaian dengan topik (1–5) | *Contoh: 4 — topik kuantitatif, cocok uji hipotesis* | *Contoh: 2 — topik tidak studi makna/konteks* | *Contoh: 5 — membangun artefak untuk uji klaim* |
| Jenis data yang dikumpulkan | *Metrik numerik, log eksperimen* | *Wawancara, observasi kualitatif* | *Hasil uji artefak, komparasi kinerja* |
| Limitasi paradigma | | | |
>>>>>>> ffac99b58491f20c5b78603a2b315eb77ca446fd

**Paradigma yang dipilih:** Design Science Research.
**Alasan:** Penelitian ini berfokus pada pengembangan dan evaluasi sebuah artefak (Sistem Informasi POS) menggunakan metode Waterfall untuk memecahkan masalah praktis, yaitu meningkatkan efektivitas transaksi kasir. Pengetahuan ilmiah dihasilkan melalui pengujian langsung terhadap artefak tersebut menggunakan metode BlackBox dan SUS.

---

## Refleksi

> Sebelum membaca materi ini, apakah pernah mempertanyakan klaim "95% akurat"? Setelah memahami rantai distorsi, pertanyaan apa yang sekarang akan diajukan saat membaca paper?

**Jawaban:**
> Sebelum memahami materi ini, saya cenderung menerima angka statistik seperti skor SUS 95,7  sebagai bukti mutlak bahwa sebuah sistem sudah sempurna. Saya jarang mempertanyakan proses di balik angka tersebut.
> Setelah memahami rantai distorsi dalam Research Trust Model, pertanyaan yang akan saya ajukan saat membaca paper adalah:
1. Tahap Reality → Data: Apakah 20 responden ini benar-benar mewakili populasi kasir yang beragam, atau hanya diambil dari satu kelompok yang homogen?
2. Tahap Analysis → Inference: Apakah skor tinggi ini benar-benar karena kualitas sistem, atau ada variabel pengganggu (confounding variable) seperti tekanan kerja atau keinginan responden untuk menyenangkan peneliti?
3. Validitas: Apakah metrik yang digunakan (SUS) sudah benar-benar mengukur apa yang diklaim (Kepuasan vs Kemampuan teknis)?
