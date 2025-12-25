# 🛵 Analisis Prediksi Status Pengiriman Foodpanda

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Library](https://img.shields.io/badge/Library-Pandas_|_Scikit--Learn_|_Seaborn-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Tentang Proyek
Proyek ini adalah bagian dari tugas mata kuliah **Data Mining**. Tujuannya adalah untuk melakukan analisis data eksploratif (EDA) dan membangun model *Machine Learning* untuk memprediksi **status pengiriman (`delivery_status`)** pada layanan Foodpanda.

Proyek ini mencakup alur kerja *Data Science* lengkap mulai dari pembersihan data, visualisasi, preprocessing, hingga perbandingan performa algoritma klasifikasi.

## 📂 Struktur Dataset
Dataset yang digunakan adalah **Foodpanda Analysis Dataset**.
* **Target Variabel:** `delivery_status` (Status pengiriman pesanan).
* **Fitur Utama:**
    * `quantity`: Jumlah item yang dipesan.
    * `price`: Harga pesanan.
    * `order_frequency`: Frekuensi pemesanan pelanggan.
    * `loyalty_points`: Poin loyalitas pelanggan.
    * `rating`: Penilaian pelanggan.
    * Fitur kategorikal lainnya: `gender`, `city`, `payment_method`, dll.

## ⚙️ Metodologi

### 1. Exploratory Data Analysis (EDA)
Tahap ini dilakukan untuk memahami distribusi data dan hubungan antar variabel:
* Pengecekan *Missing Values* dan *Duplikat*.
* **Analisis Univariat:** Histogram dan Countplot untuk melihat distribusi fitur numerik dan kategorikal.
* **Analisis Bivariat:** Hubungan antara `price` vs `loyalty_points`, `rating`, dan `churned` menggunakan Boxplot, Scatterplot, dan Heatmap korelasi.
* **Deteksi Outlier:** Menggunakan metode IQR (Interquartile Range) dan Z-Score.

### 2. Data Preprocessing
Sebelum pemodelan, data diproses melalui tahapan:
* **Cleaning:** Menghapus kolom ID yang tidak relevan (`customer_id`, `order_id`) dan menangani *missing values*.
* **Feature Engineering:** Mengubah kolom tanggal menjadi tipe `datetime`.
* **Encoding:** Menggunakan `LabelEncoder` untuk mengubah variabel kategorikal (seperti `gender`, `city`, `churned`) menjadi numerik.
* **Scaling:** Normalisasi fitur numerik menggunakan `MinMaxScaler` agar berada dalam rentang 0-1.

### 3. Modeling
Tiga algoritma klasifikasi digunakan dan dibandingkan performanya:
1.  **K-Nearest Neighbors (KNN):** (`n_neighbors=5`)
2.  **Decision Tree Classifier**
3.  **Random Forest Classifier**

Data dibagi menjadi **80% Training** dan **20% Testing**.

## 📊 Hasil Evaluasi
Evaluasi dilakukan menggunakan **Confusion Matrix** dan **Classification Report**. Berikut adalah perbandingan akurasi model:

| Model | Akurasi |
| :--- | :--- |
| **K-Nearest Neighbors (KNN)** | *(0.32)* |
| **Decision Tree** | *(0.32)* |
| **Random Forest** | *(0.34)* |

> *Kesimpulan sementara: Random Forest cenderung memberikan performa yang lebih stabil dibandingkan model lainnya.*

## 🚀 Cara Menjalankan Project
Karena proyek ini dibuat di Google Colab dengan integrasi Google Drive, ikuti langkah berikut untuk menjalankannya di lokal atau Colab orang lain:

1.  **Clone Repository:**
    ```bash
    git clone [https://github.com/enjeliaa/Project-data-mining.git](https://github.com/enjeliaa/Project-data-mining.git)
    ```
2.  **Dataset Path:**
    * Jika menggunakan Google Colab: Upload dataset ke Google Drive Anda dan sesuaikan path pada baris:
        ```python
        df = pd.read_csv('/content/drive/MyDrive/path/to/dataset.csv')
        ```
    * Jika menggunakan Jupyter Lokal: Simpan file CSV di folder yang sama dengan notebook dan ubah menjadi:
        ```python
        df = pd.read_csv('Foodpanda Analysis Dataset.csv')
        ```
3.  **Install Library:**
    Pastikan library berikut sudah terinstall:
    ```bash
    pip install pandas numpy seaborn matplotlib scikit-learn scipy
    ```

## 👤 Identitas Penulis
* **Nama:** Anjelia Hidayat
* **NIM:** 09011182429012
* **Kelas:** SK3A
* **Mata Kuliah:** Data Mining

---
*Jangan lupa beri ⭐ pada repository ini jika bermanfaat!*
