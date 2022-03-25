# Ide Solusi : Sistem Pengelolaan Organisasi
![Sistem Pengelolaan Organisasi](https://user-images.githubusercontent.com/49604034/158011424-6adf05fd-890c-4627-851e-021021491393.png)
![ERD](https://user-images.githubusercontent.com/49604034/160035210-3b05543b-f903-47ef-a670-a6d3468d5b3f.PNG)

## Deskripsi!
Aplikasi ini dibuat untuk mempermudah pengurus dari sebuah organisasi untuk mendata berbagai macam kegiatan yang akan dilakukan kedepannya serta pemasukan dan pengeluaran organisasi agar menghindari penyalahgunaan dana yang telah dikumpulkan dari anggota. Fitur fitur aplikasi ini antara lain :
- Pengelolaan Jadwal Kegiatan Organisasi
- Pengelolaan Sistem Keuangan Organisasi
- Pengelolaan Data Anggota Organisasi
## Entitas  dan Atribut :
### Anggota
- /* id_anggota
- nama_anggota
- alamat_anggota
### Kegiatan
- /* id_kegiatan
- nama_kegiatan
- waktu_kegiatan
- tempat_kegiatan
- detail_kegiatan
### Pendapatan
- /* id_pendapatan
- waktu_pendapatan
- id_jenis_pendapatan
- nominal_pendapatan
### Pengeluaran
- /* id_pengeluaran
- waktu_pengeluaran
- id_jenis_pengeluaran
- nominal_pengeluaran
### Jenis Pendapatan
- /* id_jenis_pendapatan
- nama_pendapatan
### Jenis Pengeluaran
- /* id_jenis_pengeluaran
- nama_pengeluaran
### Laporan
- /* id_laporan
- nama_laporan
- id_kegiatan
