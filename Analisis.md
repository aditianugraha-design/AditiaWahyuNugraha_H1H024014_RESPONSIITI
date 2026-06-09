# ANALISIS RESPONSI INFRASTRUKTUR TEKNOLOGI INFORMASI

## Identitas
- Nama: Aditia Wahyu Nugraha
- NIM: H1H024014

## Daftar Bug yang Ditemukan dan Diperbaiki

### Bug 1 - Syntax error: services tanpa titik dua
- **Gejala:** docker compose gagal dijalankan
- **Penyebab:** `services` tidak diikuti tanda titik dua
- **Solusi:** Ganti menjadi `services:`

### Bug 2 - DB_HOST salah pada web1
- **Gejala:** web1 tidak bisa konek ke database
- **Penyebab:** DB_HOST diisi `mysql` padahal nama service-nya `db`
- **Solusi:** Ganti DB_HOST menjadi `db`

### Bug 3 - Password database salah pada web2
- **Gejala:** web2 gagal autentikasi ke database
- **Penyebab:** DB_PASS diisi `wrongpassword`
- **Solusi:** Ganti DB_PASS menjadi `student123`

### Bug 4 - Context folder salah pada web3
- **Gejala:** Docker gagal build image web3
- **Penyebab:** context mengarah ke `./web33` yang tidak ada
- **Solusi:** Ganti menjadi `./web3`

### Bug 5 - web3 tidak terhubung ke network frontend
- **Gejala:** Nginx tidak bisa menjangkau web3
- **Penyebab:** web3 hanya ada di network backend
- **Solusi:** Tambahkan network frontend pada web3

### Bug 6 - Nama volume tidak konsisten
- **Gejala:** Docker gagal mount volume database
- **Penyebab:** Volume didefinisikan sebagai `database-data` tapi dipakai sebagai `db-data`
- **Solusi:** Samakan nama volume menjadi `db-data`

### Bug 7 - Nginx upstream server web1 salah
- **Gejala:** Nginx tidak bisa forward ke web1
- **Penyebab:** server name ditulis `web11` bukan `web1`
- **Solusi:** Ganti menjadi `web1:80`

### Bug 8 - Nginx upstream port web3 salah
- **Gejala:** Nginx tidak bisa forward ke web3
- **Penyebab:** Port web3 ditulis `8080` padahal seharusnya `80`
- **Solusi:** Ganti menjadi `web3:80`

### Bug 9 - Dockerfile web1 typo nama image
- **Gejala:** Docker gagal build web1
- **Penyebab:** Image ditulis `php:8.2-apach`
- **Solusi:** Ganti menjadi `php:8.2-apache`

### Bug 10 - Dockerfile web3 typo nama image
- **Gejala:** Docker gagal build web3
- **Penyebab:** Image ditulis `php:8.2-apche`
- **Solusi:** Ganti menjadi `php:8.2-apache`

### Bug 11 - Container name web2 salah di index.php
- **Gejala:** Output web2 menampilkan WEB-WEB
- **Penyebab:** Hardcoded string salah di index.php
- **Solusi:** Ganti menjadi `WEB-2`

### Bug 12 - Container name web3 salah di index.php
- **Gejala:** Output web3 menampilkan WEB-WOB
- **Penyebab:** Hardcoded string salah di index.php
- **Solusi:** Ganti menjadi `WEB-3`

### Bug 13 - Nama dan NIM praktikan belum diisi
- **Gejala:** Output menampilkan placeholder
- **Penyebab:** Variabel $nama dan $nim belum diisi
- **Solusi:** Isi dengan nama dan NIM yang benar
