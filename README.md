<div align="center">

# 🎮 MarBlox.id

**Sistem Informasi Pengisian Mata Uang Virtual Game Roblox Menggunakan Arsitektur Asynchronous Webhook Integration API Digiflazz dan Midtrans**

[![Laravel](https://img.shields.io/badge/Laravel-12-FF2D20?logo=laravel&logoColor=white)](https://laravel.com)
[![Vue.js](https://img.shields.io/badge/Vue.js-3-4FC08D?logo=vue.js&logoColor=white)](https://vuejs.org)
[![Inertia.js](https://img.shields.io/badge/Inertia.js-2-9553E9?logo=inertia&logoColor=white)](https://inertiajs.com)
[![TailwindCSS](https://img.shields.io/badge/Tailwind-4-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker&logoColor=white)](https://docker.com)

</div>

---

## ✨ Fitur Utama

| Kategori | Fitur |
| --- | --- |
| **Pengisian** | Pengisian Robux via Username Roblox tanpa login |
| **Transaksi** | Checkout otomatis, pembayaran, riwayat & tracking status |
| **Keamanan** | Tanpa menyimpan kredensial akun pengguna |
| **Otomatisasi** | Webhook Digiflazz & Midtrans - proses real-time |
| **Admin** | Manajemen produk, kategori, laporan & analitik |

---

## 🚀 Quick Start

### Opsi 1 — Docker (Direkomendasikan)

**Prasyarat:** Docker & Docker Compose terinstall.

```bash
# 1. Clone repository
git clone <repository-url>
cd Marblox

# 2. Salin file environment
cp .env.docker .env

# 3. Setup otomatis (build image, migrate, generate key)
./docker-run.sh setup
```

Aplikasi berjalan di **http://localhost**

#### Perintah Docker yang Tersedia

```bash
./docker-run.sh setup       # Setup otomatis
./docker-run.sh up          # Mulai semua service
./docker-run.sh down        # Hentikan semua service
./docker-run.sh shell       # Masuk ke bash container app
./docker-run.sh build       # Build ulang image Docker
./docker-run.sh artisan ... # Jalankan perintah Artisan
./docker-run.sh logs        # Tail log semua container
./docker-run.sh test        # Jalankan Pest tests
./docker-run.sh reset       # Reset semua data
```

---

### Opsi 2 — Manual

**Prasyarat:** PHP 8.4, MySQL 8, Redis, Node.js 22, Composer.

```bash
# 1. Install dependencies
composer install && npm install

# 2. Salin file environment
cp .env.example .env

# 3. Generate application key
php artisan key:generate

# 4. Sesuaikan konfigurasi database di .env, lalu jalankan migrasi
php artisan migrate --seed

# 5. Buat symlink storage
php artisan storage:link

# 6. Jalankan development server
composer run dev
```

---

## 🔑 Konfigurasi API

Isi kredensial berikut di file `.env`:

```env
# Midtrans — https://midtrans.com
MIDTRANS_MERCHANT_ID=
MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=

# Digiflazz — https://member.digiflazz.com/buyer-area
DIGIFLAZZ_USERNAME=
DIGIFLAZZ_API_KEY=
DIGIFLAZZ_WEBHOOK_SECRET=
```

---

## 🛠 Tech Stack

- **Backend:** Laravel 12, PHP 8.4
- **Frontend:** Vue 3, Inertia.js v2, TailwindCSS v4
- **Database:** MySQL 8
- **Cache / Queue:** Redis
- **Web Server:** Nginx
- **Payment Gateway:** Midtrans
- **Supplier Produk Digital:** Digiflazz
