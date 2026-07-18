**SUPERMARKET CUSTOMERS DATA DICTIONARY**

**Author: Edward Hutapea – Data Scientist**

**Overview**

Loyalitas pelanggan terhadap produk supermarket merupakan tantangan supermarket dari waktu ke waktu. Dataset menunjukkan Churn Rate 68%. Kondisi ini bisa disebabkan strategi marketing yang kurang tepat sasaran dan kurang atraktif, serta prediksi nilai transaksi pelanggan yang kurang akurat. Jika masalah ini tidak diselesaikan sekarang, laba supermarket bisa stagnan atau menurun. Kondisi ini diperburuk dengan kehadiran kompetitor beserta variasi produk yang ditawarkan, sehingga pelanggan memiliki banyak opsi untuk mendapatkan produk yang dibutuhkan.

Peningkatan laba bisa mulai dilakukan dengan meningkatkan promosi yang atraktif kepada most valuable customers. Berdasarkan return of investment, mengeluarkan uang untuk mengejar mereka jauh lebih efektif dibandingkan mengejar pelanggan lainnya. Project ini bantu supermarket menemukan most valuable customers berdasarkan analisa data historis pelanggan dan memberikan rekomendasi personalized promotion yang kontekstual sesuai profil mereka. 

Di sisi lain, target penjualan perlu juga diprediksi sedari awal untuk menjadi referensi dalam menghitung budget promo yang reasonable sesuai target laba. Project ini juga bangun model machine learning yang digunakan untuk prediksi nilai transaksi pelanggan, sehingga penentuan target penjualan jadi lebih realistis. Kombinasi personalized promotion kepada most valuable customers dan implementasi model machine learning bisa turunkan churn rate dan tingkatkan laba supermarket.

**Insights**

1.	*Most Valuable Customers* – Beberapa fitur dataset diolah lebih lanjut untuk menggambarkan profil demografi pelanggan seperti generasi, usia, status pernikahan, pendidikan dan income. Untuk setiap segmentasi demografi, rasio transaksi pelanggan dihitung dengan membagi total nilai transaksi dengan jumlah pelanggan. Semakin tinggi rasio transaksi, semakin kecil ”cost” supermarket untuk memperoleh penjualan yang besar. Most valuable customers adalah segmen dengan rasio transaksi tertinggi, yaitu segmen pelanggan dengan income selama 2 tahun > $120K.

2.	*Personalized Promotion* – Rekomendasi personalized promotion kepada most valuable customers disusun berdasarkan spending/income rate, yaitu indikator kapasitas dan kemauan belanja seorang pelanggan. Bagi pelanggan dengan spending/income rate > nilai mediannya, relatif tidak ada keraguan untuk “spending” di supermarket. Namun, bagi pelanggan dengan spending/income rate < median, budget belanjanya terbatas sehingga perlu berhati-hati saat berbelanja. Personalized promotion difokuskan pada segmen pelanggan spending/income rate > median terlebih dahulu.

3.	*Model Machine Learning* – Model terbaik dipilih berdasarkan R squared dan error (MAE, MSE, RMSE). Semakin R-squared mendekati 1, model semakin fit mewakili variasi data. Semakin kecil error, model semakin akurat prediksi total transaksi pelanggan. Model terbaik yaitu tuning random forest regressor, namun prediksi total transaksi masih bisa meleset (rata-rata) $110 per orangnya. Berdasarkan feature importances, total transaksi banyak dipengaruhi cara berbelanja, income dan sudah berapa lama menjadi member supermarket.

**Conclusion**

Jika supermarket melakukan personalized promotion kepada most valuable customers (mulai dari pelanggan yang memiiki spending/income rate > median) serta menerapkan model tuning random forest regressor, maka supermarket bisa beralih dari strategi bisnis bersifat tebakan (instinct-driven) menjadi berbasis data (data-driven), dan berujung pada penurunan churn rate dan peningkatan laba supermarket.
