# Laravel PWA oleh KangPcode (Dhafa Nazula P)

![Lisensi](https://img.shields.io/github/license/kangpcode/laravel-pwa)
![Versi Rilis](https://img.shields.io/github/v/release/kangpcode/laravel-pwa)
![Commit Terakhir](https://img.shields.io/github/last-commit/kangpcode/laravel-pwa)
![Issues Terbuka](https://img.shields.io/github/issues/kangpcode/laravel-pwa)
![Pull Requests](https://img.shields.io/github/issues-pr/kangpcode/laravel-pwa)
![Pengamat Repo](https://img.shields.io/github/watchers/kangpcode/laravel-pwa?style=social)
![Bintang](https://img.shields.io/github/stars/kangpcode/laravel-pwa?style=social)
![Fork](https://img.shields.io/github/forks/kangpcode/laravel-pwa?style=social)

Paket Laravel ini memungkinkan Anda untuk mengubah aplikasi web Anda menjadi **Progressive Web App (PWA)** dengan mudah.

## 🔥 Tutorial Video

📺 Ikuti tutorial pemasangan Laravel PWA berikut:

[<img src="https://img.youtube.com/vi/9H-T81KQPyo/0.jpg" width="250">](https://youtu.be/9H-T81KQPyo)

▶️ Tonton juga konten Laravel lainnya di YouTube:
[<img src="https://img.youtube.com/vi/yMtsgBsqDQs/0.jpg" width="580">](https://www.youtube.com/@basecamp_tech?sub_confirmation=1)

📸 Ikuti di Instagram: [@seehai.dhafa](https://instagram.com/seehai.dhafa)  
📂 Sumber kode: [https://github.com/kangpcode/laravel-pwa](https://github.com/kangpcode/laravel-pwa)

---

## 🚀 Instalasi

Jalankan perintah berikut untuk menginstal paket (hilangkan `--dev` jika digunakan di production):

```bash
composer require --dev kangpcode/laravel-pwa
```

### Tambahkan Service Provider

Jika Anda menggunakan Laravel versi lama, tambahkan provider ke dalam `config/app.php`:

```php
kangpcode\LaravelPwa\PWAServiceProvider::class,
```

### Tambahkan Alias (Facade)

Tambahkan alias berikut ke bagian `aliases` di `config/app.php`:

```php
'LaravelPwa' => \kangpcode\LaravelPwa\LaravelPwa::class,
```

### Publikasikan Asset

```bash
php artisan laravel-pwa:publish
```

---

## ⚙️ Konfigurasi di Blade

### Tambahkan ke `<head>` file utama Anda:

```blade
<!-- PWA -->
<meta name="theme-color" content="#6777ef"/>
<link rel="apple-touch-icon" href="{{ asset('logo.png') }}">
<link rel="manifest" href="{{ asset('/manifest.json') }}">
```

### Tambahkan sebelum `</body>`:

```blade
<script src="{{ asset('/sw.js') }}"></script>
<script>
   if ("serviceWorker" in navigator) {
      navigator.serviceWorker.register("/sw.js").then(
         registration => {
            console.log("Pendaftaran service worker berhasil:", registration);
         },
         error => {
            console.error("Pendaftaran service worker gagal:", error);
         }
      );
   } else {
      console.error("Service worker tidak didukung di browser ini.");
   }
</script>
```

---

## 🧩 Tombol Instalasi Manual

Anda dapat menambahkan tombol instalasi PWA seperti ini:

```blade
<!-- Tambahkan di dalam <body> -->
<button id="pwa-install-btn" style="display:none; position: fixed; bottom: 20px; right: 20px; padding: 10px 20px; background-color: #007bff; color: white; border: none; border-radius: 8px; z-index: 1000;">
   Install Aplikasi
</button>
```

Dan tambahkan juga file JS:

```blade
<script src="{{ asset('pwa-install.js') }}"></script>
```

---

## 🛡️ Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE.md). Silakan gunakan dan kontribusikan sesuai kebutuhan.

---

## ⚠️ Catatan Penting

PWA hanya berfungsi penuh di **HTTPS**. Jika Anda menggunakan `php artisan serve`, itu cukup untuk pengembangan lokal.  
Untuk produksi, pastikan aplikasi Anda berjalan di domain dengan HTTPS.

Tonton juga video cara membuat virtual host dengan HTTPS:

[<img src="https://img.youtube.com/vi/D5IqDcHyXSQ/0.jpg" width="550">](https://youtu.be/D5IqDcHyXSQ)

---

☕ Dukung karya ini:

<a href="https://www.buymeacoffee.com/kangpcode" target="_blank">
  <img src="https://cdn.buymeacoffee.com/buttons/v2/default-red.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;">
</a>

---

🔗 **Dhafa | Laravel Dev & Creator**  
GitHub: [@kangpcode](https://github.com/kangpcode)  
Instagram: [@seehai.dhafa](https://instagram.com/seehai.dhafa)  
YouTube: [@basecamp_tech](https://youtube.com/@basecamp_tech)
