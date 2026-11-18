# Smart Irrigation IoT — Streamlit UI

## Deskripsi Proyek
Proyek ini merupakan prototipe Sistem Irigasi Pintar berbasis Internet of Things (IoT) dan Machine Learning. Aplikasi antarmuka (UI) ini dikembangkan menggunakan Streamlit untuk memantau dan memprediksi status penyiraman pada 16 petak area rumah kaca secara real-time. Keputusan penyiraman otomatis didasarkan pada inferensi model Machine Learning yang telah dilatih menggunakan data primer dari sensor lingkungan mikro (kelembapan tanah, suhu udara, cuaca, dan curah hujan), guna mengoptimalkan penggunaan air serta mencegah kerugian agronomis.

## Struktur Direktori Proyek

```text
smart_irrigation_vscode/
├── .streamlit/
│   └── config.toml                        # Konfigurasi parameter tampilan dan tema Streamlit
├── .vscode/
│   ├── launch.json                        # Konfigurasi debugging untuk VSCode
│   ├── settings.json                      # Konfigurasi lingkungan interpreter Python lokal
│   └── tasks.json                         # Automasi task runner VSCode
├── data/
│   └── sample_greenhouse_16petak.csv      # Dataset sampel kondisi lingkungan mikro 16 petak 
├── notebooks/
│   └── Kasus_07_Smart_Irrigation_IoT_Optimasi_Lengkap.ipynb  # Notebook eksplorasi dan pelatihan model 
├── app.py                                 # Skrip utama antarmuka Streamlit
├── model_irigasi_pintar_streamlit.pkl     # Berkas serialisasi model Machine Learning (pipeline)
├── requirements.txt                       # Daftar dependensi paket Python
├── run_windows.bat                        # Skrip eksekusi otomatis untuk platform Windows
├── run_mac_linux.sh                       # Skrip eksekusi otomatis untuk platform macOS/Linux
└── README.md                              # Dokumentasi teknis repositori
```

## Prasyarat dan Eksekusi Lokal

Aplikasi ini dapat dieksekusi pada lingkungan lokal menggunakan virtual environment Python untuk memastikan isolasi dependensi paket.

### Eksekusi Manual (Terminal Bebas)
Untuk platform non-Windows atau pengaturan manual, jalankan perintah berikut secara berurutan di dalam terminal:

```bash
# 1. Inisialisasi virtual environment
python -m venv venv

# 2. Aktivasi virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# 3. Instalasi dependensi
pip install -r requirements.txt

# 4. Inisialisasi peladen aplikasi
streamlit run app.py
```

### Eksekusi Otomatis (Skrip Batch - Windows)
Bagi pengguna sistem operasi Windows, instalasi dan eksekusi dapat dilakukan secara langsung melalui terminal VSCode:
```cmd
.\run_windows.bat
```
*(Skrip ini akan memvalidasi keberadaan environment, menginstal seluruh dependensi, dan memulai server Streamlit secara otomatis).*

## Panduan Deployment Publik (Streamlit Community Cloud)

Repositori ini siap untuk integrasi langsung (deployment) ke layanan cloud publik tanpa modifikasi tambahan. 
1. Inisialisasi repositori baru pada akun **GitHub** Anda.
2. Lakukan commit dan push untuk berkas serta direktori berikut: `app.py`, `model_irigasi_pintar_streamlit.pkl`, `requirements.txt`, direktori `data/`, dan direktori `.streamlit/`. 
   *(Catatan: Direktori `venv/` dan berkas sistem konfigurasi lokal tidak perlu diikutsertakan ke dalam repositori).*
3. Akses layanan [share.streamlit.io](https://share.streamlit.io/) dan lakukan autentikasi menggunakan akun GitHub.
4. Buat aplikasi baru (**New app**), pilih repositori yang relevan, dan pastikan parameter *Main file path* merujuk pada **`app.py`**.
5. Pada menu *Advanced settings*, tetapkan versi Python ke **3.11** untuk menjaga kompatibilitas versi library. 
6. Eksekusi proses deploy.
