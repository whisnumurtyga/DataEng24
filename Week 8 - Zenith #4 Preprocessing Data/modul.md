# Welcome to ZENITH #4 🔥  
## Zero-hour Engagement: Nurture Insight, Thrive Higher

### Preprocessing Data 👩‍💻

👉🏻 **Data Preprocessing** merupakan salah satu tahapan dalam melakukan mining data. Sebelum menuju ke tahap pemprosesan, data mentah akan diolah terlebih dahulu. Melalui data preprocessing, memungkinkan proses mining akan berjalan dengan lebih efektif dan efisien karena data yang telah melalui pra-pemrosesan sudah melalui beberapa tahap pembersihan.

#### Manfaat Preprocessing Data:
1. Memperlancar proses data mining.
2. Membuat data lebih mudah untuk dibaca.
3. Mengurangi beban representasi dalam data.
4. Mengurangi durasi data mining secara signifikan.
5. Mempermudah proses analisis data dalam machine learning.

#### Langkah-langkah Preprocessing Data:
1. **Mengumpulkan Data**  
   Mengambil dataset dari berbagai sumber (misalnya file CSV, SQL, API, dll.).

2. **Memahami Metadata (Exploratory Data Analysis, EDA)**:
   - Melihat struktur dataset: memahami fitur-fitur (kolom), tipe data, jumlah observasi, dan statistik dasar.
   - Mencari pola, outlier, atau ketidaksesuaian yang memerlukan penanganan lebih lanjut.

3. **Data Cleaning**  
   Data mentah akan dibersihkan melalui beberapa proses berikut:
   - **Mengatasi Data Hilang (Missing Data)**:
     - Menghapus baris/kolom yang memiliki nilai hilang.
     - Mengisi data hilang dengan metode tertentu (mean, median, mode, interpolasi).
   - **Menghapus Duplikasi**:
     - Menghapus baris-baris yang berulang (duplikat).
   - **Mengatasi Outliers**:
     - Deteksi dan penanganan outliers menggunakan metode seperti z-score atau IQR.

4. **Data Integration**  
   Data integration adalah tahap yang menggabungkan data dari berbagai sumber menjadi satu kesatuan. Dalam proses ini, data dengan format yang berbeda harus diubah ke format yang sama.
   - Memastikan data memiliki format dan atribut yang sama.
   - Menghapus atribut yang tidak dibutuhkan.
   - Mendeteksi nilai data yang konflik.

5. **Data Transformation**  
   Pada tahap ini, data akan dinormalisasi dan digeneralisasi. Langkah-langkahnya adalah:
   - **Normalisasi/Standarisasi**: Mengubah skala data agar fitur-fitur memiliki skala yang sama (misalnya dengan Min-Max scaling atau Standard scaling).
   - **Encoding Data Kategori**: Mengubah data kategorikal menjadi data numerik (misalnya dengan One-hot encoding atau Label encoding).
   - **Feature Scaling**: Melakukan scaling terhadap fitur numerik agar berada dalam rentang yang sama.
   - **Binning**: Mengelompokkan data numerik menjadi beberapa kategori (misalnya untuk umur: "anak-anak", "dewasa", "manula").

6. **Feature Engineering**:
   - **Membuat Fitur Baru**: Menggabungkan atau mengubah fitur yang ada untuk menciptakan fitur baru yang lebih representatif.
   - **Menghapus Fitur yang Tidak Relevan**: Menghilangkan fitur yang kurang informatif atau sangat berkorelasi dengan fitur lain.
   - **Principal Component Analysis (PCA)**: Mengurangi dimensi fitur agar lebih mudah diolah dengan tetap mempertahankan informasi penting.
