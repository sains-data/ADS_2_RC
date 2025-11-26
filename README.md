# 1. Cara menjalankan script
1. Buka file codeR_2_RC.Rmd menggunakan RStudio.
2. Pastikan paket yang dibutuhkan sudah terinstal :

    install.packages(c("readxl", "dplyr","tidyr"))
3. Import dataset jika diperlukan :

    data <- read_csv("data/dataset.csv")
4. Untuk menjalankan seluruh analisis ANOVA dan menghasilkan output lengkap, klik tombol Knit di bagian atas RStudio.
5. Hasil analisis akan muncul dalam bentuk output console,sesuai kode yang ada pada file .Rmd.

# 2. Paket R yang digunakan
Analisis dalam file codeR_2_RC.Rmd menggunakan tiga paket utama :

readxl = digunakan untuk membaca file Excel (.xlsx) yang berisi data penelitian.

dplyr = digunakan untuk melakukan pembersihan data, seleksi kolom, manipulasi data, dan filtering.

tidyr = digunakan untuk mengubah data dari format wide ke long (pivoting) sebelum dilakukan analisis ANOVA.

# 3. Penjelasan singkat dataset
Dataset yang digunakan dalam analisis ini berisi data jam belajar mahasiswa per minggu berdasarkan kategori tingkat keterlibatan dalam kegiatan kampus. Data diambil dari file Excel yang kemudian dibaca menggunakan paket readxl.

Variabel utama yang digunakan:

Kategori 

Berisi empat kelompok tingkat keterlibatan mahasiswa : Aktif kegiatan akademik, Aktif kegiatan organisasi kemahasiswaan, Tidak aktif, Lainnya

Jam

Jumlah jam belajar per minggu dari masing-masing mahasiswa.
Nilai ini digunakan sebagai variabel respon dalam analisis ANOVA.

Dataset kemudian diubah dari format wide ke long menggunakan pivot_longer() agar dapat dianalisis menggunakan ANOVA one-way.