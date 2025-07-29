# SISTEM MANAJEMEN INVENTORI TOKO KECIL
Aplikasi sederhana untuk mencatat dan mengelola data inventori barang pada sebuah toko kecil.

## 1. Dokumentasi Teknis

### Struktur File/Kode
Aplikasi ini terdiri dari satu file Python utama, inventory_app.py, dan satu file data inventory.json yang akan dibuat secara otomatis saat aplikasi dijalankan dan data ditambahkan.
* inventory_app.py :
    * Berisi semua logika aplikasi, termasuk fungsi untuk menambah, menampilkan, mengedit, menghapus, mencari, mengekspor, dan membuat laporan barang.
  * Inventory.json
      * File ini digunakan untuk menyimpan data inventori secara persisten dalam format JSON. Setiap kali aplikasi ditutup dan dibuka kembali, data akan tetap tersedia.
   
### Library yang Digunakan
* json: Digunakan untuk membaca dan menulis data inventori ke/dari file inventory.json. Ini memastikan data tetap ada meskipun aplikasi ditutup.
* os: Digunakan untuk memeriksa keberadaan file inventory.json saat aplikasi pertama kali dijalankan atau saat memuat data.

### Diagram Alur Kerja Aplikasi
+----------------+
|     Mulai      |
+----------------+
        |
        v
+----------------+
| Muat Inventori |
| (inventory.json)|
+----------------+
        |
        v
+----------------+
|   Tampilkan    |
|      Menu      |
+----------------+
        |
        v
+----------------+
|   Pilih Opsi   |
+----------------+
        |
        |---- 1. Tambah Barang ----> +----------------+
        |                            |   Input Data   |
        |                            | (Nama, Stok, Harga) |
        |                            +----------------+
        |                                   |
        |                                   v
        |                            +----------------+
        |                            | Simpan Data    |
        |                            | ke Inventori   |
        |                            +----------------+
        |                                   |
        |                                   v
        |                            +----------------+
        |                            | Simpan Inventori|
        |                            | (inventory.json)|
        |                            +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 2. Tampilkan Daftar Barang --> +----------------+
        |                                    | Tampilkan Semua|
        |                                    | Barang         |
        |                                    +----------------+
        |                                           |
        |-------------------------------------------+
        |
        |---- 3. Edit Barang --------> +----------------+
        |                             | Pilih Barang   |
        |                             | (berdasarkan No.)|
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Input Data Baru|
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Perbarui Data  |
        |                             | di Inventori   |
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Simpan Inventori|
        |                             | (inventory.json)|
        |                             +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 4. Hapus Barang -------> +----------------+
        |                             | Pilih Barang   |
        |                             | (berdasarkan No.)|
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Konfirmasi     |
        |                             | Penghapusan    |
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Hapus Data     |
        |                             | dari Inventori |
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Simpan Inventori|
        |                             | (inventory.json)|
        |                             +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 5. Cari Barang --------> +----------------+
        |                             | Input Nama     |
        |                             | Barang Dicari  |
        |                             +----------------+
        |                                   |
        |                                   v
        |                             +----------------+
        |                             | Tampilkan Hasil|
        |                             | Pencarian      |
        |                             +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 6. Ekspor ke CSV ------> +----------------+
        |                             | Tulis Data     |
        |                             | ke inventory_report.csv |
        |                             +----------------+
        |                                   |
        |-----------------------------------+
        |
        |---- 7. Laporan Inventori ----> +----------------+
        |                               | Hitung Total   |
        |                               | Barang & Nilai |
        |                               +----------------+
        |                                     |
        |-------------------------------------+
        |
        |---- 8. Keluar -------------------> +----------------+
        |                                    |     Selesai    |
        +------------------------------------+----------------+

## 2. User manual

### Cara Menjalankan Aplikasi
1. Pastikan Python Terinstal: Anda perlu memiliki Python 3.x terinstal di komputer Anda. Anda bisa mengunduhnya dari python.org.
2. Simpan Kode: Salin kode Python yang disediakan ke dalam sebuah file dan simpan dengan nama inventory_app.py (atau nama lain dengan ekstensi .py).
3. Buka Terminal/Command Prompt: Navigasikan ke direktori tempat Anda menyimpan file inventory_app.py menggunakan terminal (Linux/macOS) atau Command Prompt/PowerShell (Windows).
4. Jalankan Aplikas: Ketik perintah berikut dan tekan Enter : python inventory_app.py
5. Aplikasi akan menampilkan menu utama di terminal.

