# 🩺 ISPA Detect: Solusi Deteksi Dini Kesehatan Pernapasan

![Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-blue)
![Made with](https://img.shields.io/badge/made%20with-FastAPI%20%7C%20Vue.js-green)

## Daftar Isi
- [Deskripsi Proyek](#deskripsi-proyek)
- [Fitur Utama](#fitur-utama)
- [Tech Stack](#tech-stack)
- [Struktur Proyek](#struktur-proyek)
- [Instalasi](#instalasi)
- [Cara Penggunaan](#cara-penggunaan)
- [Environment Variables](#environment-variables)
- [Roadmap](#roadmap)
- [Kontribusi](#kontribusi)
- [Penafian Medis](#penafian-medis-medical-disclaimer)
- [Lisensi](#lisensi)
- [Pengembang](#pengembang)

## Landing Page
![Logo Aplikasi Saya](src/assets/localhost_5173_ (1).png)

## Deskripsi Proyek
**ISPA Detect** adalah sistem deteksi dini berbasis *Machine Learning* yang dirancang untuk membantu tenaga medis dan masyarakat dalam melakukan skrining awal risiko Infeksi Saluran Pernapasan Akut (ISPA). Proyek ini menggabungkan teknik *Ensemble Learning* yang canggih (Random Forest & XGBoost) dengan pendekatan *Soft Voting* untuk memberikan prediksi risiko yang lebih akurat dan dapat diandalkan dibandingkan model tunggal.

Sistem ini dikembangkan sebagai bagian dari penyelesaian studi Informatika dengan fokus pada implementasi teknologi cerdas di bidang kesehatan masyarakat.

## Fitur Utama
- **Analisis Prediktif Cerdas** — Menggunakan model *Ensemble Learning* untuk mengklasifikasikan risiko ISPA berdasarkan 16 parameter klinis (demografi dan gejala).
- **Mekanisme Soft Voting** — Meningkatkan probabilitas akurasi prediksi melalui integrasi probabilitas dari beberapa model *machine learning*.
- **Antarmuka Modern** — Dibangun dengan **Vue.js** dan **Tailwind CSS** untuk pengalaman pengguna yang responsif, bersih, dan klinis.
- **Edukasi Kesehatan** — Menyediakan informasi komprehensif mengenai ISPA, langkah pencegahan, serta panduan kegawatdaruratan (*Red Flags*).
- **Validasi Klinis** — Menerapkan validasi input yang ketat untuk memastikan integritas data medis sebelum diproses oleh sistem.

## Tech Stack

### Backend
| Komponen | Teknologi |
|---|---|
| Framework | FastAPI (Python) |
| Machine Learning | Scikit-Learn (Random Forest), XGBoost |
| Validasi Data | Pydantic |

### Frontend
| Komponen | Teknologi |
|---|---|
| Framework | Vue.js 3 (Vite) |
| Styling | Tailwind CSS |
| Validasi Form | VeeValidate / Zod |
| HTTP Client | Axios |

## Struktur Proyek
```text
├── src/
│   ├── assets/           # CSS Global & aset visual
│   ├── components/       # Komponen UI modular (Navbar, Form, Dashboard)
│   ├── services/         # Integrasi API FastAPI
│   └── views/            # Halaman utama aplikasi
├── models/               # File serialisasi model (.pkl)
└── main.py               # Entry point API FastAPI
```

## Instalasi

### Prasyarat
- Node.js `>= 18.x` dan npm
- Python `>= 3.10`
- Git

### Clone Repository
```bash
git clone https://github.com/alviansyahburhani/Ispa-Detect-Frontend.git
cd Ispa-Detect-Frontend
```

### Setup Backend
```bash
cd backend
python -m venv venv
venv\Scripts\activate      # Windows
# source venv/bin/activate # macOS/Linux

pip install -r requirements.txt
uvicorn main:app --reload
```
Backend akan berjalan pada `http://127.0.0.1:8000`.

### Setup Frontend
```bash
cd frontend
npm install
npm run dev
```
Frontend akan berjalan pada `http://localhost:5173`.

## Cara Penggunaan
1. **Backend** — Pastikan FastAPI sudah berjalan pada `http://127.0.0.1:8000`.
2. **Frontend**:
   - Instalasi dependensi: `npm install`
   - Jalankan server pengembangan: `npm run dev`
   - Akses antarmuka melalui: `http://localhost:5173`
3. **Diagnosis** — Masukkan data klinis pada form yang tersedia, lalu tunggu sistem memberikan hasil prediksi beserta persentase probabilitas risikonya.

## Environment Variables
Buat file `.env` pada folder `frontend/` dengan isi berikut:
```env
VITE_API_BASE_URL=http://127.0.0.1:8000
```

## Roadmap
- [ ] Integrasi riwayat pemeriksaan pengguna (history tracking)
- [ ] Dukungan multi-bahasa (Indonesia/English)
- [ ] Deployment ke cloud (Docker + CI/CD)
- [ ] Peningkatan akurasi model dengan dataset yang lebih besar

## Kontribusi
Kontribusi sangat terbuka untuk pengembangan proyek ini. Silakan ikuti langkah berikut:
1. Fork repository ini
2. Buat branch baru (`git checkout -b fitur/nama-fitur`)
3. Commit perubahan (`git commit -m "Menambahkan fitur X"`)
4. Push ke branch (`git push origin fitur/nama-fitur`)
5. Buat Pull Request

## Penafian Medis (Medical Disclaimer)
> Sistem deteksi dini "ISPA Detect" menggunakan model kecerdasan buatan untuk tujuan skrining awal dan edukasi. Hasil prediksi yang diberikan oleh sistem ini **tidak dapat menggantikan** diagnosis, anjuran, atau pengobatan dari dokter profesional. Selalu konsultasikan kondisi kesehatan Anda ke fasilitas layanan kesehatan terdekat jika gejala memburuk.

## Lisensi
Proyek ini dilisensikan di bawah [MIT License](LICENSE).

## Pengembang
Proyek ini dikembangkan oleh **Alvian Syah Burhani** sebagai bagian dari tugas akhir mahasiswa Informatika angkatan 2022.

📧 Untuk pertanyaan atau kolaborasi, silakan hubungi melalui GitHub: [@alviansyahburhani](https://github.com/alviansyahburhani)
