# Project-Machine-Learning
## ANALISIS PENGARUH STRATEGI PEMASARAN TERHADAP PENDAPATAN PENJUALAN PADA MARKETING SALES DATASET 

## DESCRIPSI PROJECT
<b>Deskripsi Studi Kasus</b> <br>
<br>
Sebuah perusahaan ingin menganalisis dan memprediksi pendapatan penjualan (sales_revenue_usd) berdasarkan berbagai faktor yang berkaitan dengan aktivitas pemasaran, karakteristik pelanggan, serta kondisi pasar. Faktor-faktor tersebut meliputi anggaran pemasaran, pengeluaran iklan online dan offline, jumlah promosi, tingkat diskon, lalu lintas website, tingkat konversi pelanggan, hingga kepuasan pelanggan. <br>
<br>
Tujuan : Memprediksi besarnya pendapatan penjualan (sales_revenue_usd) yang akan diperoleh perusahaan berdasarkan berbagai data terkait aktivitas pemasaran, karakteristik pelanggan, dan kondisi pasar. Model yang dibangun nantinya dapat digunakan sebagai alat pendukung pengambilan keputusan dalam merencanakan strategi pemasaran dan mengalokasikan anggaran promosi secara lebih efektif. Dengan adanya prediksi pendapatan penjualan yang lebih akurat, perusahaan diharapkan dapat meningkatkan efisiensi dalam perencanaan bisnis, memaksimalkan potensi pendapatan, serta meningkatkan daya saing di pasar


## ANGGOTA KELOMPOK :

```text
Zalma Hasna Solikhin      (K1D024004)
Salman Alfarisy           (K1D024010)
Natasya Jamila Mapaza     (K1D024016)
Galih Tri Prasetyo        (K1D024028)
Arroja Aliya Fadhilah     (K1D024037)
```
## SUMBER DATASET
```text
Dataset yang digunakan dalam penelitian ini diperoleh dari platform Kaggle dengan nama Marketing Sales Dataset,
yang menyediakan data terkait aktivitas pemasaran dan kinerja penjualan untuk keperluan analisis data
dan pengembangan model prediktif.

https://www.kaggle.com/datasets/abdelfattahibrahim/marketing-sales-dataset
```
## CARA MENJALANKAN SCRIPT
1. Buka Google Colab <br>
* Akses colab.researchearch.google.com.
* Buat Notebook baru dengan klik New Notebook (atau File > New Notebook).
  
2. Instal Library Pendukung <br>
  Pada sel pertama, jalankan perintah untuk menginstall pustaka openpyxl dan xgboost <br>
  Catatan: Sebagian besar library seperti NumPy, Pandas, Scikit-Learn, dan Matplotlib sudah terinstal di Colab, jadi tidak perlu diinstal   ulang.

3. Upload Dataset <br>
  Salin kode berikut ke sel baru dan jalankan:
  ```text
  python
  from google.colab import files
  uploaded = files.upload()
  ```
  Setelah dijalankan, akan muncul tombol "Choose Files". Klik dan pilih file marketing_dataset.xlsx dari komputer Anda. <br>  Tunggu hingga muncul pesan "Saving marketing_dataset.xlsx to marketing_dataset.xlsx" (artinya file berhasil diunggah ke lingkungan        runtime Colab).

