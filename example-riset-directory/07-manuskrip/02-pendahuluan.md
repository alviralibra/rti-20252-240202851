# 02-pendahuluan.md

# 1. Pendahuluan

## 1.1 Latar Belakang Masalah
Transformasi digital dalam industri layanan pesan-antar makanan (*on-demand food delivery*) di Indonesia telah mengubah perilaku konsumsi masyarakat secara fundamental, di mana kecepatan dan kemudahan akses menjadi standar utama. Di tengah persaingan ketat antara platform raksasa, aspek *User Experience* (UX)—terutama pada proses *checkout* atau penyelesaian transaksi—telah menjadi titik krusial yang menentukan keberhasilan konversi sebuah pesanan. Halaman checkout merupakan fase final yang sangat sensitif; kegagalan dalam menyajikan informasi secara efektif dapat memicu keraguan pengguna yang berujung pada pembatalan transaksi.

Seiring dengan meningkatnya kompleksitas fitur aplikasi, mulai dari integrasi berbagai metode pembayaran hingga skema promo yang berlapis, beban kognitif (*cognitive load*) pengguna saat memproses informasi menjadi tantangan baru bagi para desainer antarmuka. Fenomena ini menuntut adanya pemahaman mendalam mengenai bagaimana struktur navigasi memengaruhi kinerja mental manusia. Kelompok yang paling terdampak dalam masalah ini adalah pengguna dari kelompok Generasi Z, yang secara demografis memiliki karakteristik mobilitas tinggi namun memiliki ambang batas perhatian (*attention span*) yang pendek. 

Gejala utama yang ditemukan di lapangan menunjukkan adanya hambatan mental atau keraguan pengguna saat berada di halaman konfirmasi, yang dibuktikan dengan durasi pengerjaan tugas (*Time on Task*) yang sering kali melampaui 15 detik hanya untuk memvalidasi detail pesanan, alamat, dan promo sebelum akhirnya melakukan pembayaran. Akar masalah dari ketidakefisienan ini terletak pada perbedaan paradigma desain alur (*user flow*) antara model *Single-Screen* yang memusatkan seluruh akumulasi data dalam satu halaman panjang, dibandingkan dengan model *Multi-Step* yang membagi informasi ke dalam beberapa tahap sistematis. Dampak dari kegagalan optimasi alur ini adalah meningkatnya beban kognitif yang memicu frustrasi pengguna, penurunan kecepatan transaksi, hingga potensi pembatalan pesanan secara mendadak (*churn*). Masalah ini berada dalam konteks persaingan antarmuka antara dua platform besar, Gojek (GoFood) dan Grab (GrabFood), yang masing-masing menerapkan standar navigasi berbeda bagi jutaan penggunanya di Indonesia pada tahun 2026.

## 1.2 Rumusan Masalah
Berdasarkan gejala lapangan dan akar permasalahan yang telah diuraikan, rumusan masalah dalam penelitian ini dirumuskan ke dalam pertanyaan riset (*Research Question*) utama berikut:
* "Bagaimana model alur yang menghasilkan efisiensi kognitif yang lebih baik dan kepuasan yang lebih tinggi bagi Generasi Z antara model Single-Screen dan Multi-Step?"

Sebagai titik awal penelitian, diajukan hipotesis bahwa alur *Single-Screen* akan memberikan durasi penyelesaian tugas yang lebih cepat secara signifikan dibandingkan alur *Multi-Step* karena minimnya interaksi perpindahan halaman.

## 1.3 Tujuan Penelitian
Sesuai dengan rumusan masalah di atas, tujuan utama yang ingin dicapai dari pelaksanaan penelitian ini adalah:
* Mengevaluasi dan membandingkan tingkat efisiensi kognitif serta kepuasan pengguna di antara dua model alur checkout yang dominan di pasar aplikasi *food delivery* (GoFood dan GrabFood) melalui pengujian komparatif *head-to-head*[cite: 1].
* Menentukan paradigma alur transaksi yang paling optimal dan responsif terhadap kebutuhan pengguna masa kini, khususnya bagi kelompok Generasi Z yang menuntut efisiensi tinggi dalam setiap interaksi digitalnya[cite: 1].

## 1.4 Kontribusi Penelitian
Hasil dari penelitian eksperimental ini diharapkan dapat memberikan kontribusi nyata yang terbagi menjadi dua aspek, yaitu:
1. **Kontribusi Teoritis (Bagi Bidang Interaksi Manusia dan Komputer):** Menyediakan dataset komparatif berbasis eksperimen riil yang membedah efisiensi alur *Single-Screen* versus *Multi-Step* dalam konteks ekosistem digital Indonesia tahun 2026[cite: 1]. Penelitian ini membuktikan secara empiris model navigasi mana yang paling mampu mereduksi beban kognitif pada kelompok pengguna dengan ambang batas perhatian pendek[cite: 1].
2. **Kontribusi Praktis (Bagi Industri Aplikasi Digital):** Menghasilkan dokumen analisis dan rekomendasi pola interaksi transaksional yang optimal[cite: 1]. Hasil evaluasi ini dapat dijadikan acuan dan panduan data empiris bagi pengembang industri dalam mengambil keputusan runtutan alur checkout yang lebih responsif terhadap batasan kognitif manusia guna menekan angka pembatalan transaksi[cite: 1].