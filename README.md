# Laporan Praktikum Framework Lanjutan - CodeIgniter 4


---

## Modul 1: Persiapan Environment
Pada modul ini, dilakukan instalasi dan konfigurasi dasar CodeIgniter 4 agar dapat berjalan di lingkungan lokal menggunakan server internal Spark.

* **Konfigurasi `.env`**: Mengubah `CI_ENVIRONMENT` menjadi `development` untuk mengaktifkan fitur *debug* dan mengatur koneksi database MySQL menggunakan host `127.0.0.1` guna menghindari kendala *resolve* pada sistem Linux.
* **Base URL**: Mengatur `app.baseURL` secara eksplisit ke `http://localhost:8080/`.

> **Screenshot Konfigurasi Environment:**
> ![Screenshot konfigurasi](<img width="1366" height="768" alt="Screenshot at 2026-04-15 11-21-35" src="https://github.com/user-attachments/assets/a3b4b023-4032-47e8-b203-378513977f5b" />
)
<img width="1366" height="768" alt="Screenshot at 2026-04-15 11-22-31" src="https://github.com/user-attachments/assets/53c6add2-06b3-4ae9-9d7d-e40c3f56e308" />

---

## Modul 2: Layout dan Komponen (View Cell)
Implementasi sistem *templating* yang efisien untuk menjaga konsistensi tampilan aplikasi.

* **Render Section**: Menggunakan fitur `renderSection` untuk memisahkan konten utama dengan layout dasar (`header`, `footer`, dan `navbar`).
* **View Cell**: Membuat komponen `RecentPosts` di `app/Cells/`. Komponen ini bertugas mengambil data artikel terbaru secara independen dari database dan menampilkannya di sidebar tanpa harus menulis ulang logika di setiap Controller.

> **Screenshot Tampilan Utama & Sidebar:**
> ![Screenshot Layout]([<img width="1366" height="768" alt="Screenshot at 2026-04-15 11-28-23" src="https://github.com/user-attachments/assets/b8641514-c169-441b-95dd-615a002e8ccd" />
])

---

## Modul 3: Database dan CRUD
Menghubungkan aplikasi dengan database `lab_ci4` dan membangun fungsi operasional data (Create, Read, Update, Delete).

* **Model**: Membuat `ArtikelModel` yang merepresentasikan tabel `artikel`.
* **Controller**: Membangun Controller `Artikel.php` dengan logika:
    * `index()`: Menampilkan daftar artikel.
    * `add()` & `store()`: Menangani input artikel baru.
    * `view()`: Menampilkan detail artikel berdasarkan *slug*.
* **Routing**: Mengonfigurasi rute di `Routes.php` dengan pola *no-leading-slash* agar rute lebih fleksibel dan kompatibel di lingkungan CLI maupun Web.

> **Screenshot Operasi CRUD:**
> ![Screenshot CRUD]([<img width="1366" height="768" alt="Screenshot at 2026-04-15 11-09-31" src="https://github.com/user-attachments/assets/b6588f88-8c1a-4d05-a8ca-1d83627110b4" />
])

---

## Modul 4: Autentikasi (Modul Login)
Membangun sistem keamanan untuk membatasi akses user ke fitur-fitur tertentu.

* **Tabel User**: Membuat tabel `user` dengan skema keamanan password menggunakan `BCRYPT` (hash).
* **Session**: Menggunakan library `Session` bawaan CodeIgniter 4 untuk menyimpan data login user (`user_id`, `username`, dan status `logged_in`).
* **Logic Auth**:
    * `User::auth()`: Memverifikasi kredensial menggunakan `password_verify`.
    * `User::logout()`: Menghancurkan session untuk keluar dari sistem.

> **Screenshot Sistem Autentikasi:**
> ![Screenshot Login]([<img width="1366" height="768" alt="Screenshot at 2026-04-15 11-09-17" src="https://github.com/user-attachments/assets/5614f4b0-8a96-4788-b64b-3dc43a618b10" />
])

---
*© 2026 - Laporan Praktikum Mandiri*
