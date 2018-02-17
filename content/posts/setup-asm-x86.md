---
title: "Setup Pemrograman ASM x86"
date: 2018-02-17T10:56:52+07:00
tags: [ASM, Geany, VM]
categories: [Lab]
---

Sistem operasi yang dipakai: [Xubuntu](https://xubuntu.org/download) atau [Ubuntu](https://www.ubuntu.com/download/desktop) 16.04 LTS 64-bit.

## Instalasi

Instal *assembler*, *compiler*, *debugger*, dan editor.

```bash
sudo apt update
sudo apt install yasm
sudo apt install gcc-multilib
sudo apt install gdb ddd
sudo apt install geany
```

## Konfigurasi

Unduh *file* `filetypes.asm` dari [GitHub](https://gist.githubusercontent.com/auriza/9fb537d16388d5f043225b3ec8070acb/raw/46ba23237da7ac1bb02ef2af390e2a50041dc5b4/filetypes.asm)
dan salin ke direktori `~/.config/geany/filedefs/`.
*File* ini berisi konfigurasi *build* dan *syntax highlight* untuk ASM x86.
Lalu, gunakan sintaks Intel untuk *disassembly*.

```bash
wget "https://gist.githubusercontent.com/auriza/9fb537d16388d5f043225b3ec8070acb/raw/46ba23237da7ac1bb02ef2af390e2a50041dc5b4/filetypes.asm"
cp filetypes.asm .config/geany/filedefs/
echo "set disassembly-flavor intel" > .gdbinit
```


## Alternatif: *virtual machine*

Disediakan *virtual disk* [VirtualBox](https://www.virtualbox.org/wiki/Downloads) untuk
*setup* di atas yang dapat diunduh pada <http://repo.apps.cs.ipb.ac.id/lab/xubuntu-oak.vdi.gz>.
Ekstrak *file* tersebut dan buat VM baru pada VirtualBox dengan menggunakan
*virtual disk* ini. Login dengan *username* `student` dan *password* `student`.

