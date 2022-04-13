
# Normalisasi
![ERD New](https://user-images.githubusercontent.com/49604034/163098378-8df244c5-8c0e-410b-b987-822a064a433e.png)

### User / Konsumen
|🔑id_user| email | password | nama_user | no_hp | alamat |
|---|---|---|---|---|---|
| 1 | salman.fazzz@gmail.com | ********** | Salman Fauzan | 089649799600 | Komp. Permata Kopo Blok C 67 |
| 2 | audisyzhn2002.com | ********** | Audi Syahzehan | 089649799678 | Jl. Terusan Buah Batu No.146 |

### Penjahit
|🔑id_penjahit| email | password | nama_penjahit | no_hp | alamat |
|---|---|---|---|---|---|
| 1 | ammar14082002@gmail.com | ********** | Ammar Taradifa | 089649799000 | Komp. Cikoneng Prima Estate No 5 |
| 2 | arsya777.com | ********** | Arsya Alifian | 089649799777 | Jl. Raya Binong  No. 1 |

### Pesanan
|🔑id_pesanan| id_user | id_penjahit | id_detail_pesanan |
|---|---|---|---|
| 1 | 1 | 1 | 1 |
| 2 | 2 | 2 | 2 |

### Detail Pesanan
|🔑id_detail_pesanan| lingkar_dada | lingkar_pinggul | lingkar_pinggang | panjang_baju | panjang_lengan | panjang_celana | keterangan | gambar |
|---|---|---|---|---|---|---|---|---|
| 1 | 90 | - | 80 | 50 | 56 | 50 | Seifuku | /storage/emulated/0/Download/seifuku.jpg |
| 2 | 100 | - | 88 | 120 | 30 | - | Summer Dress | /storage/emulated/0/Download/summerdress.jpg |

### Konsultasi
|🔑id_konsultasi| id_user | id_penjahit | waktu_konsultasi |
|---|---|---|---|
| 1 | 1 | 1 | 2022-04-12 10:20:27 |
| 2 | 2 | 2 | 2022-04-13 10:29:27 |

### Keranjang
|🔑id_keranjang| id_pesanan | jumlah |
|---|---|---|
| 1 | 1 | 1 |
| 2 | 2 | 1 |

### Pembayaran
|🔑id_pembayaran| id_keranjang | waktu_pembayaran | total_bayar | status_bayar |
|---|---|---|---|---|
| 1 | 1 | 2022-04-12 10:40:27 | 300000 | SUKSES |
| 2 | 2 | 2022-04-13 10:49:27 | 150000 | PENDING |
