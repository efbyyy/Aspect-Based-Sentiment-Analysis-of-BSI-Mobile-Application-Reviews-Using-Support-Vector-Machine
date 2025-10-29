# Aspect-Based Sentiment Analysis of BSI Mobile Application Reviews Using Support Vector Machine

## 📘 Deskripsi Proyek

Proyek ini merupakan implementasi **Aspect-Based Sentiment Analysis (ABSA)** pada ulasan pengguna aplikasi **BSI Mobile**, menggunakan algoritma **Support Vector Machine (SVM)**.  
Tujuan utamanya adalah mengidentifikasi aspek yang dibahas dalam setiap ulasan dan menentukan **polaritas sentimen** untuk setiap aspek, yaitu:

- `-1` → Negatif
- `0` → Netral
- `1` → Positif

Aspek yang dianalisis mencakup:

1. **Layanan (Service)**
2. **Transaksi (Transaction)**
3. **Performa Aplikasi (Application Performance)**
4. **Keamanan (Security)**

---

## 🧩 Latar Belakang

Dengan meningkatnya jumlah ulasan pengguna di platform digital, analisis sentimen berbasis aspek membantu memahami persepsi pengguna terhadap fitur tertentu.  
Metode SVM dipilih karena memiliki performa tinggi untuk klasifikasi teks dan efektif dalam menangani data berdimensi tinggi hasil ekstraksi **TF-IDF (Term Frequency – Inverse Document Frequency)**.

---

## 🚀 Fitur Utama

- Ekstraksi fitur teks menggunakan **TF-IDF**
- Klasifikasi multi-label menggunakan pendekatan **Binary Relevance**
- Model pelatihan dan evaluasi dengan **One-vs-One SVM**
- Hyperparameter tuning menggunakan **GridSearchCV**
- Evaluasi menggunakan **akurasi dan f1-score**
- Eksperimen tambahan dengan **SMOTE**

---

## 🧠 Arsitektur Sistem

```text
+-----------------------+
|  Dataset Ulasan BSI   |
+----------+------------+
           |
           v
+-----------------------+
|  Preprocessing Text   |
|  (Tokenize, Stopword) |
+----------+------------+
           |
           v
+-----------------------+
|  Ekstraksi Fitur TF-IDF |
+----------+------------+
           |
           v
+-----------------------+
|  Klasifikasi SVM BR   |
|  (Binary Relevance)   |
+----------+------------+
           |
           v
+-----------------------+
|  Hasil Sentimen per   |
|  Aspek (-1, 0, 1)     |
+-----------------------+
```

## ⚙️ Cara Menjalankan Proyek di Lokal

1. Clone Repository

   ```bash
   git clone https://github.com/efbyyy/Aspect-Based-Sentiment-Analysis-of-BSI-Mobile-Application-Reviews-Using-Support-Vector-Machine.git
   cd Aspect-Based-Sentiment-Analysis-of-BSI-Mobile-Application-Reviews-Using-Support-Vector-Machine
   ```

2. Buat Virtual Environment

   ```bash
      python -m venv venv
      source venv/bin/activate   # macOS/Linux
      # .\venv\Scripts\activate  # Windows
   ```

3. Instal Dependensi
   Jika tersedia file requirements.txt:

   ```bash
      pip install -r requirements.txt
   ```

   Jika belum ada, instal manual:

   ```bash
      pip install scikit-learn pandas numpy joblib openpyxl jupyter imbalanced-learn matplotlib seaborn
   ```

4. Jalankan Notebook

   ```bash
      jupyter notebook
   ```

Lalu buka file seperti:

```bash
   notebooks/gambaran umum sistem-Awal.ipynb
   notebooks/gambaran umum sistem-SMOTE-fold 10.ipynb
```
