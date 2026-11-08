# ⚡ Campus IoT — Platform Manajemen Inventaris Komponen Terpadu
> **Product Case Study Portfolio &bull; Program MSIB Batch 5 &bull; PT VINIX SEVEN AURUM**

[![HTML5 Semantic](https://img.shields.io/badge/HTML5-Semantic%20Architecture-E34F26?logo=html5&logoColor=white)](index.html)
[![Modern CSS Tokens](https://img.shields.io/badge/CSS3-Design%20Tokens%20%26%20Bento-1572B6?logo=css3&logoColor=white)](style.css)
[![WCAG 2.1 AA](https://img.shields.io/badge/Accessibility-WCAG%202.1%20AA-22C55E)](index.html)
[![Live Demo](https://img.shields.io/badge/Live%20Demo-iot--inventaris.egie.my.id-2563EB?logo=googlechrome&logoColor=white)](https://iot-inventaris.egie.my.id/)
[![Source Code](https://img.shields.io/badge/GitHub-Iot--Component--Manager-181717?logo=github&logoColor=white)](https://github.com/egieirwn/Iot-Component-Manager)

---

## 📌 Ringkasan Proyek

**Campus IoT** adalah platform digital berbasis web yang dirancang untuk mentransformasi sistem pencatatan inventaris perangkat keras laboratorium Teknik Informatika dari sistem manual (buku tulis) menjadi sistem pelacakan otomatis dan *real-time*.

Studi kasus ini mendokumentasikan perjalanan iterasi produk digital selama **10 minggu (Modul 1 s/d Modul 10)**, mencakup riset pengguna, perancangan *design system*, arsitektur kode frontend, pengujian *usability* ke pengguna nyata, hingga audit performa dan keamanan siber.

---

## 🚀 Tautan Penting
- **🌐 Web Aplikasi Live:** [https://iot-inventaris.egie.my.id/](https://iot-inventaris.egie.my.id/)
- **💻 Repositori Kode Web Utama:** [github.com/egieirwn/Iot-Component-Manager](https://github.com/egieirwn/Iot-Component-Manager)
- **📑 Repositori Case Study Ini:** [github.com/egieirwn/study-case](https://github.com/egieirwn/study-case)

---

## 🎨 Struktur Dokumen & Fase Studi Kasus

Halaman case study diorganisasi menjadi 5 fase sistematis:

### 1. Fase 01 — Validasi Masalah & Riset Pengguna (Modul 1–3)
- Pemetaan akar masalah logistik manual di laboratorium.
- Perumusan **User Persona** (Mahasiswa IoT & Asisten Laboratorium) serta **Empathy Map** 4-kuadran (*Says, Thinks, Does, Feels*).
- Identifikasi 5 *Pain Points* kritis mahasiswa saat mencari ketersediaan modul.

### 2. Fase 02 — Blueprint, User Flow & Design Tokens (Modul 4–5)
- Perancangan **User Flow 6 Tahap**: SSO Autentikasi &rarr; Katalog Dinamis &rarr; Filter Cerdas &rarr; Checkout Peminjaman &rarr; Tracking Realtime &rarr; Diagnosis Pengembalian.
- **Design Tokens Asli**:
  - `--color-primary: #2563EB` (Biru Muda Tombol)
  - `--color-bg-surface: #FFFFFF` (Putih Background)
  - `--color-text-main: #0F172A` (Hitam Teks Utama)
  - `--status-available: #16A34A` (Hijau Barang Tersedia)
  - `--status-partial: #0369A1` (Biru Agak Gelap saat Dipinjam Separuh)
  - `--status-borrowed: #EA580C` (Oranye saat Dipinjam Penuh)
- Komparasi *Low-Fidelity Wireframe* ke *High-Fidelity Figma Prototype*.

### 3. Fase 03 — Web Development & Clean Code (Modul 6–8)
- Implementasi semantic HTML5 murni tanpa *div soup*.
- Arsitektur data dinamis via **Supabase BaaS (Postgres + Auth)**.
- Dokumentasi *Prompt Engineering* menggunakan AI (Cursor / Claude 3.5 Sonnet) untuk validasi logic checkout atomik.

### 4. Fase 04 — Usability Testing & Iterasi Nyata (Modul 9)
Pengujian langsung terhadap 5 partisipan mahasiswa dengan protokol *Think-Aloud*:
- **Task Success Rate:** **100%** (seluruh 4 skenario diselesaikan mandiri).
- **Rata-rata Skor SEQ (Single Ease Question):** **6.6 / 7** (*Sangat Mudah Digunakan*).
- **Rata-rata Waktu Sesi:** **17 Menit 45 Detik**.
- **Perbaikan 1 (Logika Stok):** Koreksi conditional rendering status *Sebagian Dipinjam* (warna biru agak gelap) agar tombol tidak terkunci keliru.
- **Perbaikan 2 (Lapor Rusak):** Penambahan fitur checkbox & diagnosis kerusakan pada formulir pengembalian.

### 5. Fase 05 — Audit Lighthouse & Keamanan (Modul 10)
- **Google Lighthouse Scores:**
  - 🟢 **Performance:** 92 / 100
  - 🟢 **Accessibility:** 95 / 100
  - 🟢 **Best Practices:** 100 / 100
  - 🟢 **SEO:** 100 / 100
- **6 Pilar Keamanan:** Enkripsi HTTPS SSL/TLS 1.3, Sanitasi Input anti-XSS, Vault Environment Secrets (`.env`), Kepatuhan Minimalisasi Data UU PDP, Whitelist CORS, dan JWT Session Security.

---

## 📂 Struktur Direktori Proyek

```
study-case/
├── index.html              # Entry point utama (support GitHub Pages langsung)
├── style.css               # Stylesheet modern (Bento Grid, Custom Properties, Glassmorphism)
├── design-system.md        # Spesifikasi Design Tokens & panduan UI/UX
├── README.md               # Dokumentasi resmi proyek
├── .gitignore              # Mengabaikan file backup dan temporary
└── assets/                 # Direktori terpusat untuk semua aset visual asli
    ├── Dashboard.png       # Screenshot web live dashboard
    ├── userflow.png        # Diagram alur 6 tahap peminjaman
    ├── wireframe hitam-putih.png   # Desain wireframe Low-Fi
    ├── UI final berwarna.png       # Prototipe High-Fi Figma
    ├── Code Editor.png     # Screenshot struktur HTML semantik
    └── matriks-testing.png # Screenshot tabel data usability testing Modul 9
```

---

## 👥 Tim Pengembang Mahasiswa
Proyek ini dikembangkan secara kolaboratif dan setara oleh **Tim 1 Divisi Web & UI/UX Developer** dalam program **MSIB Batch 5 bersama PT VINIX SEVEN AURUM**:

1. **Aditya Herlambang** — NIM: `230103154`
2. **Egie Irawan** — NIM: `230103132`
3. **Gibrand Putra Pradana** — NIM: `230103136`
4. **Lintang Wahyu Aji Saputro** — NIM: `230103140`
5. **Nabil Dzaka Fahrizal Santoso** — NIM: `230103202`

---

## 💻 Cara Menjalankan Secara Lokal

1. **Clone repositori:**
   ```bash
   git clone https://github.com/egieirwn/study-case.git
   cd study-case
   ```
2. **Buka file di browser:**
   - Cukup buka file `index.html` langsung di browser favorit Anda (Chrome, Edge, Firefox, Safari).
   - Atau gunakan ekstensi **Live Server** di VS Code untuk pengalaman live reload.

---

<p align="center">
  <small>&copy; 2026 Tim 1 MSIB Batch 5 &bull; PT VINIX SEVEN AURUM. Hak Cipta Dilindungi.</small>
</p>
