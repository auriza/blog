---
title: "Hugo Start"
date: 2017-11-14T15:50:00+07:00
draft: false
tags: [blog, hugo]
categories: [web]
---


Hugo adalah *generator* situs web statik.
Halamannya ditulis menggunakan format Markdown.


## Inisialisasi Situs Baru

```sh
       # buat situs baru
     ~ $ hugo new site blog
     ~ $ cd blog
       # tambahkan tema
~/blog $ git init
~/blog $ git submodule add https://github.com/MunifTanjim/minimo themes/minimo
~/blog $ cp themes/minimo/exampleSite/config.toml .
       # edit baseURL
~/blog $ sed -i "/baseURL/ s_example.org_os.apps.cs.ipb.ac.id/~$USER/blog_" config.toml
```


## *Link* Akses Publik

```sh
       # symlink ke direktori webroot user
~/blog $ ln -s ~/blog/public ~/public_html/blog
```


## Tulis *Post* Baru

```sh
       # buat post baru
~/blog $ hugo new posts/first-post.md
       # edit isinya
~/blog $ editor content/posts/first-post.md
```

Pastikan *header* dokumen `draft` diset `false` agar terpublikasi.


## *Generate* Situs Statik

```sh
       # generate HTML
~/blog $ hugo --baseURL http://os.apps.cs.ipb.ac.id/~$USER/blog/
```

Buka laman di atas untuk melihat situs baru anda.

Setiap kali menambahkan atau mengubah isi *post*, jalankan perintah `hugo` di
atas untuk meng-*generate* perubahan isi situs.
