# Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel

Laporan: Implementasi Apache2 dan Koneksi ke Server menggunakan Putty, SSH (CMD), dan SSH (Ubuntu Desktop)

A. Cara Menginstall Apache2:

Update Daftar Paket:
Buka terminal di sistem Ubuntu dan jalankan perintah berikut untuk memperbarui daftar paket perangkat lunak.

ruby
Copy code
tiaraptri@tiaraputri:~$ sudo apt-get update
Install Apache2:
Instal dan konfigurasi Apache2 dengan menjalankan perintah berikut.

ruby
Copy code
tiaraptri@tiaraputri:~$ sudo apt install apache2
Aktifkan Apache2:
Apache2 harus diizinkan untuk memulai pada waktu boot sistem. Jalankan perintah berikut untuk mengaktifkannya.

ruby
Copy code
tiaraptri@tiaraputri:~$ sudo systemctl enable apache2
Periksa Status Apache2:
Pastikan Apache2 berjalan dengan baik dengan menjalankan perintah status.

ruby
Copy code
tiaraptri@tiaraputri:~$ sudo systemctl status apache2
Verifikasi di Browser:
Buka browser web dan ketik "localhost" di kotak alamat untuk memastikan bahwa server Apache2 telah dimulai dan menampilkan halaman indeks default.

B. Cara Menghubungkan Server ke Putty melalui Alamat IP:

Pastikan Ubuntu server dalam keadaan online.
Install Putty dari internet dan buka aplikasi.
Pada terminal Ubuntu server, ketik ip addr untuk mengetahui IP server.
Masukkan IP server ke dalam tabel "Host Name (or IP address)" di Putty.
Klik "Open" dan masukkan username serta password dari Ubuntu server.
Jika berhasil, pesan yang sama saat login ke Ubuntu server akan ditampilkan.
C. Cara Menghubungkan Server ke CMD menggunakan SSH:

Hubungkan Ubuntu server dengan CMD menggunakan SSH.
Buka CMD di Windows dan ketik ssh <nama_user@IP_user>.
Masukkan password Ubuntu.
Jika pesan selamat datang muncul pada CMD, CMD siap digunakan untuk mengontrol Ubuntu server.
D. Cara Menghubungkan Server ke Ubuntu Desktop menggunakan SSH:

Langkah pertama sama dengan CMD, yakni melalui SSH.
Tampilkan terminal pada kedua distro tersebut.
Ketik ssh <nama_user@IP_user> pada terminal dan masukkan password Ubuntu server.
Pesan selamat datang akan muncul pada terminal Ubuntu Desktop.
Dengan langkah-langkah di atas, implementasi Apache2 dan koneksi ke server melalui berbagai metode berhasil dilakukan.
