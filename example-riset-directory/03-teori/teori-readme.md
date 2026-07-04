# Analisis Teoretis dan Pembuktian Hipotesis Komparatif Antarmuka Checkout

Dokumen ini menyajikan artikulasi landasan teori interaksi manusia dan komputer (HCI) serta pembuktian hipotesis empiris yang dibangun mandiri secara vertikal dari hasil olah data statistik inferensial menggunakan IBM SPSS Statistics (berdasarkan rekaman data pada Screenshot 2026-06-28 181638_2.png and Screenshot 2026-06-28 181630_2.png).

---

## 1. Landasan Teori Komparatif Desain Antarmuka

Berdasarkan hasil komparasi data berpasangan (Paired Differences) terhadap 35 responden Generasi Z, dirumuskan dua postulat teori terkait impak struktural alur Single-Screen (GoFood) versus Multi-Step (GrabFood):

### A. Teori Reduksi Friksi Kognitif (Single-Screen Optimization)
Arsitektur informasi yang mengintegrasikan seluruh elemen esensial transaksi (informasi pengiriman, rincian pesanan, dan instrumen pembayaran) ke dalam satu halaman terpadu terbukti secara empiris memangkas ambang beban kerja mental pengguna. 
* Data pada variabel **Pair 1 (Durasi Checkout Grab - Durasi Checkout GoFood)** menghasilkan nilai selisih rata-rata waktu (Mean Paired Difference) sebesar **5.829 detik**.
* Temuan ini melahirkan teori bahwa peniadaan proses memuat halaman baru (page reloading) dan eliminasi tombol navigasi sekuensial "Lanjut" mampu mempercepat proses pengambilan keputusan taktis pengguna secara signifikan sebesar **kurang lebih 5,8 detik**.

### B. Teori Degradasi Usability Akibat Fragmentasi Alur (Multi-Step Usability Drop)
Pemisahan tahapan konfirmasi transaksi ke dalam beberapa halaman bertingkat secara linier memicu resistensi dan kelelahan kognitif ringan bagi pengguna digital.
* Data pada **Pair 2 (Total Skor SUS Grab - Total Skor SUS GoFood)** menunjukkan selisih nilai rata-rata kepuasan subjektif yang masif, yaitu sebesar **-25.7143 poin**.
* Nilai deviasi negatif yang besar ini mengonfirmasi adanya penurunan tingkat akseptabilitas sistem (usability score) ketika alur kerja dibuat terfragmentasi. Langkah klik tambahan memaksa memori kerja pengguna mengingat informasi dari halaman sebelumnya, yang berdampak pada penurunan penilaian kepuasan hingga **kurang lebih 25,7 poin**.

---

## 2. Analisis Inferensial dan Pengujian Hipotesis (Paired t-test)

Pengujian signifikansi dilakukan menggunakan pemodelan statistik parametrik Paired Samples t-test pada tingkat kepercayaan 95% (alpha = 0.05) dengan derajat kebebasan (df) = 34.

### A. Parameter Metrik Objektif: Efisiensi Waktu (Time on Task)
Pengujian ditujukan untuk menilai apakah selisih durasi pengerjaan skenario transaksi antara kedua model antarmuka bersifat signifikan atau sekadar bias kebetulan.
* **Nilai Statistik Kunci:** Diperoleh nilai t_hitung = 33.068 dengan probabilitas signifikansi **Sig. (2-tailed) = 0.000**.
* **Analisis & Keputusan:** Karena nilai signifikansi jauh lebih kecil dari standar alpha (Sig. < 0.05), maka Hipotesis Nol (H0) ditolak secara mutlak dan Hipotesis Alternatif (Ha) diterima. 
* **Kesimpulan Ilmiah:** Alur Single-Screen terbukti secara valid memberikan performa efisiensi waktu pemrosesan transaksi yang jauh lebih cepat bagi Generasi Z secara ilmiah dibandingkan dengan alur Multi-Step.

### B. Parameter Metrik Subjektif: Tingkat Kepuasan (System Usability Scale)
Pengujian digunakan untuk memastikan validitas perbedaan kenyamanan psikologis responden setelah berinteraksi dengan kedua aplikasi.
* **Nilai Statistik Kunci:** Diperoleh nilai t_hitung = -10.948 dengan probabilitas signifikansi **Sig. (2-tailed) = 0.000**.
* **Analisis & Keputusan:** Nilai signifikansi yang menyentuh angka 0.000 (p < 0.05) mengindikasikan penolakan total terhadap Hipotesis Nol (H0).
* **Kesimpulan Ilmiah:** Perbedaan tingkat kepuasan bernilai nyata secara statistik. Alur navigasi tunggal (Single-Screen) sukses mereduksi batasan psikologis pengguna, menghasilkan skor standardisasi SUS yang superior dibanding model navigasi bertahap (Multi-Step).

---

## 3. Kesimpulan Teoretis Akhir

Dari sintesis data statistik IBM SPSS di atas, didapatkan konklusi teoretis bahwa **desain arsitektur Single-Screen memiliki performa jauh lebih unggul dibandingkan Multi-Step**. Model ini berhasil meminimalisasi durasi pemrosesan internal pada kognisi mahasiswa Generasi Z sekaligus mendongkrak kepuasan interaksi digital secara signifikan.