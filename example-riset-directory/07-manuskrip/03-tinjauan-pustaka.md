# 03-tinjauan-pustaka.md

# 2. Tinjauan Pustaka

## 2.1 Arsitektur Informasi Modul Checkout Mobile
Arsitektur informasi dalam aplikasi mobile menentukan bagaimana data dan fitur disusun untuk memandu alur kerja pengguna. Pada modul checkout layanan pesan-antar makanan, terdapat dua paradigma utama yang bersaing:
* **Model Single-Screen (Halaman Tunggal):** Mengintegrasikan seluruh komponen transaksi—mulai dari titik pengantaran, detail pesanan, opsi pembayaran, hingga penyerahan promo—dalam satu halaman linear yang memanfaatkan interaksi gulir (*scrolling*).
* **Model Multi-Step (Alur Bertahap):** Memfragmentasi informasi ke dalam beberapa layar sekuensial yang terpisah. Pengguna wajib menyelesaikan satu tahapan sebelum diizinkan berpindah ke halaman konfirmasi berikutnya melalui tombol navigasi.

## 2.2 Efisiensi Kognitif dan Beban Memori Kerja
Efisiensi kognitif mengukur seberapa optimal kapasitas pemrosesan informasi mental manusia saat berinteraksi dengan sebuah antarmuka digital. Menurut teori beban kognitif (*cognitive load theory*), manusia memiliki keterbatasan dalam memori kerja (*working memory*). 
* Desain *Multi-Step* memaksa pengguna melakukan retensi informasi lintas layar, yang dapat memicu interupsi psikologis dan keraguan transaksional jika elemen transisinya lambat atau membingungkan.
* Sebaliknya, desain *Single-Screen* menerapkan prinsip reduksi friksi kognitif dengan menyajikan seluruh data secara transparan, sehingga mempercepat durasi pengerjaan tugas (*Time on Task*).

## 2.3 Evaluasi Kegunaan Sistem (System Usability Scale)
*System Usability Scale* (SUS) merupakan instrumen kuesioner terstandarisasi untuk mengukur persepsi kegunaan subjektif dari suatu sistem digital secara global. Pengukuran ini melibatkan indikator kepuasan, kemudahan integrasi fitur, tingkat konsistensi antarmuka, dan kenyamanan operasional sistem. Skor akhir SUS berkisar antara 0–100 dan menjadi acuan mutlak untuk menentukan tingkat akseptabilitas dan kelayakan produk di mata pengguna akhir.

## 2.4 Penelitian Terkait (Related Work)
Penelitian mengenai antarmuka mobile-commerce saat ini mulai bergeser dari sekadar estetika visual menuju pengukuran performa mikro antarmuka. Beberapa studi relevan yang melandasi riset ini antara lain:
* Penelitian oleh Chen dan Wang (2025) yang menguji efisiensi kognitif pada desain mobile dan menemukan bahwa struktur halaman memengaruhi kecepatan checkout secara signifikan.
* Studi komparatif oleh Hidayat dan Sari (2024) mengenai evaluasi usability platform ojek online pada kelompok mahasiswa yang menyoroti pentingnya skor SUS untuk mengukur kenyamanan navigasi.
* Analisis beban kognitif pengguna Generasi Z oleh Aditama dan Putri (2024) yang menegaskan bahwa kelompok muda ini memiliki *attention span* yang pendek dan sensitif terhadap penundaan transaksi di atas 15 detik.