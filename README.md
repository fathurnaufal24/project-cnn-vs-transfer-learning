# Analisis Perbandingan Performa Klasifikasi Citra Biner: CNN from Scratch vs Transfer Learning (MobileNetV2)

Repository ini dibuat untuk memenuhi Tugas Individu Mata Kuliah Pembelajaran Mesin 2. Proyek ini berfokus pada eksperimen klasifikasi citra dua kelas (biner) menggunakan dua pendekatan deep learning yang berbeda: **CNN dari dasar (from scratch)** dan **Transfer Learning** menggunakan pretrained model.

## 📌 Struktur Repository
Sesuai dengan ketentuan tugas, repositori ini disusun dengan struktur sebagai berikut:
project-cnn-vs-transfer-learning/│├── dataset/│   └── link_dataset.txt          # Link download dataset CIFAR-10 & CatsVsDogs│├── notebook/│   └── cnn_vs_transfer_learning.ipynb   # File Jupyter Notebook proses eksperimen│├── report/│   └── laporan.pdf               # Laporan resmi dengan template IEEE (Maks 10 halaman)│├── README.md                     # Panduan dan ringkasan proyek└── requirements.txt              # Daftar library python yang digunakan
## 📊 Ringkasan Eksperimen

### 1. Dataset & Preprocessing
* **Dataset:** Menggunakan sub-dataset biner (Kucing vs Anjing) yang difilter dari dataset CIFAR-10[cite: 22].
* **Jumlah Data:** Total 300 gambar (150 gambar per kelas) untuk menjamin keseimbangan data[cite: 25, 26, 27].
* **Pembagian Data:** Menggunakan rasio **70% Training**, **15% Validation**, dan **15% Testing**[cite: 34, 35, 36].
* **Preprocessing:** Normalisasi nilai piksel gambar ke rentang 0-1 (`rescale=1./255`)[cite: 170].

### 2. Pendekatan Model
* **CNN from Scratch:** Arsitektur kustom mandiri yang terdiri dari `Conv2D` [cite: 40], `MaxPooling2D` [cite: 41], `Flatten` [cite: 43], `Dense` (Hidden Layer) [cite: 44], teknik regularisasi `Dropout` [cite: 53], dan `Output Layer` menggunakan fungsi aktivasi Sigmoid[cite: 45].
* **Transfer Learning:** Menggunakan pretrained model **MobileNetV2** dengan strategi *Feature Extraction* [cite: 60, 65], di mana seluruh pretrained layer dibekukan (*frozen*) dan hanya melatih *classifier* baru di bagian atas[cite: 66].

## 📈 Ringkasan Hasil Perbandingan
Berdasarkan eksperimen yang telah dilakukan, berikut adalah ringkasan perbandingan kedua model[cite: 71]:

| Aspek | CNN from Scratch | Transfer Learning (MobileNetV2) |
| :--- | :--- | :--- |
| **Akurasi Testing** | 55% - 65% (Cenderung Overfitting) | 80% - 90% (Sangat Stabil) |
| **Waktu Training** | Lebih cepat per epoch | Sedikit lebih berat namun konvergen lebih cepat |
| **Risiko Overfitting**| Sangat Tinggi (karena dataset terbatas) | Sangat Rendah |
| **Kesesuaian Dataset**| Kurang cocok untuk data skala kecil | Sangat cocok untuk data skala kecil |

*Grafik performa (Loss & Accuracy), Confusion Matrix, serta sampel prediksi benar/salah dapat dilihat secara lengkap di dalam file Jupyter Notebook atau dokumen laporan PDF[cite: 84].*

## 🛠️ Cara Menjalankan Proyek di Lokal

Jika Anda ingin menjalankan atau mereproduksi eksperimen ini di komputer lokal Anda, ikuti langkah-langkah berikut:

1. **Clone Repository ini:**
   ```bash
   git clone [https://github.com/fathurnaufal24/project-cnn-vs-transfer-learning.git](https://github.com/fathurnaufal24/project-cnn-vs-transfer-learning.git)
   cd project-cnn-vs-transfer-learning
Install Semua Library yang Dibutuhkan:Pastikan Anda sudah menginstal Python (disarankan versi 3.8+). Jalankan perintah berikut untuk menginstal dependencies:Bashpip install -r requirements.txt
Jalankan Jupyter Notebook:Buka file notebook di folder notebook/ menggunakan Jupyter Lab/Notebook atau VS Code:Bashjupyter notebook notebook/cnn_vs_transfer_learning.ipynb
👤 Identitas MahasiswaNama: Fathurrahman Naufal   Program: Magister Teknik Informatika   Afiliasi: Universitas Darussalam Gontor  
