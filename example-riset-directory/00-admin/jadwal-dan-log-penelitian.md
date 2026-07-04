# Jadwal & Log Pelaksanaan Penelitian

Catatan kronologis pelaksanaan tiap tahap (sumber: riwayat commit git & dokumen `09-docs/tahap-N-*.md`). Tanggal mengikuti `git log`.

## Log Pelaksanaan

| Tanggal | Tahap | Aktivitas | Referensi |
|---|---|---|---|
| 2026-04-06 | Tahap 1 | **WS 01: Ideasi & Topik Riset.** Menentukan topik komparasi efisiensi kognitif dan proses *checkout* pada aplikasi Food Delivery (GoFood vs GrabFood) untuk Generasi Z. | `worksheets/ws-01-ideasi.md` |
| 2026-04-06 | Tahap 1 | **WS 02: Perumusan Masalah.** Menyusun latar belakang masalah terkait *friction* atau hambatan UI/UX saat proses transaksi dan menetapkan *research questions*. | `worksheets/ws-02-perumusan-masalah.md` |
| 2026-04-20 | Tahap 1 | **WS 03: Kajian Literatur Awal.** Melakukan *literature review* dasar mengenai *Cognitive Load Theory* (Teori Beban Kognitif) dan metode *System Usability Scale* (SUS). | `worksheets/ws-03-kajian-literatur.md` |
| 2026-04-20 | Tahap 2 | **WS 04: Metodologi & Desain Riset.** Menentukan variabel penelitian, kriteria responden (Gen Z), dan menyusun alur eksperimen perekaman durasi waktu *checkout*. | `worksheets/ws-04-metodologi.md` |
| 2026-04-28 | Tahap 2 | **WS 05: Instrumen Pengujian.** Membuat skenario tugas (Task Scenario) belanja makanan hingga *checkout* dan menyusun draf kuesioner SUS di Google Form. | `worksheets/ws-05-instrumen.md` |
| 2026-05-11 | Tahap 2 | **WS 06: Validasi Eksperimen.** Melakukan uji coba mandiri terhadap alur prototype simulasi Figma dan mematikan fungsi *tracker* waktu berjalan dengan akurat. | `worksheets/ws-06-validasi.md` |
| 2026-05-11 | Tahap 3 | **WS 07: Pengumpulan Data Kelompok 1.** Menyebarkan kuesioner dan mengeksekusi tes durasi langsung ke 15 responden pertama dari target kelompok Gen Z. | `worksheets/ws-07-pengumpulan-data-1.md` |
| 2026-05-18 | Tahap 3 | **WS 08: Ekspansi Data Responden.** Melanjutkan pengambilan data lapangan hingga berhasil mengumpulkan total **35 responden Gen Z** yang valid. | `worksheets/ws-08-pengumpulan-data-2.md`, `04-data/mentah-35.csv` |
| 2026-05-26 | Tahap 4 | **WS 09: Tabulasi & Cleaning Data.** Memindahkan rekaman durasi waktu (detik) dan skor jawaban kuesioner SUS dari 35 responden ke Excel serta membersihkan data anomali. | `worksheets/ws-09-tabulasi-data.md` |
| 2026-06-03 | Tahap 4 | **WS 10: Perhitungan Skor SUS.** Mengolah nilai kuesioner menggunakan rumus konversi standar SUS untuk mendapatkan nilai *Acceptability*, *Grade Scale*, dan *Adjective Rating* GoFood vs GrabFood. | `worksheets/ws-10-skor-sus.md` |
| 2026-06-19 | Tahap 4 | **WS 11: Analisis Durasi Kognitif.** Menghitung nilai rata-rata (*mean*) dan standar deviasi kecepatan waktu *checkout* responden pada kedua aplikasi. | `worksheets/ws-11-analisis-durasi.md` |
| 2026-06-25 | Tahap 4 | **WS 12: Uji Statistik Komparatif.** Melakukan analisis perbandingan inferensial (seperti uji beda rata-rata) untuk melihat aplikasi mana yang memiliki beban kognitif lebih rendah secara signifikan. | `worksheets/ws-12-uji-statistik.md` |
| 2026-06-28 | Tahap 4 | **WS 13: Preprocessing & Visualisasi.** Menyusun grafik perbandingan akhir, diagram batang skor SUS, dan mengarsipkan dataset final n=35 ke repositori Git. | `worksheets/ws-13-preprocessing.md` |
| 2026-06-28 | Tahap 5 | **WS 14: Analisis & Interpretasi.** Menulis pembahasan mendalam mengenai temuan friksi desain (seperti taktik *dark pattern* atau penempatan tombol) yang memperlambat responden. | `worksheets/ws-14-analysis-interpretation.md` |
| 2026-06-18 | Tahap 5 | **WS 15: Penulisan Ilmiah (Scientific Writing).** Menyusun naskah manuskrip lengkap dari abstrak, metode, hasil pembahasan, hingga 18 referensi daftar pustaka. | `worksheets/ws-15-scientific-writing.md`, `07-manuskrip/naskah-jurnal.md` |
| 2026-06-18 | Tahap 5 | **WS 16: Presentasi & Pertahanan (Presentation Defense).** Membuat slide presentasi hasil riset dan melakukan finalisasi seluruh dokumen laporan untuk siap di-submit. | `worksheets/ws-16-presentation-defense.md` |

## Status Ringkas

- **Tahap 1–4 (WS 01 s.d. WS 13)**: Selesai (Dataset final: 35 responden kelompok Gen Z, pengujian komparasi durasi waktu *checkout* dan pengisian skor kuesioner SUS GoFood vs GrabFood selesai dianalisis).
- **Tahap 5 (WS 14 s.d. WS 16)**: Selesai (Konten naskah naskah jurnal ilmiah telah selesai dikonsolidasikan secara lengkap dengan statistik final n=35, menyisakan keputusan pemindahan ke template jurnal tujuan yang terakreditasi).

## Item Tindak Lanjut (Checklist Sebelum Submission)

- [x] Lengkapi matriks literatur dengan paper *related work* nyata ([02-literatur/matriks-literatur.md](../02-literatur/matriks-literatur.md)) — 18 referensi terverifikasi
- [x] Verifikasi CVE-2026-48524 terhadap basis data NVD/MITRE — terkonfirmasi via GHSA-fhv5-28vv-h8m8 (PyJWT, CVSS 3.7)
- [ ] Tetapkan bahasa final naskah (Indonesia/Inggris) sesuai jurnal tujuan
- [ ] Pindahkan konten [07-manuskrip/naskah-jurnal.md](../07-manuskrip/naskah-jurnal.md)/`.docx` ke template jurnal tujuan
- [ ] Finalisasi penempatan figure/tabel sesuai gaya jurnal
- [ ] Review akhir seluruh klaim numerik agar konsisten antar dokumen (lihat daftar pada [07-manuskrip/00-outline.md](../07-manuskrip/00-outline.md))

## Korespondensi

*(belum ada — tambahkan catatan korespondensi dengan pembimbing/editor jurnal di sini saat tersedia)*
