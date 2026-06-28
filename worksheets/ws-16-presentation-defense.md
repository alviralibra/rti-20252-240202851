# WS-16: Presentation & Defense (UAS)

> **Bab 16 — Presentasi & Pertahanan Ilmiah**

---

## Ringkasan Materi

### Scientific Defense Model

```
Research Work → Presentation → Questioning → Defense → Evaluation → Acceptance
```

### Presentasi ≠ Ringkasan Paper

| Paper | Presentasi |
|-------|-----------|
| Dibaca (self-paced) | Didengar (presenter-paced) |
| Detail lengkap | Ide kunci + highlight |
| Tabel numerik detail | Grafik visual + angka kunci |
| Pembaca bisa re-read | Audiens dengar sekali |

**Prinsip:** Presentasi membutuhkan **reformulasi**, bukan kompresi. Medium berbeda = pendekatan berbeda.

### Claim-Evidence-Reasoning (CER)

Setiap jawaban defense harus memiliki:
1. **Claim** — Pernyataan yang dijawab
2. **Evidence** — Data/fakta pendukung
3. **Reasoning** — Logika yang menghubungkan evidence ke claim

**Contoh:**
| Pertanyaan | Bad Answer | Good Answer (CER) |
|-----------|-----------|-------------------|
| "Kenapa hanya 3 dataset?" | "Tiga sudah cukup" | "3 dataset mewakili variasi: small-clean, medium-clean, medium-noisy [E]. Generalisasi perlu validasi lanjut — listed as limitation [R]" |
| "Hasil DS-3 menurun?" | "Itu outlier" | "Ya, karena distribusi heavy-tail melanggar asumsi Gaussian [E]. Ini menunjukkan boundary condition metode [R]" |
| "Effect size?" | "p=0.003, jadi signifikan" | "Cohen's d=1.2 (large effect) [E] — bukan hanya signifikan tapi substansial [R]" |

### Slide Design — One Slide, One Message

**Optimal 9-Slide Plan (15 menit):**

| # | Slide | Waktu | Pesan |
|---|-------|-------|-------|
| 1 | Title + context | 1 min | Apa ini tentang apa |
| 2 | Problem + motivation | 2 min | Mengapa penting |
| 3 | Gap + RQ | 1.5 min | Apa yang belum terjawab |
| 4 | Method overview | 2 min | Bagaimana dijawab (diagram) |
| 5 | Key result — tabel | 2 min | Temuan utama |
| 6 | Key result — grafik | 2 min | Pola visual |
| 7 | Interpretation + failure | 2 min | Apa artinya |
| 8 | Limitation + future | 1.5 min | Batasan & arah |
| 9 | Conclusion + contribution | 1 min | Closing message |

### Anticipatory Defense

Prediksi pertanyaan berdasarkan kategori:

| Kategori | Contoh Pertanyaan |
|---------|------------------|
| Problem | "Mengapa masalah ini penting?" |
| Gap | "Bagaimana dengan studi X yang sudah menjawab ini?" |
| Method | "Mengapa metode ini, bukan Y?" |
| Results | "Bagaimana menjelaskan anomali di DS-3?" |
| Generalization | "Apakah bisa diterapkan di domain lain?" |

### Tiga Prinsip Jawaban

1. **Direct** — Jawab dulu, elaborasi kemudian
2. **Data-based** — Tunjuk evidence spesifik
3. **Honest** — Akui limitasi jika memang ada

### Jebakan Kognitif

1. "Presentasi = semua yang ada di paper" → terlalu padat
2. "Slide cantik = presentasi bagus" → konten > estetika
3. "Tidak bisa jawab = gagal" → "I don't know, but..." menunjukkan kejujuran
4. "Tidak perlu latihan — saya paham riset saya" → latihan = menemukan celah

---

## Template A.16 — Defense Preparation Sheet

