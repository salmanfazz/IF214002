# 1. Rancang solusi digital dari permasalahan yang teman-teman anggap penting untuk diselesaikan
Aplikasi ini dibuat untuk mempermudah proses pemesanan pembuatan baju (jahit baju) yang biasanya dilakukan secara offline datang langsung ke tempat penjahitnya, dengan aplikasi ini user atau konsumen dapat memesan pembuatan baju (jahit baju) secara online menggunakan aplikasi tanpa harus datang langsung ke tempat penjahitnya. Fitur fitur yang ada dalam aplikasi ini antara lain :
# 2. Tentukan fitur-fitur utama dari solusi digital tersebut
- Service (Pemesanan Baju)
- Payment (Pembayaran)
- History (List Pesanan)
# 3. Buat rancangan basis datanya dalam bentuk ER diagram
![ERD NEW](https://user-images.githubusercontent.com/49604034/176567490-ab43bb2f-d0e9-424d-b6fc-507e5deae400.png)
# 4. Buat model fisik dari basis datanya dalam bentuk query SQL yang meliputi: 1) data definition language untuk pembuatan tabel, 2) data manipulation language untuk contoh data awal, 3) data query language untuk analisis / business intelligence
## DDL
### User
```sql
CREATE TABLE `users` (
  `id_users` int(10) NOT NULL AUTO_INCREMENT,
  `email` varchar(100) DEFAULT NULL,
  `password` varchar(100) DEFAULT NULL,
  `nama` varchar(100) DEFAULT NULL,
  `jenis_kelamin` enum('Laki-Laki','Perempuan') DEFAULT NULL,
  `alamat` varchar(100) DEFAULT NULL,
  `no_hp` varchar(20) DEFAULT NULL,
  `roles` enum('konsumen', 'penjahit'),
  PRIMARY KEY (`id_users`)
)
```
### Pesanan
```sql
CREATE TABLE `pesanans` (
  `id_pesanans` int(10) NOT NULL AUTO_INCREMENT,
  `id_users_1` int(10) DEFAULT NULL,
  `id_users_2` int(10) DEFAULT NULL,
  `id_detail_pesanans` int(10) DEFAULT NULL,
  PRIMARY KEY (`id_pesanans`)
)
```

### Detail Pesanan
```sql
CREATE TABLE `detail_pesanans`(  
  `id_detail_pesanans` INT(10) NOT NULL AUTO_INCREMENT,
  `lingkar_dada` VARCHAR(100),
  `lingkar_pinggul` VARCHAR(100),
  `lingkar_pinggang` VARCHAR(100),
  `panjang_baju` VARCHAR(100),
  `panjang_lengan` VARCHAR(100),
  `panjang_celana` VARCHAR(100),
  `keterangan` VARCHAR(100),
  `gambar` TEXT,
  PRIMARY KEY (`id_detail_pesanans`)
);
```
### Pembayaran
```sql
CREATE TABLE `pembayarans` (
  `id_pembayarans` int(10) NOT NULL AUTO_INCREMENT,
  `id_pesanans` int(10) DEFAULT NULL,
  `waktu_bayar` datetime DEFAULT NULL,
  `total_bayar` varchar(100) DEFAULT NULL,
  `status` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`id_pembayarans`)
)
```
### Alter Table
```sql
ALTER TABLE pesanans  
  ADD FOREIGN KEY (id_users_2) REFERENCES users(id_users);
ALTER TABLE pesanans
  ADD FOREIGN KEY (id_users_1) REFERENCES users(id_users);
ALTER TABLE pesanans  
  ADD FOREIGN KEY (id_detail_pesanans) REFERENCES detail_pesanans(id_detail_pesanans);
ALTER TABLE pembayarans 
  ADD FOREIGN KEY (id_pesanans) REFERENCES pesanans(id_pesanans);
  ```
## DML
### Users
```sql
INSERT INTO users(id_users,email,password,nama,alamat,no_hp,roles) VALUES
('1','salman.fazzz@gmail.com','123456','Salman Fauzan Fahri Aulia','089649799600','Bandung','konsumen')
('2','ammartaradia@gmail.com','123456','Ammar Taradifa','089649799601','Bandung','konsumen')
('3','arsyaalifian@gmail.com','123456','Arsya Alifian Widiatmoko','089649799602','Bandung','konsumen')
('4','audisyzhn2002@gmail.com','123456','Audi Syahzehan','089649799654','Bandung','penjahit')
('5','karenina@gmail.com','123456','Karenina Casandra Rahmat','089649799601','089649799655','penjahit')
('6','nurcahyaningsih@gmail.com','123456','Nur Cahya Ningsih','089649799656','Bandung','penjahit')
```
### Pesanans
```sql
INSERT INTO pesanans(id_pesanans,id_users_1,id_users_1,id_detail_pesanans) VALUES
('1','1','4','1')
('2','2','5','2')
('3','3','6','3')
```
### Detail Pesanans
```sql
INSERT INTO detail_pesanans(id_detail_pesanans,lingkar_dada,lingkar_pinggul,lingkar_pinggang,panjang_baju,panjang_lengan,panjang_celana,keterangan,gambar) VALUES
('1','90','','80','50','56','50','Seifuku','/storage/emulated/0/Download/seifuku.jpg')
('2','120','','110','80','86','80','Seifuku','/storage/emulated/0/Download/seragam.jpg')
('3','90','','80','50','56','50','Seifuku','/storage/emulated/0/Download/jas.jpg')
```

### Pembayaran
```sql
INSERT INTO pembayarans(id_pembayarans,id_pesanans,waktu_bayar,total_bayar,status) VALUES
('1','1','2022-04-12 10:40:27','300000','Selesai')
('1','1','2022-04-12 10:40:27','450000','Belum Dibayar')
('1','1','2022-04-12 10:40:27','600000','Selesai')
```
## DQL
### Menampilan Pesanan dengan Status Selesai dari Konsumen 1
```sql
SELECT `pesanans`.`id_pesanans`, `users`.`nama`, `pesanans`.`id_users_1`, `pesanans`.`id_users_2`, `detail_pesanans`.`lingkar_dada`, `detail_pesanans`.`lingkar_pinggul`, `detail_pesanans`.`lingkar_pinggang`, `detail_pesanans`.`panjang_baju`, `detail_pesanans`.`panjang_lengan`, `detail_pesanans`.`panjang_celana`, `detail_pesanans`.`keterangan`, `detail_pesanans`.`gambar`, `pembayarans`.`waktu_bayar`, `pembayarans`.`total_bayar`, `pembayarans`.`status` 
FROM `pesanans` 
INNER JOIN `detail_pesanans` ON `detail_pesanans`.`id_detail_pesanans` = `pesanans`.`id_detail_pesanans` 
INNER JOIN `users` ON `users`.`id_users` = `pesanans`.`id_users_2` 
INNER JOIN `pembayarans` ON `pesanans`.`id_pesanans` = `pembayarans`.`id_pesanans` 
WHERE `users`.`roles` = 'penjahit' AND `pesanans`.`id_users_1` = '1'
AND `pembayarans`.`status` = 'Selesai'
```
### Menampilkan Pesanan degan Status Belum Dibayar dari Konsumen 1
```sql
SELECT `pesanans`.`id_pesanans`, `users`.`nama`, `pesanans`.`id_users_1`, `pesanans`.`id_users_2`, `detail_pesanans`.`lingkar_dada`, `detail_pesanans`.`lingkar_pinggul`, `detail_pesanans`.`lingkar_pinggang`, `detail_pesanans`.`panjang_baju`, `detail_pesanans`.`panjang_lengan`, `detail_pesanans`.`panjang_celana`, `detail_pesanans`.`keterangan`, `detail_pesanans`.`gambar`, `pembayarans`.`waktu_bayar`, `pembayarans`.`total_bayar`, `pembayarans`.`status` 
FROM `pesanans` 
INNER JOIN `detail_pesanans` ON `detail_pesanans`.`id_detail_pesanans` = `pesanans`.`id_detail_pesanans` 
INNER JOIN `users` ON `users`.`id_users` = `pesanans`.`id_users_2` 
INNER JOIN `pembayarans` ON `pesanans`.`id_pesanans` = `pembayarans`.`id_pesanans` 
WHERE `users`.`roles` = 'penjahit' AND `pesanans`.`id_users_1` = '1'
AND `pembayarans`.`status` = 'Belum Dibayar'
```
### Menampilkan Pesanan dengan Status Belum Dibayar dari Penjahit 4
```sql
SELECT `pesanans`.`id_pesanans`, `users`.`nama`, `pesanans`.`id_users_1`, `pesanans`.`id_users_2`, `detail_pesanans`.`lingkar_dada`, `detail_pesanans`.`lingkar_pinggul`, `detail_pesanans`.`lingkar_pinggang`, `detail_pesanans`.`panjang_baju`, `detail_pesanans`.`panjang_lengan`, `detail_pesanans`.`panjang_celana`, `detail_pesanans`.`keterangan`, `detail_pesanans`.`gambar`, `pembayarans`.`waktu_bayar`, `pembayarans`.`total_bayar`, `pembayarans`.`status` 
FROM `pesanans` 
INNER JOIN `detail_pesanans` ON `detail_pesanans`.`id_detail_pesanans` = `pesanans`.`id_detail_pesanans` 
INNER JOIN `users` ON `users`.`id_users` = `pesanans`.`id_users_1` 
INNER JOIN `pembayarans` ON `pesanans`.`id_pesanans` = `pembayarans`.`id_pesanans` 
WHERE `users`.`roles` = 'konsumen' AND `pesanans`.`id_users_2` = '4'
AND `pembayarans`.`status` = 'Belum Dibayar'
```
### Menampilkan Pesanan dengan Status Selesai dari Penjahit 4
```sql
SELECT `pesanans`.`id_pesanans`, `users`.`nama`, `pesanans`.`id_users_1`, `pesanans`.`id_users_2`, `detail_pesanans`.`lingkar_dada`, `detail_pesanans`.`lingkar_pinggul`, `detail_pesanans`.`lingkar_pinggang`, `detail_pesanans`.`panjang_baju`, `detail_pesanans`.`panjang_lengan`, `detail_pesanans`.`panjang_celana`, `detail_pesanans`.`keterangan`, `detail_pesanans`.`gambar`, `pembayarans`.`waktu_bayar`, `pembayarans`.`total_bayar`, `pembayarans`.`status` 
FROM `pesanans` 
INNER JOIN `detail_pesanans` ON `detail_pesanans`.`id_detail_pesanans` = `pesanans`.`id_detail_pesanans` 
INNER JOIN `users` ON `users`.`id_users` = `pesanans`.`id_users_1` 
INNER JOIN `pembayarans` ON `pesanans`.`id_pesanans` = `pembayarans`.`id_pesanans` 
WHERE `users`.`roles` = 'konsumen' AND `pesanans`.`id_users_2` = '4'
AND `pembayarans`.`status` = 'Selesai'
```
