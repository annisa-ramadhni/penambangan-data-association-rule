# Analisis Association Rule untuk Menemukan Pola Perilaku dan Produktivitas Mahasiswa

## 📌 Deskripsi Proyek

Proyek ini merupakan implementasi **Association Rule Mining** untuk menemukan pola hubungan antara perilaku mahasiswa dengan produktivitas akademik menggunakan metode **Frequent Pattern Mining**.

Analisis dilakukan menggunakan dua algoritma, yaitu:

- **Apriori Algorithm**
- **FP-Growth**

Data yang digunakan merupakan **Student Productivity and Behavior Dataset** yang berisi informasi mengenai aktivitas dan kebiasaan mahasiswa. Data numerik terlebih dahulu dikategorisasi menjadi beberapa kelompok seperti rendah, sedang, dan tinggi, kemudian ditransformasikan ke dalam bentuk transaksi agar dapat diproses menggunakan metode Association Rule Mining.

Pola yang ditemukan kemudian dianalisis menggunakan metrik **support, confidence, dan lift** untuk mengetahui frekuensi kemunculan pola serta kekuatan hubungan antarvariabel.

---

## 🎯 Tujuan

Proyek ini bertujuan untuk:

1. Mengolah data perilaku mahasiswa ke dalam bentuk transaksi yang sesuai untuk diterapkan pada metode Frequent Pattern Mining.
2. Menggunakan algoritma Apriori dan FP-Growth untuk menemukan pola kemunculan bersama (*frequent itemset*) dari berbagai aktivitas dan kebiasaan mahasiswa.
3. Mengidentifikasi hubungan antar faktor perilaku mahasiswa, seperti waktu belajar, pola tidur, penggunaan media sosial, tingkat stres, dan kehadiran yang berkaitan dengan produktivitas akademik.
4. Menginterpretasikan association rule untuk memahami hubungan antara kebiasaan mahasiswa dan tingkat produktivitas akademik.

---

## ❓ Rumusan Masalah

Beberapa permasalahan yang dibahas dalam proyek ini meliputi:

1. Bagaimana mengubah data perilaku mahasiswa ke dalam bentuk transaksi yang sesuai untuk digunakan dalam Frequent Pattern Mining?
2. Bagaimana algoritma Apriori dan FP-Growth digunakan untuk menemukan pola hubungan antarvariabel perilaku mahasiswa?
3. Apa saja pola association rule yang dihasilkan dari data perilaku mahasiswa yang berkaitan dengan produktivitas akademik?
4. Bagaimana hasil association rule dapat digunakan untuk menjelaskan hubungan antara kebiasaan mahasiswa dan tingkat produktivitas akademik?

---

## 📊 Dataset

Dataset yang digunakan adalah:

**Student Productivity and Behavior Dataset**

Dataset memuat informasi mengenai aktivitas dan kebiasaan mahasiswa yang berkaitan dengan produktivitas akademik.

Variabel yang digunakan dalam proses analisis meliputi:

- `study_hours_per_day`
- `sleep_hours`
- `social_media_hours`
- `stress_level`
- `phone_usage_hours`
- `exercise_minutes`
- `attendance_percentage`
- `productivity_score`

Sebelum proses mining, data numerik dikategorikan menjadi beberapa kelompok seperti:

- `low`
- `medium`
- `high`

Contohnya:

- `study_low`
- `study_medium`
- `study_high`
- `sleep_low`
- `sleep_good`
- `productivity_low`
- `productivity_medium`

Data yang telah dikategorikan kemudian ditransformasikan menjadi bentuk transaksi untuk proses Frequent Pattern Mining.

> Dataset tidak disertakan secara langsung dalam repository karena file dataset asli tidak menjadi bagian dari repository ini. Proses pengolahan data dapat dilihat pada notebook yang tersedia.

---

## 🔄 Metodologi

Tahapan analisis dalam proyek ini secara umum meliputi:

1. **Data Understanding**
2. **Data Exploration**
3. **Data Preprocessing**
4. **Seleksi Variabel**
5. **Diskretisasi Data**
6. **Transformasi Data ke Bentuk Transaksi**
7. **Transaction Encoding**
8. **Frequent Pattern Mining**
9. **Association Rule Mining**
10. **Evaluasi dan Interpretasi Hasil**
11. **Perbandingan Algoritma Apriori dan FP-Growth**

### Data Preprocessing

Tahap preprocessing dilakukan dengan:

- Memeriksa struktur data.
- Memeriksa missing value.
- Memeriksa data duplikat.
- Melakukan seleksi variabel yang relevan.
- Melakukan diskretisasi data numerik.
- Mengubah data ke dalam bentuk transaksi.
- Melakukan transaction encoding.

Berdasarkan hasil pemeriksaan pada dataset, tidak ditemukan missing value maupun data duplikat sehingga data dapat digunakan untuk tahap preprocessing dan analisis selanjutnya.

---

## 🔎 Association Rule Mining

Association Rule digunakan untuk menemukan hubungan atau pola kemunculan bersama antaritem dalam data transaksi.

Tiga metrik utama yang digunakan adalah:

### Support

Support menunjukkan seberapa sering suatu kombinasi item muncul dalam keseluruhan transaksi.

### Confidence

Confidence menunjukkan tingkat kepercayaan bahwa suatu item akan muncul ketika item lain telah muncul.

### Lift

Lift digunakan untuk mengetahui kekuatan hubungan antara dua item dibandingkan dengan kemunculannya secara acak.

Nilai lift lebih dari 1 menunjukkan adanya keterkaitan positif antara item dalam suatu association rule.

---

## ⚙️ Algoritma yang Digunakan