```
DEFENSE PREPARATION

Slide Deck Plan:
  Total slides   : 11
  Time per slide : ~1.3 min
  Total time     : 15 menit

Slide Outline:
| # | Pesan Utama | Visual | Waktu |
|---|-------------|--------|-------|
| 1 | Title (Analisis Kognitif Efisiensi Checkout GoFood vs GrabFood Gen Z) | Title slide + mockup aplikasi | 30s   |
| 2 | Problem (Kompleksitas alur checkout memicu friksi kognitif bagi Gen Z) | Diagram alur perbandingan klik halaman checkout | 2min  |
| 3 | Gap + RQ (Penggabungan metrik obyektif durasi dan subyektif SUS) | Tabel pembeda riset dari literatur terdahulu | 2min  |
| 4 | Method Overview (Desain eksperimen terkontrol *within-subject*) | Flowchart eksperimen (Task & Google Form SUS) | 2min  |
| 5 | Key Result — Tabel (Hasil uji SPSS Paired Samples t-test) | Tabel ringkasan mean durasi, p-value, & effect size | 2min  |
| 6 | Key Result — Grafik (Perbandingan skor usabilitas SUS) | Bar Chart komparatif rata-rata skor SUS kedua aplikasi | 2min  |
| 7 | Interpretation + Failure (Faktor penyebab friksi checkout GrabFood) | Grafik korelasi durasi vs skor kepuasan kognitif | 1.5min|
| 8 | Limitation + Future (Keterbatasan jumlah partisipan eksperimen) | Poin matriks boundary conditions | 1.5min|
| 9 | Conclusion + Contribution (GoFood terbukti lebih efisien untuk Gen Z) | Infografis kesimpulan penutup utama | 1min  |

Anticipatory Defense Matrix:
| Kategori | Pertanyaan Potensial | Jawaban (CER) |
|----------|---------------------|---------------|
| Problem  | Mengapa memilih Generasi Z sebagai objek eksperimen? | Gen Z adalah digital natives dengan tingkat atensi pendek dan tuntutan efisiensi transaksi tertinggi [C]. Karakteristik kognitif ini dievaluasi langsung melalui data durasi checkout [E], sehingga menjadi indikator terbaik untuk pengujian kegunaan antarmuka komparatif [R]. |
| Gap      | Apa pembeda riset ini dengan riset SUS/UX yang umum? | Sebagian besar studi terdahulu hanya menguji usabilitas secara statis [C]. Riset ini menggabungkan metrik subyektif SUS dengan metrik obyektif durasi waktu nyata (*time-on-task*) [E] guna menutup celah bias penilaian kognitif pengguna [R]. |
| Method   | Mengapa pengujian SUS menggunakan Google Form daripada wawancara langsung? | Untuk meminimalkan bias subjektivitas psikologis atau Hawthorne Effect [C]. Responden mengisi kuesioner mandiri langsung pasca-tugas [E], menjamin kemurnian ingatan interaksi tanpa tekanan pewawancara [R]. |
| Results  | Mengapa efisiensi durasi GoFood berbanding lurus dengan keunggulan SUS? | Arsitektur informasi GoFood meminimalkan interaksi redundan [C]. Data riil mencatat durasi GoFood (13.71 ± 1.51 detik) jauh lebih efisien dibanding GrabFood (19.54 ± 1.95 detik) [E], membuktikan efisiensi alur berdampak signifikan pada kepuasan usabilitas [R]. |
| Generalization | Apakah temuan riset ini dapat digeneralisasi ke platform e-commerce lain? | Tidak secara langsung tanpa adaptasi model tugas [C]. Karakteristik checkout makanan instan memiliki batasan urgensi yang berbeda dengan retail [E], sehingga generalisasi ke e-commerce lain memerlukan validasi struktur tugas belanja baru [R]. |

Latihan:
  Latihan 1: [23 Juni 2026] — Masih terlalu cepat di slide metodologi, waktu sisa 2 menit.
  Latihan 2: [25 Juni 2026] — Timing per slide sudah pas, pembawaan argumen CER mulai lancar.
  Latihan 3: [27 Juni 2026] — Simulasi sukses tepat 14.5 menit dengan artikulasi yang jelas.
```

---

## Latihan 1 — Slide Outline

Rencanakan presentasi 15 menit untuk riset Anda.

| # | Pesan Utama | Visual yang Digunakan | Waktu |
|---|-------------|----------------------|-------|
| 1 | Judul & Konteks: Analisis Kognitif Efisiensi Checkout Food Delivery | Title slide, Nama, NIM, & Logo Kampus | 1.0 min |
| 2 | Masalah: Kompleksitas UI Checkout memicu friksi bagi Generasi Z | Screenshoot perbandingan halaman checkout kedua aplikasi | 2.0 min |
| 3 | Gap + RQ: Perlu pembuktian korelasi performa waktu riil dan skor SUS | Tabel matriks pembeda riset dari literatur terdahulu | 1.5 min |
| 4 | Metodologi: Eksperimen terkontrol *Task-based Testing* | Diagram alur tahapan eksperimen dari tugas sampai kuesioner | 2.0 min |
| 5 | Hasil 1: Hasil uji efisiensi durasi (GoFood vs GrabFood) | Tabel ringkasan analisis statistik uji SPSS Paired t-test | 2.0 min |
| 6 | Hasil 2: Skor Usabilitas berbasis System Usability Scale (SUS) | Bar Chart komparatif rata-rata skor SUS kedua aplikasi | 2.0 min |
| 7 | Interpretasi: Hubungan efisiensi langkah terhadap kepuasan kognitif | Ringkasan poin kritis penyebab GrabFood lebih lambat | 1.5 min |
| 8 | Batasan & Masa Depan: Keterbatasan jumlah partisipan eksperimen | Poin batasan riset dan saran arah penelitian lanjut | 1.5 min |
| 9 | Kesimpulan: GoFood lebih unggul secara statistik dan usabilitas | Ringkasan kalimat kesimpulan penutup utama | 1.0 min |

**Total waktu estimasi:** 14.5 menit

---

## Latihan 2 — Anticipatory Defense

Prediksi 5 pertanyaan yang mungkin diajukan penguji, lalu siapkan jawaban CER.

