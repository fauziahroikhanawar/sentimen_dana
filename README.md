# Klasifikasi Sentimen Ulasan Pengguna E-Wallet DANA di Google Play Store

## Deskripsi Proyek
Proyek ini menganalisis sentimen 1.000 ulasan pengguna aplikasi DANA di Google Play Store menggunakan pendekatan NLP dengan TF-IDF, Multinomial Naive Bayes, dan Support Vector Machine (SVM). Pelabelan dilakukan secara lexicon-based (InSet). SVM unggul dengan akurasi 87% dibanding Naive Bayes (83,5%). K-Means Clustering (k=7 positif, k=6 negatif) mengidentifikasi topik keluhan utama: kegagalan transaksi, masalah saldo, dan keamanan akun.

## Tujuan
- Menganalisis sentimen ulasan pengguna aplikasi DANA di Google Play Store.
- Mengklasifikasikan ulasan menjadi sentimen positif, negatif, dan netral.
- Mengidentifikasi aspek layanan yang sering mendapat tanggapan positif maupun negatif.
- Mengevaluasi performa metode terbaik dengan metrik akurasi, presisi, dan recall.

## Tools & Library
- Python
- Scikit-learn (TF-IDF, Naive Bayes, SVM, K-Means, PCA, metrik evaluasi)
- Sastrawi (stemming bahasa Indonesia)
- WordCloud (visualisasi frekuensi kata)
- Pandas, NumPy (manipulasi data)
- Matplotlib, Seaborn (visualisasi)
- Google Colab

## Tahapan Proyek
1. **Web Scraping** - 1.000 ulasan DANA dari Google Play Store
2. **Preprocessing** - Stopword removal, stemming, normalisasi slang, hapus emoji/URL/angka
3. **EDA** - WordCloud, distribusi panjang ulasan, distribusi rating
4. **Pelabelan** - Lexicon-based (InSet: positif, negatif, netral)
5. **Feature Engineering** - TF-IDF (max_features=5000, ngram_range=(1,2))
6. **Klasifikasi** - Multinomial Naive Bayes vs Support Vector Machine (SVM)
7. **Evaluasi** - Accuracy, precision, recall, F1-score, confusion matrix
8. **Clustering** - K-Means untuk topik positif (k=7) dan negatif (k=6)
9. **Visualisasi** - PCA 2D, Silhouette Score, perbandingan model

## Hasil
| Model | Akurasi | F1-Score (Weighted) |
|---|---|---|
| Multinomial Naive Bayes | 83,5% | 0,76 |
| **Support Vector Machine (SVM)** | **87%** | **0,84** |

- **Distribusi Rating:** 552 bintang 1 (dominan), rata-rata 2,25, median 1,0.
- **Distribusi Sentimen:** ~800 negatif, ~190 positif, ~10 netral.
- **Kesimpulan:** SVM lebih stabil dan tidak terlalu bias terhadap kelas negatif.

**Topik keluhan utama (dari clustering negatif):**
1. Fitur Dana Cicil/Limit tidak tersedia
2. Paksaan upgrade ke Premium
3. Error aplikasi setelah update
4. Masalah akun setelah ganti nomor & CS lambat
5. Saldo terpotong/hilang otomatis
6. Kegagalan OTP & verifikasi wajah

## File Terkait
- Notebook: (./notebook/sentimen_dana.ipynb)

## Author
**Fauziah Roikhana Wardah** (dan tim Kelompok 08)
- Program Studi S1 Sains Data, Universitas Negeri Surabaya
