#!/usr/bin/env bash

# setup_structure.sh

# Script untuk membuat struktur folder proyek ABSA (BSI Mobile)

echo "📁 Membuat struktur direktori proyek..."

# Membuat folder utama

mkdir -p data notebooks models src

# Membuat file contoh jika belum ada

touch data/scrapped_data.csv
touch data/data_bersih.xlsx
touch notebooks/"gambaran umum sistem-Awal.ipynb"
touch notebooks/"gambaran umum sistem-SMOTE-fold 10.ipynb"
touch models/.gitkeep
touch src/.gitkeep
touch combined_stop_words.txt
touch README.md
touch requirements.txt

echo "✅ Struktur proyek berhasil dibuat!"
echo
echo "Struktur akhir:"
tree -L 2 2>/dev/null || (echo; echo "Jika perintah 'tree' tidak tersedia, berikut struktur dasarnya:"; echo)
echo "
.
├── data/ # masukkan dataset csv/xlsx di sini
│ ├── scrapped*data.csv
│ └── data_bersih.xlsx
├── notebooks/ # notebook eksplorasi & eksperimen
│ ├── gambaran umum sistem-Awal.ipynb
│ ├── gambaran umum sistem-SMOTE-fold 10.ipynb
│ └── ...
├── models/ # pindahkan file .joblib ke sini
│ ├── svm_model_Layanan*...joblib
│ └── ...
├── src/ # script Python yang bisa dieksekusi
│ └── ...
├── combined_stop_words.txt
├── README.md
└── requirements.txt
"

echo "💡 Catatan:

- Pastikan menaruh dataset di folder ./data/
- Notebook eksplorasi di ./notebooks/
- Model hasil training (.joblib) di ./models/
- Script Python modular di ./src/
  "

## Cara menggunakan

1. **Siapkan environment**
   - Disarankan buat virtual environment:
     ```bash
     python -m venv .venv
     source .venv/bin/activate   # Linux / macOS
     .\.venv\Scripts\activate    # Windows PowerShell
     pip install -r requirements.txt
     ```
2. **Notebook**
   - Buka notebook di `notebooks/` atau root (file `.ipynb`) dengan Jupyter:
     ```bash
     jupyter notebook
     ```
3. **Menjalankan skrip / training**
   - Jika kamu memindahkan kode dari notebook ke `src/`, jalankan:
     ```bash
     python src/train.py
     ```
   - (Catatan: sesuaikan path dataset dan model output di skrip)

## Dependencies (contoh)

Lihat `requirements.txt` untuk daftar paket. Contoh paket yang dipakai:

- python (3.8+)
- numpy
- pandas
- scikit-learn
- imbalanced-learn
- joblib
- openpyxl
- jupyter
- matplotlib

## Perhatian terkait file besar & privasi

- File model `.joblib` atau file Excel/CSV berukuran besar sebaiknya dipindah ke folder `models/` / `data/` dan di-exclude dari tracking git jika tidak ingin menyimpan history besar.
- Jika dataset mengandung data sensitif, jangan commit ke repositori publik. Gunakan `.gitignore` atau Git LFS untuk file besar.

## Rekomendasi / Perbaikan yang disarankan

1. Tambahkan `README.md` (sudah dibuat) dan `LICENSE` (mis. MIT/CC-BY jika ingin membuka).
2. Buat struktur folder: pindahkan dataset ke `data/`, model ke `models/`, notebook ke `notebooks/`, kode ke `src/`.
3. Tambahkan `requirements.txt` (sudah dibuat oleh script ini) atau `environment.yml` untuk reproducibility.
4. Buat file `run.sh` atau skrip Python untuk menjalankan pipeline (preprocess → feature extraction → train → eval).
5. Tambahkan `.gitignore` untuk:
   - `__pycache__/`, `.ipynb_checkpoints/`
   - `*.joblib`, `*.h5` (opsional, atau pindahkan ke LFS)
   - `*.xlsx`, `*.csv` (opsional, tergantung apakah dataset akan disimpan dalam repo)
6. Jika ukuran file besar jadi masalah, gunakan Git LFS atau simpan dataset dan model di releases / cloud storage.

## Kontak

Pembuat repo: `efbyyy`  
Jika perlukan bantuan format ulang notebook menjadi skrip atau menyusun pipeline reproducible, hubungi pemilik repo atau buka issue.

EOF

cat > "$GITIGNORE_FILE" << 'EOF'

# Python

**pycache**/
_.py[cod]
_.so

# Jupyter

.ipynb_checkpoints/

# Environments

.env
.venv/
venv/

# Data / Models (sesuaikan: jika ingin commit dataset, jangan masukkan)

_.joblib
_.pkl
_.h5
_.xlsx
\*.csv

# Mac/Windows

.DS_Store
Thumbs.db
EOF

cat > "$REQ_FILE" << 'EOF'
numpy
pandas
scikit-learn
imbalanced-learn
joblib
openpyxl
jupyter
matplotlib
EOF

