# Analisis Sentimen dan Ekstraksi Insight Ulasan Produk Menggunakan AI

## Ringkasan Proyek

Proyek ini merupakan capstone end-to-end yang bertujuan untuk menganalisis dataset ulasan produk *Amazon Fine Food Reviews*. Tujuan utamanya ada dua: pertama, membangun model Machine Learning untuk **mengklasifikasikan sentimen** ulasan secara otomatis (Positif/Negatif). Kedua, menggunakan Large Language Model (LLM) **IBM Granite** untuk **mengekstrak dan merangkum insight kualitatif** dari ulasan negatif, guna menghasilkan rekomendasi bisnis yang dapat ditindaklanjuti.

## Latar Belakang Masalah

Di era e-commerce, ulasan pelanggan adalah aset vital. Namun, volume ulasan yang sangat besar membuat analisis manual menjadi tidak mungkin dilakukan. Akibatnya, banyak insight berharga terkait masalah produk, keluhan layanan, dan tren pelanggan terlewatkan. Proyek ini mendemonstrasikan bagaimana kombinasi Machine Learning klasik dan AI generatif dapat mengatasi tantangan ini secara efisien dan dalam skala besar.

## Dataset

Proyek ini menggunakan dataset publik **[Amazon Fine Food Reviews dari Kaggle](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)**, yang berisi lebih dari 500.000 ulasan produk makanan dari Amazon.

## Alur Kerja Proyek

1.  **Data Loading & Cleaning:** Memuat data, menangani nilai yang hilang, dan menghapus duplikat.
2.  **Exploratory Data Analysis (EDA):** Menganalisis distribusi skor ulasan dan mempersiapkan data untuk pemodelan.
3.  **Klasifikasi Sentimen:** Melatih dan mengevaluasi model baseline (Logistic Regression) untuk memprediksi sentimen (Positif/Negatif).
4.  **Summarization dengan AI:** Menggunakan model IBM Granite dengan pendekatan "Map-Reduce" untuk meringkas ribuan ulasan negatif.
5.  **Analisis Insight:** Mengubah output ringkasan AI menjadi temuan bisnis yang jelas.
6.  **Rekomendasi Bisnis:** Merumuskan rekomendasi yang actionable untuk berbagai tim (Produk, Operasional, CS).

## Teknologi yang Digunakan

* **Bahasa & Library:** Python, Pandas, Scikit-learn, Matplotlib, Seaborn
* **Platform:** Google Colab, GitHub
* **Model AI:**
    * Machine Learning: Logistic Regression
    * Large Language Model: IBM Granite 3.3 8B Instruct (via LangChain & Replicate)

## Cara Menjalankan Proyek

1.  **Clone Repository:**
    ```bash
    git clone https://github.com/radityankw/Capstone-Project.git
    cd Capstone-Project
    ```
2.  **Setup Environment di Google Colab:**
    * Buka file `notebooks/CapstoneProject.ipynb`.
    * Di Colab, buka tab "Secrets" (ikon kunci) dan tambahkan secret baru dengan nama `REPLICATE_API_TOKEN` dan value berupa API token Anda dari Replicate.
3.  **Instalasi Dependensi:**
    Jalankan sel pertama di notebook yang berisi:
    ```python
    !pip install pandas scikit-learn matplotlib seaborn langchain-community replicate
    ```
4.  **Jalankan Notebook:**
    Ikuti dan jalankan semua sel di dalam notebook secara berurutan. Pastikan file `Reviews.csv` sudah diunggah ke environment Colab.

## Hasil Utama

### 1. Kinerja Model Klasifikasi
Model klasifikasi sentimen berhasil mencapai **F1-Score sebesar 91%**, menunjukkan efektivitas tinggi dalam membedakan secara akurat antara ulasan positif dan negatif.

### 2. Insight dari Ringkasan AI (IBM Granite)
Analisis mendalam terhadap ulasan negatif menggunakan IBM Granite mengungkapkan 5 tema masalah utama:
* **Kualitas & Konsistensi Rasa:** Keluhan paling umum terkait rasa produk yang aneh, hambar, atau bahkan basi dan berjamur.
* **Ekspektasi vs. Realitas Produk:** Produk yang diterima tidak sesuai dengan deskripsi atau klaim fungsionalnya (misalnya, camilan anjing yang tidak disukai anjing).
* **Masalah Kebersihan & Integritas Kemasan:** Ditemukan laporan serius mengenai kemasan yang terkontaminasi jamur.
* **Perubahan Produk (Shrinkflation):** Pelanggan kecewa dengan pengurangan kuantitas atau perubahan komposisi produk yang tidak diinformasikan.
* **Pengalaman Layanan Pelanggan yang Tidak Konsisten:** Penanganan keluhan sangat bervariasi, dari yang sangat memuaskan hingga sangat buruk.

## Rekomendasi Bisnis

1.  **Untuk Tim Quality Assurance:** Lakukan audit proses QC dan implementasikan panel uji rasa untuk memastikan konsistensi produk.
2.  **Untuk Tim Pemasaran:** Tinjau ulang semua deskripsi produk untuk memastikan akurasi dan kesesuaian dengan produk fisik.
3.  **Untuk Tim Operasional:** Investigasi segera laporan kontaminasi kemasan dan periksa kondisi penyimpanan gudang.
4.  **Untuk Tim Layanan Pelanggan:** Buat dan sosialisasikan SOP standar untuk penanganan keluhan terkait kualitas produk guna memastikan pengalaman pelanggan yang konsisten.

## Penjelasan Peran AI (IBM Granite)
IBM Granite memainkan peran krusial dalam mengubah data teks tidak terstruktur menjadi insight terstruktur. Kemampuannya untuk membaca, memahami, dan mensintesis ribuan ulasan memungkinkan analisis kualitatif dalam skala besar—sebuah tugas yang mustahil dilakukan secara manual. Ini membuktikan bagaimana AI Generatif dapat berfungsi sebagai akselerator untuk menemukan "akar masalah" yang tersembunyi di dalam data.

## Lisensi
Proyek ini dilisensikan di bawah Lisensi MIT.
