# 04-metodologi.md

# 3. Metodologi Penelitian

## 3.1 Arsitektur Eksperimen
Penelitian ini menggunakan pendekatan kuantitatif dengan metode eksperimen terkontrol tipe *Within-Subject*[cite: 1]. Melalui metode ini, seluruh responden akan menguji kedua jenis antarmuka halaman checkout secara bergantian untuk meminimalkan variabilitas bias personal individu[cite: 1]. 
* **Kondisi Baseline:** Diwakili oleh alur *Multi-Step* pada aplikasi GrabFood (informasi transaksi dipecah ke beberapa halaman sekuensial)[cite: 1].
* **Kondisi Intervensi:** Diwakili oleh alur *Single-Screen* pada aplikasi GoFood (akumulasi seluruh data transaksi dalam satu halaman gulir panjang)[cite: 1].

Untuk mengantisipasi munculnya efek pembelajaran (*learning effect*) yang dapat membiaskan pencatatan waktu, penelitian ini menerapkan teknik *counterbalancing*[cite: 1]. Urutan pengerjaan tugas dibedakan secara acak; sebagian responden memulai dari GoFood terlebih dahulu, sementara sebagian lainnya memulai dari GrabFood[cite: 1].

## 3.2 Partisipan dan Purposive Sampling
Pengambilan sampel dilakukan menggunakan teknik *purposive sampling* dengan jumlah akhir **35 responden** mahasiswa aktif kelompok Generasi Z yang memiliki kecakapan dalam mengoperasikan aplikasi pesan-antar makanan mobile[cite: 1]. 

Untuk menjaga standarisasi dan keabsahan data eksperimen, seluruh responden melakukan pengujian secara langsung menggunakan **satu perangkat smartphone yang sama milik peneliti**. Hal ini bertujuan untuk mengeliminasi bias perbedaan spesifikasi perangkat keras (*hardware*) dan variasi performa layar yang dapat memengaruhi durasi pengerjaan tugas. Pengujian dilakukan dalam kondisi koneksi internet yang stabil dan lingkungan yang tenang[cite: 1].

## 3.3 Skenario Tugas (Task Scenario)
Setiap responden diwajibkan menyelesaikan tugas simulasi transaksional yang telah distandardisasi pada kedua aplikasi[cite: 1]. Skenario tugas yang diberikan diatur secara identik sebagai berikut:
* Partisipan diminta melakukan pemesanan komoditas makanan tiruan dengan menu dan jumlah yang ditentukan[cite: 1].
* Navigasi dilakukan mulai dari penambahan menu ke keranjang belanja hingga berhasil mencapai halaman konfirmasi pembayaran akhir (fase pemeriksaan alamat, detail item, penyerahan promo, dan rincian biaya)[cite: 1].
* Aktivitas interaksi dihentikan tepat ketika responden mengonfirmasi validasi data di halaman final sebelum tombol eksekusi pembayaran ditekan[cite: 1].

## 3.4 Prosedur Pengumpulan Data dan Pengukuran Metrik
Pengumpulan data dilakukan secara terintegrasi melalui dua instrumen utama:
1. **Metrik Objektif (Efisiensi Kognitif):** Diukur melalui durasi pengerjaan tugas (*Time on Task*) dalam satuan detik[cite: 1]. Data diperoleh secara presisi dengan merekam layar smartphone milik peneliti menggunakan perangkat lunak *Screen Recording* selama skenario berlangsung[cite: 1].
2. **Metrik Subjektif (Kepuasan Pengguna):** Diukur menggunakan instrumen kuesioner evaluasi yang disematkan ke dalam **Google Form**[cite: 1]. Segera setelah menyelesaikan skenario di masing-masing aplikasi, responden diminta memindai **Kode QR** yang disediakan oleh peneliti untuk mengakses dan mengisi lembar penilaian tersebut guna menjaga kesegaran persepsi secara langsung[cite: 1].

## 3.5 Teknik Analisis Statistik
Data hasil eksperimen dari 35 responden dikumpulkan dan ditabulasi sebelum diolah menggunakan perangkat lunak IBM SPSS Statistics[cite: 1]. Analisis dilakukan melalui dua tahapan:
* **Analisis Deskriptif:** Untuk memetakan nilai rata-rata (*mean*) dan standar deviasi dari metrik *Time on Task* serta total skor kepuasan pada masing-masing aplikasi[cite: 1].
* **Analisis Inferensial:** Menggunakan uji statistik **Paired Samples t-test** (Uji t Sampel Berpasangan)[cite: 1]. Pengujian ini membandingkan data durasi (Pair 1) dan data skor kepuasan (Pair 2) secara berpasangan per responden[cite: 1]. Hipotesis penelitian akan diterima jika nilai signifikansi p-value berada di bawah ambang batas alpha 0,05, yang membuktikan bahwa perbedaan performa mutlak dipengaruhi oleh struktur alur antarmuka[cite: 1].