
Proses Analisis Sentimen Pelanggan
1. Pemuatan dan Eksplorasi Data
    Dataset yang digunakan terdiri dari 1.200 entri dengan tiga kolom utama:
      •	Sentiment: Label sentimen (Positive atau Negative).
      •	Customer Review: Ulasan asli dari pelanggan.
      •	Corpus: Hasil preprocessing teks.

     Setelah diperiksa, dataset tidak memiliki nilai kosong, sehingga tidak perlu dilakukan imputasi atau penghapusan data.

3. Preprocessing Teks
    Sebelum digunakan dalam pemodelan, teks dalam dataset melalui beberapa tahap preprocessing:
      1.	Konversi Slang Words
          o	Menggunakan kamus slang (kamusalay.csv) untuk mengganti kata-kata tidak baku dengan versi yang lebih formal.
      2.	Penghapusan Tanda Baca (Punctuation Removal)
          o	Menghapus simbol atau tanda baca yang tidak diperlukan dalam analisis sentimen.
      3.	Penghapusan Karakter Berulang (Repetition Character Removal)
          o	Menghapus huruf yang berulang lebih dari dua kali dalam suatu kata, misalnya "baguuusss" menjadi "bagus".
      4.	Stemming dengan Sastrawi
          o	Mengubah kata-kata menjadi bentuk dasarnya menggunakan Sastrawi, misalnya "pengiriman" menjadi "kirim".
      5.	Stopwords Removal
          o	Menghapus kata-kata yang tidak memiliki makna signifikan dalam analisis sentimen menggunakan daftar stopwords yang diperoleh dari Sastrawi dan tambahan kata dari stopwordbahasa.csv.
    Setelah tahap preprocessing, data disimpan kembali dalam bentuk CSV dengan nama data_bersih.csv.

4. Vektorisasi Teks
Untuk mengubah teks menjadi format numerik, digunakan TF-IDF Vectorizer. Teknik ini membantu dalam merepresentasikan kata-kata yang lebih penting dalam suatu teks berdasarkan kemunculannya di seluruh dokumen.

5. Pembagian Data
   Data kemudian dibagi menjadi:
    •	70% untuk data latih (train set)
    •	30% untuk data uji (test set)

6. Model Klasifikasi dengan Support Vector Machine (SVM)
    •	Model SVM (Support Vector Classification) digunakan untuk mengklasifikasikan sentimen pelanggan.
    •	Setelah pelatihan model, diperoleh hasil evaluasi sebagai berikut:
Hasil Evaluasi Model
    •	Akurasi: 89%
    •	Precision (Negative/Positive): 86% / 94%
    •	Recall (Negative/Positive): 95% / 83%
    •	F1-score (Negative/Positive): 90% / 88%
Berdasarkan confusion matrix, terdapat 179 prediksi benar untuk sentimen negatif dan 142 prediksi benar untuk sentimen positif, dengan beberapa kesalahan klasifikasi.
Kesimpulan
    •	Model SVM menunjukkan performa yang baik dalam mengklasifikasikan sentimen pelanggan dengan akurasi 89%.
    •	Preprocessing teks membantu meningkatkan akurasi dengan membersihkan teks sebelum digunakan dalam pemodelan.
    •	Model ini dapat digunakan untuk analisis lebih lanjut, seperti mengidentifikasi aspek tertentu dari ulasan pelanggan atau mengembangkan sistem rekomendasi berbasis sentimen.

