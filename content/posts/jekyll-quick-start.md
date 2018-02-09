---
title: "Jekyll Quick Start"
date: 2017-01-12T08:00:00+07:00
draft: false
tags: [jekyll, blog]
categories: [web]
---

## Instal Jekyll

~~~ sh
sudo apt install ruby-full
sudo gem install jekyll
~~~

## Buat situs baru

~~~ sh
jekyll new blog
cd blog
bundle exec jekyll serve
~~~

Akses blog baru kamu di <http://localhost:4000>.


## Buat postingan baru

~~~ sh
cat > _posts/YYYY-MM-DD-title-of-post.md << EOF
---
layout: post
title: "Jekyll Quick Start"
tags: jekyll, markdown, debian
---

## Instal Jekyll

...
EOF
~~~

Server Jekyll secara otomatis akan memantau perubahan *file* dan memperbarui isi
situs. Muat ulang halaman <http://localhost:4000> untuk melihat postingan baru
kamu.


## Publikasi via GitHub Pages

Setelah blog di lokal sudah berjalan, kamu bisa mempublikasikan blogmu melalui
[GitHub Pages](https://pages.github.com/). Nanti, blog kamu dapat diakses di
alamat <https://<USERNAME>.github.io>, keren kan!

Pertama, daftar dulu di [GitHub](https://github.com/) untuk mendapatkan
*username*. Setelah itu, buat repo dengan nama *username*.github.io.
Lalu, inisialisasi `git` di direktori blog kamu dan tambahkan repo *remote*
GitHub tersebut (ganti `USERNAME` di sini dengan *username* aktual kamu).

~~~ sh
sudo apt install git
git init
git remote add origin https://github.com/<USERNAME>/<USERNAME>.github.io.git
~~~

Selanjutnya, tiap selesai mengubah konten blog, *add* dan *commit* semua
perubahan ke repo lokal dan *push* juga ke repo *remote*.

~~~ sh
git add --all
git commit -m "First commit"
git push -u origin master
~~~

Buka *browser* dan buka blog baru kamu di laman <https://<USERNAME>.github.io>.
