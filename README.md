# 🌾 Smart Agriculture Pipeline: Prediksi Produktivitas Panen untuk Mewujudkan Zero Hunger
> Infrastruktur Data End-to-End untuk Integrasi Data Pertanian (BPS) & Cuaca (BMKG) guna Mendukung Ketahanan Pangan

[![Status Project](https://img.shields.io/badge/Status-Completed-success.svg)]()
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)]()
[![Streamlit](https://img.shields.io/badge/Dashboard-Streamlit-red.svg)]()
[![Institution](https://img.shields.io/badge/Universitas-Brawijaya-red.svg)]()

Repositori ini berisi kode sumber, skrip pipeline ETL, model pemprediksian, dan dokumentasi laporan lengkap untuk **Proyek Akhir Pemrosesan Infrastruktur Data**. Sistem ini dirancang untuk mengintegrasikan data statistik pertanian dari BPS dan data cuaca historis dari BMKG, melakukan *feature engineering* agronomis, serta menyajikan visualisasi analitik dan prediksi produktivitas padi nasional melalui *dashboard* interaktif.

---

## 🏛️ Informasi Akademik
* **Mata Kuliah:** Pemrosesan Infrastruktur Data
* **Dosen Pengampu:** Eko Sakti Pramukantoro, S.Kom., M.Kom., Ph.D.
* **Institusi:** Fakultas Ilmu Komputer, Universitas Brawijaya (FILKOM UB)

### 👥 Tim Penyusun (Kelompok)
1. **Rezky Auliasarie** (245150300111014)
2. **Alexander Agung Widhi P.** (245150300111054)
3. **Muhammad Raihan Bakhtiar** (245150301111010)
4. **Zeyra Rahma Alivia** (245150301111016)
5. **Muhammad Naufal M.R.** (245150307111006)
6. **Chelsea Kurnia Sandy** (245150307111053)

---

## 💡 Latar Belakang & Tujuan
Ketahanan pangan nasional menghadapi tantangan besar akibat fluktuasi iklim dan ketidakpastian hasil panen. Proyek ini bertujuan untuk:
1. Membangun **Pipeline ETL Batch** yang menyatukan data heterogen (data tahunan BPS [BPS Pertanian](https://www.bps.go.id/id/statistics-table/2/MT050CMy/luas-panen-produksi-dan-produktivitas-padi-menurut-provinsi.html) dan data harian BMKG [Data Online BMKG](https://dataonline.bmkg.go.id/dataonline-home)).
2. Mengembangkan model **Regresi Linear Berganda** (Multiple Linear Regression) untuk memprediksi produktivitas panen berdasarkan parameter iklim, cuaca, dan kondisi kekeringan (*drought index*).
3. Menyediakan antarmuka **Dashboard Interaktif berbasis Streamlit** untuk pemantauan tren spasial dan simulasi prediksi (*what-if analysis*).

---

## ⚙️ Arsitektur Sistem / Pipeline Data
Alur pemrosesan data dalam sistem ini dibagi menjadi beberapa tahapan utama:
1. **Extract:** Pengambilan data statis/batch dari portal [BPS](https://www.bps.go.id/id/statistics-table/2/MT050CMy/luas-panen-produksi-dan-produktivitas-padi-menurut-provinsi.html) (luas panen, produksi, produktivitas) dan portal [BMKG](https://dataonline.bmkg.go.id/dataonline-home) (suhu, curah hujan, kelembaban).
2. **Transform:** Pembersihan data (*missing values*, normalisasi nama provinsi), agregasi temporal tahunan, serta *feature engineering* (seperti penghitungan *Drought Index*, kategori suhu & hujan, serta fitur interaksi).
3. **Load:** Penyimpanan data bersih (*raw & processed*) ke dalam database relasional **PostgreSQL** menggunakan SQLAlchemy dan Psycopg2.
4. **Modeling & Evaluation:** Pelatihan model regresi menggunakan Scikit-learn serta evaluasi performa menggunakan metrik $R^2$ dan MSE.
5. **Visualize:** Visualisasi hasil analitik dan prediksi melalui dashboard **Streamlit** dan Plotly.

---

## 📂 Struktur Repositori
```text
├── Projek Akhir Pemrosesan Infrastruktur Data.pdf    # Dokumen laporan lengkap proyek (analisis, arsitektur, & evaluasi)
├── src/                                             # Direktori kode sumber pipeline, pemodelan, dan aplikasi
└── README.md                                        # Dokumentasi proyek
