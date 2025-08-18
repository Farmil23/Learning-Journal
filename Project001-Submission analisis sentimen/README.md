## Project machine learning path Dicoding modul 3
project ini memecahkan masalah analisis sentimen pada review instagram. disini saya mengambil sample tersebut menggunakan teknik scaper dan mendapat ribuan review secara langsung.

## Masalah yang dipecahkan
pada kasus ini, saya memecahkan sentimen menjadi:
#### 📈 Penjelasan:

- **Rating 1** menunjukkan dominasi sentimen **Negatif** (~50%) tetapi menariknya juga terdapat sekitar **40% sentimen Positif** — menandakan adanya kontradiksi atau ekspresi campuran dalam ulasan.
- **Rating 2** sampai **3** menunjukkan pergeseran yang lebih seimbang, dengan mulai meningkatnya proporsi sentimen **Positif** dan turunnya **Negatif**.
- **Rating 4 dan 5** hampir seluruhnya didominasi oleh **sentimen Positif**, yang sesuai ekspektasi untuk skor tinggi.
- **Sentimen Netral** hanya menempati porsi kecil di semua level bintang — paling tinggi sekitar **10% di rating 3**.


### 📉 Hasil Pelatihan Model LSTM untuk Klasifikasi Sentimen

![Training Result](attachment:image.png)

---

#### 🧠 Rangkuman Training:

- **Model**: LSTM (kemungkinan dengan regularisasi dan optimisasi)
- **Jumlah Epoch**: 12/20 (Early stopping kemungkinan diterapkan)
- **Learning Rate**: 5e-4 (default), menurun menjadi 1e-4 pada epoch ke-11 dan 12
- **Loss Function**: CrossEntropy (asumsi umum untuk klasifikasi)
- **Optimasi**: Adam (umumnya default di Keras/Tensorflow)

---

#### 📊 Performa:

| Epoch | Accuracy | Val Accuracy | Loss  | Val Loss |
|-------|----------|--------------|-------|----------|
| 1     | 0.5514   | 0.7821       | 1.1489| 0.6119   |
| 2     | 0.7947   | 0.8396       | 0.5974| 0.4697   |
| 3     | 0.8539   | 0.8629       | 0.4541| 0.4242   |
| 6     | 0.9088   | 0.8739       | 0.3129| 0.3851   |
| 10    | 0.9281   | 0.8889       | 0.2499| 0.3773   |
| 12    | 0.9377   | 0.8851       | 0.2074| 0.3855   |

---

#### ✅ Evaluasi Akhir:

- **Test Accuracy**: `0.8799`
- **Test Loss**: `0.3613`

Model menunjukkan performa yang cukup stabil dengan **val_accuracy** berkisar antara **87% hingga 89%** tanpa overfitting signifikan. Hal ini menunjukkan bahwa model cukup generalisasi terhadap data validasi dan pengujian.

---

#### 💡 Insight:

- Model dapat ditingkatkan lagi dengan:
  - Pre-trained Embeddings (misal GloVe, FastText)
  - Bidirectional LSTM
  - Penambahan layer Dense atau Dropout
  - Fine-tuning hyperparameter (learning rate schedule, optimizer, dll)

---

Markdown ini cocok untuk laporan akhir atau presentasi hasil eksperimen klasifikasi sentimen dengan LSTM.

## Catatan dari reviewer Dicoding
Hallo farmiljobs!, Selamat! Kamu telah berhasil menyelesaikan tugas untuk Proyek Analisis Sentimen. Dengan demikian kamu telah berhasil membuat proyek analisis sentimen.

Terima kasih telah sabar menunggu. Kami membutuhkan waktu untuk bisa memberikan feedback yang komprehensif. Untuk meningkatkan kualitas project submission yang dikirimkan, kamu dapat menerapkan beberapa saran berikut:

Overall Review

Well done, kamu telah berhasil menyelesaikan submission ini dengan cukup baik. Kamu juga telah menerapkan seluruh kriteria saran yang ada.  Good job !!

Saat ini, kamu melakukan inference pada seluruh skema pelatihan. Sebaiknya, kamu cukup memilih satu skema terbaik, kemudian menggunakan skema terbaik tersebut untuk melakukan testing untuk memprediksi sentiment yang ingin di analisis.

Pertimbangkan untuk melakukan penangan pada data yang tidak seimbang. Seperti dengan menggunakan teknik oversampling, yaitu menambah data dengan label minoritas. Ataupun Undersampling dengan mengurangi data pada label mayoritas agar jumlahnya seimbang. Karena dengan data yang tidak seimbang pada masing-masing kelas dapat membuat model cenderung melakukan prediksi kepada kelas yang lebih dominan. 

Tetap semangat menyelesaikan kelas Belajar Pengembangan Machine Learning.

Silakan berkunjung ke forum diskusi untuk mengasah kembali penguasaan ilmu kamu dan membuat ilmu kamu bisa semakin bermanfaat dengan membantu developer yang lain. 

Terima kasih telah membantu misi kami. Kesuksesan developer Indonesia adalah energi bagi kami.