echo "================================================================================"
echo "README.md, .gitignore, and requirements.txt have been created."
echo
echo "Rekomendasi ringkas (lanjutan):"
echo "- Pindahkan file .joblib ke folder models/"
echo "- Pindahkan file dataset (csv/xlsx) ke folder data/ jika ingin struktur yang rapi"
echo "- Buat LICENSE jika ingin membagikan secara resmi"
echo "- Buat skrip runnable di src/ (train.py, preprocess.py, evaluate.py)"
echo
echo "Jika kamu mau, saya bisa:"
echo "1) bantu konversi notebook tertentu menjadi script Python (src/)."
echo "2) buatkan contoh run script (train.py) yang memuat proses: load data -> preprocess -> TF-IDF -> train SVM -> simpan model."
echo
echo "Selesai."
echo "================================================================================"

## Cara menggunakan

1. **Siapkan environment**
   - Disarankan buat virtual environment:
     ```bash
     python -m venv .venv
     source .venv/bin/activate   # Linux / macOS
     .\.venv\Scripts\activate    # Windows PowerShell
     pip install -r requirements.txt
     ```
2. **Notebook**
   - Buka notebook di `notebooks/` atau root (file `.ipynb`) dengan Jupyter:
     ```bash
     jupyter notebook
     ```
3. **Menjalankan skrip / training**
   - Jika kamu memindahkan kode dari notebook ke `src/`, jalankan:
     ```bash
     python src/train.py
     ```
   - (Catatan: sesuaikan path dataset dan model output di skrip)

## Dependencies (contoh)

Lihat `requirements.txt` untuk daftar paket. Contoh paket yang dipakai:

- python (3.8+)
- numpy
- pandas
- scikit-learn
- imbalanced-learn
- joblib
- openpyxl
- jupyter
- matplotlib

## Perhatian terkait file besar & privasi

- File model `.joblib` atau file Excel/CSV berukuran besar sebaiknya dipindah ke folder `models/` / `data/` dan di-exclude dari tracking git jika tidak ingin menyimpan history besar.
- Jika dataset mengandung data sensitif, jangan commit ke repositori publik. Gunakan `.gitignore` atau Git LFS untuk file besar.

## Rekomendasi / Perbaikan yang disarankan

1. Tambahkan `README.md` (sudah dibuat) dan `LICENSE` (mis. MIT/CC-BY jika ingin membuka).
2. Buat struktur folder: pindahkan dataset ke `data/`, model ke `models/`, notebook ke `notebooks/`, kode ke `src/`.
3. Tambahkan `requirements.txt` (sudah dibuat oleh script ini) atau `environment.yml` untuk reproducibility.
4. Buat file `run.sh` atau skrip Python untuk menjalankan pipeline (preprocess → feature extraction → train → eval).
5. Tambahkan `.gitignore` untuk:
   - `__pycache__/`, `.ipynb_checkpoints/`
   - `*.joblib`, `*.h5` (opsional, atau pindahkan ke LFS)
   - `*.xlsx`, `*.csv` (opsional, tergantung apakah dataset akan disimpan dalam repo)
6. Jika ukuran file besar jadi masalah, gunakan Git LFS atau simpan dataset dan model di releases / cloud storage.

## Kontak

Pembuat repo: `efbyyy`  
Jika perlukan bantuan format ulang notebook menjadi skrip atau menyusun pipeline reproducible, hubungi pemilik repo atau buka issue.

EOF

cat > "$GITIGNORE_FILE" << 'EOF'

# Python

**pycache**/
_.py[cod]
_.so

# Jupyter

.ipynb_checkpoints/

# Environments

.env
.venv/
venv/

# Data / Models (sesuaikan: jika ingin commit dataset, jangan masukkan)

_.joblib
_.pkl
_.h5
_.xlsx
\*.csv

# Mac/Windows

.DS_Store
Thumbs.db
EOF

cat > "$REQ_FILE" << 'EOF'
numpy
pandas
scikit-learn
imbalanced-learn
joblib
openpyxl
jupyter
matplotlib
EOF

echo "================================================================================"
echo "README.md, .gitignore, and requirements.txt have been created."
echo
echo "Rekomendasi ringkas (lanjutan):"
echo "- Pindahkan file .joblib ke folder models/"
echo "- Pindahkan file dataset (csv/xlsx) ke folder data/ jika ingin struktur yang rapi"
echo "- Buat LICENSE jika ingin membagikan secara resmi"
echo "- Buat skrip runnable di src/ (train.py, preprocess.py, evaluate.py)"
echo
echo "Jika kamu mau, saya bisa:"
echo "1) bantu konversi notebook tertentu menjadi script Python (src/)."
echo "2) buatkan contoh run script (train.py) yang memuat proses: load data -> preprocess -> TF-IDF -> train SVM -> simpan model."
echo
echo "Selesai."
echo "================================================================================"