4. Jalankan Tahapan Pemodelan 
  * Eksplorasi Data Awal <br>
    Baca file dengan pd.read_excel(), tampilkan df.info(), df.describe(), dan cek missing value. Tujuannya untuk memahami struktur dan        tipe data.
    
  * Visualisasi Data <br>
    Buat histogram, boxplot, scatter plot, dan heatmap korelasi. Langkah ini berguna untuk mendeteksi outlier, melihat distribusi, dan        mengidentifikasi fitur yang berkorelasi kuat dengan target (sales_revenue_usd).
    
  * Pra-pemrosesan (Preprocessing) <br>
    Lakukan Label Encoding pada kolom kategorikal (region, sales_channel, product_category, customer_segment, season). <br>
    Seleksi fitur: pilih hanya kolom yang paling relevan (misal: marketing_budget_usd, conversion_rate, num_previous_purchases, dll.). <br>
    Normalisasi dengan RobustScaler untuk menangani outlier pada fitur numerik.
    
  * Pembagian Data <br>
    Pisahkan data menjadi Training (80%) dan Testing (20%) menggunakan train_test_split.
    
  * Latih Model Baseline <br>
    Jalankan Regresi Linier Berganda dan Lasso sebagai model dasar (baseline) untuk melihat performa awal.
    
  * Latih Model Ensemble <br>
    Latih Random Forest Regressor dan XGBoost Regressor (dengan parameter default) untuk meningkatkan akurasi dibandingkan model linier.
    
  * Hyperparameter Tuning (Optimasi) <br>
    Lakukan pencarian parameter terbaik pada XGBoost menggunakan RandomizedSearchCV (proses ini akan memakan waktu sekitar 2–5 menit).
    
  * Evaluasi dan Perbandingan <br>
    Bandingkan semua model berdasarkan metrik MAPE, MAE, RMSE, dan R2. Model dengan MAPE terkecil adalah yang terbaik.
    
  * Analisis Lanjutan <br>
    Tampilkan Feature Importance untuk mengetahui fitur paling berpengaruh (biasanya marketing_budget_usd). <br>
    Buat Learning Curve untuk memastikan model tidak overfitting/underfitting. <br>
    Lakukan Analisis Residual untuk melihat pola kesalahan prediksi. <br>
    Tips: Tulis kode untuk tiap step di atas dalam sel terpisah. Dengan begitu, jika terjadi error, Anda tahu persis di bagian mana yang      bermasalah.

5. Perhatikan Proses Tuning <br>
Saat menjalankan RandomizedSearchCV, Colab akan menampilkan progres "Fitting 3 folds for each of 50 candidates". Biarkan hingga selesai (jangan hentikan runtime).

6. Cek Output Akhir <br>
Setelah semua sel selesai, Colab akan menampilkan secara otomatis:
-- Tabel statistik (deskripsi data, missing value, dll.). <br>
-- Grafik interaktif (histogram, boxplot, heatmap korelasi, scatter plot prediksi vs aktual). <br>
-- Tabel perbandingan model yang diurutkan berdasarkan MAPE (Mean Absolute Percentage Error). <br>
-- Feature Importance (grafik batang yang menunjukkan bahwa marketing_budget_usd adalah faktor terpenting). <br>
-- Learning Curve untuk memastikan model tidak overfitting/underfitting.

8. Simpan Notebook <br>
   Jangan lupa simpan progres ke Google Drive (File > Save a copy in Drive) agar pekerjaan tidak hilang dan bisa diakses kembali.
7. Model Terbaik <br>
   Di akhir proses, sistem akan mencetak teks: <br>
  "Berdasarkan MAPE terkecil, model terbaik adalah: Tuned XGBoost Regressor dengan MAPE: 0.1355". <br>
  Ini adalah hasil akhir yang menunjukkan bahwa model XGBoost yang sudah di-tuning menghasilkan error prediksi sekitar 13.55%,           menjadikannya yang paling akurat.



## RINGKASAN HASIL

Project ini membangun model machine learning untuk memprediksi pendapatan penjualan (sales revenue) berdasarkan strategi pemasaran menggunakan Marketing Sales Dataset. Tahapan yang dilakukan meliputi EDA, preprocessing, seleksi fitur, pemodelan regresi, hyperparameter tuning, dan evaluasi model.

Beberapa algoritma dibandingkan, yaitu Linear Regression, Lasso Regression, Random Forest Regressor, dan XGBoost Regressor. Berdasarkan metrik MAPE, XGBoost menjadi model terbaik dengan akurasi yang meningkat setelah hyperparameter tuning, menghasilkan MAPE 13,6%, MAE 45,87, RMSE 2411,5, dan R² 0,816.

Analisis feature importance menunjukkan bahwa customer_segment dan marketing_budget_usd merupakan faktor yang paling berpengaruh terhadap pendapatan penjualan, diikuti oleh season, product_category, dan sales_channel. Hasil evaluasi juga menunjukkan bahwa model memiliki kemampuan generalisasi yang baik dan tidak mengalami overfitting yang signifikan, meskipun akurasi masih menurun pada transaksi dengan nilai penjualan yang sangat tinggi akibat keberadaan outlier.

Secara keseluruhan, proyek ini menunjukkan bahwa XGBoost merupakan model yang efektif untuk memprediksi pendapatan penjualan dan dapat dimanfaatkan sebagai pendukung pengambilan keputusan dalam menyusun strategi pemasaran berbasis data.

