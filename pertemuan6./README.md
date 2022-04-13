
# Ide Solusi : Sistem Jahit Online
![ERD New](https://user-images.githubusercontent.com/49604034/163092780-a6cad3bb-dae4-491a-ae5c-f5223e51cd66.png)

### User / Konsumen
|🔑id_user| email | password | nama_user | no_hp | alamat|
|---|---|---|---|---|---|
| 1 | salman.fazzz@gmail.com | ********** | Salman Fauzan | 089649799600 | Bandung |
| 2 | audisyzhn2002.com | ********** | Audi Syahzehan | 089649799678 | Jakarta |

### Penjahit
- /* id_penjahit
- email
- password
- nama_penjahit
- no_hp
- alamat

### Pesanan
- id_pesanan
- id_user
- id_penjahit
- id_detail_pesanan

### Detail Pesanan
- /* id_detail_pesanan
- lingkar_dada
- lingkar_pinggul
- lingkar_pinggang
- panjang_baju
- panjang_lengan
- panjang_celanan
- gambar

### Konsultasi
- /* id_konsutlasi
- id_user
- id_penjahit
- waktu_konsultasi

### Keranjang
- /* id_keranjang
- id_pesanan
- jumlah

### Pembayaran
- /* id_pembayaran
- id_keranjang
- waktu_pembayaran
- total_bayar
- status_bayar
