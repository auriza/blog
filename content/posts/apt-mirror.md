---
title: "Mirror Repositori Ubuntu"
date: 2017-01-21T08:00:00+07:00
draft: false
tags: [mirror, repo, ubuntu]
categories: [linux]
---

## Install apt-mirror

~~~ sh
sudo apt update
sudo apt install apt-mirror
~~~

## Konfigurasi repo sumber

~~~ sh
sudo editor /etc/apt/mirror.list
~~~

~~~
...
deb-amd64 http://id.archive.ubuntu.com/ubuntu xenial main restricted universe multiverse
deb-amd64 http://id.archive.ubuntu.com/ubuntu xenial-security main restricted universe multiverse
deb-amd64 http://id.archive.ubuntu.com/ubuntu xenial-updates main restricted universe multiverse

deb-i386 http://id.archive.ubuntu.com/ubuntu xenial main restricted universe multiverse
deb-i386 http://id.archive.ubuntu.com/ubuntu xenial-security main restricted universe multiverse
deb-i386 http://id.archive.ubuntu.com/ubuntu xenial-updates main restricted universe multiverse

clean http://id.archive.ubuntu.com/ubuntu
~~~

## Jalankan apt-mirror

~~~ sh
sudo apt-mirror
~~~


## Publikasikan repo via web

~~~ sh
sudo apt install apache2
sudo ln -s /var/spool/apt-mirror/mirror/archive.ubuntu.com/ubuntu/
~~~


## Otomatisasi *update* repo (opsional)

~~~ sh
sudo editor /etc/cron.d/apt-mirror
~~~

Hapus tanda komentar (`#`) pada baris terakhir untuk menjalankan `apt-mirror` secara otomatis tiap hari pada pukul 4:00.

~~~
0 4 * * *   apt-mirror      /usr/bin/apt-mirror > /var/spool/apt-mirror/var/cron.log
~~~

Selesai untuk bagian server.


## Setting klien

Pada klien, set sumber repo sebagai berikut (misal, nama *host* server repo adalah `$REPO`).

~~~ sh
sudo editor /etc/apt/sources.list
~~~

~~~
deb http://$REPO/ubuntu xenial main restricted universe multiverse
deb http://$REPO/ubuntu xenial-security main restricted universe multiverse
deb http://$REPO/ubuntu xenial-updates main restricted universe multiverse
~~~

Tes dengan meng-*update* repositori.

~~~ sh
sudo apt update
~~~
