# Laporan Proyek Machine Learning - Moch. Ichwan Alif Kurniawan

## Project Overview

Ditengah perkembangan industri game yang berkembang pesat, game semakin banyak macamnya di pasar. Para pemain sering kali kebingungan dalam memilih game apa yang ingin mereka mainkan. Oleh karena itu, dibutuhkan suatu sistem rekomendasi, agar para pemain tidak lagi kesulitan dalam memilih game yang sesuai dengan selera mereka.

Projek ini saya buat, dengan harapan untuk membantu para pemain game untuk menemukan game sesuai minat mereka. Agar mereka tidak perlu menghabiskan banyak waktu dalam menjelahi pasar game

**Rubrik/Kriteria Tambahan (Opsional)**:
- Sistem rekomendasi dapat memicu efek domino terhadap game dengan genre yang sama. seperti yang terlihat di artikel ini dimana kepopuleran suatu game sepak bola memicu keinginan developer lain untuk membuat game dengan genre yang sama. yang membuat semakin banyaknya pilihan yang bisa diterima pemain
- Sistem Rekomendasi Pemilihan Pemain Pada Game Fantasy Premier League.
- Artikel selengkapnya dapat dilihat [disini](https://dspace.uii.ac.id/handle/123456789/40425)
- Artikel ini dapat ditemukan di Google Scholar [Scholar](https://scholar.google.com/)

## Business Understanding

### Problem Statements

Menjelaskan pernyataan masalah:
- Bagaimana merekomendasikan game kepada pengguna berdasarkan kesukaan genre yang sama
- Bagaimana kesimpulan akurasi berbasis evaluasi, berdasarkan sistem rekomendasi game berdasarkan genre

### Goals

Menjelaskan tujuan proyek :
- Membuat sistem rekomendasi game berdasarkan genre yang sama
- Menarik kesimpulan akurasi model berbasis evaluasi, berdasatkan sistem rekomendasi game berdasarkan genre

Goal yang diharapkan adalah, sebuah sistem yang dapat memberikan rekomendasi nama game. Dengan genre yang serupa dengan yang kita inputkan. juga untuk menarik kesimpulan dari nilai metriks akurasi, berdasarkan sistem rekomendasi yang sudah dibangun.

## Data Understanding
Dataset ini diambil dari Metacritic. sebuah platform kolektif milik pemain game. yang dihimpun dengan berbagai jenis judul game. Link selengkapnya dapat dilihat [disini](https://www.kaggle.com/datasets/uuratl/metacritic-game-12-23-2024).

## fitur Dataset
- Dataset ini memiliki 13390 baris
- dataset ini memiliki 12 kolom

## Kondisi Awal Dataset
- Dataset ini memiliki 2 kolom yang terdapat missing value, yakni kolom user_review_count 1557 missing value. Dan kolom esrb sebanyak 2103 missing value
- Dataset ini tidak memiliki nilai duplikasi

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

1. Mengatasi missing value di kolom user_review_count dan esrb. Dengan cara menghapus baris yang terdapat missing value: berfungsi untuk mempermudah pelatihan model
2. Menghapus kolom Unnamed : 0 berfungsi menghilangkan kolom yang aslinya tidak ada
3. Mengurutkan berdasarkan genre: agar model lebih mudah mencari berdasarkan genre
4. Melakukan normalisasi terhadap kolom metacritic_review_count, user_review_count, developer, publiser, esrb. Dengan cara mereplace value string didalam kolom dengan nilai kosong. berfungsi agar kolom hanya memiliki nilai numeric
5. Merubah type data metacritic_review_count, metacritic_review_score, user_review_count, user_review_score menjadi int dan float. agar type data kolom lebih sesuai dengan valuenya
6. membuat kolom combined_features dari kolom name, developer, publisher, genre, esrb. Membuat agar kolom penting menjadi satu kolom, berfungsi mempemudah fungsi tf-idf untuk hanya fokus ke satu kolom
7. menormalisasi kolom combined_features, berfungsi untuk menyeragamkan text agar mudah menghitung cosine similarity mengunakan tf-idf
8. TF-IDF Vectorizer : berfungsi merubah teks menjadi bentuk numeric, yang akan digunakan dalam cosine similarity

## Modeling
## Model yang digunakan 
content base filtering, Mengambil pemahaman mengenai content apa yang pernah disukai, lalu memberikan rekomendasi konten baru, sesuai dengan konten yang pernah disuakai dimasalalu.

## Alur Kerja Sistem yang dibuat
1. Kolom dihitung kesamaannya menggunakan cosine Similarity
2. Fungsi rekomendasi berdasarkan genre akan dibuat, untuk mencari game berdasarkan genre
3. Membuat data preferensi dari pengguna di array user_preference
4. Fungsi rekomendasi akan dipanggil, berdasarkan genre game dari user_preferences
5. Rekomendasi game didapatkan, berdasarkan nama-nama game teratas

## parameter yang digunakan
- Content base filtering yang saya buat menggunakan parameter : genre, top_n=5, user_preferences, metacritic_review_score
- Cosine Similarity menggunakan 2 buah parameter tfidf-matrix

## penjelasan parameter
- genre : merupakan nama genre yang dimasukkan pengguna
- top_n=5 : merupakan nilai default untuk menampilkan 5 game teratas
- user_preferences : mengambil nama genre untuk dicari preferensinya
- metacritic_review_score : digunakan sebagai parameter acuan untuk memilih game mana yang akan direkomendasikan.
- tfidf-matrix : digunakan untuk menampung nilai matrix dari kesamaan yang sudah dibuat
  
## Hasil Rekomendasi setiap Genre
'Open-World Action':
        genres                                     
 -  ['Open-World Action']     The Legend of Zelda: Ocarina of Time
 -  ['Open-World Action']                      Grand Theft Auto IV
 -  ['Open-World Action']                       Grand Theft Auto V
 -  ['Open-World Action']                    Red Dead Redemption 2
 -  ['Open-World Action']  The Legend of Zelda: Breath of the Wild
 
 --------------------
 '3D Platformer':                
         genres                  
 -   ['3D Platformer']  Super Mario Galaxy 2
 -  ['3D Platformer']   Super Mario Odyssey
 -   ['3D Platformer']    Super Mario Galaxy
 -  ['3D Platformer']             Astro Bot
 -  ['3D Platformer']  Super Mario 3D World,

 --------------------
 'JRPG':        
         genres                  
 -   ['JRPG']       Persona 5 Royal
 -  ['JRPG']          Chrono Cross
 -   ['JRPG']      Final Fantasy IX
 -   ['JRPG']  Metaphor: ReFantazio
 -  ['JRPG']             Persona 5

 --------------------
 'Action RPG':              
         genres                               
 -   ['Action RPG']                         Elden Ring
 -   ['Action RPG']                             Diablo
 -   ['Action RPG']  Elden Ring: Shadow of the Erdtree
 -  ['Action RPG']                      Mass Effect 3
 -  ['Action RPG']          Final Fantasy VII Rebirth

 --------------------
 'MOBA':         
         genres                 
 -  ['MOBA']  Heroes of the Storm
 -  ['MOBA']                SMITE
 -  ['MOBA']    League of Legends
 -  ['MOBA']         Awesomenauts
 -  ['MOBA']              Demigod

 --------------------
 'Soccer':              
         genres                                         
 -  ['Soccer Sim']                       Pro Evolution Soccer 2
 -  ['Soccer Sim']  World Soccer Winning Eleven 7 International
 -  ['Soccer Sim']  World Soccer Winning Eleven 8 International
 -  ['Soccer Sim']                               FIFA Soccer 12
 -  ['Soccer Sim']                               FIFA Soccer 13

 --------------------
 'MMORPG':          
         genres                                       
 -  ['MMORPG']                          World of Warcraft
 -  ['MMORPG']               Final Fantasy XIV: Endwalker
 -  ['MMORPG']  World of Warcraft: Wrath of the Lich King
 -  ['MMORPG']     World of Warcraft: The Burning Crusade
 -  ['MMORPG']               World of Warcraft: Cataclysm

 --------------------
 'Turn-Based Strategy':                       
         genres                                      
 -  ['Turn-Based Strategy']                        Total War: Shogun 2
 -  ['Turn-Based Strategy']          Shogun: Total War Warlord Edition
 -   ['Turn-Based Strategy']     Age of Wonders II: The Wizard's Throne
 -  ['Turn-Based Strategy']  Total War: Shogun 2 - Fall of the Samurai
 -  ['Turn-Based Strategy']                       Total War: WARHAMMER

 --------------------
 'Virtual Life':                
         genres                           
 -  ['Virtual Life']                       The Sims
 -  ['Virtual Life']  Animal Crossing: New Horizons
 -  ['Virtual Life']                     The Sims 2
 -  ['Virtual Life']      Animal Crossing: New Leaf
 -  ['Virtual Life']                Animal Crossing

 --------------------
 
## Evaluation
## Metriks yang Digunakan
- Precision
- Recall
- F1-score

## Penjelasan Matriks
- Precision : Mengukur relevansi item-item teratas yang direkomendasikan sistem
- Recall : Mengukur seberapa banyak item relevan yang ditemukan
- F1-Score : rata-rata harmonis dari Precision dan Recall

## Hasil Tiap Genre
Genre 'Open-World Action':
- Precision@5: 0.4000
- Recall@5: 1.0000
- F1-score@5: 0.5714
--------------------
Genre '3D Platformer':
- Precision@5: 0.2000
- Recall@5: 1.0000
- F1-score@5: 0.3333
--------------------
Genre 'JRPG':
- Precision@5: 0.2000
- Recall@5: 1.0000
- F1-score@5: 0.3333
--------------------
Genre 'Action RPG':
- Precision@5: 0.0000
- Recall@5: 0.0000
- F1-score@5: 0.0000
--------------------
Genre 'MOBA':
- Precision@5: 0.0000
- Recall@5: 0.0000
- F1-score@5: 0.0000
--------------------
Genre 'Soccer':
- Precision@5: 0.0000
- Recall@5: 0.0000
- F1-score@5: 0.0000
--------------------
Genre 'MMORPG':
- Precision@5: 0.2000
- Recall@5: 1.0000
- F1-score@5: 0.3333
--------------------
Genre 'Turn-Based Strategy':
- Precision@5: 0.2000
- Recall@5: 1.0000
- F1-score@5: 0.3333
--------------------
Genre 'Virtual Life':
- Precision@5: 0.2000
- Recall@5: 1.0000
- F1-score@5: 0.3333
--------------------
## Hasil Rata-rata
- Average Precision at N across all genres: 0.1556
- Average Recall at N across all genres: 0.6667
- Average F1-score at N across all genres: 0.2487

## Kesimpulan dari Nilai Rata-rata
1. Precision = nilai 0.1556 berarti, hanya 15 persen pergenre dari rekomendasi yang diberikan, merupakan nama game yang secara spesifik disebutkan di user_preferences
2. Recall = nilai 0.6667 berati, ada 66 persen pergenre dari user_preferences yang disebutkan, berhasil muncul dalam 5 rekomendasi game teratas untuk genre yang sesuia
3. F1-score = nilai 2487 berarti, nilai rata-rata harmonis antara precision dan recall cenderung rendah, sebagai akibat dari nilai precision yang rendah.
## insight
1. Sistem sudah berhasil merekomendasikan game dengan genre yang sama dengan kesukaan pengguna
2. Kesimpulan dari evaluasi adalah, sistem hanya memiliki kemampuan menengah dalam menyebutkan kembali game yang disukai pengguna atau (user_preferences). Nilai precision yang kecil menujukkan kalau nama game yang direkomendasikan oleh sistem, hanya sebagian kecil yang disukai pangguna. nilai f1-score yang rendah juga berarti bahwa kemampuan keseluruhan sistem, masih memiliki ruang yang besar untuk perbaikan

## saran yang bisa diambil
daftar game yang disukai atau user_preferences bisa ditambah, supaya rekomendasi yang diberikan sistem bisa semakin mendekati game yang disukai pengguna, dan untuk menaikan nilai precision.

**---Ini adalah bagian akhir laporan---**
