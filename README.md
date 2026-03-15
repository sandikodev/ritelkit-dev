# 🛒 RitelKit Open Source Developer Ecosystem

Selamat datang di repository resmi **RitelKit Dev**. Project ini adalah ekosistem manajemen ritel multi-tenant modern yang dibangun untuk kecepatan, isolasi data, dan kemudahan replikasi.

## 📁 Struktur Repository

Repository ini menggunakan Git Submodules untuk mengelola dua project utama:
1. **ritelkit (Dashboard Pusat)**: Manajemen global tenant, audit log, dan stok global.
2. **ritelkit-app (Aplikasi Tenant)**: Aplikasi operasional yang digunakan oleh tenant (Point of Sale, Inventory, Invoicing).

## 🚀 Quick Start untuk Developer

### 1. Prasyarat
- Node.js & pnpm
- Turso CLI (untuk database production)
- Konfigurasi `/etc/hosts` untuk domain lokal (`ritelkit.local`)

### 2. Instalasi & Setup Submodules
```bash
# Clone dengan submodules
git clone --recursive git@github.com:sandikodev/ritelkit-dev.git

# Atau jika sudah clone
git submodule update --init --recursive
```

### 3. Jalankan Project
```bash
# Install dependencies di kedua folder
cd ritelkit && pnpm install
cd ../ritelkit-app && pnpm install
```

### 4. Panduan Pengembangan
Silakan baca [ECOSYSTEM_GUIDE.md](./ECOSYSTEM_GUIDE.md) untuk detail arsitektur, cara kerja multi-tenancy, dan kebijakan internal tim.

## 🤝 Kontribusi
Kami sangat terbuka bagi komunitas untuk ikut mengembangkan RitelKit. Silakan buka Issue atau kirim Pull Request jika Anda menemukan bug atau memiliki ide fitur baru!
