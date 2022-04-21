1. Basis data relasional dapat langsung dibangun menggunakan perintah SQL di sistem basis data seperti MySQL, dsb tanpa ada perancangan terlebih dahulu. Jelaskan apa keuntungan melakukan perancangan basis data terlebih dahulu (menggunakan ERD ataupun Class Diagram) !
2. Jelaskan bagaimana cara mentransformasikan proses bisnis sebuah organisasi menjadi struktur data di basis data !
3. Rancang solusi digital dari satu permasalahan yang ada di sekitar Anda. 

   a. Deskripsikan solusi digital tersebut dalam satu paragraf
   
   b. Buat list fitur-fitur yang ada pada solusi digital tersebut
   
   c. Buat ERD notasi Chen dari struktur data yang mewakili fitur2 di solusi digital tersebut
   
   d. Buat ERD notasi Crow Foot dari struktur data logical yang mewakili fitur2 di solusi digital tersebut, lengkap dengan keys, tipe data, dan normalisasi hingga bentuk ke 3

Jawab :
1. Keuntungan melakukan perancangan basis data terlebih dahulu baik menggunakan ERD ataupun Class Diagram adalah kita dapat mengetahui kelebihan dan kekurangan dari database yang kita buat nanti, jika database tersebut terdapat kemungkinan untuk dikembangkan lebih lanjut atau akan terus berkembang atau akan terdapat penambahan fitur-fitur pada aplikasi yang akan dibuat nanti alangkah lebih baiknya melakukan perancangan terlebih dahulu agar kita tidak perlu membuat database kembali dari awal untuk menambahkan fitur tersebut serta untuk menghindari kesalahan yang terjadi akibat database yang kita buat tersebut tidak efektif.
2. - Menentukan tujuan pembuatan database yang akan dibuat dan digunakan
   - Mengetahui data apa saja yang akan digunakan, kemudian membaginya menjadi beberapa tabel
   - Setelah membuat tabel, tentukan field field apa saja yang akan digunakan pada masing masing tabel
   - Setelah menentukan field field apa saja yang digunakan, tentukan primary key pada masing masing tabel
   - Apabila terdapat tabel yang saling berhubungan, maka dapat ditambahkan foreign key ke dalam tabel tersebut sehingga akan berelasi
   - Melakukan normalisasi hingga bentuk ke 3 untuk menghindari redudansi data
3. a. Aplikasi ini dibuat untuk mengetahui data histori karyawan yang dimulai dari data histori gaji, data histori jabatan dan data histori tempat tinggal. Dengan menggunakan aplikasi ini, maka perusahaan atau karyawan dapat mengetahui histori dari setiap karyawan yang ada dalam perusahaannya.

   b. Fitur - fitur yang akan dibuat nantinya antara lain :
      - Data Karyawan
      - Data Histori Gaji
      - Data Histori Jabatan
      - Data Histori Tempat Tinggal
 
   c. ERD Karyawan - Notasi Chen
   ![Notasi Diagram](https://user-images.githubusercontent.com/49604034/164362635-c9988dc2-0f8c-4fc8-9459-b577063d543e.jpg)
   
   d. ERD Karyawan - Notasi Crew
   
  ![ERD_Karyawan](https://user-images.githubusercontent.com/49604034/164363238-5fe6d71d-6120-4f01-880f-510b80c8cd26.jpg)