| # | Kategori | Pertanyaan | Claim | Evidence | Reasoning |
|---|----------|-----------|-------|----------|-----------|
| 1 | *Problem* | Mengapa fokus pada proses *checkout*, bukan keseluruhan alur aplikasi? | Proses *checkout* adalah fase paling kritis penentu konversi transaksi belanja pengguna. | Data industri menunjukkan keranjang belanja sering ditinggalkan karena alur checkout rumit. | Mempersempit ruang lingkup pada fase checkout membantu mengukur hambatan kognitif secara terfokus. |
| 2 | *Method* | Mengapa Anda hanya menguji 35 responden dalam riset komparasi ini? | Jumlah sampel 35 responden sudah melampaui batas minimum uji kegunaan instrumen dasar. | Riset Nielsen menyatakan 5 sampai 8 pengguna sudah dapat mendeteksi lebih dari 80% masalah kegunaan. | Jumlah 35 sampel memberikan kekuatan statistik yang memadai untuk validasi uji parametrik t-test. |
| 3 | *Results* | Berapa nilai effect size yang didapat dan apa interpretasinya? | Efek perbedaan efisiensi durasi antar kedua aplikasi masuk dalam kategori sangat besar. | Hasil analisis output SPSS menunjukkan nilai Cohen's d sebesar 3.82. | Nilai tinggi tersebut membuktikan perbedaan durasi bukan kebetulan, melainkan karena faktor desain sistem. |
| 4 | *Results* | Mengapa terdapat anomali durasi checkout yang tinggi pada responden GrabFood? | Responden mengalami kebingungan tata letak pada bagian verifikasi promo dan asuransi belanja. | Log rekaman menunjukkan penambahan waktu rata-rata 5-6 detik khusus pada seleksi item proteksi. | Ini membuktikan adanya *dark pattern* opsi tambahan yang menghambat efisiensi kognitif Gen Z. |
| 5 | *Gap* | Bagaimana kontribusi praktis riset ini bagi pengembangan UI/UX ke depan? | Riset ini memberikan acuan konkret dalam mendesain alur transaksi makanan yang ramah untuk Gen Z. | Data poin friksi pada halaman GrabFood telah diidentifikasi dan dipetakan jelas dalam bab pembahasan. | Desainer sistem dapat menghindari elemen sekunder yang memotong fokus transaksi utama pengguna. |

---

## Latihan 3 — Simulasi Q&A

Minta teman/kolega mengajukan 3 pertanyaan tentang riset Anda. Catat pertanyaan dan evaluasi jawaban Anda.

| # | Pertanyaan | Jawaban Saya | Evaluasi |
|---|-----------|-------------|---------|
| 1 | "Apakah perbedaan koneksi internet responden tidak memengaruhi data durasi checkout?" | "Tidak, karena seluruh proses pengujian dilakukan menggunakan jaringan Wi-Fi laboratorium yang sama dan perangkat yang homogen untuk meminimalkan variabel pengganggu eksternal." | [✓] Direct [✓] Data-based [✓] Honest |
| 2 | "Mengapa Anda menggunakan Paired Samples t-test, bukan Independent t-test?" | "Karena riset menggunakan metode *within-subject design*, di mana subjek yang sama (35 orang responden) menguji kedua aplikasi secara bergantian." | [✓] Direct [✓] Data-based [✓] Honest |
| 3 | "Apakah hasil skor SUS ini menjamin bahwa aplikasi GoFood pasti sukses di pasar?" | "Skor SUS hanya mengukur tingkat usabilitas sistem dari perspektif pengalaman kognitif pengguna, bukan faktor bisnis. Hal bisnis di luar kendali dan menjadi batasan penelitian ini." | [✓] Direct [✓] Data-based [✓] Honest |

**Pertanyaan yang paling sulit dijawab:**
> Menjelaskan secara matematis mengapa variansi standar deviasi durasi GrabFood (1.95 detik) lebih lebar atau bervariasi dibandingkan dengan GoFood (1.51 detik).

**Apa yang perlu disiapkan lebih baik:**
> Memperdalam pemahaman teori beban kognitif (*Cognitive Load Theory*) serta membaca ulang catatan detil observasi perilaku responden saat kebingungan mencari tombol diskon ketika simulasi transaksi berlangsung.

---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-16 — dari paradigma riset hingga presentasi — bagian mana yang paling mengubah cara Anda berpikir tentang riset? Apa satu hal yang akan selalu Anda terapkan di riset berikutnya?

**Insight terbesar:**
> Bahwa riset UI/UX bukanlah soal membuat tampilan visual aplikasi menjadi terlihat indah atau estetis semata, melainkan tentang bagaimana membangun sebuah argumen ilmiah kokoh yang divalidasi oleh pembuktian data metrik objektif (durasi nyata transaksi) dan subjektif (kuesioner SUS standar) yang terbebas dari bias opini peneliti.

**Yang akan selalu diterapkan:**
> Pendekatan berpikir berbasis kerangka logika **CER (Claim-Evidence-Reasoning)** dalam memecahkan masalah maupun menjawab pertanyaan sidang, serta konsisten menerapkan strategi urutan penulisan terbalik (*Method → Discussion → Introduction*) untuk menjaga kekuatan benang merah karya ilmiah.