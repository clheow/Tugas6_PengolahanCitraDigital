# Program Deteksi Tanda Tangan pada Ijazah

## Deskripsi

Program ini digunakan untuk mendeteksi keberadaan tanda tangan pada gambar ijazah menggunakan Python dan OpenCV. Proses deteksi dilakukan melalui pemotongan area tertentu (ROI), konversi gambar ke grayscale, thresholding, dan perhitungan rasio piksel foreground.

## Cara Menjalankan Program

1. Buka folder proyek di Visual Studio Code.
2. Pastikan gambar ijazah sudah ditempatkan pada folder `images/ada_ttd/` dan `images/tidak_ada_ttd/`.
3. Buka terminal di VS Code melalui menu **Terminal → New Terminal**.
4. Jalankan perintah berikut:

```bash
python main.py
```

5. Program akan menampilkan gambar untuk memilih area tanda tangan (ROI). Pilih area yang sama pada setiap gambar, lalu tekan **Enter** atau **Space** untuk melanjutkan.
6. Tunggu hingga seluruh gambar selesai diproses.
7. Hasil deteksi dan perhitungan akurasi akan ditampilkan oleh program.

## Hasil Program

Hasil deteksi disimpan dalam file CSV bernama `hasil_deteksi_tanda_tangan.csv` di dalam folder `hasil/`. File tersebut berisi label asli, rasio foreground, hasil prediksi, dan status benar atau salah.


## Mengapa thresholding diperlukan sebelum melakukan analisis keberadaan tanda tangan?
Thresholding diperlukan untuk memisahkan objek tanda tangan dari latar belakang gambar ijazah. Pada tahap ini, gambar grayscale diubah menjadi citra biner yang terdiri dari piksel hitam dan putih. Dengan begitu, tanda tangan lebih mudah dibedakan dari kertas ijazah.

Hasil thresholding juga memudahkan perhitungan jumlah piksel foreground yang digunakan sebagai salah satu ciri untuk menentukan apakah tanda tangan terdapat pada gambar atau tidak.

# Jawaban Analisis

## Apa masalah yang terjadi jika threshold terlalu tinggi atau terlalu rendah?
Jika nilai threshold terlalu tinggi, beberapa bagian tanda tangan yang tipis atau kurang jelas dapat hilang karena dianggap sebagai latar belakang. Akibatnya, jumlah piksel foreground menjadi lebih sedikit dan tanda tangan mungkin tidak terdeteksi.

Sebaliknya, jika nilai threshold terlalu rendah, bagian latar belakang, tulisan lain, atau noda pada ijazah dapat ikut dianggap sebagai foreground. Hal ini membuat jumlah piksel foreground bertambah dan dapat menyebabkan sistem salah mengidentifikasi keberadaan tanda tangan.
