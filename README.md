# **Customer Segmentation Using RFM Analysis**

## **Deskripsi Proyek**

Proyek ini bertujuan untuk menganalisis perilaku pelanggan menggunakan metode **RFM (Recency, Frequency, Monetary)**. RFM adalah teknik yang digunakan untuk membagi pelanggan ke dalam segmen-segmen berdasarkan tiga faktor utama:

1. **Recency (R)**: Seberapa baru transaksi terakhir pelanggan.
2. **Frequency (F)**: Seberapa sering pelanggan melakukan transaksi.
3. **Monetary (M)**: Total nilai pembelian pelanggan.

Dengan menggunakan skor RFM, pelanggan dikelompokkan ke dalam beberapa segmen seperti **Champion**, **Loyal Customer**, **Need Attention**, **Hibernating**, dan **Lost**. Analisis ini membantu perusahaan untuk memahami perilaku pelanggan mereka dan merancang strategi pemasaran yang lebih efektif.

---

## **Tujuan Proyek**

1. **Segmentasi Pelanggan**
   - Mengelompokkan pelanggan berdasarkan skor RFM untuk mengidentifikasi segmen-segmen penting seperti pelanggan setia, pelanggan potensial, dan pelanggan yang membutuhkan perhatian khusus.

2. **Strategi Pemasaran**
   - Memberikan wawasan tentang cara meningkatkan retensi pelanggan dengan menargetkan segmen tertentu melalui kampanye pemasaran yang dipersonalisasi.

3. **Optimasi Sumber Daya**
   - Memungkinkan perusahaan untuk mengalokasikan sumber daya secara lebih efisien dengan fokus pada pelanggan yang memiliki potensi tinggi untuk memberikan pendapatan lebih besar.

4. **Peningkatan Profitabilitas**
   - Mengidentifikasi pelanggan yang mungkin memerlukan insentif tambahan atau kampanye retensi untuk mencegah kehilangan mereka.

---

## **Dataset**

Dataset yang digunakan mencakup informasi transaksi pelanggan dengan kolom-kolom berikut:

| **Kolom**      | **Deskripsi**                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| `customer_id`   | ID unik pelanggan.                                                           |
| `Recency`       | Jumlah hari sejak transaksi terakhir pelanggan.                              |
| `Frequency`     | Jumlah transaksi yang dilakukan oleh pelanggan.                              |
| `Monetary`      | Total nilai pembelian pelanggan.                                             |
| `R_Score`       | Skor Recency (1-5), semakin tinggi nilainya, semakin baru transaksi pelanggan. |
| `F_Score`       | Skor Frequency (1-5), semakin tinggi nilainya, semakin sering transaksi.      |
| `M_Score`       | Skor Monetary (1-5), semakin tinggi nilainya, semakin besar total pembelian.  |
| `RFM_Score`     | Gabungan dari R_Score, F_Score, dan M_Score.                                  |

Contoh data awal:

| customer_id | Recency | Frequency | Monetary | R_Score | F_Score | M_Score | RFM_Score | Customer Segment  |
|-------------|---------|-----------|----------|---------|---------|---------|-----------|-------------------|
| CS1112      | 62      | 15        | 1012     | 3       | 2       | 2       | 322       | Hibernating       |
| CS1113      | 36      | 20        | 1490     | 4       | 4       | 4       | 444       | Loyal Customer    |
| CS1114      | 33      | 19        | 1432     | 4       | 3       | 4       | 434       | Need Attention    |
| CS1115      | 12      | 22        | 1659     | 5       | 4       | 5       | 545       | Champion          |
| CS1116      | 204     | 13        | 857      | 1       | 1       | 2       | 112       | Lost              |

---

## **Fitur Utama Analisis**

1. **Penghitungan Skor RFM**
   - **Recency Score**: Diukur berdasarkan seberapa baru transaksi terakhir pelanggan.
   - **Frequency Score**: Diukur berdasarkan jumlah transaksi yang dilakukan oleh pelanggan.
   - **Monetary Score**: Diukur berdasarkan total nilai pembelian pelanggan.

