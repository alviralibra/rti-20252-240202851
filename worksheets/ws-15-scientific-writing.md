# WS-15: Scientific Writing

> **Bab 15 — Penulisan Ilmiah**

---

## Ringkasan Materi

### Scientific Argument Flow

```
Problem → Gap → RQ → Method → Result → Analysis → Conclusion → Contribution
```

Paper ilmiah adalah **satu argumen utuh** dari masalah ke kontribusi. Setiap node harus terhubung logis ke node sebelum dan sesudahnya.

### Struktur IMRAD

| Section | Peran | Pertanyaan Kunci |
|---------|-------|-----------------|
| **Introduction** | Motivasi + frame | Why is this needed? |
| **Method** | Deskripsi (reproducible) | How was it done? |
| **Results** | Laporan objektif | What was found? |
| **Discussion** | Interpretasi + refleksi | What does it mean? |
| **Conclusion** | Ringkasan + kontribusi | So what? |

### Logical Flow — "Red Thread"

Setiap paragraf menjawab satu pertanyaan dan memicu pertanyaan berikutnya. Alur logis ini harus terasa di tiga level:
1. **Antar-kalimat** dalam paragraf
2. **Antar-paragraf** dalam section
3. **Antar-section** dalam paper

### Internal Consistency

Setiap elemen yang dijanjikan di Introduction harus hadir di Discussion/Conclusion.

**Consistency Matrix:**
```
           Intro  Method  Result  Discuss  Conclude
RQ1          ✓      ✓       ✓       ✓        ✓
RQ2          ✓      ✓       ✓       ✗ ←      ✓
Metrik-X     ✗      ✗       ✓ ←     ✗        ✗
```
**Masalah:** RQ2 dibahas di semua bagian kecuali Discussion. Metrik-X muncul di Result tapi tidak diperkenalkan di Method.

### Writing Quality Triad

| Kualitas | Deskripsi | Contoh Buruk → Baik |
|----------|----------|---------------------|
| **Clarity** | Dipahami sekali baca | "Performa meningkat" → "Accuracy meningkat dari 85.3% ke 89.7%" |
| **Precision** | Istilah eksak, tanpa ambiguitas | "signifikan" → "signifikan secara statistik (p=0.003, d=1.2)" |
| **Conciseness** | Setiap kata menambah informasi | Hapus kalimat redundan, filler words |

### Urutan Penulisan yang Disarankan

1. **Method & Results** — paling stabil, tulis pertama
2. **Discussion** — interpretasi berdasarkan hasil
3. **Introduction** — frame sesuai temuan aktual
4. **Abstract & Conclusion** — terakhir

### Target Jumlah Kata

| Section | Target |
|---------|--------|
| Introduction | 500–700 |
| Related Work | 700–1000 |
| Method | 800–1200 |
| Results | 500–800 |
| Discussion | 600–900 |
| Conclusion | 200–400 |

### Jebakan Kognitif

1. "Lebih panjang = lebih lengkap" → conciseness lebih berharga
2. "Introduction harus ditulis pertama" → justru ditulis terakhir
3. "Jargon teknis = lebih ilmiah" → clarity lebih penting
4. "Discussion = ringkasan Results" → Discussion = interpretasi + konteks

---

## Template A.15 — Paper Structure Checklist

```
PAPER STRUCTURE CHECKLIST

Title   : Analisis Komparatif Efisiensi Kognitif dan Usabilitas Proses Checkout Food Delivery Apps Antara GoFood dan GrabFood pada Generasi Z
Target  : [✓] Jurnal  [ ] Konferensi  [ ] Laporan

Section Check:
  [✓] Abstract — masalah, metode, hasil utama, kontribusi (max 250 kata)
  [✓] Introduction — konteks → gap → RQ → kontribusi → struktur paper
  [✓] Related Work — concept-centric, gap positioning
  [✓] Method — reproducible: desain, variabel, metrik, setup, prosedur
  [✓] Results — tabel + grafik + observasi (tanpa interpretasi)
  [✓] Discussion — interpretasi, perbandingan, implikasi, limitation
  [✓] Conclusion — jawaban RQ, kontribusi, future work

Consistency Matrix:
  [✓] RQ di Introduction = RQ di Method = RQ di Conclusion
  [✓] Variabel di Method = variabel di Results
  [✓] Klaim di Discussion didukung data di Results
  [✓] Limitasi di Discussion di-address di Conclusion/Future Work

Writing Quality:
  [✓] Clarity — mudah dipahami tanpa re-read
  [✓] Precision — tidak ada istilah ambigu
  [✓] Conciseness — tidak ada kalimat redundan
```

