# ScrapPlaystore


# Sentiment Analysis of Mobile App Reviews  
Analisis sentimen terhadap ulasan aplikasi menggunakan metode **TF-IDF** dan **Support Vector Machine (SVM)**.

Proyek ini terdiri dari tiga bagian utama:  
1. **Scraping ulasan aplikasi**  
2. **Dataset hasil scraping**  
3. **Model sentiment analysis (TF-IDF + SVM)**  

---

## 📁 Struktur Repository

.
├── scraping_reviews.py
├── hasil_scraper_ulasan_APP.csv
├── sentiment_analysis_svm.ipynb
└── README.md


---

## 📌 Deskripsi File

### **1. scraping_reviews.py**  
Script untuk mengambil (scraping) ulasan pengguna dari platform aplikasi.  
Isi utamanya mencakup:
- pemanggilan halaman ulasan  
- ekstraksi teks ulasan  
- pembersihan data dasar  
- penyimpanan hasil ke CSV  

### **2. hasil_scraper_ulasan_APP.csv**  
Dataset hasil scraping, berisi ribuan ulasan pengguna.  
Contoh kolom:
- `review` : teks ulasan  
- `rating` : nilai rating bintang  
- `sentiment_label` (opsional) : label yang diberikan / hasil anotasi  

### **3. sentiment_analysis_svm.ipynb**  
Notebook analisis sentimen lengkap.  
Berisi:
- preprocessing teks  
- tokenization  
- transformasi TF-IDF  
- training model Support Vector Machine  
- evaluasi model  
- confusion matrix & classification report  

Akurasi model: **81%**

---

## 🛠️ Teknologi Utama

| Komponen | Tools |
|---------|--------|
| Bahasa | Python |
| Scraping | Requests / Selenium / BeautifulSoup (tergantung script kamu) |
| Feature Extraction | TF-IDF (sklearn) |
| Model | SVM (LinearSVC) |
| Evaluasi | Confusion Matrix, Classification Report |

---

## 📊 Hasil Model

### **Classification Report**

          precision    recall  f1-score   support

negative       0.87      0.85      0.86     12242
 neutral       0.16      0.23      0.19      1415
positive       0.88      0.85      0.87      8463

accuracy                           0.81     22120

macro avg 0.64 0.64 0.64 22120
weighted avg 0.83 0.81 0.82 22120


### **Confusion Matrix**

[[10381, 1188, 673],
[ 810, 322, 283],
[ 777, 504, 7182]]


Kesimpulan:
- Model sangat baik untuk **positif dan negatif**
- Kelas **netral masih sulit**, terutama karena dataset tidak seimbang  

---

## 🚀 Cara Menjalankan Analisis

1. Clone repository ini:
```bash
git clone <repo-url>
cd sentiment-analysis-app

    Install dependencies:

pip install -r requirements.txt

    Jalankan notebook:

    Buka sentiment_analysis_svm.ipynb

    Run semua sel dari preprocessing hingga evaluasi

🧩 Pengembangan Selanjutnya

Beberapa peningkatan yang direkomendasikan:

    Menambah data netral (dataset balancing)

    Menggunakan model berbasis konteks seperti BERT / IndoBERT

    Oversampling/SMOTE untuk kelas minoritas

    Hyperparameter tuning lebih luas