2. **Segmentasi Pelanggan**
   - Pelanggan dibagi menjadi beberapa segmen berdasarkan kombinasi skor RFM:
     - **Champion**: Pelanggan dengan skor RFM tertinggi (contoh: 555, 554).
     - **Loyal Customer**: Pelanggan yang sering melakukan transaksi dan memiliki nilai pembelian tinggi.
     - **Need Attention**: Pelanggan yang memiliki potensi untuk berkembang tetapi memerlukan perhatian khusus.
     - **Hibernating**: Pelanggan yang jarang melakukan transaksi dan memiliki nilai pembelian rendah.
     - **Lost**: Pelanggan yang sudah tidak aktif dan kemungkinan besar telah beralih ke pesaing.

3. **Visualisasi Data**
   - Menampilkan distribusi segmen pelanggan menggunakan grafik batang atau pie chart untuk memberikan gambaran yang lebih jelas tentang proporsi setiap segmen.

---

## **Cara Menggunakan Program**

### **Prasyarat**
- Pastikan Anda memiliki Python versi 3.x terinstal di sistem Anda.
- Instal modul yang diperlukan dengan menjalankan perintah berikut:
  ```bash
  pip install pandas numpy matplotlib seaborn
  ```

### **Langkah-langkah Penggunaan**

1. **Muat Dataset**
   Muat dataset yang berisi informasi transaksi pelanggan menggunakan `pandas`:
   ```python
   import pandas as pd
   df = pd.read_csv("customer_data.csv")
   ```

2. **Jalankan Program**
   Jalankan skrip untuk menghitung skor RFM dan membuat segmentasi pelanggan:
   ```python
   python nama_file.py
   ```

3. **Simpan Hasil**
   Hasil segmentasi pelanggan dapat disimpan ke file CSV untuk referensi lebih lanjut:
   ```python
   df.to_csv('rfm_segmentation_results.csv', index=False)
   ```

---

## **Insight Utama**

1. **Champion**
   - Pelanggan ini adalah pelanggan terbaik perusahaan, dengan skor RFM tertinggi.
   - Strategi: Berikan insentif loyalitas seperti diskon eksklusif atau akses awal ke produk baru.

2. **Loyal Customer**
   - Pelanggan ini sering melakukan transaksi dan memiliki nilai pembelian tinggi.
   - Strategi: Pertahankan loyalitas mereka dengan program reward atau penawaran khusus.

3. **Need Attention**
   - Pelanggan ini memiliki potensi untuk berkembang tetapi memerlukan perhatian khusus.
   - Strategi: Kirimkan email promosi atau tawarkan diskon untuk mendorong mereka melakukan transaksi lebih sering.

4. **Hibernating**
   - Pelanggan ini jarang melakukan transaksi dan memiliki nilai pembelian rendah.
   - Strategi: Lakukan kampanye re-engagement untuk membangkitkan minat mereka kembali.

5. **Lost**
   - Pelanggan ini sudah tidak aktif dan kemungkinan besar telah beralih ke pesaing.
   - Strategi: Lakukan analisis mendalam untuk memahami penyebab kehilangan mereka dan coba tarik mereka kembali dengan penawaran spesial.

---

## **Keunggulan Program**

- **Segmentasi Otomatis**: Menggunakan skor RFM untuk mengelompokkan pelanggan secara otomatis.
- **Evaluasi Komprehensif**: Memberikan wawasan tentang perilaku pelanggan berdasarkan data transaksi historis.
- **Visualisasi Interaktif**: Menggunakan library `matplotlib` dan `seaborn` untuk menghasilkan grafik yang informatif.
- **Rekomendasi Strategis**: Memberikan saran praktis berdasarkan hasil segmentasi untuk mendukung pengambilan keputusan bisnis.


---

Terima kasih telah menggunakan **Customer Segmentation Using RFM Analysis**! Kami harap proyek ini dapat membantu Anda memahami perilaku pelanggan dan mendukung pengambilan keputusan bisnis yang lebih baik. 😊