### Contoh Input: 
* Menampilakan Daftar Barang:
    1. Pilih opsi 1 (Tampilkan Daftar Barang).
    2. Aplikasi akan menampilkan semua barang yang ada di inventori dalam bentuk tabel.
        
* Menambah Barang
    1. Pilih opsi 2 (Tambah Barang).
    2. Aplikasi akan meminta:
         * Masukkan Nama Barang: (misal: Teh Hijau)
         * Masukkan Stok Barang: (misal: 10)
         * Masukkan Harga Barang: (misal: 7000)
    3. Barang akan ditambahkan dan disimpan

### Cara Edit dan Hapus Data
* Mengedit Data Barang:
    1. Pilih opsi 3 (Edit Barang).
    2. Aplikasi akan menampilkan daftar barang dengan nomor urut.
    3. Masukkan Nomor Barang yang ingin diedit: (misal: 1 untuk barang pertama).
    4. Aplikasi akan menampilkan detail barang tersebut dan meminta input untuk nama, stok, dan harga baru.
    5. Setelah Anda memasukkan perubahan, data barang akan diperbarui.

* MengHapus Data Barang:
    1. Pilih opsi 4 (Hapus Barang).
    2. Aplikasi akan menampilkan daftar barang dengan nomor urut.
    3. Masukkan Nomor Barang yang ingin dihapus: (misal: 2 untuk barang kedua).
    4. Aplikasi akan meminta konfirmasi: Anda yakin ingin menghapus 'Nama Barang'? (ya/tidak):
           * Ketik ya dan tekan Enter untuk mengonfirmasi penghapusan.
           * Ketik tidak atau apapun selain ya untuk membatalkan.
       
### Fitur Bonus 
* Pencarian Barang:
  1. Pilih opsi 5 (Cari Barang).
  2. Masukkan Nama Barang yang dicari: (misal: Teh Melati).
  3. Aplikasi akan menampilkan semua barang yang namanya mengandung kata "Teh" (tidak peka huruf besar/kecil).

* Laporan Ringkas
  1. pilih opsi 7 (laporan Ringkas)
  2. Aplikasi akan menampilkan ringkasan seperti jumlah total barang unik, total stok, dan total nilai inventori


 ## Pengujian dan Evaluasi (Contoh Skenario)


 ### Skenario 1: Tambah dan Hapus Barang
   1. Mulai Aplikasi: Jalankan python inventory_app.py.
   2. Tampilkan Daftar Harga
       * Pilih 1
       * Pastikan "Teh Hijau" muncul dalam daftar dengan stok dan harga yang benar.
   3. Tambah Barang 1:
       * Pilih 2
       * Nama: Teh Hijau, Stok: 10, Harga: 7000.
       * Verifikasi pesan "Teh Hijau' berhasil ditambahkan.
  4. Hapus Barang 1 (Teh Hijau):
       * Pilih 4
       * Masukkan nomor 1 (untuk Teh Hijau)
       * Konfirmasi ya
       * Verifikasi pesan "Barang 'Teh Hijau' berhasil dihapus."
   5. Tampilkan Daftar Barang:
        * Pilih 1
        * Pastikan hanya "Penghapus" yang tersisa dalam daftar.
  6. Keluar: Pilih 7
  7. Jalankan Ulang Aplikasi: Jalankan python inventory_app.py lagi.
  8. Tampilkan Daftar Barang
        * Pilih 1
        * Pastikan "Teh Hijau" masih ada, menunjukkan data berhasil disimpan dan dimuat.
     
### Skenario 2: Edit Barang dan Laporan
  1. Mulai Aplikasi: Jalankan python inventory_app.py. (Pastikan ada data, jika tidak, tambahkan beberapa barang terlebih dahulu).
  2. Tambah Barang (jika inventori kosong):
        * Pilih 2. Nama: Teh Hijau, Stok: 10, Harga: 7000.
  3. Tampilkan Daftar Barang
        * Pilih 1. Catat nomor urut untuk "Teh Hijau".
  4. Edit Barang "Teh Hijau":
        * Pilih 3. Masukkan nomor urut "1".
        * Nama Baru: (kosongkan)
        * Stok Baru: 3
        * Harga Baru: (kosongkan)
  5. Tampilkan Daftar Barang:
        * Pilih 2. Pastikan "Teh Hijau" sekarang memiliki Stok 3 dan Harga 7000.
  6.  Generate Laporan:
         * Pilih 6
         * Periksa Jumlah Barang Unik, Total Stok Semua Barang, dan Total Nilai Inventori sesuai dengan data yang ada (termasuk perubahan pada "Buku").
  7. Keluar: Pilih 7
        
        
     


