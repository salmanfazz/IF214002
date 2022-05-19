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
CREATE TABLE `user` (
  `id_user` int(10) NOT NULL AUTO_INCREMENT,
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
  `id_user` int(10) DEFAULT NULL,
  `id_penjahit` int(10) DEFAULT NULL,
  `id_detail_pesanan` int(10) DEFAULT NULL,
  PRIMARY KEY (`id_pesanan`),
  KEY `id_user` (`id_user`),
  KEY `id_penjahit` (`id_penjahit`),
  KEY `id_detail_pesanan` (`id_detail_pesanan`),
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
  PRIMARY KEY (`id_pembayaran`),
  KEY `id_keranjang` (`id_keranjang`),
)
```
### Konsultasi
```sql
CREATE TABLE `konsultasi` (
  `id_konsultasi` int(10) NOT NULL AUTO_INCREMENT,
  `id_user` int(10) DEFAULT NULL,
  `id_penjahit` int(10) DEFAULT NULL,
  `waktu_konsultasi` datetime DEFAULT NULL,
  PRIMARY KEY (`id_konsultasi`),
  KEY `id_user` (`id_user`),
  KEY `id_penjahit` (`id_penjahit`),
)
```
### Keranjang
```sql
CREATE TABLE `keranjang` (
  `id_keranjang` int(10) NOT NULL AUTO_INCREMENT,
  `id_pesanan` int(10) DEFAULT NULL,
  `jumlah` int(10) DEFAULT NULL,
  PRIMARY KEY (`id_keranjang`),
  KEY `id_pesanan` (`id_pesanan`),
)
```
# DML
# DQL
