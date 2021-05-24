---
title: Microsoft Learn Catalog LTI Provider
description: Bawa katalog Microsoft Learn ke dalam Learning Management System (LMS) Anda dengan aplikasi Learning Tools Interoperability (LTI) open-source
ms.author: saadad
author: sadadow
ms.date: 07/1/2020
ms.topic: article
ms.prod: non-product-specific
breadcrumb_path: toc.yml
ms.openlocfilehash: 095e45259039820a4f4aad9ab258dc72167b6383
ms.sourcegitcommit: 7b98b56c8e5bb1bdf66dda665bc9e6f307c65845
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/22/2021
ms.locfileid: "107696253"
---
# <a name="microsoft-learn-catalog-lti-provider"></a>Microsoft Learn Catalog LTI Provider

## <a name="overview"></a>Gambaran Umum

Untuk membawa konten Microsoft Learn ke dalam kelas, kami telah membuat aplikasi Learning Tools Interoperability (LTI) yang memungkinkan Anda memadukan konten pembelajaran mandiri dengan lancar dari katalog Microsoft Learn dengan kurikulum dan Learning Management System (LMS) Anda.

> [!TIP]
> [Tambahkan Katalog Microsoft Learn ke LMS Anda sekarang!](https://aka.ms/LearnLTI-Repo)

Pendidik dan Institusi dapat menggunakan aplikasi LTI untuk mengintegrasikan Jalur Pembelajaran dan Modul Microsoft Learn ke dalam kurikulum mereka sambil memberikan pengalaman langsung dengan Azure dan teknologi Microsoft lainnya. Pelajar akan dirutekan dari LMS mereka ke Microsoft Learn, tempat mereka dapat mengumpulkan poin pengalaman dan prestasi, serta melacak kemajuan pada aktivitas pembelajaran.

Aplikasi LTI Microsoft Learn mematuhi standar [v1.1](https://www.imsglobal.org/specs/ltiv1p1) dan [v1.3.](http://www.imsglobal.org/spec/lti/v1p3/) Untuk lebih spesifik tentang aplikasi itu sendiri, lihat [dokumentasi](#documentation).

## <a name="key-features"></a>Fitur Utama

- **Single Sign-On** (SSO) - pengguna hanya perlu masuk ke institusi mereka sekali untuk mengakses aplikasi Learn LTI
- **LMS Pairing** - instruktur dapat membuat, mengedit, dan menerbitkan tugas berbasis Learn untuk kursus mereka dan mengisi LMS institusi mereka dengan mudah
- **LTI v1.1** dan **v1.3 Compliant** - data siswa tidak dikumpulkan dan data mereka tidak dapat diakses; semua data pengguna dilindungi

## <a name="what-do-i-need-to-get-started"></a>Apa yang harus saya mulai?

Biasanya, akan ada empat peran yang terlibat dalam penyebaran, konfigurasi, dan penggunaan aplikasi Microsoft Learn LTI dengan LMS Institusi.

1. **TI Pusat / Admin TI** – Pengguna yang menggunakan aplikasi Microsoft Learn LTI ke Azure. Mereka harus menjadi pemilik langganan Azure dan memiliki hak istimewa untuk membuat sumber daya Azure. Orang ini juga akan menjadi orang yang mengonfigurasi aplikasi Microsoft Learn LTI untuk bekerja dengan LMS.
2. **Admin LMS** – Pengguna mengonfigurasi LMS untuk bekerja dengan aplikasi LTI Microsoft Learn yang diterapkan. Setelah dikonfigurasi, aplikasi LTI Microsoft Learn akan muncul sebagai alat LTI (alat eksternal) untuk digunakan oleh semua Pendidik di LMS.
3. **Pendidik** – Pengguna LMS yang ditetapkan sebagai "Guru" dalam kursus dan akan memfasilitasi pembelajaran. Orang ini akan membuat aktivitas atau sumber daya berdasarkan alat LTI yang dikonfigurasi pada LMS.
4. **Siswa** – Pengguna LMS yang akan mengkonsumsi pembelajaran yang diberikan kepada mereka oleh Pendidik.

Visual berikut ini mengilustrasikan alur kerja secara penuh: ![ Alur kerja penempatan menurut peran](https://raw.githubusercontent.com/microsoft/Learn-LTI/main/images/Readme.1.png?token=AC7AB7EPCTCG22JELW3YF2S7NEPCM)

### <a name="to-deploy-the-microsoft-learn-lti-application-the-central-it--it-admin-will-need"></a>Untuk menggunakan aplikasi Microsoft Learn LTI, Admin TI / TI Pusat akan memerlukan:

- Sistem LMS yang mendukung LTI v1.1 atau v1.3
- Anda harus menjadi **pemilik** langganan Azure
- Hak istimewa administrator TI untuk membuat sumber daya Azure

## <a name="documentation"></a>Dokumentasi

1. [Panduan Penyebaran](https://aka.ms/LearnLTI-Repo-Docs1)
2. [Panduan Konfigurasi](https://aka.ms/LearnLTI-Repo-Docs2)
3. [Panduan Pendidik](https://aka.ms/LearnLTI-Repo-Docs3)
4. [Panduan Siswa](https://aka.ms/LearnLTI-Repo-Docs4)
5. [Gambaran Umum Arsitektur](https://aka.ms/LearnLTI-Repo-Docs5)
6. [Struktur Harga](https://aka.ms/LearnLTI-Repo-Docs6)
7. [Ambil lebih lanjut](https://aka.ms/LearnLTI-Repo-Docs7)
8. [Tanya Jawab Umum](https://aka.ms/LearnLTI-Repo-Docs8)
9. [Pemecahan Masalah](https://aka.ms/LearnLTI-Repo-Docs9)

## <a name="contributing"></a>Berkontribusi

Proyek ini bersumber terbuka dan menyambut baik kontribusi dan saran.  Untuk mempelajari lebih  [lanjut, kunjungi repo GitHub.](https://aka.ms/LearnLTI-Repo)


> [!NOTE]
> Sebagian besar kontribusi mengharuskan Anda menyetujui Perjanjian Lisensi Kontributor (CLA) yang menyatakan bahwa Anda memiliki hak untuk, dan benar-benar melakukannya, memberi kami hak untuk menggunakan kontribusi Anda. Untuk detailnya, kunjungi https://cla.opensource.microsoft.com.
>
>Proyek ini telah mengadopsi [Kode Etik Sumber Terbuka Microsoft](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=learnlti-github-cxa).
Untuk informasi selengkapnya, lihat [Tanya Jawab Umum Kode Etik](https://opensource.microsoft.com/codeofconduct/faq/?WT.mc_id=learnlti-github-cxa) atau kontak dengan pertanyaan atau komentar [opencode@microsoft.com](mailto:opencode@microsoft.com) tambahan.