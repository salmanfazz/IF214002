# Data Definition Language
Data Definition Language (DDL) digunakan untuk mendefinisikan, mengubah dan menghapus basis data dan objek-objek yang diperlukan, misalnya tabel, view, user, index dan sebagainya.DDL biasa digunakan oleh DBA dalam pembuatan sebuah aplikasi basis data.
## Create Table
CREATE TABLE table_name (column_name, type_data);

Digunakan untuk membuat table

Contoh :

CREATE TABLE `user` ( -> Nama Table

  `id_user` int(10) NOT NULL AUTO_INCREMENT, -> Nama Kolom = id_user, Type Data = INT Not Null Auto Increment
  
  `email` varchar(100) DEFAULT NULL, -> Nama Kolom = email, Type Data = varchar(100)
  
  `password` varchar(100) DEFAULT NULL,
  
  `nama` varchar(100) DEFAULT NULL,
  
  `jenis_kelamin` enum('Laki-Laki','Perempuan') DEFAULT NULL, -> Nama Kolom = jenis_kelamin, Type Data = Enum('Laki-Laki','Perempuan')
  
  `no_hp` varchar(20) DEFAULT NULL,
  
  PRIMARY KEY (`id_user`) -> Primary Key Table User
  
)

column_name, diisi dengan nama kolom yang akan dibuat

type_data / column_type, diisi deengan type data yang akan digunakan disertai dengan maksimal digit yang dapat diinputkan

 `id_user` int(10) NOT NULL AUTO_INCREMENT, -> Berarti Nama Kolomnya adalah id_user, Type Datanya INT dengan maksimal digit 10
 
 Kondisi type_data yang NOT NULL apabila tidak diisi pada saat akan memasukan data akan mengakibatkan error, sebaliknya type data NULL apabila tidak diisi tidak akan menyebabkan error
 
 Kondisi type_data yang AUTO INCREMENT maka secara otomatis akan terisi dengan angka yang dimulai dari 1 pada saat memasukan data pertama kali dan akan terus bertambah  setiap kita memasukan data baru
 
 PRIMARY KEY digunakan untuk menandakan kolom yang bersifat unique, dan apabila terdapat isi data yang sama dengan kolom sebelumnya akan mengakibatkan error
 
## Drop Table
DROP TABLE table_name ;

Digunakan untuk menghapus table

DROP TABLE user;

## Alter Table
ALTER TABLE table_name [alter_option ...];

Digunakan ketika akan mengubah kolom dari taable, dimulai dari menambahkan kolom baru atau menghapus kolom yang telah ada serta mengubah kolom yang telah ada

Terdapat banyak jenis contoh dari penggunaan ALTER TABLE namun pada dasarnya berikut adalah jenis contoh penggunaan alter table yang sering digunakan
- Menambahkan Foreign Key

ALTER TABLE table_name ADD CONSTRAINT key FORIEGN KEY (column_name);

Setelah membuat beberapa table dan ingin menghubungkannya dengan table lainnya maka dibutuhkan Foreign Key pada table yang akan dihubungkan

ALTER TABLE pesanan ADD FOREIGN KEY (`id_user`) REFERENCES `user`(`id_user`);

Diatas adalah contoh menambahkan foreign key id_user di table pesanan dengan id_user yang ada pada table user

- Menambahkan Kolom

ALTER TABLE table_name ADD COLUMN (column_name column_definition...)

Digunakan untuk menambahkan kolom baru pada table tertentu

ALTER TABLE user ADD COLUMN (alamat VARCHAR(100));

Diatas adalah contoh untuk menambahkan kolom alamat di table user dengan type data varchar yang berisi 100 digit

- Menghapus Kolom

ALTER TABLE table_name DROP COLUMN column_name;

Digunakan untuk menghapus kolom pada table tertentu

ALTER TABLE user DROP COLUMN alamat;

Diatas adalah contoh untuk menghapus kolom alamat di table user


# Data Manipulation Language
Data Manippulation Language (DML) adalah perintah-perintah yang digunakan untuk mengubah , mamnipulasi dan mengambil data pada basis data. Tindakan seperti menghapus, mengubah, dan mengambil data menjadi bagian dari DML. 
## Insert Table
INSERT INTO table_name ( field1, field2,...fieldN )
   VALUES
   ( value1, value2,...valueN );

Digunakan untuk menambahkan data pada table tertentu

INSERT INTO pesanan ( id_pesanan, id_user, id_detail_pesanan )
   VALUES
   ( '1', '1', '1' );

Ketika menggunakan query diatas, kita harus memastikan bahwa urutan dari kolom yang akan kita isi telah sesuai dengan yang ada pada database apabila tidak maka dapat menyebabkan error pada saat menjalankan query tersebut

## Update Table
UPDATE table_name SET field1 = new-value1, field2 = new-value2
(WHERE Clause)

Digunakan untuk mengubah data pada table tertentu

UPDATE pesanan SET id_user = 2, id_detail_pesanan = 2
WHERE id_pesanan = 1

Diatas adalah contoh penggunaan update table yang akan merubah id_user dan id_detail_pesanan pada id_pesanan = 1

## Delete Table
DELETE FROM table_name (WHERE Clause)

Digunakan untuk menghapus kolom pada table tertentu

DELETE FROM table_name WHERE id_pesanan = 1

Diatas adalah contoh penggunakan Delete kolom yang digunakan untuk menghapus isi kolom dengan id_pesanan = 1

# Data Query Language
Data Query Language (DQL) biasanya digunakan untuk mempermudah proses pencarian atau pengurutan dari satu table atau lebih dengan cara menggabungkan table yang telah ada menjadi table baru yang bersifat sementara yang hanya dapat dilihat ketika kita menjalankan query tersebut serta tidak akan mengubah isi table yang telah ada sebelumnya

Terdapat berbagai macam jenis penggunaan dari Data Query Language, namun pada dasarnya penggunaan dari Data Query Language ini selalu diawali dengan perintah SELECT yang diikuti oleh kondisi selanjutnya seperti :
- SELECT, FROM dari dua table atau lebih
- WHERE, menambahkan kondisi tertentu agar data yang dicari lebih spesifik
- LIKE, hampir sama dengan WHERE akan tetapi penggunaannya lebih fleksible karena akan menampilkan seluruh isi data yang terdapat dari kondisi LIKE yang akan dicari
- ORDER BY, mengurutkan table dari yang terkecil atau terendah yang biasanya disebut ASC dan DESC
- JOIN, menggabungkan isi dari dua table atau lebih dengan tujuan untuk menampilkan sebuah data dengan kondisi tertentu
- CONCAT, digunakan untuk menyatukan isi dari dua table atau lebih
- GROUP BY, terdiri atas SUM COUNT AVERAGE dan MIN MAX yang memiliki fungsi tersendiri seperti SUM dapat menjumlahkan isi dari dua kolom atau lebih, COUNT dapat menghitung jumlah data pada table tertentu, AVERAGE digunakan untuk menghitung rata rata serta MIN MAX untuk mengetahui data terkecil dan terbesar


SELECT * , TIMESTAMPDIFF(YEAR,tanggal_lahir,CURDATE()) AS umur 
FROM penduduk 
WHERE kode_kabupaten = 3204

TIMESTAMPIFF (Untuk menghitung umur)
