---
title: "Panduan Pemakaian Software Lab"
date: 2018-02-17T10:13:01+07:00
tags: [PostgreSQL, Apache, GeoServer]
categories: [Lab]
papersize: a4
fontsize: 12pt
colorlinks: true
header-includes:
    - \renewcommand{\figurename}{Gambar}
---

Panduan ini khusus untuk *software* yang tidak ada di menu *desktop* dan
memerlukan langkah tambahan untuk menjalankannya.

## PostgreSQL

Parameter koneksi *database* untuk *user* `student` adalah sebagai berikut:

- Username: `student`
- Password: `student`
- Database: `student`

*User* `student` memiliki izin untuk membuat *database* baru.

#### PostGIS

*Database* `student` telah ditambahkan ekstensi PostGIS.

#### pgAdmin

Berikut cara membuat koneksi ke server dengan parameter login di atas.

- *File --> Add Server...*
- Isikan parameter berikut:
    - Name: `student`
    - Host: `localhost`
    - Maintenance DB: `student`
    - Username: `student`
    - Password: `student`
  ![Parameter koneksi server untuk *user* `student`](/server-new.png)
- Klik ganda *Server Groups --> Servers --> student*
  ![Membuka koneksi server untuk *user* `student`](/server-added.png)


## Apache

Langkah paling awal adalah membuat direktori *web root*, yaitu `public_html`.

- Buat direktori `public_html` di dalam direktori *home* `student`
  ![Direktori *web root* untuk *user* `student`](/public-html.png)
- Letakkan *file* HTML, PHP, dan sebagainya ke direktori ini
- Isi direktori ini dapat diakses melalui alamat <http://localhost/~student>

Untuk menguji instalasi Apache, PHP, dan PostgreSQL, berikut contoh
aplikasi web PHP sederhana untuk buku tamu:
<https://gist.github.com/auriza/aba559515b329c3e4d62d4c6d8591af7>.


## GeoServer

- Untuk menjalankan GeoServer, buka terminal dan ketikkan perintah berikut:

    ```bash
    /opt/geoserver/bin/startup.sh &
    ```

- Antarmuka web GeoServer dapat diakses pada <http://localhost:8080/geoserver>.
    Login dengan *username* `admin` dan *password* `geoserver`.

- Untuk menghentikan GeoServer, ketikkan perintah berikut:

    ```bash
    /opt/geoserver/bin/shutdown.sh
    ```

