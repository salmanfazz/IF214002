
# Ide Solusi : Sistem Jahit Online
![Sistem Jahit Online](https://user-images.githubusercontent.com/49604034/161682156-d596a8c4-aebe-4a09-a364-0234a8e617b0.png)
![ERD Sistem Jahit Online](https://user-images.githubusercontent.com/49604034/161681960-e1380034-577a-403c-9d45-da97ba35e634.png)

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
- jenis_baju

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
