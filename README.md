# Laporan Submission Akhir - System Recommendation Movie
---

## Project Overview
### Latar Belakang
Film adalah gambar-hidup yang juga sering disebut movie. Film secara kolektif sering disebut sebagai sinema. Sinema itu sendiri bersumber dari kata kinematik atau gerak. Selain itu film sendiri bisa kita tonton dimana saja dan kapan saja karena sudah tersedia di banyak platform seperti *Disney Hotsar*, *Netflix*, dan platform lainnya.

Sistem Rekomendasi merupakan suatu aplikasi yang digunakan untuk memberikan rekomendasi dalam membuat suatu keputusan yang diinginkan pengguna, untuk meningkatkan *User experience* dalam menentukan anime yang menarik dan sesuai dengan preferensi user. Jadi user memiliki rekomendasi sesuai dengan genre atau film yang disukai atau telah ditonton oleh user.

Pada proyek ini, dataset yang dipakai berasal dari situ web [Kaggle](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows), dan dataset ini memiliki 1000 data film.

## Bussiness Understanding

### Problem Statements
- Bagaimana cara membuat sistem yang dapat merekomendasikan film berdasarkan genre yang sama ?
- Bagaimana cara membuat sistem yang dapat merekomendasikan film dari histori tontonan yang pernah kita lihat sebelumnya?

### Goals
- Mengetahui cara membuat sistem rekomendasi film berdasarkan genre yang sama
- Mengetahui cara membuat sistem rekomendasi film berdasarkan histori tontonan yang pernah kita lihat sebelumnya

### Solution Statements
Solusi yang saya pilih untuk menyelesaikan masalah ini adalah dengan menggunakan teknik *content-based filtering*, berikut adalah penjelasan teknik-teknik yang digunakan untuk masalah ini :

- **Content-based filtering** : adalah algoritma yang merekomendasikan film serupa dengan apa yang disukai pengguna, berdasarkan tindakan mereka sebelumnya atau umpan balik eksplisit.
- Filter jenis ini tidak melibatkan pengguna lain Melainkan hanya diri kita sendiri. Berdasarkan apa yang kita suka, algoritma ini hanya akan memilih item dengan konten serupa untuk merekomendasikan kita.

## Data Understanding
Dataset yang saya pakai adalah [IMDB Movies Dataset](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows) yang berisi informasi tentang top 1000 berdasarkan rating halaman IMDB, Analisis Data Eksplorasi mencakup proses mengidentifikasi pola,menemukan anomali,menguji hipotesis, dan memeriksa asumsi melalui statistik ringkasan.

- Dataset ini memiliki 1000 data dan memiliki 16 kolom dalam dataset kali ini namun dalam proyek ini saya hanya menggunakan 6 kolom, berikut penjelasannya :

  - Series_Title : Judul dari film
  - Certificate : Rating umur pada film
  - Genre : Genre film
  - IMDB_Rating : Nilai rating yang diberikan oleh IMDB
  - Meta_score : Skor yang didapat oleh film
  - Director : Nama dari direktor film
  
### Analisis Data Eksplorasi

#### Univariate Analysis
- Informasi yang bisa didapat dari hasil eksplorasi pada variabel pada dataset

    ![rating](https://user-images.githubusercontent.com/77862455/197952430-2c4a08e3-d794-4549-827d-70b68eec8446.PNG)

    <em>Gambar 1. Univariate Analysis</em>

- Informasi yang saya dapat dari data diatas adalah :
    - Film dengan rating U memiliki jumlah paling banyak
    - Film dengan rating GP memiliki jumlah paling sedikit

    ![displot](https://user-images.githubusercontent.com/77862455/197952484-b58c26f1-af7e-42db-8ad6-53407ed9706d.PNG)

    <em>Gambar 2. Univariate Analysis</em>

- Informasi yang saya dapat dari data diatas adalah :
    - Banyak film yang memiliki rentang nilai dari 7-8 dibandingkan dengan rentang yang lainnya.


#### Multivariate Analysis

 ![multi](https://user-images.githubusercontent.com/77862455/197952822-14ea477e-eaa6-4a93-8439-b3990e8c02bd.PNG)

 <em>Gambar 3. Multivariate Analysis</em>

## Data Preparation

Sebelum melakukan pembuatan model, perlu dilakukan data preparation, berikut adalah hal yang dilakukan pada proses data preparation

- **Drop Missing Value** : ini bertujuan untuk membersihkan data agar tidak ada data yang kosong, karena data kosong sangat mempengaruhi hasil akurasi dari model, disini saya membuang beberapa variabel yaitu 'Poster_Link','Released_Year', 'Runtime', 'Overview', 'Star1', 'Star2', 'Star3', 'Star4', 'No_of_Votes', 'Gross'

- **Text Cleaning** : ini bertujuan untuk menghapus simbol ataupun teks yang tidak diperlukan dan mengubah semua huruf menjadi huruf kecil

## Modeling

Model yang saya gunakan pada data ini adalah dengan menggunakan teknik *content-based filtering*.
- Saya juga menggunakan ``TF-IDF Vectorizer`` untuk membangun sistem rekomendasi berdasarkan genre, dimana ``TF-IDF`` berfungsi untuk mengukur seberapa pentingnya suatu kata terhadap kata-kata lain dalam dokumen.
- Selanjutnya saya melakukan fit dan transformasi kedalam bentuk matriks, untuk menghitung derajat kesamaan antar film, disini saya menggunakan teknik *cosine similarity*
- Berikut adalah hasil dari teknik *cosine similarity*

    ![cosine](https://user-images.githubusercontent.com/77862455/197954157-9ad97dee-f019-465b-9119-408ce626ea20.PNG)

    <em>Gambar 4. Hasil dari Cosine Similarity</em>

    ![hasilcosine](https://user-images.githubusercontent.com/77862455/197954208-26f4e08f-894f-4cd7-b92c-ca70546dc7de.PNG)

    <em>Gambar 5. Hasil dari Cosine Similarity</em>

- Lalu setelah melakukan teknik *cosine similarity* dan muncul rekomendasi, maka saya mencoba membuat fungsi untuk meminta rekomendasi film berdasarkan judul yang saya inputkan.
    ```
    get_Movie_Recommendations('big hero 6')
    ```

- Dan berikut adalah hasil 10 anime yang direkomendasikan dari model *content-based filtering* :
  ![hasilrek](https://user-images.githubusercontent.com/77862455/197954543-d4205574-cf51-453a-bf55-f4fef0af908e.PNG)

    <em>Gambar 6. Hasil dari Content-based filtering</em> 

    Model berhasil memberikan rekomendasi 10 film dengan genre yang sama seperti yang diharapkan.
