# Membuat User Baru PostgreSQL
Untuk bisa membuat user baru, maka harus login terlebih dahulu ke postgres dengan perintah:
```
$ su - postgres
```
lalu masukan password akun postgres linuxnya, setelah itu ketikan:
```
$ psql
```
Sehingga hasilnya kurang lebih seperti ini:
```
server@server:~$ su - postgres
Password: 
postgres@server:~$ psql
psql (10.10 (Ubuntu 10.10-0ubuntu0.18.04.1))
Type "help" for help.
postgres=#
```
Perintah yang diperlukan untuk membuat user baru adalah:
```
CRATE USER namauser [[ WITH] option [ ... ]]
```
Di mana option adalah:
```
SUPERUSER | NOSUPERUSER | CREATEDB | NOCREATEDB | CRATERULE | NOCERATERULE | CREATEUSER | NOCERATEUSER | INHERIT | NOINHERIT | LOGIN | NOLOGIN | CONNECTION LIMIT connlimit [ENCRYPTED | UNENCRYPTED] PASSWORD 'password' VALID UNTIL 'timestamp' IN ROLE rolename [, ...] IN GROUP rolename [, ...] ADMIN rolename [, ...] USER [, ...] SYSID uid
```
Membuat user baru sebagai super-user dengan nama "aila" dan password "putericantik":
```
CREATE USER aila WITH PASSWORD 'putericantik' SUPERUSER;
```
Mengubah / Memodifikasi Kewenangan User PostgreSQL :
```
ALTER USER namauser [[WITH] option [ ... ]]
```
Di mana option adalah:
```
SUPERUSER | NOSUPERUSER | CREATEDB | NOCREATEDB | CRATERULE | NOCERATERULE | CREATEUSER | NOCERATEUSER | INHERIT | NOINHERIT | LOGIN | NOLOGIN | CONNECTION LIMIT connlimit [ENCRYPTED | UNENCRYPTED] PASSWORD 'password' VALID UNTIL 'timestamp'
```
Mengganti nama user yang sudah ada dengan nama yang baru:
```
ALTER USER rizqi RENAME TO qiqi; 
```
Mengubah kewenangan user biasa menjadi super user:
```
ALTER USER rizqi SUPERUSER;
```
Mengganti status user permanen menjadi user sementara (yang valid hingga waktu tertentu):
```
ALTER USER rizqi VALID UNTIL 'Sep 25 2020';
```
Mengganti password milik user:
```
ALTER USER rizqi WITH PASSWORD 'passwordbaru'; 
```
Menghapus User PostgreSQL :
```
DROP USER nama_user; 
```
Nenampilkan Daftar User PostgreSQL :
```
\du
```
Menampilkan Kewenangan User Tertentu :
```
\du nama_user;
```

# Membuat Database baru
Masuk ke akun postgres di server dengan menggunakan:
```
$ su - postgres
```
```
$ createdb kampus
```
```
$ psql ..
```
Melihat isi Tabel
```
# \dt
```

# Restore Postgres
Masuk ke Postgre
```
$ su - postgres
```
Tambahkan perintah psql -d (Nama Database) -p (Port Postgres) -U (User Database) -f (Direktori File Backup)
Contoh
```
$ psql -d baru -p 5432 -U postgres -f /home/dna/Desktop/test/backup_database_warna_salestrack_11-12-2022.tar
```
Tunggu Hingga Proses Restorasi Selesai

Refrensi : https://www.youtube.com/watch?v=eZR6FKLIde0
