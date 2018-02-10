---
title: "Bad RAM"
date: 2017-03-31T14:04:00+07:00
draft: false
tags: [ram, memtest, grub]
categories: [linux]
---

Dua bulan terakhir, Firefox sering *crash* jika tab yang terbuka sudah agak banyak.
Saya cek di internet tapi tidak menemukan kasus serupa.
Kemarin lusa, kernel Linux tiba-tiba *hang* saat memutar video.
Dari sini, mungkin kesalahan bukan pada *software*, tetapi pada *hardware*, yaitu RAM.

Saya cek RAM dengan Memtest86+, ternyata alamat `0x3fad8e08` bermasalah.
Sebabnya karena cuma satu bit saja yang *error* (misal dari 1111 berubah menjadi 1101).
Jadi saat pemakaian RAM melebihi 1 GB, maka alamat ini akan terpakai dan *software* menjadi tidak stabil.

![Memtest86+](/img/badram.jpg)

Apakah RAM yang bermasalah ini masih bisa dipakai? Bisa.
Ada fitur pada kernel Linux untuk menandai alamat RAM yang bermasalah, yaitu [BadRAM](https://help.ubuntu.com/community/BadRAM).
Untuk kasus saya, cukup dengan menambahkan konfigurasi berikut pada *file* `/etc/default/grub`, lalu jalankan `update-grub`.

    GRUB_BADRAM="0x3fad8e08,0xfffffffc"

Setelah itu, Firefox jarang *crash* lagi.
Kesalahan 1 bit saja bisa berakibat fatal, oleh karena itu komputer server memakai modul RAM dengan fitur ECC.
