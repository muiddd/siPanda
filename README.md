# SIPANDA

SIPANDA adalah aplikasi web pendamping belajar yang membantu siswa mengatur kegiatan belajar, mengakses materi, berlatih soal, dan memantau progres dalam satu tempat.

## Fitur utama

- **Dashboard siswa** untuk melihat ringkasan aktivitas belajar.
- **Materi belajar** dengan opsi menandai materi favorit.
- **Latihan soal** dan pencatatan hasil/skor.
- **Asisten belajar berbasis AI** melalui fitur chat dan pemrosesan AI. Ketersediaan fitur ini bergantung pada konfigurasi layanan yang diperlukan.
- **Gamifikasi** dengan sesi belajar, streak, dan pencapaian.
- **Pengelolaan belajar** melalui timer Pomodoro, daftar tugas, buku catatan, dan riwayat skor.
- **Akun pengguna** dengan pengaturan profil, autentikasi Google, serta alur OTP untuk pendaftaran.
- **Panel administrasi** yang dibangun menggunakan Filament.

## Teknologi

- **PHP 8.2+** dan **Laravel 12** untuk backend dan routing.
- **Filament 4** untuk panel administrasi.
- **Blade** untuk template tampilan.
- **Vite**, **Tailwind CSS 4**, dan **JavaScript** untuk aset frontend.
- **SQLite** sebagai konfigurasi database bawaan contoh; database lain yang didukung Laravel dapat dikonfigurasi.
- **Laravel Socialite** untuk integrasi OAuth, termasuk autentikasi Google.
- **PHPUnit** untuk pengujian.

## Prasyarat

Pastikan perangkat pengembangan memiliki:

- PHP **8.2 atau lebih baru** dengan ekstensi yang dibutuhkan Laravel.
- Composer.
- Node.js dan npm.
- Git.
- SQLite (untuk konfigurasi lokal bawaan), atau server database yang kompatibel dengan Laravel.
- Kredensial layanan eksternal yang sesuai jika ingin menggunakan autentikasi Google atau fitur AI.

## Instalasi

```bash
git clone https://github.com/muiddd/sipanda.git
cd sipanda

composer install
npm install

cp .env.example .env
php artisan key:generate
```

Konfigurasi koneksi database di `.env`. Untuk SQLite, buat file database apabila belum tersedia:

```bash
touch database/database.sqlite
```

Pastikan konfigurasi `DB_CONNECTION` dan `DB_DATABASE` di `.env` menunjuk ke SQLite tersebut, lalu jalankan migrasi:

```bash
php artisan migrate
```

Jalankan aplikasi dan Vite dalam mode pengembangan:

```bash
composer run dev
```

Aplikasi dapat diakses melalui alamat lokal yang ditampilkan oleh Laravel (biasanya `http://localhost:8000`). Untuk membuat aset produksi:

```bash
npm run build
```

> Untuk mengaktifkan Google OAuth atau integrasi AI, lengkapi variabel lingkungan dan kredensial layanan terkait. Jangan commit rahasia atau file `.env` ke repository.

## Contoh penggunaan

1. Buka aplikasi lokal dan daftar atau masuk ke akun.
2. Dari dashboard, pilih **Materi** untuk membaca materi dan menyimpan materi favorit.
3. Buka **Latihan Soal** untuk mengerjakan latihan, lalu lihat hasilnya di **Riwayat Skor**.
4. Gunakan **Chat** untuk berinteraksi dengan asisten belajar apabila integrasi AI sudah dikonfigurasi.
5. Atur sesi belajar dengan Pomodoro, dan catat tugas atau rangkuman menggunakan daftar tugas serta buku catatan.

Untuk menjalankan pengujian:

```bash
php artisan test
```

## Susunan project

```text
sipanda/
├── app/
│   ├── Filament/       # Sumber daya dan konfigurasi panel administrasi
│   ├── Http/           # Controller dan middleware aplikasi
│   ├── Mail/           # Kelas email
│   ├── Models/         # Model Eloquent
│   ├── Providers/      # Service provider Laravel
│   ├── Services/       # Layanan aplikasi
│   └── View/           # Komponen/dukungan tampilan
├── bootstrap/          # Bootstrap aplikasi Laravel
├── config/             # Konfigurasi aplikasi dan layanan
├── database/
│   ├── migrations/     # Skema database
│   ├── factories/      # Factory untuk data pengujian
│   └── seeders/        # Seeder database
├── public/             # Entry point dan aset publik
├── resources/
│   ├── css/            # Sumber CSS
│   ├── js/             # Sumber JavaScript
│   └── views/          # Template Blade
├── routes/             # Definisi route web dan API
├── storage/            # Log, cache, dan file hasil aplikasi
├── tests/              # Pengujian otomatis
├── composer.json       # Dependensi dan skrip PHP
├── package.json        # Dependensi dan skrip frontend
└── vite.config.js      # Konfigurasi Vite
```

## Kontribusi

Kontribusi sangat dihargai. Untuk perubahan yang cukup besar, silakan buat issue terlebih dahulu agar usulan dapat didiskusikan.

1. Fork repository dan buat branch baru dari `main`.
2. Buat perubahan dengan cakupan yang jelas.
3. Jalankan pengujian (`php artisan test`) dan pemeriksaan lain yang relevan.
4. Kirim pull request dengan penjelasan perubahan, alasan, dan langkah untuk mengujinya.

Jangan sertakan kredensial, data pribadi, atau konfigurasi rahasia dalam commit. Jika menemukan celah keamanan, laporkan secara privat kepada pemelihara repository alih-alih mempublikasikannya sebagai issue.

## Lisensi

Project ini menggunakan lisensi **MIT**. Lihat teks lisensi MIT di [opensource.org/licenses/MIT](https://opensource.org/licenses/MIT).
