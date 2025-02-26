# Analisis Sentimen Pelanggan

## 📌 Deskripsi Proyek
Proyek ini bertujuan untuk menganalisis sentimen pelanggan berdasarkan ulasan yang diberikan. Model yang digunakan adalah **Support Vector Machine (SVM)** dengan teknik **TF-IDF Vectorizer** untuk merepresentasikan teks dalam format numerik. Dataset terdiri dari **1.200 entri** dengan label sentimen **Positive** atau **Negative**.

---

## 📂 Dataset
Dataset yang digunakan memiliki tiga kolom utama:
- **Sentiment**: Label sentimen (*Positive* atau *Negative*).
- **Customer Review**: Ulasan asli dari pelanggan.
- **Corpus**: Hasil *preprocessing* teks.

Dataset telah diperiksa dan tidak mengandung nilai kosong.

---

## 🔄 Preprocessing Teks
Sebelum digunakan dalam pemodelan, teks melalui beberapa tahap *preprocessing*:
1. **Konversi Slang Words**: Menggunakan kamus slang (*kamusalay.csv*) untuk mengganti kata tidak baku dengan versi formal.
2. **Penghapusan Tanda Baca**: Menghapus simbol atau tanda baca yang tidak diperlukan.
3. **Penghapusan Karakter Berulang**: Menghapus huruf yang berulang lebih dari dua kali, misalnya "baguuusss" menjadi "bagus".
4. **Stemming**: Mengubah kata menjadi bentuk dasarnya menggunakan **Sastrawi**, misalnya "pengiriman" menjadi "kirim".
5. **Stopwords Removal**: Menghapus kata-kata yang tidak memiliki makna signifikan dalam analisis sentimen.

Setelah tahap *preprocessing*, data disimpan kembali dalam format CSV dengan nama **data_bersih.csv**.

---

## 🔢 Vektorisasi Teks
- Digunakan **TF-IDF Vectorizer** untuk mengubah teks menjadi format numerik.
- Teknik ini membantu merepresentasikan kata-kata yang lebih penting berdasarkan kemunculannya di seluruh dokumen.

---

## 🔀 Pembagian Data
Dataset dibagi menjadi:
- **70% untuk data latih (train set)**
- **30% untuk data uji (test set)**

---

## 🧠 Model Klasifikasi: Support Vector Machine (SVM)
- Model **Support Vector Classification (SVC)** digunakan untuk mengklasifikasikan sentimen pelanggan.
- Dilakukan pelatihan model menggunakan data yang telah melalui tahap *preprocessing* dan vektorisasi.

### 📊 Hasil Evaluasi Model
| Metrik  | Negative | Positive |
|---------|---------|---------|
| **Akurasi** | **89%** | - |
| **Precision** | 86% | 94% |
| **Recall** | 95% | 83% |
| **F1-score** | 90% | 88% |

📌 **Confusion Matrix** menunjukkan:
- 179 prediksi benar untuk sentimen **Negative**.
- 142 prediksi benar untuk sentimen **Positive**.
- Beberapa kesalahan klasifikasi yang masih dapat diperbaiki dengan optimasi lebih lanjut.

---

## ✅ Kesimpulan
- Model **SVM** menunjukkan performa yang cukup baik dengan akurasi **89%**.
- Proses *preprocessing* teks berperan penting dalam meningkatkan akurasi model.
- Model ini dapat dikembangkan lebih lanjut untuk analisis aspek spesifik dalam ulasan pelanggan atau integrasi dengan sistem rekomendasi berbasis sentimen.



---

## 📌 Teknologi yang Digunakan
- Python 🐍
- Pandas 📝
- Scikit-Learn 🤖
- Sastrawi 🔍

📌 **Silakan beri ⭐ jika proyek ini bermanfaat!** 😊

