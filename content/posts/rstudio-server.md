---
title: "Instalasi RStudio Server"
date: 2017-11-03T08:00:00+07:00
draft: false
tags: [rstudio, server, ubuntu]
categories: [linux]
---

## Tambahkan repo R

~~~ sh
echo "deb http://cran.rstudio.com/bin/linux/ubuntu xenial/" | sudo tee -a /etc/apt/sources.list
gpg --keyserver keyserver.ubuntu.com --recv-key E084DAB9
gpg -a --export E084DAB9 | sudo apt-key add -
sudo apt update
~~~

## Install R

~~~ sh
sudo apt install r-base
~~~

## Install RStudio Server

~~~ sh
sudo apt install gdebi-core
wget https://download2.rstudio.org/rstudio-server-1.1.383-amd64.deb
sudo gdebi rstudio-server-1.1.383-amd64.deb
~~~

RStudio dapat diakses pada laman <http://localhost:8787>.
