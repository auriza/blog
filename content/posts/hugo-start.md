---
title: "Hugo Start"
date: 2018-02-09T21:32:53+07:00
draft: false
tags: [blog, hugo]
categories: [web]
---


Hugo adalah generator situs web statik.
Halaman ditulis menggunakan Markdown.

# Inisialisasi Situs Baru

```sh
hugo new site blog
cd blog
git init
git submodule add https://github.com/MunifTanjim/minimo themes/minimo
cp themes/minimo/exampleSite/config.toml .
# edit info situs dan penulis
editor config.toml
```

# Link Akses Publik

```sh
ln -s public ~/public_html/blog
```

# Tulis Post Baru

```sh
hugo new posts/first-post.md
editor content/posts/first-post.md
```

Pastikan *header* dokumen `draft` diset `false` agar terpublikasi.

# Generate Situs Statik

```sh
hugo -b http://os.apps.cs.ipb.ac.id/~$USER/blog
```

Buka laman di atas untuk melihat situs baru anda.

Setiap kali menambahkan atau mengubah isi post, jalankan perintah `hugo` di
atas untuk meng-generate perubahan isi situs.
