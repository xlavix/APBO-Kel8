# ERD
![ERD APBO](https://github.com/xlavix/APBO-Kel8/assets/145998330/e8d9ed5c-7882-416d-a1b3-ef61d71d8768)
## ERD Pemesanan Lapangan
## Entitas:

## Lapangan:
### id_lapangan: Identitas unik lapangan (Primary Key)
### nama_lapangan: Nama lapangan
### jenis_lapangan: Jenis lapangan (misalnya futsal, badminton)
### kapasitas: Kapasitas lapangan (jumlah orang)
### harga_sewa: Harga sewa lapangan per jam

## Admin:
### id_admin: Identitas unik admin (Primary Key)
### nama_admin: Nama admin

## Pelanggan:
### id_pelanggan: Identitas unik pelanggan (Primary Key)
### nama_pelanggan: Nama pelanggan
### no_telepon: Nomor telepon pelanggan
### email: Alamat email pelanggan (opsional)

## Reservasi:
### id_reservasi: Identitas unik reservasi (Primary Key)
### id_lapangan: Identitas lapangan yang dipesan (Foreign Key mengacu pada Lapangan.id_lapangan)
### id_pelanggan: Identitas pelanggan yang memesan (Foreign Key mengacu pada Pelanggan.id_pelanggan)
### tanggal_reservasi: Tanggal reservasi
### jam_mulai: Jam mulai reservasi
### jam_berakhir: Jam berakhir reservasi
### status_reservasi: Status reservasi (misalnya tertunda, dikonfirmasi, dibatalkan)
### catatan: Catatan tambahan tentang reservasi

## Pembayaran:
### id_transaksi: Identitas unik transaksi pembayaran (Primary Key)
### id_reservasi: Identitas reservasi yang dibayarkan (Foreign Key mengacu pada Reservasi.id_reservasi)
### metode: Metode pembayaran (misalnya tunai, transfer bank)
### status: Status pembayaran (misalnya terbayar, belum terbayar)

## Kardinalitas
### Lapangan:N Reservasi: Satu lapangan dapat memiliki banyak reservasi, tetapi satu reservasi hanya dapat milik satu lapangan.
### Pelanggan:N Reservasi: Satu pelanggan dapat memiliki banyak reservasi, tetapi satu reservasi hanya dapat milik satu pelanggan.
### Admin:N Reservasi: Satu admin dapat memproses banyak reservasi, tetapi satu reservasi hanya dapat diproses oleh satu admin.
### Reservasi:1 Pembayaran: Satu reservasi hanya dapat memiliki satu pembayaran, tetapi satu pembayaran dapat digunakan untuk membayar banyak reservasi.


# CLASS DIAGRAM
![Class DIagram](https://github.com/xlavix/APBO-Kel8/assets/145998330/f195d008-86f8-46cb-8139-acd17a0b01ab)

## Pelanggan: Mewakili pelanggan yang menggunakan sistem untuk memesan lapangan futsal.
### Atribut:
### id_pelanggan: Pengenal unik untuk pelanggan (Kunci Utama)
### nama_pelanggan: Nama pelanggan
### no_telepon: Nomor telepon pelanggan
### email: Alamat email pelanggan (opsional)
### Metode:
### getNamaPelanggan(): Mengembalikan nama pelanggan
### getAlamat(): Mengembalikan alamat pelanggan (tidak ditampilkan dalam diagram)
### getNoTelepon(): Mengembalikan nomor telepon pelanggan
### getEmail(): Mengembalikan alamat email pelanggan
### setNamaPelanggan(nama_pelanggan: String): Mengatur nama pelanggan
### setAlamat(alamat: String): Mengatur alamat pelanggan (tidak ditampilkan dalam diagram)
### setNoTelepon(no_telepon: String): Mengatur nomor telepon pelanggan
### setEmail(email: String): Mengatur alamat email pelanggan

## Admin: Mewakili administrator sistem yang mengelola pemesanan dan operasi lainnya.
### Atribut:
### id_admin: Pengenal unik untuk administrator (Kunci Utama)
### nama_admin: Nama administrator
### Metode:
### getNamaAdmin(): Mengembalikan nama administrator
### setNamaAdmin(nama_admin: String): Mengatur nama administrator

## Lapangan: Mewakili lapangan futsal yang tersedia untuk dipesan.
### Atribut:
### id_lapangan: Pengenal unik untuk lapangan (Kunci Utama)
### nama_lapangan: Nama lapangan
### jenis_lapangan: Jenis lapangan (misalnya, indoor, outdoor)
### kapasitas: Kapasitas lapangan (jumlah orang)
### harga_sewa: Harga sewa lapangan per jam
### Metode:
### getNamaLapangan(): Mengembalikan nama lapangan
### getJenisLapangan(): Mengembalikan jenis lapangan
### getKapasitas(): Mengembalikan kapasitas lapangan
### getHargaSewa(): Mengembalikan harga sewa lapangan
### setNamaLapangan(nama_lapangan: String): Mengatur nama lapangan
### setJenisLapangan(jenis_lapangan: String): Mengatur jenis lapangan
### setKapasitas(kapasitas: int): Mengatur kapasitas lapangan
### setHargaSewa(harga_sewa: double): Mengatur harga sewa lapangan

## Reservasi: Mewakili pemesanan yang dilakukan pelanggan untuk lapangan futsal.
### Atribut:
### id_reservasi: Pengenal unik untuk pemesanan (Kunci Utama)
### id_lapangan: Kunci asing yang merujuk pada lapangan yang dipesan (Lapangan.id_lapangan)
### id_pelanggan: Kunci asing yang merujuk pada pelanggan yang memesan (Pelanggan.id_pelanggan)
### tanggal_reservasi: Tanggal pemesanan
### jam_mulai: Jam mulai pemesanan
### jam_berakhir: Jam berakhir pemesanan
### status_reservasi: Status pemesanan (misalnya, tertunda, dikonfirmasi, dibatalkan)
### catatan: Catatan tambahan tentang pemesanan
### Metode:
### getIdPelanggan(): Mengembalikan ID pelanggan
### getIdLapangan(): Mengembalikan ID lapangan
### getTanggalReservasi(): Mengembalikan tanggal pemesanan
### getJamMulai(): Mengembalikan jam mulai pemesanan
### getJamBerakhir(): Mengembalikan jam berakhir pemesanan
### getStatusReservasi(): Mengembalikan status pemesanan
### getCatatan(): Mengembalikan catatan pemesanan
### setIdPelanggan(id_pelanggan: int): Mengatur ID pelanggan
### setIdLapangan(id_lapangan: int): Mengatur ID lapangan
### setTanggalReservasi(tanggal_reservasi: Date): Mengatur tanggal pemesanan
### setJamMulai(jam_mulai: Time): Mengatur jam mulai pemesanan
### setJamBerakhir(jam_berakhir: Time): Mengatur jam berakhir pemesanan
### setStatusReservasi(status_reservasi: String): Mengatur status reservasi saat ini.
### setCatatan(catatan: String): Mengatur catatan yang terkait dengan reservasi.


# ACTIVITY DIAGRAM
![jasa sewa lapangan (activity diagram APBO](https://github.com/xlavix/APBO-Kel8/assets/145998330/5da6d1dc-a7cf-4917-8f4c-e4f60c0fc8b2)
## Penjelasan Lebih Detail:
## Aktor:
### -Pelanggan: Orang yang ingin memesan lapangan futsal.
### -Sistem: Sistem pemesanan lapangan futsal.
### -Petugas Lapangan: Orang yang bertugas menjaga lapangan futsal.

## Aktivitas:
### -Membuka Halaman Utama: Pelanggan membuka halaman utama aplikasi pemesanan lapangan futsal.
### -Memilih Lapangan: Pelanggan memilih lapangan yang ingin dipesan dari daftar yang tersedia.
### -Memilih Tanggal dan Jam: Pelanggan memilih tanggal dan jam yang ingin dipesan untuk lapangan yang dipilih.
### -Melakukan Pembayaran: Pelanggan memilih metode pembayaran yang ingin digunakan dan menyelesaikan proses pembayaran.
### -Menerima Pembayaran: Sistem menerima pembayaran dari pelanggan dan memperbarui status pemesanan.
### -Mengirimkan Bukti Pembayaran: Sistem mengirimkan email konfirmasi pemesanan kepada pelanggan.
### -Menerima Bukti Pembayaran: Pelanggan menerima bukti pembayaran melalui email atau SMS.
### -Menggunakan Lapangan: Pelanggan datang ke lapangan pada tanggal dan jam yang dipesan dan menggunakan lapangan.
### -Selesai Menggunakan Lapangan: Pelanggan selesai menggunakan lapangan dan keluar dari lapangan.

## Alur Kerja:
### -Pelanggan membuka halaman utama aplikasi pemesanan lapangan futsal.
### -Pelanggan memilih lapangan yang ingin dipesan.
### -Pelanggan memilih tanggal dan jam yang ingin dipesan.
### -Jika lapangan tersedia, sistem akan menampilkan informasi pemesanan.
### -Pelanggan memilih metode pembayaran dan menyelesaikan proses pembayaran.
### -Sistem menerima pembayaran dari pelanggan dan memperbarui status pemesanan.
### -Sistem mengirimkan email konfirmasi pemesanan kepada pelanggan.
### -Pelanggan menerima bukti pembayaran.
### -Pelanggan datang ke lapangan pada tanggal dan jam yang dipesan.
### -Pelanggan menunjukkan bukti pemesanan kepada petugas lapangan.
### -Petugas lapangan mengizinkan pelanggan untuk menggunakan lapangan.
### -Pelanggan selesai menggunakan lapangan.
