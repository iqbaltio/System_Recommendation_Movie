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
