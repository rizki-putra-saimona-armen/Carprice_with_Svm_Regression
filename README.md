# Support Vector Regression (SVR) & Hyperparameter Tuning

Repository ini berisi proyek implementasi algoritma **Support Vector Machine (SVM) untuk kasus Regresi (SVR)**. Proyek ini berfokus pada pentingnya penanganan skala data (*Feature Scaling*) pada algoritma berbasis jarak, penanganan *outliers*, serta bagaimana mengevaluasi performa prediksi menggunakan berbagai metrik regresi standar industri.

##  Fitur Utama Proyek
* **Data Preprocessing & Scaling:** Implementasi `MinMaxScaler` secara konsisten untuk mencegah *Data Leakage* antara data latihan dan data uji.
* **Support Vector Regression:** Pemodelan menggunakan `SVR` dengan analisis performa berbasis batas toleransi (*$\epsilon$-insensitive tube*).
* **Comprehensive Evaluation:** Mengukur tingkat error model menggunakan tiga metrik utama: **MAE**, **MSE**, dan **RMSE**.
* **Outliers & Scaling Impact Analysis:** Analisis mengapa algoritma berbasis jarak seperti SVR mewajibkan adanya *scaling* agar fitur berdomain besar tidak mendominasi perhitungan jarak.

---

##  Mengapa Scaling Sangat Krusial pada SVR?

Algoritma SVR bekerja dengan cara menghitung jarak geometris antar titik data untuk menemukan *hyperplane* terbaik. 
* Tanpa *Scaling*, fitur yang memiliki rentang nilai besar (misal: Harga Rumah dalam jutaan) akan mendominasi fitur berrentang kecil (misal: Jumlah Kamar), sehingga model menjadi bias.
* **Konsistensi `.fit()` & `.transform()`:** Proses `.fit(X_train)` mendeteksi batas minimum dan maksimum murni dari data *training*, lalu dipergunakan untuk men-`.transform()` kedua *set* data. Hal ini menjaga agar model tetap diuji secara adil menggunakan data baru (`X_test`) tanpa mengubah standar skala yang sudah dipelajari.

---

##  Metrik Evaluasi Regresi

Untuk mengukur seberapa presisi model SVR dalam memprediksi target, proyek ini menggunakan:
1. **MAE (Mean Absolute Error):** Memberikan gambaran rata-rata tingkat melesetnya prediksi secara riil dan linear.
2. **MSE (Mean Squared Error):** Menghitung rata-rata kuadrat *error* untuk melihat seberapa konsisten model menghindari kesalahan tebakan yang fatal.
3. **RMSE (Root Mean Squared Error):** Mengakar-kuadratkan MSE untuk mengembalikan satuan error ke bentuk aslinya, memberikan metrik yang ketat terhadap pencilan (*outliers*) namun tetap mudah diinterpretasikan.

---

##  Tech Stack & Library
* **Python** (Bahasa Pemrograman Utama)
* **Jupyter Notebook** (`.ipynb`)
* **Pandas & NumPy** (Manipulasi Data dan Komputasi Numerik)
* **Scikit-Learn** (`SVR`, `MinMaxScaler`, `train_test_split`, dan `metrics`)
* **Matplotlib / Seaborn** (Visualisasi Prediksi vs Nilai Aktual)

---

##  Cara Menjalankan Proyek

1. **Clone Repositori Ini:**
   ```bash
   git clone [https://github.com/username-kamu/nama-repositori.git](https://github.com/username-kamu/nama-repositori.git)
   cd nama-repositori
