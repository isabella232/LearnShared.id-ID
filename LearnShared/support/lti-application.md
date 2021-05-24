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
# <a name="microsoft-learn-catalog-lti-provider"></a><span data-ttu-id="58f53-103">Microsoft Learn Catalog LTI Provider</span><span class="sxs-lookup"><span data-stu-id="58f53-103">Microsoft Learn Catalog LTI Provider</span></span>

## <a name="overview"></a><span data-ttu-id="58f53-104">Gambaran Umum</span><span class="sxs-lookup"><span data-stu-id="58f53-104">Overview</span></span>

<span data-ttu-id="58f53-105">Untuk membawa konten Microsoft Learn ke dalam kelas, kami telah membuat aplikasi Learning Tools Interoperability (LTI) yang memungkinkan Anda memadukan konten pembelajaran mandiri dengan lancar dari katalog Microsoft Learn dengan kurikulum dan Learning Management System (LMS) Anda.</span><span class="sxs-lookup"><span data-stu-id="58f53-105">To bring Microsoft Learn's content into the classroom, we've made a Learning Tools Interoperability (LTI) application that enables you to seamlessly blend self-paced learning content from the Microsoft Learn catalog with your curriculum and Learning Management System (LMS).</span></span>

> [!TIP]
> [<span data-ttu-id="58f53-106">Tambahkan Katalog Microsoft Learn ke LMS Anda sekarang!</span><span class="sxs-lookup"><span data-stu-id="58f53-106">Add Microsoft Learn's Catalog to your LMS now!</span></span>](https://aka.ms/LearnLTI-Repo)

<span data-ttu-id="58f53-107">Pendidik dan Institusi dapat menggunakan aplikasi LTI untuk mengintegrasikan Jalur Pembelajaran dan Modul Microsoft Learn ke dalam kurikulum mereka sambil memberikan pengalaman langsung dengan Azure dan teknologi Microsoft lainnya.</span><span class="sxs-lookup"><span data-stu-id="58f53-107">Educators and Institutions can leverage the LTI application to integrate Microsoft Learn Modules and Learning Paths into their curricula while providing hands-on experiences with Azure and other Microsoft technologies.</span></span> <span data-ttu-id="58f53-108">Pelajar akan dirutekan dari LMS mereka ke Microsoft Learn, tempat mereka dapat mengumpulkan poin pengalaman dan prestasi, serta melacak kemajuan pada aktivitas pembelajaran.</span><span class="sxs-lookup"><span data-stu-id="58f53-108">Learners will be routed from their LMS to Microsoft Learn, where they can accrue experience points and achievements as well as track progress on learning activities.</span></span>

<span data-ttu-id="58f53-109">Aplikasi LTI Microsoft Learn mematuhi standar [v1.1](https://www.imsglobal.org/specs/ltiv1p1) dan [v1.3.](http://www.imsglobal.org/spec/lti/v1p3/)</span><span class="sxs-lookup"><span data-stu-id="58f53-109">The Microsoft Learn LTI Application adheres to [v1.1](https://www.imsglobal.org/specs/ltiv1p1) and [v1.3](http://www.imsglobal.org/spec/lti/v1p3/) standards.</span></span> <span data-ttu-id="58f53-110">Untuk lebih spesifik tentang aplikasi itu sendiri, lihat [dokumentasi](#documentation).</span><span class="sxs-lookup"><span data-stu-id="58f53-110">For more specifics on the application itself, check out the [documentation](#documentation).</span></span>

## <a name="key-features"></a><span data-ttu-id="58f53-111">Fitur Utama</span><span class="sxs-lookup"><span data-stu-id="58f53-111">Key Features</span></span>

- <span data-ttu-id="58f53-112">**Single Sign-On** (SSO) - pengguna hanya perlu masuk ke institusi mereka sekali untuk mengakses aplikasi Learn LTI</span><span class="sxs-lookup"><span data-stu-id="58f53-112">**Single Sign-On** (SSO) - users only have to sign into their institution once to access the Learn LTI application</span></span>
- <span data-ttu-id="58f53-113">**LMS Pairing** - instruktur dapat membuat, mengedit, dan menerbitkan tugas berbasis Learn untuk kursus mereka dan mengisi LMS institusi mereka dengan mudah</span><span class="sxs-lookup"><span data-stu-id="58f53-113">**LMS Pairing** - instructors can create, edit, and publish Learn-based assignments for their courses and populate their institution's LMS with them easily</span></span>
- <span data-ttu-id="58f53-114">**LTI v1.1** dan **v1.3 Compliant** - data siswa tidak dikumpulkan dan data mereka tidak dapat diakses; semua data pengguna dilindungi</span><span class="sxs-lookup"><span data-stu-id="58f53-114">**LTI v1.1** and **v1.3 Compliant** - student data is not gathered and their data cannot be accessed; all user data is protected</span></span>

## <a name="what-do-i-need-to-get-started"></a><span data-ttu-id="58f53-115">Apa yang harus saya mulai?</span><span class="sxs-lookup"><span data-stu-id="58f53-115">What do I need to get started?</span></span>

<span data-ttu-id="58f53-116">Biasanya, akan ada empat peran yang terlibat dalam penyebaran, konfigurasi, dan penggunaan aplikasi Microsoft Learn LTI dengan LMS Institusi.</span><span class="sxs-lookup"><span data-stu-id="58f53-116">Typically, there will be four roles involved in deploying, configuring, and using the Microsoft Learn LTI application with Institution’s LMS.</span></span>

1. <span data-ttu-id="58f53-117">**TI Pusat / Admin TI** – Pengguna yang menggunakan aplikasi Microsoft Learn LTI ke Azure.</span><span class="sxs-lookup"><span data-stu-id="58f53-117">**Central IT / IT Admin** – The user deploying the Microsoft Learn LTI application to Azure.</span></span> <span data-ttu-id="58f53-118">Mereka harus menjadi pemilik langganan Azure dan memiliki hak istimewa untuk membuat sumber daya Azure.</span><span class="sxs-lookup"><span data-stu-id="58f53-118">They need to be an owner of an Azure subscription and have the privileges to create Azure resources.</span></span> <span data-ttu-id="58f53-119">Orang ini juga akan menjadi orang yang mengonfigurasi aplikasi Microsoft Learn LTI untuk bekerja dengan LMS.</span><span class="sxs-lookup"><span data-stu-id="58f53-119">This person will also be the one configuring the Microsoft Learn LTI application to work with the LMS.</span></span>
2. <span data-ttu-id="58f53-120">**Admin LMS** – Pengguna mengonfigurasi LMS untuk bekerja dengan aplikasi LTI Microsoft Learn yang diterapkan.</span><span class="sxs-lookup"><span data-stu-id="58f53-120">**LMS Admin** – The user configuring the LMS to work with the deployed Microsoft Learn LTI application.</span></span> <span data-ttu-id="58f53-121">Setelah dikonfigurasi, aplikasi LTI Microsoft Learn akan muncul sebagai alat LTI (alat eksternal) untuk digunakan oleh semua Pendidik di LMS.</span><span class="sxs-lookup"><span data-stu-id="58f53-121">Once configured, the Microsoft Learn LTI application will appear as an LTI tool (external tool) to be used by all Educators on the LMS.</span></span>
3. <span data-ttu-id="58f53-122">**Pendidik** – Pengguna LMS yang ditetapkan sebagai "Guru" dalam kursus dan akan memfasilitasi pembelajaran.</span><span class="sxs-lookup"><span data-stu-id="58f53-122">**Educators** – The user(s) of the LMS who is set up as a “Teacher” in a course and will facilitate the learning.</span></span> <span data-ttu-id="58f53-123">Orang ini akan membuat aktivitas atau sumber daya berdasarkan alat LTI yang dikonfigurasi pada LMS.</span><span class="sxs-lookup"><span data-stu-id="58f53-123">This person will create activities or resources based on the configured LTI tool on the LMS.</span></span>
4. <span data-ttu-id="58f53-124">**Siswa** – Pengguna LMS yang akan mengkonsumsi pembelajaran yang diberikan kepada mereka oleh Pendidik.</span><span class="sxs-lookup"><span data-stu-id="58f53-124">**Students** – The users of the LMS who will consume the learning provisioned to them by the Educators.</span></span>

<span data-ttu-id="58f53-125">Visual berikut ini mengilustrasikan alur kerja secara penuh: ![ Alur kerja penempatan menurut peran](https://raw.githubusercontent.com/microsoft/Learn-LTI/main/images/Readme.1.png?token=AC7AB7EPCTCG22JELW3YF2S7NEPCM)</span><span class="sxs-lookup"><span data-stu-id="58f53-125">The following visual illustrates the workflow in full: ![Deployment workflow by role](https://raw.githubusercontent.com/microsoft/Learn-LTI/main/images/Readme.1.png?token=AC7AB7EPCTCG22JELW3YF2S7NEPCM)</span></span>

### <a name="to-deploy-the-microsoft-learn-lti-application-the-central-it--it-admin-will-need"></a><span data-ttu-id="58f53-126">Untuk menggunakan aplikasi Microsoft Learn LTI, Admin TI / TI Pusat akan memerlukan:</span><span class="sxs-lookup"><span data-stu-id="58f53-126">To deploy the Microsoft Learn LTI application, the Central IT / IT Admin will need:</span></span>

- <span data-ttu-id="58f53-127">Sistem LMS yang mendukung LTI v1.1 atau v1.3</span><span class="sxs-lookup"><span data-stu-id="58f53-127">LMS System that supports LTI v1.1 or v1.3</span></span>
- <span data-ttu-id="58f53-128">Anda harus menjadi **pemilik** langganan Azure</span><span class="sxs-lookup"><span data-stu-id="58f53-128">You need to be the **owner** of an Azure subscription</span></span>
- <span data-ttu-id="58f53-129">Hak istimewa administrator TI untuk membuat sumber daya Azure</span><span class="sxs-lookup"><span data-stu-id="58f53-129">IT administrator privileges to create an Azure resource</span></span>

## <a name="documentation"></a><span data-ttu-id="58f53-130">Dokumentasi</span><span class="sxs-lookup"><span data-stu-id="58f53-130">Documentation</span></span>

1. [<span data-ttu-id="58f53-131">Panduan Penyebaran</span><span class="sxs-lookup"><span data-stu-id="58f53-131">Deployment Guide</span></span>](https://aka.ms/LearnLTI-Repo-Docs1)
2. [<span data-ttu-id="58f53-132">Panduan Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="58f53-132">Configuration Guide</span></span>](https://aka.ms/LearnLTI-Repo-Docs2)
3. [<span data-ttu-id="58f53-133">Panduan Pendidik</span><span class="sxs-lookup"><span data-stu-id="58f53-133">Educator Guide</span></span>](https://aka.ms/LearnLTI-Repo-Docs3)
4. [<span data-ttu-id="58f53-134">Panduan Siswa</span><span class="sxs-lookup"><span data-stu-id="58f53-134">Student Guide</span></span>](https://aka.ms/LearnLTI-Repo-Docs4)
5. [<span data-ttu-id="58f53-135">Gambaran Umum Arsitektur</span><span class="sxs-lookup"><span data-stu-id="58f53-135">Architecture Overview</span></span>](https://aka.ms/LearnLTI-Repo-Docs5)
6. [<span data-ttu-id="58f53-136">Struktur Harga</span><span class="sxs-lookup"><span data-stu-id="58f53-136">Pricing Structure</span></span>](https://aka.ms/LearnLTI-Repo-Docs6)
7. [<span data-ttu-id="58f53-137">Ambil lebih lanjut</span><span class="sxs-lookup"><span data-stu-id="58f53-137">Take it Further</span></span>](https://aka.ms/LearnLTI-Repo-Docs7)
8. [<span data-ttu-id="58f53-138">Tanya Jawab Umum</span><span class="sxs-lookup"><span data-stu-id="58f53-138">Frequently Asked Questions</span></span>](https://aka.ms/LearnLTI-Repo-Docs8)
9. [<span data-ttu-id="58f53-139">Pemecahan Masalah</span><span class="sxs-lookup"><span data-stu-id="58f53-139">Troubleshooting</span></span>](https://aka.ms/LearnLTI-Repo-Docs9)

## <a name="contributing"></a><span data-ttu-id="58f53-140">Berkontribusi</span><span class="sxs-lookup"><span data-stu-id="58f53-140">Contributing</span></span>

<span data-ttu-id="58f53-141">Proyek ini bersumber terbuka dan menyambut baik kontribusi dan saran.</span><span class="sxs-lookup"><span data-stu-id="58f53-141">This project is open-source and welcomes contributions and suggestions.</span></span>  <span data-ttu-id="58f53-142">Untuk mempelajari lebih  [lanjut, kunjungi repo GitHub.](https://aka.ms/LearnLTI-Repo)</span><span class="sxs-lookup"><span data-stu-id="58f53-142">To learn more,  [visit the GitHub repo.](https://aka.ms/LearnLTI-Repo)</span></span>


> [!NOTE]
> <span data-ttu-id="58f53-143">Sebagian besar kontribusi mengharuskan Anda menyetujui Perjanjian Lisensi Kontributor (CLA) yang menyatakan bahwa Anda memiliki hak untuk, dan benar-benar melakukannya, memberi kami hak untuk menggunakan kontribusi Anda.</span><span class="sxs-lookup"><span data-stu-id="58f53-143">Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution.</span></span> <span data-ttu-id="58f53-144">Untuk detailnya, kunjungi https://cla.opensource.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="58f53-144">For details, visit https://cla.opensource.microsoft.com.</span></span>
>
><span data-ttu-id="58f53-145">Proyek ini telah mengadopsi [Kode Etik Sumber Terbuka Microsoft](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=learnlti-github-cxa).</span><span class="sxs-lookup"><span data-stu-id="58f53-145">This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=learnlti-github-cxa).</span></span>
<span data-ttu-id="58f53-146">Untuk informasi selengkapnya, lihat [Tanya Jawab Umum Kode Etik](https://opensource.microsoft.com/codeofconduct/faq/?WT.mc_id=learnlti-github-cxa) atau kontak dengan pertanyaan atau komentar [opencode@microsoft.com](mailto:opencode@microsoft.com) tambahan.</span><span class="sxs-lookup"><span data-stu-id="58f53-146">For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/?WT.mc_id=learnlti-github-cxa) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.</span></span>