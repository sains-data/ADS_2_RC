# ADS_2_RC - Analisis Data Statistik Tugas Kelompok 2

## Daftar Isi
- [Struktur Repository](#struktur-repository)
- [Cara Menjalankan Script](#cara-menjalankan-script)
- [Paket R yang Digunakan](#paket-r-yang-digunakan)
- [Penjelasan Dataset](#penjelasan-dataset)

---

## Struktur Repository

```
ADS_2_RC/
├── README.md                 # Dokumentasi proyek
├── codeR_2_RC.Rmd            # Script R Markdown untuk analisis ANOVA
├── data_2_RC.xlsx            # Data jam belajar mahasiswa per kategori keterlibatan
├── Output_2_RC.pdf           # Folder untuk output analisis
├── poster_ads_2.pdf          # Poster penelitian
```

---

## Cara Menjalankan Script

### Prasyarat
- **RStudio** sudah terinstal
- **R** versi 3.6 atau lebih baru

### Langkah-langkah

1. **Buka file** `codeR_2_RC.Rmd` menggunakan RStudio

2. **Instal paket yang dibutuhkan** (jika belum terinstal):
   ```r
   install.packages(c("readxl", "dplyr", "tidyr"))
   ```

3. **Pastikan dataset tersedia** di folder `data/dataset.xlsx`

4. **Jalankan analisis** dengan mengklik tombol **Knit** di bagian atas RStudio
   - Pilih format output (HTML, PDF, atau Word)

5. **Output akan dihasilkan** dalam bentuk:
   - Laporan HTML/PDF/Word
   - File teks hasil analisis di folder `output/`
   - Visualisasi grafik

---

## Paket R yang Digunakan

| Paket | Fungsi |
|-------|--------|
| **readxl** | Membaca file Excel (.xlsx) yang berisi data penelitian |
| **dplyr** | Pembersihan data, seleksi kolom, manipulasi data, dan filtering |
| **tidyr** | Mengubah data dari format wide ke long (pivoting) sebelum analisis ANOVA |

---

## Penjelasan Dataset

### Deskripsi Umum
Dataset berisi **data jam belajar mahasiswa per minggu** berdasarkan kategori tingkat keterlibatan dalam kegiatan kampus. Data berasal dari file Excel dan dianalisis menggunakan **ANOVA One-Way**.

### Variabel Utama

| Variabel | Penjelasan |
|----------|-----------|
| **Kategori** | Empat kelompok tingkat keterlibatan mahasiswa:<br>- Aktif kegiatan akademik<br>- Aktif kegiatan organisasi kemahasiswaan<br>- Tidak aktif<br>- Lainnya |
| **Jam** | Jumlah jam belajar per minggu dari masing-masing mahasiswa (variabel respon ANOVA) |

### Transformasi Data
- Data awal berformat **wide** (masing-masing kategori di kolom terpisah)
- Ditransformasi ke format **long** menggunakan `pivot_longer()` dari paket **tidyr**
- Format long memudahkan analisis ANOVA one-way

---

## Metode Analisis

Penelitian ini menggunakan **ANOVA One-Way** untuk menguji hipotesis:
- **H₀**: Rata-rata jam belajar sama untuk semua kategori keterlibatan
- **H₁**: Minimal ada satu kategori yang berbeda rata-rata jam belajarnya

---

## Output yang Dihasilkan

1. **Statistik Deskriptif** - Mean, SD, N untuk setiap kategori
2. **Tabel ANOVA** - F-statistic, p-value, dan kesimpulan
3. **Visualisasi** - Boxplot dan barplot perbandingan jam belajar
4. **Interpretasi** - Kesimpulan hasil analisis
