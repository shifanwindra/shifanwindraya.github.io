# Dokumentasi Proyek — Import Database Geospasial (Basis Data)

**Mata Kuliah:** Basis Data  
**Nama Proyek:** Praktikum Basis Data Geospasial — Import MongoDB  
**Penyusun:** Shifan Windraya Prassasti (24/541727/SV/24944)  
**Program Studi:** D-IV Teknologi Rekayasa Internet — Sekolah Vokasi UGM  

---

## 1. Latar Belakang

MongoDB adalah sistem manajemen basis data NoSQL yang sangat baik untuk menangani data tidak terstruktur dan semi-terstruktur, termasuk data geospasial. Pada proyek ini, dua dataset geospasial diimport ke dalam MongoDB sebagai praktik penggunaan basis data dokumen.

---

## 2. Tujuan Proyek

- Memahami cara mengimport data ke dalam MongoDB menggunakan `mongoimport`.
- Mengeksplorasi database geospasial: data Airbnb dan data Shipwrecks (bangkai kapal).
- Memahami struktur dokumen JSON dalam konteks basis data geospasial.

---

## 3. Dataset yang Digunakan

| Dataset | Deskripsi |
|---------|-----------|
| `listingsAndReviews.json` | Data listing properti Airbnb beserta ulasan |
| `shipwrecks.json` | Data lokasi bangkai kapal (geospasial) |

---

## 4. Penyelesaian

### Tools
- **MongoDB** — database NoSQL berbasis dokumen.
- **MongoDB Tools** (`mongoimport`) — untuk import data JSON ke MongoDB.
- **Download MongoDB Tools:** [atlas-app-services-cli_windows_x64](https://downloads.mongodb.com/app-services-cli/)

### Langkah-langkah Import

1. **Install MongoDB Tools** — download dan ekstrak MongoDB Database Tools untuk Windows.
2. **Jalankan perintah `mongoimport`** untuk masing-masing dataset:
   ```bash
   mongoimport --db geospasial2 --collection airbnb --file listingsAndReviews.json --jsonArray
   mongoimport --db geospasial2 --collection shipwrecks --file shipwrecks.json --jsonArray
   ```
3. **Verifikasi import** melalui MongoDB Compass atau MongoDB Shell.

---

## 5. Hasil

- ✅ Database `geospasial2` berhasil dibuat di MongoDB.
- ✅ **Dataset Airbnb** (`listingsAndReviews`) berhasil diimport — memuat data listing properti dengan koordinat lokasi.
- ✅ **Dataset Shipwrecks** berhasil diimport — memuat data bangkai kapal dengan informasi posisi geospasial.
- Screenshot hasil import tersedia: `airbnb shifan.png` dan `shpwreck shifan.png`.

---

## 6. Kesimpulan

Praktikum ini berhasil mendemonstrasikan proses import dua database geospasial ke MongoDB. Penggunaan `mongoimport` terbukti efektif untuk memuat data JSON berukuran besar. Basis data geospasial ini dapat selanjutnya digunakan untuk query berbasis koordinat dan analisis lokasi menggunakan operator geospasial MongoDB.