### 1. Apriori

Apriori digunakan untuk menemukan frequent itemset dan association rule berdasarkan minimum support dan minimum confidence yang telah ditentukan.

### 2. FP-Growth

FP-Growth digunakan untuk menemukan frequent itemset dengan membangun struktur **FP-Tree** dan kemudian menghasilkan association rule berdasarkan pola yang ditemukan.

Kedua algoritma menggunakan parameter:

- **Minimum Support:** `0.1`
- **Minimum Confidence:** `0.5`

---

## 📈 Hasil Analisis

### Frequent Itemset

Hasil proses Frequent Pattern Mining menghasilkan **203 frequent itemset** pada masing-masing algoritma.

Beberapa pola yang memiliki nilai support tinggi antara lain:

| Item | Support |
|---|---:|
| `attendance_low` | 0.50040 |
| `exercise_high` | 0.49390 |
| `social_medium` | 0.37665 |
| `study_medium` | 0.31445 |
| `stress_high` | 0.29905 |

Hasil tersebut menunjukkan bahwa beberapa kategori perilaku tertentu cukup sering ditemukan pada dataset mahasiswa.

---

### Association Rule

Dari proses mining diperoleh **157 association rule** pada masing-masing algoritma.

Salah satu rule yang memiliki hubungan kuat adalah:

**`study_low → productivity_low`**

Dengan nilai:

- **Support:** `0.115`
- **Confidence:** `0.724`
- **Lift:** `2.613`

Interpretasinya, sekitar 11,5% data mahasiswa memiliki kombinasi waktu belajar rendah dan produktivitas rendah. Confidence sebesar 0,724 menunjukkan bahwa mahasiswa dengan waktu belajar rendah cukup sering memiliki produktivitas rendah.

Nilai lift sebesar 2,613 menunjukkan bahwa hubungan tersebut memiliki keterkaitan yang lebih kuat dibandingkan kemunculan secara acak.

Rule lainnya:

**`productivity_high → study_high`**

Dengan:

- **Confidence:** `0.978`
- **Lift:** `1.856`

Rule tersebut menunjukkan adanya hubungan antara produktivitas tinggi dengan kategori waktu belajar tinggi dalam dataset.

---

## ⚖️ Perbandingan Apriori dan FP-Growth

Perbandingan dilakukan berdasarkan waktu komputasi, jumlah frequent itemset, dan jumlah association rule.

| Algoritma | Waktu Komputasi | Frequent Itemset | Association Rule |
|---|---:|---:|---:|
| Apriori | 0.129041 detik | 203 | 157 |
| FP-Growth | 12.888725 detik | 203 | 157 |

Berdasarkan hasil pengujian pada dataset yang digunakan, **Apriori membutuhkan waktu komputasi lebih rendah dibandingkan FP-Growth**, sementara jumlah frequent itemset dan association rule yang dihasilkan sama.

Dengan demikian, pada dataset dan konfigurasi eksperimen ini, perbedaan waktu komputasi menunjukkan bahwa Apriori menyelesaikan proses mining lebih cepat.

> Hasil perbandingan ini berlaku pada dataset dan implementasi yang digunakan dalam proyek, sehingga tidak dimaksudkan sebagai kesimpulan umum bahwa satu algoritma selalu lebih cepat daripada algoritma lainnya.

---

## 💡 Insight

Beberapa pola yang diperoleh dari hasil association rule antara lain:

- Waktu belajar memiliki keterkaitan dengan produktivitas akademik.
- `study_low` memiliki hubungan kuat dengan `productivity_low`.
- Produktivitas tinggi memiliki hubungan dengan kategori waktu belajar tinggi.
- Kebiasaan belajar, pola tidur, penggunaan telepon, penggunaan media sosial, tingkat stres, dan kehadiran memiliki pola keterkaitan tertentu dengan produktivitas akademik.
- Association Rule dapat digunakan untuk melihat kombinasi perilaku yang sering muncul secara bersamaan dalam dataset mahasiswa.

---

## 📓 Notebook

Seluruh proses pengolahan data, preprocessing, implementasi algoritma Apriori dan FP-Growth, serta visualisasi hasil analisis tersedia pada notebook:

**`Kode_Project_Penambangan_Data_Kelompok_10.ipynb`**

Notebook dapat dibuka melalui folder [`notebook`](./notebook/).

---

## 🗂️ Struktur Repository

```text
penambangan-data-association-rule/
│
├── notebook/
│   └── Kode_Project_Penambangan_Data_Kelompok_10.ipynb
│
└── README.md
```

---

## 🛠️ Tools & Technologies

- Python
- Google Colab
- Jupyter Notebook
- Pandas
- NumPy
- MLxtend
- Matplotlib
- Seaborn
- Association Rule Mining
- Apriori
- FP-Growth

---

## 🎓 Informasi Proyek

**Mata Kuliah:** Penambangan Data  
**Program Studi:** S1 Sains Data  
**Fakultas:** Matematika dan Ilmu Pengetahuan Alam  
**Universitas:** Universitas Negeri Surabaya  
**Kelas:** 2024B

---

## 👥 Author

### Kelompok 10

**Yanaka Sofia Pardede**  
NIM: `24031554065`

**Fajria Rasmi Ridha Rumkel**  
NIM: `24031554191`

**Annisa Ramadhani**  
NIM: `24031554206`

---

## 📌 Catatan

Proyek ini dibuat sebagai bagian dari tugas mata kuliah **Penambangan Data** dengan fokus pada penerapan **Frequent Pattern Mining** dan **Association Rule Mining** untuk menganalisis pola perilaku dan produktivitas mahasiswa.
