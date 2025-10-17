<h1 align="center">🧠 FaceID — Aplikasi Verifikasi Identitas Berbasis MobileNetV2-Siamese</h1>

<p align="center">
  <img src="https://github.com/abdul014/Identity-Verification/blob/main/precision_recall.png?raw=true" width="650" alt="Model Precision Recall Graph">
</p>

<p align="center">
  <b>Implementasi verifikasi identitas berbasis wajah menggunakan arsitektur Siamese Network dengan backbone MobileNetV2.</b><br>
  Aplikasi ini memungkinkan pengguna untuk melakukan <b>pendaftaran (Register)</b> dan <b>verifikasi (Verify)</b> wajah secara real-time melalui antarmuka desktop berbasis Python.
</p>

---

## 📖 Tentang Proyek
Proyek ini dirancang untuk melakukan **verifikasi identitas wajah** dengan menggunakan model deep learning **Siamese Neural Network (SNN)** berbasis **MobileNetV2** sebagai feature extractor.  
Sistem ini menghitung **jarak (distance)** antar embedding wajah untuk menentukan apakah dua wajah berasal dari orang yang sama atau tidak.

> 🔍 Mekanisme utama: semakin kecil jarak antar embedding, semakin besar kemungkinan identitas cocok.

---

## 🧩 Arsitektur Model
Model yang digunakan adalah **Siamese Neural Network** dengan backbone **MobileNetV2** yang sudah di-finetune.  
Setiap citra wajah diubah menjadi **embedding vektor**, dan hasilnya dibandingkan menggunakan fungsi jarak **L2 (Euclidean Distance)**.

<p align="center">
  <img src="https://github.com/abdul014/Identity-Verification/blob/main/60c9435c-0688-4f15-ad34-928f6e420042.png?raw=true" width="700" alt="Arsitektur Siamese Network">
</p>

> ⚙️ Output model berupa nilai distance yang dibandingkan terhadap threshold untuk menentukan kecocokan identitas.

---

## 🚀 Mekanisme Kerja Aplikasi
1. **Register:** pengguna memasukkan wajah baru ke database dengan menyimpan embedding hasil MobileNetV2.  
2. **Verify:** aplikasi mengambil citra wajah baru dan membandingkannya dengan data embedding sebelumnya.  
3. **Distance Calculation:** sistem menghitung jarak antara embedding baru dan data referensi.  
4. **Decision:**  
   - Jika *Average Distance (AD) ≤ Threshold* → **Verifikasi Berhasil (Match)** ✅  
   - Jika *Average Distance (AD) > Threshold* → **Verifikasi Gagal (Not Match)** ❌

---

## 💻 Tampilan Antarmuka (GUI)
Aplikasi prototipe dibuat menggunakan **Tkinter** dengan fitur utama:
- **Register wajah**
- **Verifikasi wajah**
- **Menampilkan nilai Distance & Average Distance**
- Indikator threshold (warna & status)

<p align="center">
  <img src="https://github.com/abdul014/Identity-Verification/blob/main/Tampilan.jpg?raw=true" width="600" alt="GUI FaceID">
</p>

> 🎨 Tampilan antarmuka didesain sederhana namun informatif agar mudah digunakan untuk uji coba sistem identifikasi wajah.

---

## 🧠 Hasil Pelatihan Model
Model dilatih menggunakan dataset wajah yang sudah diolah dan dilakukan augmentasi.  
Evaluasi dilakukan dengan metrik **accuracy**, **precision**, **recall**, dan **loss function** selama 10 epoch pelatihan.

- **Akurasi pelatihan:** 94%
- **Akurasi validasi:** 85.71%
- **Loss:** 0.1308 (training), 0.6575 (validation)

---

## ⚙️ Informasi Installer dan Model
> ⚠️ **Catatan Penting:**  
> File `FaceID_Installer.exe` dan model hasil pelatihan (`.h5`) tidak disertakan dalam repositori karena ukuran file yang besar.  
> Jika Anda ingin mencoba aplikasi versi penuh (dengan installer dan model asli), silakan hubungi pengembang melalui kontak di bawah ini.

<p align="center">
  <img src="https://github.com/abdul014/Identity-Verification/blob/main/Installer/Installer.jpg?raw=true" width="550" alt="Installer Folder Screenshot">
</p>

---

## 📁 Struktur Folder
```
Identity-Verification/
│
├── SignIDApp/                # Source code aplikasi GUI
├── Installer/                # File setup dan installer (offline)
│   ├── FaceID_Installer.exe  # File installer (tidak diunggah ke GitHub)
│   └── faceid_installer.iss  # Script instalasi Inno Setup
│
├── MobileNetV2.ipynb         # Notebook pelatihan model
├── history.json              # Riwayat pelatihan model
├── precision_recall.png      # Grafik hasil pelatihan
└── README.md                 # Dokumentasi proyek
```

---

## 🧩 Demo (GIF)
<p align="center">
  <img src="https://github.com/abdul014/Identity-Verification/blob/main/demo_faceid.gif?raw=true" width="600" alt="FaceID Demo">
</p>

> 🎞️ *Demo di atas menampilkan proses Register dan Verify pada aplikasi FaceID.*

---

## 🧭 Cara Menjalankan Aplikasi
1. Clone repositori ini:
   ```bash
   git clone https://github.com/abdul014/Identity-Verification.git
   ```
2. Masuk ke direktori proyek:
   ```bash
   cd Identity-Verification/SignIDApp
   ```
3. Jalankan aplikasi:
   ```bash
   python app.py
   ```
4. Untuk versi Installer, jalankan file `FaceID_Installer.exe` (jika sudah Anda miliki).

---

## 👨‍💻 Pengembang
**Abd Rahman**  
GitHub: [abdul014](https://github.com/abdul014)  
📬 Untuk permintaan model atau installer, silakan hubungi melalui GitHub.

---

## 📜 Lisensi
Proyek ini dirilis untuk tujuan riset akademik dan pengembangan teknologi verifikasi wajah.  
Silakan mencantumkan kredit kepada pengembang jika Anda menggunakan atau memodifikasi proyek ini.

---

<h4 align="center">🧠 "Mengenali identitas bukan hanya tentang wajah, tetapi tentang keakuratan model yang memahaminya."</h4>