---

## Latihan 1 — Paper Outline

Buat outline paper untuk riset Anda menggunakan struktur IMRAD.

| Section | Konten Utama (2-3 kalimat) | Target Kata |
|---------|---------------------------|------------|
| Abstract | Alur checkout pada aplikasi *food delivery* berdampak langsung pada beban kognitif pengguna Gen Z yang menuntut kecepatan transaksi. Studi ini membandingkan efisiensi proses checkout GoFood dan GrabFood menggunakan metrik durasi tugas (*Task Completion Time*) dan *System Usability Scale* (SUS) dengan uji statistik *Paired Samples t-test* ($n=35$). Hasil pengujian menunjukkan GoFood secara signifikan lebih cepat ~5.83 detik ($p<0.001$, $d=3.82$) dan meraih skor SUS yang jauh lebih unggul (73.14 vs 47.42). | 200-250 |
| Introduction | Mobilitas tinggi membuat Generasi Z menginginkan interaksi produk digital yang serba instan, minimalis, dan intuitif. Namun, beberapa platform *food delivery* masih menerapkan alur checkout multiprosedur yang berpotensi memicu tingginya beban kognitif (*cognitive load*). Penelitian ini bertujuan mengukur secara empiris perbedaan efisiensi alur checkout antara GoFood dan GrabFood untuk memberikan panduan arsitektur informasi UX yang optimal bagi segmentasi pengguna muda. | 500-700 |
| Related Work | Bagian ini mengkaji literatur mengenai metrik evaluasi beban kognitif produk digital, implementasi *Hick's Law* dalam arsitektur informasi transaksi *e-commerce*, serta karakteristik psikologis perilaku interaksi Gen Z. Selain itu, dipetakan pula posisi (*positioning*) riset ini yang berfokus pada studi komparatif kuantitatif langsung pada modul transaksi final (*checkout*). | 700-1000 |
| Method | Penelitian eksperimental ini menggunakan desain *within-subject* di mana 35 responden mahasiswa melakukan tugas checkout menu makanan yang identik pada aplikasi GoFood dan GrabFood. Variabel bebas dalam riset ini adalah jenis platform aplikasi, sedangkan variabel terikatnya adalah durasi waktu checkout dan nilai total usabilitas SUS. Analisis inferensial dilakukan menggunakan uji *Paired Samples t-test* setelah seluruh data lolos uji asumsi normalitas. | 800-1200 |
| Results | Menyajikan tabel data deskriptif hasil SPSS serta visualisasi grafik komparasi durasi transaksi dan skor kepuasan SUS dari 35 responden. Dilaporkan hasil uji signifikansi di mana durasi GrabFood (19.54 ± 1.95 detik) terbukti lebih lama dari GoFood (13.71 ± 1.51 detik) dengan nilai t(34) = 33.068, p < 0.001. Skor kepuasan SUS GoFood juga unggul mutlak (73.14 ± 11.22) dibanding GrabFood (47.42 ± 8.28) dengan nilai t(34) = -10.948, p < 0.001. | 500-800 |
| Discussion | Perbedaan durasi checkout yang sangat signifikan membuktikan bahwa struktur informasi langkah tunggal pada GoFood sukses memangkas waktu keputusan konsumen (*Hick's Law*). Skor SUS GrabFood yang rendah (47.42) mengindikasikan adanya hambatan psikologis akibat penempatan informasi sekunder iklan/promo yang berlebihan di layar checkout. Limitasi riset ini terletak pada homogenitas sampel mahasiswa IT yang memiliki tingkat literasi teknologi yang tinggi. | 600-900 |
| Conclusion | Penelitian menyimpulkan bahwa alur checkout GoFood memiliki tingkat efisiensi kognitif dan kepuasan pengguna yang jauh lebih unggul bagi segmentasi Gen Z dibandingkan GrabFood. Kontribusi praktis riset ini terletak pada penyediaan basis data empiris kuantitatif mengenai metrik performa interaksi aplikasi lokal di Indonesia. *Future work* disarankan untuk memperluas pengujian pada variasi demografi responden lintas generasi. | 200-400 |

---

## Latihan 2 — Consistency Matrix

Buat consistency matrix untuk memverifikasi internal consistency paper Anda.

|  | Intro | Method | Result | Discussion | Conclusion |
|--|-------|--------|--------|-----------|-----------|
| RQ1 | ✓ | ✓ | ✓ | ✓ | ✓ |
| RQ2 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Metrik utama | ✓ | ✓ | ✓ | ✓ | ✓ |
| Variabel IV | ✓ | ✓ | ✓ | ✓ | ✓ |
| Variabel DV | ✓ | ✓ | ✓ | ✓ | ✓ |
| Klaim/kontribusi | ✓ | ✓ | ✓ | ✓ | ✓ |

**Isi setiap sel:** ✓ (ada & konsisten), ✗ (missing), ~ (ada tapi inkonsisten)

**Inkonsistensi yang ditemukan:**
> Tidak ditemukan inkonsistensi. Seluruh elemen mulai dari Research Question (RQ), metrik pengujian (Durasi & SUS), variabel penelitian, hingga klaim kontribusi telah dipetakan dengan harmonis dan konsisten di setiap bab, dari pendahuluan hingga penutup.

**Tindakan perbaikan:**
> Mempertahankan konsistensi ini selama proses penulisan draf final dan memastikan penulisan simbol statistik serta istilah teknis tetap seragam di seluruh dokumen.

---

## Latihan 3 — Writing Quality Check

**Paragraf asli:**
> Berdasarkan apa yang sudah diuji kemarin, aplikasi GoFood kerasa lebih cepat banget pas dipakai buat checkout pesanan sama anak-anak Gen Z dibandingin sama GrabFood yang agak ribet. Terus hasil dari SPSS juga nunjukkin kalau nilainya berbeda secara signifikan antara kedua aplikasi itu.

| Kriteria | Evaluasi | Perbaikan |
|----------|---------|-----------|
| Clarity | Kalimat pertama menggunakan kata subjektif ("kerasa lebih cepat banget") dan bahasa kurang baku ("pas dipakai", "anak-anak"). | Mengubah diksi menjadi objektif dengan indikator berbasis data durasi riil. |
| Precision | Klaim "berbeda secara signifikan" tidak disertai angka statistik pelapor yang konkret dan standar. | Menambahkan nilai rata-rata, standar deviasi, nilai p, dan effect size dari output SPSS. |
| Conciseness | Penggunaan kata "Berdasarkan apa yang sudah", "pas dipakai buat" terlalu bertele-tele (filler words). | Memadatkan struktur kalimat agar langsung berfokus pada hubungan antar variabel. |

**Paragraf setelah perbaikan:**
> Hasil analisis eksperimen menunjukkan bahwa proses checkout GoFood secara signifikan lebih efisien dibandingkan GrabFood pada pengguna Generasi Z. Durasi rata-rata checkout GoFood terbukti lebih singkat (13.71 ± 1.51 detik) daripada GrabFood (19.54 ± 1.95 detik). Uji statistik Paired Samples t-test memperkuat temuan ini secara presisi dengan nilai t(34) = 33.068, p < 0.001, dan ukuran efek (effect size) Cohen's d = 3.82 yang masuk kategori sangat besar.

---

## Refleksi

> Apa perbedaan antara menulis "tentang" riset dan menulis sebagai "argumen" riset? Bagaimana urutan penulisan (Method → Discussion → Introduction) mengubah kualitas tulisan?

> Menulis "tentang" riset cenderung bersifat deskriptif naratif yang sekadar melaporkan kronologi aktivitas dan tumpukan data mentah tanpa arah yang jelas. Sebaliknya, menulis sebagai "argumen" riset berarti menyusun sebuah bangunan logika yang kokoh, di mana data dikonversi menjadi bukti (*evidence*) ilmiah untuk mempertahankan posisi klaim, menjawab pertanyaan penelitian (*RQ*), dan membuktikan kontribusi terhadap kesenjangan (*gap*) ilmiah yang ada.
> 
> Mengubah urutan penulisan dengan mendahulukan komponen yang paling stabil (*Method* dan *Results*) ke komponen interpretatif (*Discussion*), dan mengakhiri dengan framing (*Introduction* dan *Abstract*) terbukti menaikkan kualitas tulisan secara drastis. Pendekatan ini meminimalkan risiko ketidakcocokan logika (*internal inconsistency*) karena alur cerita pendahuluan (*Introduction*) ditulis dengan kesadaran penuh terhadap temuan aktual yang sudah terbukti di bab hasil (*Results*), sehingga benang merah (*red thread*) tulisan terjaga erat tanpa ada klaim yang melompat atau berlebihan.
