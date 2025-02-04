# Instalasi

## Instalasi Aplikasi Server

Seperti yang disinggung sebelumnya, untuk mempermudah proses instalasi kita akan menggunakan aplikasi server Laragon. Ikuti langkah-langkah berikut.

1. Kunjungi halaman resmi Laragon pada [link berikut](https://laragon.org/download/).
2. Pada bagian **Edition**, klik **Download Laragon - Full (173 MB)** untuk mengunduh aplikasi Laragon.
3. Setelah proses download selesai, double klik pada file **laragon-wamp.exe** untuk melakukan instalasi.
4. Klik **Next** dan **Install** sampai selesai, lalu klik **Finish**.
5. Pada jendela aplikasi Laragon yang terbuka, klik Start All untuk menjalankan server web dan database.
6. Cukup klik tanda ++x++ untuk meminimalkan aplikasi Laragon.

## Mengunduh Aplikasi

Untuk mengunduh aplikasi ini, lakukan langkah-langkah berikut:

1. Kunjungi halaman release aplikasi pada [link berikut](https://github.com/masipnu/apg/releases/tag/v1.0).
2. Unduh kode sumber dalam format ZIP dengan klik `Source code (zip)` pada bagian Assets.
3. Anda akan mendapatkan file `apg-1.0.zip`.
4. Ekstrak file tersebut pada direktori `C:\laragon\www`.
5. Anda akan mendapati direktori `apg-01`, silakan rename menjadi `apg`.

## Instalasi Database

Karena aplikasi ini bekerja menggunakan database, maka kita perlu mengatur databasenya terlebih dahulu sebelum dijalankan.

1. Buka aplikasi Laragon.
    ![laragon]
2. Klik `Database` untuk membuka aplikasi manajemen database Heidi SQL.
    ![heidi]
3. Biarkan bagian password (kosong), lalu klik **Open**.
    ![open]
4. Saat jendela Heidi SQL terbuka, klik menu `File` > `Run SQL file`, lalu arahkan ke file `apg.sql` yang berada di direktori `C:laragon\www\apg\database` dan klik **Open**. Jika ada peringatan, klik **Yes**.
5. Selama tidak ada pesan `Error`, berarti database sudah tersedia.
6. Tekan tombol ++F5++ pada jendela Heidi SQL untuk me-refresh database, maka Anda akan menemukan database `apg` lengkap dengan struktur tabel beserta contoh datanya.
7. Sekarang Anda bisa menutup aplikasi Heidi SQL dan meminimalkan Laragon.

## Konfigurasi Aplikasi

Setelah mengatur database, kita perlu melakukan konfigurasi database pada aplikasi APG. Ikuti langkah-langkah berikut.

1. Buka file `config.php` pada direktori `C:\laragon\www\apg\library` dengan teks editor, seperti Visual Studio Code atau Notepad.
2. Atur konfigurasi user dan password database pada baris berikut.

```php
<?php
$host = "localhost";
$user = "root";
$pass = "";
$db = "apg";

$con = mysqli_connect($host, $user, $pass, $db);

if (mysqli_connect_errno()) {
     echo "Koneksi gagal! : " . mysqli_connect_error();
}
?>
```

3. Karena pada user root tidak perlu memakai password, maka saya rubah `$user = "root";` menjadi `$user = "";`.
4. Cukup ini saja dan APPASI siap dijalankan.


[def]: images/open.png