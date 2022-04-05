# Ide Solusi : Sistem Jahit Online
![Sistem Jahit Online]()
![ERD Sistem Jahit Online]()

## Deskripsi!
Aplikasi ini dibuat untuk mempermudah proses pemesanan pembuatan baju (jahit baju) yang biasanya dilakukan secara offline datang langsung ke tempat penjahitnya, dengan aplikasi ini user atau konsumen dapat memesan pembuatan baju (jahit baju) secara online menggunakan aplikasi tanpa harus datang langsung ke tempat penjahitnya. Fitur fitur yang ada dalam aplikasi ini antara lain :
- Pemesanan Pembuatan Baju
- List Pesanan 
- Konsultasi
- Ulasan Pembeli
## Entitas  dan Atribut :
### User / Konsumen
- /* id_user
- email
- password
- nama_user
- no_hp
- alamat

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
