# Spring Boot Deployment to VPS

## Tech Stack
- **Framework**: Spring Boot 3 + Spring Web
- **Database**: MySQL 8.0
- **Cache**: Redis
- **Containerization**: Docker & Docker Compose
- **Language**: Java 21

## Cara Clone dan Menjalankan API di Lokal
1. Clone repository ini:
   ```bash
   git clone <URL_REPOSITORY_GITHUB>
   cd springboot-deploy-vps
   ```
2. Pastikan Docker dan Docker Compose sudah terinstall di lokal.
3. Ubah nama `.env.example` menjadi `.env` jika belum ada:
   ```bash
   cp .env.example .env
   ```
4. Jalankan aplikasi menggunakan Docker Compose:
   ```bash
   docker-compose up -d --build
   ```
5. API akan berjalan di `http://localhost:9003`.

## Step by step deployment ke VPS
1. Login ke VPS menggunakan SSH:
   ```bash
   ssh <username>@<ip_vps>
   ```
2. Install Docker dan Git di VPS jika belum tersedia.
3. Clone repository ini di dalam VPS:
   ```bash
   git clone <URL_REPOSITORY_GITHUB>
   cd springboot-deploy-vps
   ```
4. Konfigurasi file `.env` di VPS sesuai dengan environment (gunakan `.env.example` sebagai referensi).
5. Jalankan aplikasi secara background menggunakan Docker Compose:
   ```bash
   docker-compose up -d --build
   ```
6. Aplikasi berhasil di-deploy dan dapat diakses publik via IP VPS di port 9003 (pastikan firewall port 9003 sudah dibuka di pengaturan VPS Anda).

## API Documentation / Testing
Berikut adalah endpoint utama yang dapat diuji melalui Postman:
- **GET All Products**: `GET http://<ip_vps>:9003/products`
- **Create Product**: `POST http://<ip_vps>:9003/products`
  Body JSON contoh:
  ```json
  {
      "name": "Produk Test",
      "price": 10000.00
  }
  ```

*(Silakan tambahkan link dokumentasi Postman / taruh hasil screenshot di repositori ini sesuai instruksi assignment)*
