# Laporan Proyek Machine Learning - Muhamad Wahyudin Nuramanu

## Project Overview

Netflix salah satu platform yang menyediakan platform resmi untuk menonton film, netflix sendiri memiliki kemampuan yang dinamakan sistem rekomendasi, sistem ini bekerja berdasarkan data masa lampau yang disimpan di dalam server atau database dari data ini sistem akan memberikan rekomendasi yang personal bagi pengguna. Selain netflix banyak platform - platform lain yang menggunakan sistem ini dalam aplikasi mereka, di rasa sistem ini memiliki kemampuan untuk menarik minat pengguna untuk sering berinteraksi dengan aplikasi. Salah satunya adalah rekomendasi fashion atau pakaian, pada proyek ini akan dikembangkan sistem rekomendasi yang memeberikan rekomendasi pakaian - pakaian dari merek tertentu menggunakan nilai rating dari barang tersebut, rekomendasi ini akan memberikan barang - barang yang memiliki kualitas bagus berdasarkan rating yang diberikan



## Business Understanding
### Problem Statements

Pernyataan Masalah:
- Bagaimana mengembangkan sistem rekomendasi fashion dari brand tertentu yang memiliki rating tinggi pada pengguna lain

### Goals
Berdasarkan masalah yang telah ditetapkan di atas terdapat tujuan yang dicapai:
- Mengembangkan sistem rekomendasi yang mampu memberikan rekomendasi fashion dari brand tertentu yang memiliki rating tertinggi pada pengguna lain


## Data Understanding
Data ini bersumber dari kaggle, data ini dapat di akses melalui [link](https://www.kaggle.com/datasets/bhanupratapbiswas/fashion-products/data) ini. Data yang digunakan telah bersih tidak ada missing value (NaN) atau duplicated data, data ini berjumlah 1000 data dengan 9 fitur atau kolom

Variabel-variabel pada fashion dataset adalah sebagai berikut:
- User ID : Nomor atau ID dari pembeli pakaian
- Product ID : Nomor atau ID dari produk atau pakaian yang telah dibeli
- Product Name : Nama dari produk yang dijual
- Brand : Nama pembuat dari barang atau pakaian
- Category : Penggolongan pakaian berdasarkan kelamin dan usia, anak - anak, wanita atau pria
- Price : Harga dari pakaian
- Ratubg : Nilai yang diberikan oleh pembeli pada barang atau pakaian yang telah mereka beli
- Color : Warna dari pakaian
- Size : Ukuran dari pakaian



## Data Preparation
Pada bagian ini dijelaskan tahapan - tahapan mempersiapkan data untuk modeling
- Mengecek keberadaan duplicated data

  ![DuplocatedData](https://github.com/user-attachments/assets/f27d86cf-16ce-4acd-917d-43cdeffa6eaa)
  
- Mengencek keberadaan Missing Value

  ![Zeo](https://github.com/user-attachments/assets/e0277ba7-a374-4a63-a44f-f9cdc00cb73e)

- Menyandikan fitur User ID dan Product ID ke dalam indeks integer

  ![Encoding](https://github.com/user-attachments/assets/6e587f69-d493-4efc-a8ba-5a48c18de89f)

- Mapping User ID dan Produk ID ke masing - masing dataframe user, produk

  ![Mapping](https://github.com/user-attachments/assets/30b5ab11-09cd-41b9-8ca4-0cce8fe5cf20)


- Memastikan berapa jumlah pelanggan (User ID) dan barang yang telah mereka beli (Product ID)

  ![ALL COunt](https://github.com/user-attachments/assets/6f269b0f-723a-471b-af2e-768ce73c6ed3)

- Mengacak data untuk memebuat data lebih random lagi dengan tujuan pada tahap training data dapat bervariasi

  ![Random](https://github.com/user-attachments/assets/e7d5b410-1acf-441a-80fd-1dd293ffe9a5)

- Menormalisasi kolom rating

  ![Normal](https://github.com/user-attachments/assets/7f682a1a-877d-4511-b0e9-b58e6945b337)


- Membagi data untuk training dan validasi

  ![NExtTime](https://github.com/user-attachments/assets/4e042626-2250-4053-94df-1a369df7dc91)


## Modeling
Pada proyek ini akan menggunakan collaborative filtering
- Pertama akan dibuat kelas yang bernama RecommenderNet

  ![Class](https://github.com/user-attachments/assets/1cf7969d-6388-4fb1-a0dc-2f3805ad010b)

- Melakukan compile pada model

  ![compile](https://github.com/user-attachments/assets/4d4ea37d-8ea2-4dbe-89e1-e240ad8ae11a)

- Melakukan training

  ![DataTrain](https://github.com/user-attachments/assets/f8fd785e-b2cf-4e66-a79a-7543d7973fe6)


Berikut adalah contoh top 10 rekomendasi dari pakaian dengan berbagai brand

![OutputRecom](https://github.com/user-attachments/assets/73e98ddb-1526-4b1c-ab56-721d9c7b514c)



## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.
Pada collaborative learning digunakan RMSE (Root Mean Square Error) sebagai metrik evaluasi. RMSE bekerja dengan cara mengukur perbedaan antara nilai yang diprediksi oleh model dengan nilai sebenarnya, dengan mengukur rata-rata kesalahan kuadrat, kemudian mengambil akar kuadratnya. Semakin rendah nilai RMSE, semakin baik kinerja model dalam melakukan prediksi. 

![val_rekom](https://github.com/user-attachments/assets/c8415fd5-3b9b-44e8-8060-522aa45228c6)

Dari grafik yang ada fiketahui bahwa loss dari train data semakin kecil dan kecil serta loss dari val juga terdapat pengecilan namun jarak antara val dan loss terlalu tinggi hal ini bisa beranggapan bahwa model mengalami overfitting


**---Ini adalah bagian akhir laporan---**
