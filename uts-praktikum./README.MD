## Query Database Karyawan

## Karyawan
CREATE TABLE karyawan(  
  id_karyawan INT(10) NOT NULL AUTO_INCREMENT,
  nama VARCHAR(100),
  tempat_lahir VARCHAR(100),
  tanggal_lahir DATE,
  jenis_kelamin ENUM('Laki-Laki','Perempuan'),
  agama ENUM('Islam','Katholik','Protestan','Hindu','Buddha'),
  no_hp VARCHAR(16),
  tanggal_masuk DATE,
  status ENUM('Menikah','Belum Menikah'),
  alamat VARCHAR(100),
  id_jabatan INT(10),
  id_gaji INT(10),
  tanggal_update_data DATE
  PRIMARY KEY (`id_karyawan`)
);

## Jabatan
CREATE TABLE jabatan(  
  id_jabatan INT(10) NOT NULL AUTO_INCREMENT,
  nama VARCHAR(100),
  status_jabatan ENUM('Aktif','Cuti','Tidak Aktif'),
  waktu DATE,
  PRIMARY KEY (`id_jabatan`)
);

## Gaji
CREATE TABLE Gaji(  
  id_gaji INT(10) NOT NULL AUTO_INCREMENT,
  gaji_bersih INT(10),
  gaji_pokok INT(10),
  tunjangan INT(10),
  total_gaji INT(10),
  waktu DATE,
  PRIMARY KEY (`id_gaji`)
);

## Foreign Key Query
ALTER TABLE karyawan
  ADD FOREIGN KEY (`id_jabatan`) REFERENCES `jabatan`(`id_jabatan`),
  ADD FOREIGN KEY (`id_gaji`) REFERENCES `gaji`(`id_gaji`);
