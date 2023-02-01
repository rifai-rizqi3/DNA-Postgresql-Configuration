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
