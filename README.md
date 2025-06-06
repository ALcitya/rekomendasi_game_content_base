# Laporan Proyek Machine Learning - Moch. Ichwan Alif Kurniawan

## Project Overview

Ditengah perkembangan industri games yang berkembang pesat, game semakin banyak macamnya di pasar. Para pemain sering kali kebingungan dalam memilih games apa yang ingin mereka mainkan. Oleh karena itu, dibutuhkan suatu sistem rekomendasi, agar para pemain tidak lagi kesulitan dalam memilih games yang sesuai dengan selera mereka.

Projek ini saya buat, dengan harapan untuk membantu para pemain games untuk menemukan games sesuai minat mereka. Agar mereka tidak perlu menghabiskan banyak waktu dalam menjelahi pasar games

**Rubrik/Kriteria Tambahan (Opsional)**:
- Sistem rekomendasi dapat memicu efek domino terhadap game dengan genre yang sama. seperti yang terlihat di artikel ini dimana kepopuleran suatu game sepak bola memicu keinginan developer lain untuk membuat game dengan genre yang sama. yang membuat semakin banyaknya pilihan yang bisa diterima pemain
- Sistem Rekomendasi Pemilihan Pemain Pada Game Fantasy Premier League.
- Artikel selengkapnya dapat dilihat [disini](https://dspace.uii.ac.id/handle/123456789/40425)
- Artikel ini dapat ditemukan di Google Scholar [Scholar](https://scholar.google.com/)

## Business Understanding

### Problem Statements

Menjelaskan pernyataan masalah:
- Bagaimana merekomendasikan game kepada pengguna berdasarkan kesukaan genre yang sama
- Bagaimana merekomendasikan publisher game yang sama kepada pengguna

### Goals

Menjelaskan tujuan proyek :
- Membuat sistem rekomendasi game berdasarkan genre yang sama
- Membuat rekomendasi game, dengan nama publisher yang sama

Goal yang diharapkan adalah, sebuah sistem yang dapat memberikan rekomendasi nama games. Dengan genre yang serupa dengan yang kita inputkan. juga memberikan rekomendasi nama games, berdasarkan nama publisher yang kita pililh

**Rubrik/Kriteria Tambahan (Opsional)**:
### Solution statements
Sistem rekomendasi nantinya akan mengambil nilai input dari user, lalu dicocokkan kedalam kolom untuk mencari inputan yang sesuai dengan user, inputan itu baik berupa genre games maupun nama publisher. Lalu sistem akan memilihkan 5 nama games teratas untuk diberikan kepada user.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai jumlah data, kondisi data, dan informasi mengenai data yang digunakan. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
