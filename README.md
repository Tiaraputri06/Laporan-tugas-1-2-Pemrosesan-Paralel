# Tiara-Putri-Amanda_Laporan-Apache2, Wordpress, Nginx, Tableau-Pemrosesan-Paralel
# Cara Menginstall Apache, Wordpress, Nginx, Tableau Desktop Menggunakan Ubuntu Server
# Daftar Isi
- #[Cara Menginstall Apache2 dan Cara Remote Server]
- [Cara Menginstall Wordpress]
- [Cara Menginstall Nginx]
- [Cara Menginstall Tableau Desktop Dari Windows]
# Cara Menginstall Apache2 dan Cara Remote Server
## Proses Instalasi Apache2
Buka terminal di sistem Ubuntu. Terminal adalah antarmuka teks ke komputer, yang akan digunakan untuk menjalankan semua perintah.
1. perbarui daftar paket perangkat lunak.
   ```
   sudo pembaruan apt-get
2. Langkah selanjutnya dalam menyiapkan tumpukan LAMP adalah menginstal dan mengkonfigurasi Apache2, server web. Jalankan perintah di bawah ini untuk menginstal Apache 2 di Ubuntu 20.04.
   ```
   sudo apt install apache2
3. Apache2 harus diizinkan untuk memulai pada waktu boot sistem dan memulai layanan untuk memverifikasi statusnya juga.
   ```
   sudo systemctl aktifkan apache2
   sudo systemctl status apache2
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/738c68d5-6dab-43e2-acdb-4618e7a009d6)

4. Buka browser web, dan ketik localhost di kotak alamat untuk memverifikasi bahwa  server Apache  telah dimulai.
Jika server web Apache2 berjalan, maka akan menampilkan halaman indeks default Apache2.
![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/d95d7d1a-3993-49f2-aa5a-4f478f66d4f0)

## Proses menghubungkan server ke putty melalui alamat IP
- Pastikan ubuntu server dalam keadaan “online”. Install putty dari internet dan lanjutkan hingga tampilan awal putty.
- Ketik pada terminal ubuntu server “ip addr” untuk mengetahui IP dari ubuntu server. IP tadi ketik kembali dalam tabel “Host Name (or IP address) ”.
  
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/eeec8cd3-f533-4194-ae24-0651cc088a57)
- Klik “Open” dan masukkan username beserta password dari ubuntu servernya sendiri.
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/7cd0ff60-3aec-4057-b953-79c9383c6fb9)

- jika berhasil, akan tampil pesan yang sama saat login ke ubuntu server.
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/c9bc9501-dd3f-4d19-924b-db6bfe658702)

## Cara menghubungkan server ke CMD menggunakan SSH
1. hubungkan ubuntu server dengan CMD menggunakan ssh. Buka CMD di windows, kemudian ketikkan “ssh <nama_user@IP_user>”.
2. Masukkan password ubuntu. Jika muncul pesan selamat datang pada CMD, maka CMD siap digunakan untuk mengontrol ubuntu server.
   ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/de4ac4f0-6e96-400c-9ff0-4919e6227ad7)

# Cara Menginstall Wordpress
## Proses Instalasi MySQL
1. Jalankan perintah berikut di terminal untuk melakukan ini
   ```
   sudo apt install mysql-server
2. Sangat disarankan agar menjalankan program keamanan setelah server database diinstal untuk menghapus pengaturan default yang tidak aman dan melindungi database.
   ```
   sudo mysql_secure_installation
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/a655b965-5bfe-4aa7-9804-dfcbd26fa93d)

Anda akan diminta untuk menginstal  plugin validasi_password  . Jadi, ketik Y/Ya, lalu tekan  Enter  dan terakhir pilih kekuatan kata sandi default. 
Untuk menjawab pertanyaan yang tersisa, tekan Y dan tekan  tombol ENTER  untuk setiap pertanyaan. 

3. Perintah ini juga akan memungkinkan MySQL untuk memulai saat boot.
   ```
   sudo systemctl aktifkan mysql
   sudo systemctl status mysql
## Proses Instalasi PHP
WordPress adalah CMS berbasis PHP. Disini membutuhkan PHP untuk memproses konten dinamis di situs WordPress.
1. Install PHP
   ```
   sudo apt install php libapache2-mod-php php-mysql
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/e9dfa534-cf10-45f8-97a8-a47afa586912)

2. ekstensi PHP, yang perlu di instal secara manual.
   ```
   sudo apt install php-curl php-gd php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/bdde53a3-d138-4418-a884-efa0e7611aab)
  
3. Mencek versi PHP
   ```
   php -v
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/c138aabd-8d5c-40e6-9bca-9d900c52d812)

4. Setelah PHP diinstal dan ekstensi apa pun yang diperlukan telah diinstal, Apache harus di-restart untuk memuat ekstensi baru.
   ```
   sudo systemctl restart apache2

