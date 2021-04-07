# Sistem_Pakar3C
Naive Bayes adalah algoritme klasifikasi yang paling mudah dan cepat, yang cocok untuk sebagian besar data. Pengklasifikasi Naive Bayes berhasil digunakan dalam berbagai aplikasi seperti pemfilteran spam, klasifikasi teks, analisis sentimen, dan sistem pemberi rekomendasi. Ini menggunakan teorema Bayes tentang probabilitas untuk prediksi kelas yang tidak diketahui.

Pengklasifikasi Naive Bayes
- Mendefinisikan Set Data
Dalam contoh ini, Anda dapat menggunakan kumpulan data dummy dengan tiga kolom: cuaca, suhu, dan permainan. Dua yang pertama adalah fitur (cuaca, suhu) dan yang lainnya adalah label.
- Fitur Pengkodean
Pertama, Anda perlu mengubah label string ini menjadi angka. misalnya: 'Mendung', 'Hujan', 'Cerah' sebagai 0, 1, 2. Ini dikenal sebagai pengkodean label. Scikit-learn menyediakan pustaka LabelEncoder untuk mengenkode label dengan nilai antara 0 dan satu kurang dari jumlah kelas diskrit.
-Generating Model
Buat model menggunakan pengklasifikasi naive bayes dengan langkah-langkah berikut:
1. Buat pengklasifikasi bayes naif
2. Sesuaikan dataset pada classifier
3. Lakukan prediksi
-Memuat Data
Mari muat dulu kumpulan data wine yang diperlukan dari kumpulan data scikit-learn.
-Menjelajahi Data
Anda dapat mencetak nama target dan fitur, untuk memastikan Anda memiliki dataset yang benar
Memisahkan Data
Pertama, Anda memisahkan kolom menjadi variabel dependen dan independen (atau fitur dan label). Kemudian Anda membagi variabel tersebut menjadi train and test set.
-Generasi Model
Setelah memisahkan, Anda akan membuat model forest acak pada set pelatihan dan melakukan prediksi pada fitur set pengujian.
-Mengevaluasi Model
Setelah pembuatan model, periksa keakuratan menggunakan nilai aktual dan prediksi.
