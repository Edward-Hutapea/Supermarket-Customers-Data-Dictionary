**SUPERMARKET CUSTOMERS DATA DICTIONARY**

**Author: Edward Hutapea – Data Analyst**

**Dataset**

Fitur-fitur di dataset berkaitan dengan profil demografi pelanggan supermarket, produk supermarket, respon pelanggan terhadap promo/diskon, dan cara pelanggan bertransaksi di supermarket.

**Overview**

Loyalitas pelanggan terhadap produk supermarket merupakan tantangan yang dihadapi supermarket dari waktu ke waktu. Dataset menunjukkan Churn Rate (dari keseluruhan pelanggan) sebesar 68%. Kondisi ini bisa menyebabkan omset penjualan supermarket menjadi stagnan. Di saat yang bersamaan, kehadiran kompetitor beserta variasi produk yang ditawarkan membuat pelanggan memiliki banyak opsi untuk mendapatkan produk yang dibutuhkan. 

**Problem Statement**

Promo/diskon produk yang kurang tepat sasaran dan kurang atraktif. 

**Goals**
1.	Menemukan “Most Valuable Customers” yang bisa signifikan meningkatkan omset penjualan supermarket berdasarkan analisa data historis pelanggan. Dari sisi biaya (Return of Investment), mengeluarkan uang untuk mengejar mereka jauh lebih efisien dibandingkan mengejar pelanggan lainnya. Jika jumlah "Most Valuable Customers" bisa bertambah, maka omset penjualan bisa melonjak signifikan. 
2.	Memberikan rekomendasi ”Personalized Promotion" yang bisa digunakan supermarket kepada “Most Valuable Customers” sehingga strategi marketing bisa lebih kontekstual.
3.	Membangun model machine learning yang membantu supermarket memprediksi total transaksi pelanggan seakurat mungkin sehingga penentuan target penjualan menjadi lebih realistis.

Kombinasi Most Valuable Customers, Personalized Promotion dan model machine learing membuat kegiatan promosi bisa lebih optimal dan profit supermarket bisa meningkat.

**Machine Learning Models Tested**
-	KNN Regressor
-	Linear Regression
-	DecisionTree Regressor
-	RandomForest Regressor dan Tuning RandomForest Regressor

**Evaluation Metrics: R squared, MAE, MSE dan RMSE**
- R-squared digunakan untuk mengetahui seberapa bagus model dapat merepresentasikan varians keseluruhan data. Semakin R-squared mendekati 1, maka semakin fit pula modelnya terhadap data observasi.
- Semakin kecil nilai Error (MAE, MSE dan RMSE) yang dihasilkan, berarti model semakin akurat dalam memprediksi total transaksi pelanggan sesuai dengan limitasi fitur yang digunakan.

**Best Model Summary: Tuning Random Forest Regressor**
- R squared = 0.867662
- MAE = 110.198016
- MSE = 45579.704465
- RMSE = 212.337884

**Key Insights**

**a) Analisa Data Historis Pelanggan Supermarket:**
1.	Pencarian "Most Valuable Customers" dilakukan berdasarkan riwayat ”Rasio Transaksi” (yaitu rasio total nilai transaksi terhadap jumlah pelanggan) untuk setiap segmen pelanggan. Semakin tinggi rasio transaksi, maka semakin kecil biaya yang supermarket keluarkan untuk mendapatkan penjualan yang besar.  "Most Valuable Customers" adalah segmen pelanggan yang memiliki income 2 tahun > $120K (memiliki rasio transaksi yang tinggi). 
2.	Berdasarkan data "Most Valuable Customers":
-	Produk Wine adalah produk paling diminati.
-	Transaksi paling banyak dilakukan secara offline langsung di supermarket.
-	Namun, jumlah transaksi dengan harga diskon hanya 10% dari keseluruhan jumlah transaksi. Promo diskon yang dilakukan selama ini mungkin kurang efektif.
3.	”Personalized Promotion" kepada “Most Valuable Customers” bisa dilakukan berdasarkan Spending/Income Rate (yaitu indikator kapasitas dan kemauan belanja seorang pelanggan). Berdasarkan spending/income rate, Most Valuable Customers bisa dibagi dalam 2 segmen yaitu:
  - Pelanggan dengan “Spending/Income Rate > Median”. Mereka tidak ragu mengeluarkan uang untuk bertransaksi di supermarket. Kehilangan 1 pelanggan di segmen ini sama sakitnya dengan kehilangan beberapa pelanggan di segmen lain. 
  - Pelanggan dengan “Spending/Income Rate < Median”. Mereka berhati-hati dalam bertransaksi karena memiliki anggaran terbatas.
