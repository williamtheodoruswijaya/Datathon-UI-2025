# Prediksi Keberhasilan IPO Saham di Indonesia

Repositori ini berisi keseluruhan alur kerja, data, model, dan analisis untuk proyek prediksi keberhasilan IPO (Initial Public Offering) saham di Indonesia. Tujuan utama dari proyek ini adalah untuk membangun model *machine learning* yang dapat memprediksi kinerja harga saham dalam berbagai jangka waktu (1 hari, 1 minggu, 1 bulan, 6 bulan, dan 1 tahun) setelah IPO.

## 📂 Struktur Direktori

Berikut adalah penjelasan mengenai struktur direktori dalam repositori ini:

```
.
├───data/                 # Berisi dataset mentah dan yang sudah diproses
├───lime/                 # Hasil interpretasi model menggunakan LIME
│   ├───1D/
│   ├───1M/
│   ├───1W/
│   ├───1Y/
│   └───6M/
├───model/                # Model-model yang sudah dilatih dan disimpan
│   ├───1D/
│   ├───1M/
│   ├───1W/
│   ├───1Y/
│   └───6M/
└───workflow/             # Berisi notebook untuk analisis dan pemodelan
    ├───Elena/
    ├───Filip/
    └───William/
```

## 💾 Dataset

Terdapat dua versi dataset utama yang digunakan dalam proyek ini:

1.  **Dataset Mentah (`data.csv`)**

      * Ini adalah dataset asli yang belum melalui proses pembersihan atau rekayasa fitur.
      * Dataset ini juga dapat diakses dan diunduh langsung dari [Hugging Face Datasets](https://huggingface.co/datasets/adamantix/Dataset_Lagi-Uas-Gaskeun).

2.  **Dataset yang Sudah Diproses (`processed-ipo-data.csv`)**

      * **Lokasi**: `data/processed-ipo-data.csv`
      * Ini adalah dataset yang sudah melalui tahap EDA (Exploratory Data Analysis), pembersihan data, dan rekayasa fitur (*feature engineering*).
      * **Gunakan dataset ini** untuk menjalankan bagian pemodelan secara langsung. Dataset ini siap untuk langsung di-split menjadi data latih dan data uji untuk dimasukkan ke dalam model.

## 📓 Notebook dan Alur Kerja

Seluruh proses analisis dan pemodelan terdokumentasi dalam Jupyter Notebook yang terletak di dalam direktori `workflow/`. Terdapat dua notebook utama dalam proyek ini:

  * `notebook.ipynb`: Ini adalah **notebook utama** yang berisi keseluruhan alur kerja, mulai dari Eksplorasi Data (EDA), rekayasa fitur, hingga pemodelan dan evaluasi menggunakan model utama seperti **TabNet**, **TabPFN**, dan *ensemble*.
  * `notebook_xgb.ipynb`: Notebook ini secara spesifik berisi implementasi dan evaluasi model **XGBoost**. Tujuannya adalah sebagai model pembanding (*baseline*) yang kuat untuk mengukur performa model berbasis *transformer*.

Setiap folder di dalam `workflow/` (`Elena/`, `Filip/`, `William/`) berisi kontribusi dan versi kerja dari masing-masing anggota tim.

## 🤖 Model dan Interpretasi (LIME)

  * **Model Tersimpan**: Direktori `model/` berisi *file-file* model yang sudah dilatih dan disimpan untuk setiap jangka waktu prediksi. Ini memungkinkan Anda untuk memuat model dan melakukan prediksi tanpa perlu melatih ulang.
  * **Penjelasan LIME**: Direktori `lime/` berisi hasil analisis interpretasi dari LIME dalam bentuk gambar (`.png`). Untuk setiap model dan jangka waktu, terdapat penjelasan mengenai fitur-fitur apa saja yang paling berkontribusi terhadap suatu prediksi, sehingga membuat model kita tidak lagi menjadi "kotak hitam".

## 🚀 Cara Menjalankan

Untuk mereplikasi hasil dari proyek ini, ikuti langkah-langkah berikut:

1.  **Clone Repositori**

    ```bash
    git clone https://github.com/williamtheodoruswijaya/Kode_Lagi-Uas-Gaskeun.git
    cd Kode_Lagi-Uas-Gaskeun
    ```

2.  **Instalasi Dependensi**
    Pastikan Anda memiliki library Python yang dibutuhkan. Anda bisa menginstalnya menggunakan pip:

    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn jupyter pytorch-tabnet tabpfen catboost lime lightgbm xgboost
    ```

    *(Disarankan untuk menggunakan virtual environment untuk menghindari konflik antar library)*

3.  **Jalankan Notebook**

      * Buka Jupyter Notebook atau Jupyter Lab.
      * Buka `notebook.ipynb` untuk alur kerja utama atau `notebook_xgb.ipynb` untuk analisis XGBoost.
      * Anda dapat menjalankan semua sel dalam notebook untuk melihat keseluruhan proses dari awal.
      * Untuk langsung ke bagian pemodelan, pastikan path ke dataset `data/processed-ipo-data.csv` sudah benar kemudian langsung jalankan pipeline Training sesuai dengan notebook.ipynb yang ada.

-----
