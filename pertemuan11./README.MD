# DDL
## Create Table
### Penjahit
```sql
CREATE TABLE `penjahit` (
  `id_penjahit` int(10) NOT NULL AUTO_INCREMENT,
  `email` varchar(100) DEFAULT NULL,  
  `password` varchar(100) DEFAULT NULL,
  `nama` varchar(100) DEFAULT NULL,
  `jenis_kelamin` enum('Laki-Laki','Perempuan') DEFAULT NULL,
  `no_hp` varchar(20) DEFAULT NULL,
  `alamat` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`id_penjahit`)
)
```
### User
```sql
CREATE TABLE `konsumen` (
  `id_konsumen` int(10) NOT NULL AUTO_INCREMENT,
  `email` varchar(100) DEFAULT NULL,
  `password` varchar(100) DEFAULT NULL,
  `nama` varchar(100) DEFAULT NULL,
  `jenis_kelamin` enum('Laki-Laki','Perempuan') DEFAULT NULL,
  `no_hp` varchar(20) DEFAULT NULL,
  `alamat` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`id_user`)
)
```
### Pesanan
```sql
CREATE TABLE `pesanan` (
  `id_pesanan` int(10) NOT NULL AUTO_INCREMENT,
  `id_konsumen` int(10) DEFAULT NULL,
  `id_penjahit` int(10) DEFAULT NULL,
  `id_detail_pesanan` int(10) DEFAULT NULL,
  PRIMARY KEY (`id_pesanan`)
)
```

### Detail Pesanan
```sql
CREATE TABLE `detail_pesanan` (
  `id_detail_pesanan` int(10) NOT NULL AUTO_INCREMENT,
  `lingkar_dada` varchar(10) DEFAULT NULL,
  `lingkar_pinggul` varchar(10) DEFAULT NULL,
  `lingkar_pinggang` varchar(10) DEFAULT NULL,
  `panjang_baju` varchar(10) DEFAULT NULL,
  `panjang_lengan` varchar(10) DEFAULT NULL,
  `panjang_celana` varchar(10) DEFAULT NULL,
  `keterangan`. varchar(100) DEFAULT NULL,
  `gambar` text,
  PRIMARY KEY (`id_detail_pesanan`)
)
```
### Pembayaran
```sql
CREATE TABLE `pembayaran` (
  `id_pembayaran` int(10) NOT NULL AUTO_INCREMENT,
  `id_keranjang` int(10) DEFAULT NULL,
  `waktu_pembayaran` datetime DEFAULT NULL,
  `total_bayar` varchar(100) DEFAULT NULL,
  `status_bayar` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`id_pembayaran`)
)
```
### Konsultasi
```sql
CREATE TABLE `konsultasi` (
  `id_konsultasi` int(10) NOT NULL AUTO_INCREMENT,
  `id_konsumen` int(10) DEFAULT NULL,
  `id_penjahit` int(10) DEFAULT NULL,
  `waktu_konsultasi` datetime DEFAULT NULL,
  PRIMARY KEY (`id_konsultasi`)
)
```
### Keranjang
```sql
CREATE TABLE `keranjang` (
  `id_keranjang` int(10) NOT NULL AUTO_INCREMENT,
  `id_pesanan` int(10) DEFAULT NULL,
  `jumlah` int(10) DEFAULT NULL,
  PRIMARY KEY (`id_keranjang`)
)
```
# DML
## INSERT TABLE
### Penjahit
```sql
INSERT INTO penjahit(id_penjahit,email,password,nama,no_hp,alamat) VALUES
('1','salman.fazzz@gmail.com','da3908a30555b982d4a93bbff0a65ea21b64442a','Salman Fauzan Fahri Aulia','089649799600','Komp. Permata Kopo Blok C67')
```
### User/Konsumen
```sql
INSERT INTO user(id_konsumen,email,password,nama,no_hp,alamat) VALUES
('1','audisyzhn2002@gmail.com','da3908a30555b982d4a93bbff0a65ea21b64442a','Audi Syahzehan','089649799678','Jl. Terusan Buah Batu No. 146')
```
### Pesanan
```sql
INSERT INTO pesanan(id_pesanan,id_konsumen,id_penjahit,id_detail_pesanan) VALUES
('1','1','1','1')
```
### Detail Pesanan
```sql
INSERT INTO detail_pesanan(id_detail_pesanan,lingkar_dada,lingkar_pinggul,lingkar_pinggang,panjang_baju,panjang_lengan,panjang_celana,keterangan,gambar) VALUES
('1','90','','80','50','56','50','Seifuku','/storage/emulated/0/Download/seifuku.jpg')
```
### Keranjang
```sql
INSERT INTO keranjang(id_keranjang,id_pesanan,jumlah) VALUES
('1','1','1')
```
### Pembayaran
```sql
INSERT INTO pembayaran(id_pembayaran,id_keranjang,waktu_pembayaran,total_bayar,status_bayar) VALUES
('1','1','2022-04-12 10:40:27','300000','SUKSES')
```
### Konsultasi
```sql
INSERT INTO konsultasi(id_konsultasi,id_konsumen,id_penjahit,waktu_konsultasi) VALUES
('1','1','1','2022-04-12 10:20:27')
```
# DQL
