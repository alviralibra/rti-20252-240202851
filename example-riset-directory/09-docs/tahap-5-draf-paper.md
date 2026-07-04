# Tahap 5 — Penulisan Draf Paper Jurnal

**Status:** Konten naskah selesai — naskah konsolidasi riset UI/UX tersedia di `../07-manuskrip/naskah-jurnal.md` & `../07-manuskrip/naskah-jurnal.docx`. Tinjauan pustaka lengkap dengan 18 referensi desain interaksi terverifikasi (BibTeX di `../02-literatur/daftar-pustaka.bib`). Sisa pekerjaan: keputusan bahasa final & pemindahan ke template jurnal tujuan (lihat "Yang Masih Perlu Dilengkapi").
**Bergantung pada:** [tahap-4-analisis-data.md](tahap-4-analisis-data.md) — *Selesai*

---

## Tujuan

Menyusun draf naskah ilmiah hasil eksperimen komparasi antarmuka checkout GoFood vs GrabFood dengan gaya bahasa akademis formal, objektif, dan pasif, guna memenuhi target publikasi nasional terakreditasi (Sinta 2) atau jurnal internasional (Scopus Q3-Q4).

---

## Rencana Deliverable (Struktur Naskah MDD)

| Bagian | File | Status |
| --- | --- | --- |
| **Naskah Konsolidasi** (Template Jurnal) | `../07-manuskrip/naskah-jurnal.md`, `../07-manuskrip/naskah-jurnal.docx` | Selesai — gabungan bab 1 sampai bab 5 + Daftar Pustaka |
| **Abstrak** | `../07-manuskrip/01-abstrak.md` | Draf selesai (Bahasa Indonesia & English) menyertakan ringkasan sampel 35 responden |
| **Pendahuluan** | `../07-manuskrip/02-pendahuluan.md` | Draf selesai — latar belakang perilaku transaksi Gen Z, rumusan masalah efisiensi checkout, tujuan riset, dan kontribusi desain |
| **Tinjauan Pustaka** | `../07-manuskrip/03-tinjauan-pustaka.md` | Selesai — kajian teori Single-Screen vs Multi-Step, landasan metrik System Usability Scale (SUS), Time on Task (ToT), serta 10 studi terkait |
| **Metodologi** | `../07-manuskrip/04-metodologi.md` | Draf selesai — alur eksperimen cross-over design, profil 35 partisipan mahasiswa kelas 3IKRA, instrumen uji, dan prosedur SPSS |
| **Hasil & Analisis** | `../07-manuskrip/05-hasil-analisis.md` | Draf selesai — memuat tabel deskriptif Mean ToT (13.71s vs 19.54s), Mean SUS (73.137 vs 47.423), nilai t-test, dan indeks D_perf |
| **Kesimpulan & Saran** | `../07-manuskrip/06-kesimpulan.md` | Draf selesai — rekomendasi desain perbaikan alur interaksi dan usulan Future Work |
| **Daftar Pustaka** | `../07-manuskrip/07-daftar-pustaka.md` | Selesai — 18 referensi format IEEE (jurnal UI/UX, buku metodologi desain, dan paper benchmarking); BibTeX: `../02-literatur/daftar-pustaka.bib` |

Peta sumber dan kerangka penulisan terinci pada: `../07-manuskrip/00-outline.md`.

---

## Teori dan Parameter Hasil yang Dimasukkan ke Naskah

### 1. Landasan Evaluasi Usability Internasional
*   **Time on Task (ToT):** Mengukur efisiensi kognitif motorik pengguna dari detik awal pengerjaan hingga transaksi selesai.
*   **System Usability Scale (SUS):** Alat ukur psikometris subjektif 10 butir pertanyaan berskala Likert untuk menentukan tingkat penerimaan sistem (Acceptability).

### 2. Ringkasan Temuan Statistik Empiris (Output SPSS)
Naskah mengunci temuan utama dari pengujian berpasangan (Paired Samples T-Test) terhadap 35 responden mahasiswa:
*   **Efisiensi Waktu (Pair 1):** Rata-rata checkout model bertahap (GrabFood) bernilai 19.54 detik, sedangkan satu layar (GoFood) bernilai 13.71 detik. Terjadi efek penundaan kognitif (D_perf) sebesar +42.52% pada model bertahap yang dibuktikan sangat signifikan melalui nilai t-hitung 33.068 (p = 0.000).
*   **Tingkat Kepuasan (Pair 2):** Model satu layar meraih predikat kelayakan rata-rata 73.137 (Acceptable / Good), jauh mengungguli model bertahap yang jatuh ke angka 47.423 (Not Acceptable / Poor) dengan penurunan kepuasan mencapai -35.16% (t-hitung = -10.948, p = 0.000).

---

## Yang Masih Perlu Dilengkapi Sebelum Submit

1.  **Keputusan Bahasa Final Naskah:** Memilih penggunaan Bahasa Indonesia secara utuh untuk target Sinta 2, atau melakukan translasi penuh ke Bahasa Inggris untuk target Scopus (saat ini draf bodi teks masih menggunakan Bahasa Indonesia akademik, sedangkan abstrak sudah dwibahasa).
2.  **Pemindahan ke Template Jurnal Tujuan:** Proses pemindahan manual isi teks dari format Markdown/Docx ke dalam layout kolom template penerbit jurnal yang ditargetkan.
3.  **Penempatan Gambar dan Tabel Final:** Memastikan penomoran urut, pemberian judul caption, dan penataan letak visual grafik resolusi tinggi (`fig_latency_p95.png`, `fig_dperf.png`, dan `fig_postgres_cpu.png`) berada tepat di bawah paragraf pembahasan teks yang relevan.
4.  **Lengkapi Metadata Penulis dan Afiliasi:** Menghapus data placeholder di lembar manuskrip utama untuk diisi dengan nama lengkap tim peneliti, nomor induk mahasiswa (NIM), nama program studi Teknologi Informasi, institusi, serta email korespondensi resmi.

---

## Catatan Tambahan

Seluruh narasi pada bab hasil dan analisis draf jurnal ini mengacu secara presisi pada angka ringkasan statistik deskriptif dan inferensial di Tahap 4 (`../06-output/tables/`). File pustaka ekstensi `.bib` berisi 18 referensi terverifikasi dapat langsung diimpor ke aplikasi Mendeley atau Zotero milik peneliti untuk memudahkan proses otomatisasi sitasi naskah.