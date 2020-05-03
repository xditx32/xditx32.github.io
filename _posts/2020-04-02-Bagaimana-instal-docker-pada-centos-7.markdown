---
title:  "Bagimana instal Docker pada CentOS7?"
description: "Panduan Instalasi Docker pada CentOS7"
date:   2020-04-02 00:00:00
categories: [Open Source, Bahasa]
tags: [Docker, CentOS7]
canonical_url: https://docs.docker.com/engine/install/centos/
---

Pengantar

Apa itu Docker? [Docker](https://www.docker.com/) adalah paket perangkat lunak populer yang membuat atau mengelola wadah (tempat) untuk pengembangan sebuah Aplikasi skala Kecil ataupun Besar.

Ini adalah panduan tentang cara menginstal Docker pada [CentOS7](https://docs.docker.com/engine/install/centos/)

Tutorial langkah demi langkah tentang cara menginstal Docker di CentOS7.x.

Langkah 1: Update CentOS + Buka jendela terminal `CTRL+T`
```bash
sudo yum -y update
```

Langkah 2: Instal Paket Dependensi 
```bash
sudo yum install -y yum-utils device-mapper-persisten-data lvm2
```

Langkah 3: Tambahkan Doker Repository pada CentOS
```bash
sudo yum-config-manager --add-repo https://download.doker.com/linux/centos/docker-ce.repo
```

Langkah 4: Instal Docker pada CentOS
```bash
sudo yum install -y docker-ce
```

Setelah instalasi selesai

Langkah 5: Kelola layanan Docker pada CentOS

Meskipun telah di instal Docker pada CentOS layanan ini mash belum berjalan.

Start Service Docker (Start Layanan Docker pada CentOS)
```bash
sudo systemctl start docker
```
Enable Service Docker (Layanan Docker Berjalan pada saat startup CentOS)
```bash
sudo systemctl enable docker
```
Status Service Docker (Status Layanan Docker telah aktif)
```bash 
sudo systemctl status docker
```


Note! Bilamana terjadi `docker-engine conflicts with docker-common2` pada Langkah 4:
```bash
Transaction check error:file /usr/bin/docker from install of docker-engine-1.13.0-1.el7.centos.x86_64 conflicts with file from package docker-common-2:1.10.3-59.el7.centos.x86_64
```
Cara memperbaiki permasalahan menghapus paket :
```bash
sudo yum remove docker-common
```
Biarkan operasi selesai bilamana sudah ulangi Langkah 4

Kesimpulan
Jika Anda mengikuti panduan ini, Anda seharusnya telah menginstal Docker pada mesin CentOS 7 Anda. Sekarang Anda dapat menjelajahi dunia Docker.

Terimakasih