4.	Monetisasi – Untuk memberikan gambaran kepada management supermarket, potensi peningkatan omset penjualan bisa dilakukan lewat 2 simulasi yaitu:
  -	Dengan mengurangi churn rate dari "Most valuable customers".
  -	Dengan meningkatkan transaksi dari pelanggan yang memiliki "spending/income rate < median" 

**b) Model Machine Learning:**
1.	Model hanya bisa dipakai untuk total transaksi pelanggan > $1,500. Model belum sepenuhnya siap untuk transaksi < $1,500 sehingga perlu dioptimalkan lagi.
2.	Model membantu supermarket dalam memprediksi total transaksi pelanggan, namun total transaksi bisa meleset sekitar $110 s/d $212 per orangnya.
3.	Model membantu supermarket beralih dari strategi bisnis yang bersifat tebakan (instinct-driven) menjadi berbasis data (data-driven).
4.	Model bisa membantu supermarket dalam personalized promotion, optimalisasi supply chain dan perencanaan target penjualan.
5.	Untuk model ini, berdasarkan feature importances, fitur yang sangat mempengaruhi total transaksi pelanggan adalah cara/metode pelanggan bertransaksi (offline, online atau memanfaatkan katalog), income pelanggan dan sudah berapa lama pelanggan menjadi member supermarket.

**Rekomendasi**

**a) Untuk Analisa Data Historis Pelanggan Supermarket:**
1.	Personalized promotion kepada “Most Valuable Customers” bisa difokuskan pada segmen pelanggan “Spending/Income Rate > Median” terlebih dahulu. Fokus pada kualitas layanan dan tawarkan produk Premium kepada mereka tanpa terlalu khawatir dengan sensitivitas harga. Kemudian lanjutkan pada segmen pelanggan “Spending/Income Rate < Median”. Fokus pada efisiensi sistem operasional supermarket agar biaya operasional tidak membengkak saat melayani jumlah pelanggan yang banyak. Tawarkan produk yang bersifat “Value-for-Money” agar mereka merasa mendapatkan keuntungan maksimal.
2.	Rekomendasi tambahan:
  -	Kampanye promosi – Optimalkan promo/discount langsung di kampanye pertama, supaya lebih banyak pelanggan yang langsung membeli produk diskon tanpa menunggu tahapan kampanye berikutnya.
  -	Jenis produk –  Tingkatkan promo dan beri tawaran khusus (seperti paket pembelian bundling, dll) untuk produk fruits, sweet, fish dan gold. Tambah variasi sub-produk untuk masing-masing produk, sehingga pelanggan tidak perlu pergi ke supermarket kompetitor.
  -	Metode/media transaksi – Kurangi biaya tambahan (seperti admin fee, service charge dll) yang terdapat di transaksi online melalui website supermarket. Biaya tambahan ini mungkin juga menjadi penyebab churn.
3.	Lakukan analisa ulang secara rutin berdasarkan data penjualan terbaru untuk meningkatkan akurasi penentuan ”most valuable customer”.

**b) Untuk Model Machine Learning:**
1.	Model Improvement – Dataset dan model algoritma bisa dikembangkan (khususnya untuk total transaksi pelanggan < $1,500) dengan cara sebagai berikut:
  -	Test Alternative Models – Scaler (Standard, Robust), Regularization (Ridge, Lasso, ElasticNet), Polynomial Features dan hyperparameter tuning.
  -	Add New Data & Re-training Data – Perbanyak data baru yang bukan duplikat. Kemudian lakukan training data secara rutin untuk meningkatkan akurasi model terhadap data terbaru.
2.	Add New Features – Waktu tempuh dari tempat tinggal menuju supermarket, metode pembayaran (tunai, kartu kredit, cicilan/paylater)