## Proses Installasi Wordpress
Setelah kita menyiapkan lingkungan LAMP, kita dapat mulai menginstal WordPress
1. Pertama, kita akan mengunduh file instalasi WordPress dan menempatkannya di direktori root server web default /var/www/html.
   ```
   cd /var/www/html
2. Sekarang unduh instalasi WordPress terbaru dengan perintah berikut.
   ```
   sudo wget -c http://wordpress.org/latest.tar.gz
3. Ekstrak filenya
   ```
   sudo tar -xzvf terbaru.tar.gz
   ls -l
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/dd3519e7-28e8-428b-a7e4-5409a21785d2)

  File WordPress yang diekstrak sekarang akan ditempatkan di direktori WordPress di lokasi berikut di server Anda. /var/www/html/wordpress Pengguna server web Anda harus memiliki file-file ini. 

  4. Disini menggunakan Apache sebagai server web. Apache berjalan di Ubuntu 20.04. Perintah berikut akan memungkinkan Anda mengubah pemilik file-file ini dan mengatur izin yang sesuai
     ```
     sudo chown -R www-data:www-data /var/www/html/wordpress
  5. Membuat Database Untuk Wordpress
     ```
     sudo mysql -u root -p

    Lalu buatlah sebuah database, Contoh :
    ```
    CREATE DATABASE tiaraptri_db;
    CREATE USER tiaraputri_user@localhost IDENTIFIED BY 'password';
    GRANT ALL PRIVILEGES ON tiara_db.* TO tiaraptri_user@localhost;
    FLUSH PRIVILEGES;
    exit;
  6. Izinkan izin yang dapat dieksekusi diberikan ke folder WordPress
     ```
     sudo chmod -R 777 wordpress
  7. Konfigurasikan WordPress
     ```
     cd wordpress/
     mv wp-config-sample.php wp-config.php
     nano wp-config.php
     
   Ubahlah pada baris define( 'DB_NAME', 'Nama Database' ); dan diganti sampai kebawah sesuai perintahnya, lalu simpan file CTRL + X

  8. Setelah selesai melakukannya, Anda dapat mengakses halaman WordPress Anda untuk menyelesaikan instalasi. Buka browser dan buka
     ```
     https://localhost/wordpress/
     
  Layar selanjutnya akan terbuka. Klik Lanjutkan untuk memilih Bahasa
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/42dd9039-be20-4c24-83d7-1e79d4ab4d57)
  
  WordPress sekarang akan berhasil diinstal. Anda dapat masuk ke dasbor admin Anda dengan informasi yang telah diatur sebelumnya. 
  Setelah berhasil login, halaman dashboard WordPress akan menyambut Anda.
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/b2ea006d-3be8-43cd-b08e-91467b7955af)

  # Cara Instalasi Nginx
  1. Update terlebih dahulu sistem ubuntu server dengan perintah
     ```
     sudo apt update
  2. Install nginx dengan perintah berikut
     ```
     sudo apt install nginx
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/d83c2cfe-a1e9-4e6e-ab53-edbb70f393ca)
  
  3. Mengecek Versi Nginx
     ```
     nginx -v
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/5ee82b7d-ee76-491f-a4ee-2cc1a11a1288)

  4. Selanjutnya pengecekan status dari nginx
     ```
     sudo systemctl status nginx
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/e1fb7db4-debd-4b58-b85c-7852dedc95d3)

  5. Pengecekan diweb browser dengan mengetik ip diweb
     ```
     https://localhost/index.nginx-debian.html/ (localhost diganti dengan ip)
  ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/e287bb4f-6f00-4d43-ab95-2fa36bb0bb5e)

  # Cara Menginstal Tableau Dekstop dari Windows
  1. Langkah pertama untuk menginstal tableau yaitu cari tableau di chrom kemudian pilih tableau public
     ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/20cd276c-8b33-4411-b37e-256e63d42cd7)
  2. Selanjutnya Download Tableau tersebut
    ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/7927b12b-b1cb-4929-8279-02b5a73916c1)
  3. Setelah terinstal masuk ke tableau dan masukan data untuk login ke tableau
     ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/ea40169a-42fc-4471-9e52-1afb611247ba)
  4. Setelah itu kita disambut di layar tableau yang sudah login seperti gambar dibawah ini
     ![image](https://github.com/Tiaraputri06/Tiara-Putri-Amanda_Laporan-tugas-1-2-Pemrosesan-Paralel/assets/150508674/dd9e0161-93b6-4086-952a-3a306329cbf7)

 







  
 
 






  










  






    
    
    












   


