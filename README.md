# Project-Machine-Learning
## DESKRIPSI PROJECT :

### ANALISIS PENGARUH STRATEGI PEMASARAN TERHADAP PENDAPATAN PENJUALAN PADA MARKETING SALES DATASET ### 

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

### RINGKASAN HASIL
```text
Project ini membangun model **machine learning** untuk memprediksi **pendapatan penjualan (sales revenue)** berdasarkan strategi pemasaran menggunakan *Marketing Sales Dataset*. Tahapan yang dilakukan meliputi **EDA, preprocessing, seleksi fitur, pemodelan regresi, hyperparameter tuning,** dan **evaluasi model**.

Beberapa algoritma dibandingkan, yaitu **Linear Regression, Lasso Regression, Random Forest Regressor,** dan **XGBoost Regressor**. Berdasarkan metrik **MAPE**, **XGBoost** menjadi model terbaik dengan akurasi yang meningkat setelah *hyperparameter tuning*, menghasilkan **MAPE 13,6%**, **MAE 745,87**, **RMSE 2411,5**, dan **R² 0,816**.

Analisis **feature importance** menunjukkan bahwa **customer_segment** dan **marketing_budget_usd** merupakan faktor yang paling berpengaruh terhadap pendapatan penjualan, diikuti oleh **season**, **product_category**, dan **sales_channel**. Hasil evaluasi juga menunjukkan bahwa model memiliki kemampuan generalisasi yang baik dan tidak mengalami **overfitting** yang signifikan, meskipun akurasi masih menurun pada transaksi dengan nilai penjualan yang sangat tinggi akibat keberadaan **outlier**.

Secara keseluruhan, proyek ini menunjukkan bahwa **XGBoost** merupakan model yang efektif untuk memprediksi pendapatan penjualan dan dapat dimanfaatkan sebagai pendukung pengambilan keputusan dalam menyusun strategi pemasaran berbasis data.
```
