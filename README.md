Aplikasi Manajemen Obat (Medicine Manager)Aplikasi berbasis Mobile (Flutter) dan Web API (Laravel) untuk memantau stok obat, mengelola harga, serta inventarisasi data medis secara real-time. Sangat cocok untuk apotek atau unit farmasi rumah sakit.

📱 Tampilan Aplikasi (Screenshots)
[Halaman Login] - Akses aman untuk petugas farmasi.
[Halaman Registrasi] - Pendaftaran akun pengguna baru.
[Dashboard Obat] - Daftar stok, kategori obat, dan status kadaluarsa.
[Form Input/Edit] - Menambah atau memperbarui data obat.

🛠️ Teknologi yang Digunakan
Frontend    Flutter (Dart)
Backend     Laravel 10/11 (PHP)
Database    MySQL / MariaDB
Autentikasi Laravel Sanctum (Bearer Token)

🚀 Panduan Instalasi & Menjalankan (Step-by-Step)
Bagian 1: Persiapan Backend (Laravel)
1. Masuk ke Folder Backend: Buka terminal di direktori project Laravel Anda.
2. Install Dependencies:   Bashcomposer install
3. Konfigurasi Database:Buat database baru 
   - (misal: dbdata-obat).
   - Salin file .env.example menjadi .env.
   - Sesuaikan konfigurasi berikut di file .env:
        DB_CONNECTION=mysql
        DB_HOST=127.0.0.1
        DB_PORT=3306
        DB_DATABASE=dbdata-obat
        DB_USERNAME=root
        DB_PASSWORD=
4. Migrasi Database: php artisan migrate
5. Jalankan Server (PENTING): Agar bisa diakses oleh HP Android dalam satu jaringan, gunakan: php artisan serve --host=0.0.0.0 --port=8000
Bagian 2: Persiapan Frontend (Flutter)
1. Cek IP Address Laptop:
    Windows: Ketik ipconfig di CMD.
    Linux/Mac: Ketik ifconfig atau ip addr.
    Contoh IP: 192.168.1.15
2. Konfigurasi API Service: Buka lib/services/api_service.dart dan ubah baseUrl:Dartstatic const String baseUrl = 'http://192.168.102.239:8000/api';
3. Install Dependencies & Jalankan:
    flutter pub get
    flutter run

⚠️ Troubleshooting (Kendala Umum)
1. Gagal Login / Koneksi Timeout?
    - Pastikan HP dan Laptop terhubung ke Wi-Fi yang sama.
    - Matikan Firewall laptop atau izinkan akses port 8000.
2. Error "Cleartext Traffic not permitted"?
    - Buka android/app/src/main/AndroidManifest.xml, pastikan ada atribut ini pada 
    - tag <application>:android:usesCleartextTraffic="true"
3. Data Tidak Muncul?
    - Cek apakah data di database sudah terisi. Gunakan perintah curl atau aplikasi Postman untuk mengetes endpoint API secara langsung.