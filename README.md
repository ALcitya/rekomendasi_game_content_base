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
Dataset ini diambil dari Metacritic. sebuah platform kolektif milik pemain game. yang dihimpun dengan berbagai jenis judul game. Link selengkapnya dapat dilihat [disini](https://www.kaggle.com/datasets/uuratl/metacritic-games-12-23-2024).

## fitur Dataset
- Dataset ini memiliki 13990 baris
- dataset ini memiliki 12 kolom

## Kondisi Awal Dataset
Dataset ini memiliki 2 kolom yang terdapat missing value, yakni kolom user_review_count 1557 missing value. Dan kolom esrb sebanyak 2103 missing value

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- Unnamed: 0 : merupakan kolom yang terbuat ketika library kagglehub mengambil dataset
- name : merupakan nama dari game
- metacritic_review_count : merupakan jumlah kritik yang diterima terhadap game, didalam metacritic
- metacritic_review_score : merupakan rata-rata score game dari pengguna, didalam metacritic
- user_review_count : merupakan jumlah review dari pengguna
- user_review_score : merupakan nilai score yang diberikan pengguna
- developer : merupakan nama dari pihak yang membuat game
- publisher : merupakan nama dari pihak yang merilis game
- platforms : merupakan platform dari game yang dimainkan
- genres : merupakan genre dari game yang disebutkan
- esrb : merupakan kategori usia yang dapat memainkan game
- must_play : merupakan penilaian apakah game layak dimainkan atau tidak

## Data Preparation

1. Mengatasi missing value di kolom user_review_count dan esrb. Dengan cara menghapus baris yang terdapat missing value
2. Mengecek Duplikasi
3. Menghapus kolom Unnamed : 0
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
