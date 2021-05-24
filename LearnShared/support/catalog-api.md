---
title: Katalog API Microsoft Learn
description: API web berbasis REST untuk menampilkan informasi tentang konten yang diterbitkan di Microsoft Learn.
ms.author: smmark
author: markjulmar
ms.date: 03/10/20
ms.topic: article
ms.prod: non-product-specific
breadcrumb_path: toc.yml
ms.openlocfilehash: aef08013af6bd2f48100909afb65d85e57d3da19
ms.sourcegitcommit: 48123434f54904a396a5616c7c05f9a03bd3a0df
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/26/2021
ms.locfileid: "107696299"
---
# <a name="microsoft-learn-catalog-api"></a><span data-ttu-id="ddd69-103">Microsoft Learn Catalog API</span><span class="sxs-lookup"><span data-stu-id="ddd69-103">Microsoft Learn Catalog API</span></span>

<span data-ttu-id="ddd69-104">Microsoft Learn Catalog API memungkinkan Anda mengirim kueri berbasis web ke Microsoft Learn dan mendapatkan detail tentang konten yang diterbitkan seperti judul, produk yang dibahas, dan tautan ke pelatihan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-104">The Microsoft Learn Catalog API lets you send a web-based query to Microsoft Learn and get back details about published content such as titles, products covered, and links to the training.</span></span> <span data-ttu-id="ddd69-105">Pelanggan dapat menggunakan informasi yang diberikan dan menampilkannya dalam sistem manajemen pembelajaran (LMS) mereka dengan konten pelatihan lainnya.</span><span class="sxs-lookup"><span data-stu-id="ddd69-105">Customers can take the returned information and display it in their learning management systems (LMSs) alongside other training content.</span></span>

> [!NOTE]
> <span data-ttu-id="ddd69-106">Pelanggan dapat menggunakan API ini untuk menampilkan informasi tentang pelatihan yang tersedia, tetapi pelatihan harus diselesaikan di Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="ddd69-106">Customers can use this API to display information about the available training, but the training must be completed on Microsoft Learn.</span></span>

<span data-ttu-id="ddd69-107">Catalog API ditawarkan berdasarkan [Ketentuan Penggunaan API Microsoft.](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)</span><span class="sxs-lookup"><span data-stu-id="ddd69-107">The Catalog API is offered under the terms of the [Microsoft APIs Terms of Use](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use).</span></span> <span data-ttu-id="ddd69-108">Halaman ini menyediakan detail teknis terkait API dan cara menginterpretasikan informasi yang ditampilkan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-108">This page provides technical details about the API and how to interpret the information returned.</span></span>

## <a name="modules-and-learning-paths"></a><span data-ttu-id="ddd69-109">Modul dan Jalur Pembelajaran</span><span class="sxs-lookup"><span data-stu-id="ddd69-109">Modules and Learning Paths</span></span>

<span data-ttu-id="ddd69-110">Konten di Microsoft Learn diatur menurut dua elemen: yaitu _modul_ dan _jalur pembelajaran_.</span><span class="sxs-lookup"><span data-stu-id="ddd69-110">Content in Microsoft Learn is organized around two elements: _modules_ and _learning paths_.</span></span>

### <a name="modules"></a><span data-ttu-id="ddd69-111">Modul</span><span class="sxs-lookup"><span data-stu-id="ddd69-111">Modules</span></span>

<span data-ttu-id="ddd69-112">_Modul_ adalah konten pelatihan yang sebenarnya.</span><span class="sxs-lookup"><span data-stu-id="ddd69-112">A _module_ is the actual training content.</span></span> <span data-ttu-id="ddd69-113">Satu modul terdiri dari beberapa halaman web yang menjelaskan tentang layanan atau teknologi dan sering kali memberikan beberapa bentuk interaktivitas untuk mencoba teknologi tersebut.</span><span class="sxs-lookup"><span data-stu-id="ddd69-113">A single module consists of multiple web pages that explore a service or technology and often provide some form of interactivity to try out the technology.</span></span> <span data-ttu-id="ddd69-114">Setiap modul memiliki metadata terkait untuk dengan cepat mengidentifikasi target modulnya, isi yang dibahas, dan waktu yang diperlukan untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="ddd69-114">Each module has related metadata to quickly identify who it's for, what's covered, and how long it typically takes to complete.</span></span> <span data-ttu-id="ddd69-115">Detail ini dapat ditemukan di ubin grafis pada [halaman penelusuran Microsoft Learn](https://docs.microsoft.com/learn/browse), seperti yang diperlihatkan dalam cuplikan layar berikut ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-115">These details can be found in the graphical tiles on the [Microsoft Learn browse page](https://docs.microsoft.com/learn/browse), as shown in the following screenshot.</span></span>

![Cuplikan layar memperlihatkan satu modul dengan semua detail dari situs web Microsoft Learn](media/module-details.png)

### <a name="learning-paths"></a><span data-ttu-id="ddd69-117">Jalur Pembelajaran</span><span class="sxs-lookup"><span data-stu-id="ddd69-117">Learning Paths</span></span>

<span data-ttu-id="ddd69-118">_Jalur pembelajaran_ adalah kumpulan modul terkait yang disajikan dalam urutan tertentu sehingga modul tersebut saling melengkapi untuk mengajarkan topik yang lebih luas.</span><span class="sxs-lookup"><span data-stu-id="ddd69-118">A _learning path_ is a collection of related modules presented in a specific order so that the modules build on one another to teach a broader topic.</span></span> <span data-ttu-id="ddd69-119">Jalur pembelajaran juga menyertakan metadata deskriptif yang mirip dengan modul, seperti yang ditunjukkan pada cuplikan layar dari halaman penelusuran di bawah ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-119">Learning paths also include descriptive metadata similar to modules, as shown in the screenshot from the browse page below.</span></span>

![Cuplikan layar memperlihatkan jalur pembelajaran dari situs web Microsoft Learn](media/learning-path-details.png)

## <a name="api-endpoint"></a><span data-ttu-id="ddd69-121">Titik akhir API</span><span class="sxs-lookup"><span data-stu-id="ddd69-121">API endpoint</span></span>

<span data-ttu-id="ddd69-122">Microsoft Learn Catalog API adalah API Web berbasis REST yang memberikan respons dalam kode JSON.</span><span class="sxs-lookup"><span data-stu-id="ddd69-122">The Microsoft Learn Catalog API is a REST-based Web API that returns a JSON-encoded response.</span></span>

<span data-ttu-id="ddd69-123">Untuk meminta katalog lengkap modul dan jalur pembelajaran, kirim permintaan GET ke:</span><span class="sxs-lookup"><span data-stu-id="ddd69-123">To request the full catalog of modules and learning paths, send a GET request to:</span></span>

```html
https://docs.microsoft.com/api/learn/catalog/
```

> [!IMPORTANT]
> <span data-ttu-id="ddd69-124">Permintaan harus menggunakan protokol HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ddd69-124">The request must use the HTTPS protocol.</span></span>

### <a name="query-parameters"></a><span data-ttu-id="ddd69-125">Parameter kueri</span><span class="sxs-lookup"><span data-stu-id="ddd69-125">Query parameters</span></span>

<span data-ttu-id="ddd69-126">Berikut adalah parameter kueri yang dapat disertakan dalam permintaan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-126">The following are the query parameters that the request may include.</span></span> <span data-ttu-id="ddd69-127">Kolom **Wajib diisi** menunjukkan bahwa Anda harus menentukan parameter.</span><span class="sxs-lookup"><span data-stu-id="ddd69-127">The **Required** column indicates whether you must specify the parameter.</span></span> <span data-ttu-id="ddd69-128">Anda harus mengodekan nilai parameter kueri ke dalam URL.</span><span class="sxs-lookup"><span data-stu-id="ddd69-128">You must URL encode the query parameter values.</span></span>

| <span data-ttu-id="ddd69-129">Nama</span><span class="sxs-lookup"><span data-stu-id="ddd69-129">Name</span></span> | <span data-ttu-id="ddd69-130">Nilai</span><span class="sxs-lookup"><span data-stu-id="ddd69-130">Value</span></span> | <span data-ttu-id="ddd69-131">Jenis</span><span class="sxs-lookup"><span data-stu-id="ddd69-131">Type</span></span> | <span data-ttu-id="ddd69-132">Diperlukan</span><span class="sxs-lookup"><span data-stu-id="ddd69-132">Required</span></span> |
|------|-------|------|----------|
| <span data-ttu-id="ddd69-133">bahasa</span><span class="sxs-lookup"><span data-stu-id="ddd69-133">locale</span></span> | <span data-ttu-id="ddd69-134">Kode bahasa yang valid dari [daftar bahasa yang didukung](https://docs.microsoft.com/locale/), misalnya 'id-id'.</span><span class="sxs-lookup"><span data-stu-id="ddd69-134">A valid locale code from the [supported list of locales](https://docs.microsoft.com/locale/), for example 'en-us'.</span></span> <span data-ttu-id="ddd69-135">Metadata yang diberikan akan disajikan dalam bahasa yang diminta jika tersedia.</span><span class="sxs-lookup"><span data-stu-id="ddd69-135">The returned metadata will be in the requested locale if available.</span></span> <span data-ttu-id="ddd69-136">Jika parameter ini tidak ditentukan, default 'id-id' akan digunakan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-136">If this parameter isn't supplied, a default of 'en-us' will be used.</span></span> | <span data-ttu-id="ddd69-137">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-137">string</span></span> | <span data-ttu-id="ddd69-138">Tidak</span><span class="sxs-lookup"><span data-stu-id="ddd69-138">No</span></span> |

## <a name="api-response"></a><span data-ttu-id="ddd69-139">Respons API</span><span class="sxs-lookup"><span data-stu-id="ddd69-139">API Response</span></span>

<span data-ttu-id="ddd69-140">Layanan dapat mengembalikan kode status HTTP berikut.</span><span class="sxs-lookup"><span data-stu-id="ddd69-140">The service may return the following HTTP status codes.</span></span>

| <span data-ttu-id="ddd69-141">Kode status</span><span class="sxs-lookup"><span data-stu-id="ddd69-141">Status code</span></span> | <span data-ttu-id="ddd69-142">Deskripsi</span><span class="sxs-lookup"><span data-stu-id="ddd69-142">Description</span></span> |
|-------------|-------------|
| <span data-ttu-id="ddd69-143">200</span><span class="sxs-lookup"><span data-stu-id="ddd69-143">200</span></span> | <span data-ttu-id="ddd69-144">Berhasil.</span><span class="sxs-lookup"><span data-stu-id="ddd69-144">Success.</span></span> <span data-ttu-id="ddd69-145">Isi respons mencakup data dalam kode JSON.</span><span class="sxs-lookup"><span data-stu-id="ddd69-145">The body of the response includes the JSON-encoded data.</span></span> |
| <span data-ttu-id="ddd69-146">400</span><span class="sxs-lookup"><span data-stu-id="ddd69-146">400</span></span> | <span data-ttu-id="ddd69-147">Salah satu parameter kueri tidak valid atau tidak ditemukan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-147">One of the query parameters is missing or not valid.</span></span> |
| <span data-ttu-id="ddd69-148">404</span><span class="sxs-lookup"><span data-stu-id="ddd69-148">404</span></span> | <span data-ttu-id="ddd69-149">URL tidak ditemukan di server.</span><span class="sxs-lookup"><span data-stu-id="ddd69-149">The URL wasn't found on the server.</span></span> |
| <span data-ttu-id="ddd69-150">500</span><span class="sxs-lookup"><span data-stu-id="ddd69-150">500</span></span> | <span data-ttu-id="ddd69-151">Kesalahan server tidak terduga.</span><span class="sxs-lookup"><span data-stu-id="ddd69-151">Unexpected server error.</span></span> |
| <span data-ttu-id="ddd69-152">503</span><span class="sxs-lookup"><span data-stu-id="ddd69-152">503</span></span> | <span data-ttu-id="ddd69-153">Layanan tidak tersedia untuk sementara.</span><span class="sxs-lookup"><span data-stu-id="ddd69-153">The service is temporarily unavailable.</span></span> |

<span data-ttu-id="ddd69-154">Respons yang berhasil akan mencakup detail tentang semua modul dan jalur pembelajaran, seperti yang ditunjukkan di bawah ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-154">A successful response will include details about all modules and learning paths, as shown below.</span></span>

> [!TIP]
> <span data-ttu-id="ddd69-155">Sebaiknya simpan respons dan refresh tampilan data secara berkala, tidak hanya ketika diperlukan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-155">It's highly recommended to cache the response and refresh the view of the data on periodic intervals rather than every time it's needed.</span></span>

### <a name="response-body"></a><span data-ttu-id="ddd69-156">Isi respons</span><span class="sxs-lookup"><span data-stu-id="ddd69-156">Response body</span></span>

<span data-ttu-id="ddd69-157">Isi respons yang sukses akan dikodekan dalam JSON dan memiliki lima bagian:</span><span class="sxs-lookup"><span data-stu-id="ddd69-157">A successful response body will be encoded in JSON and have five sections:</span></span>

```json
{
    "modules": [ ... ],
    "learningPaths": [ ... ],
    "products": [ ... ],
    "roles": [ ... ],
    "levels": [ ... ]
}
```

<span data-ttu-id="ddd69-158">Setiap larik memiliki satu atau beberapa objek dalam kode JSON yang berisi data khusus untuk bagian respons tersebut.</span><span class="sxs-lookup"><span data-stu-id="ddd69-158">Each array has one or more JSON-encoded objects containing data specific to that section of the response.</span></span>

1. <span data-ttu-id="ddd69-159">`modules`: adalah larik modul yang diterbitkan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-159">`modules`: is an array of published modules.</span></span>
1. <span data-ttu-id="ddd69-160">`learningPaths`: adalah larik jalur pembelajaran yang diterbitkan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-160">`learningPaths`: is an array of published learning paths.</span></span>
1. <span data-ttu-id="ddd69-161">`levels`: adalah larik kemungkinan tingkat audiens.</span><span class="sxs-lookup"><span data-stu-id="ddd69-161">`levels`: is an array of possible audience levels.</span></span>
1. <span data-ttu-id="ddd69-162">`roles`: adalah larik kemungkinan jabatan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-162">`roles`: is an array of possible job roles.</span></span>
1. <span data-ttu-id="ddd69-163">`products`: adalah larik produk dan layanan yang tercakup dalam modul yang diterbitkan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-163">`products`: is an array of products and services covered in published modules.</span></span>

### <a name="module-records"></a><span data-ttu-id="ddd69-164">Data modul</span><span class="sxs-lookup"><span data-stu-id="ddd69-164">Module records</span></span>

<span data-ttu-id="ddd69-165">Setiap modul akan memiliki bentuk berikut:</span><span class="sxs-lookup"><span data-stu-id="ddd69-165">Each module will have the following form:</span></span>

```json
{
    "summary": "<p sourcefile=\"azure/principles-cloud-computing/index.yml\" sourcestartlinenumber=\"1\" jsonPath=\"/summary\">Explore the core concepts of cloud computing and how it can help your business.</p>\n",
    "levels": [
        "beginner"
    ],
    "roles": [
        "administrator",
        "business-analyst",
        "developer"
    ],
    "products": [
        "azure",
        "azure-portal",
        "azure-resource-manager"
    ],
    "uid": "learn.principles-cloud-computing",
    "type": "module",
    "title": "Cloud Concepts - Principles of cloud computing",
    "duration_in_minutes": 62,
    "rating": {
        count: 2014,
        average: 4.84
    },
    "popularity": 0.8839785477023878, 
    "icon_url": "https://docs.microsoft.com/learn/achievements/principles-cloud-computing.svg",
    "locale": "en-us",
    "last_modified": "2018-09-24T00:00:00Z",
    "url": "https://docs.microsoft.com/en-us/learn/modules/principles-cloud-computing",
    "firstUnitUrl": "https://docs.microsoft.com/en-us/learn/modules/principles-cloud-computing/1-introduction",
    "number_of_children": 10
}
```

| <span data-ttu-id="ddd69-166">Bidang</span><span class="sxs-lookup"><span data-stu-id="ddd69-166">Field</span></span> | <span data-ttu-id="ddd69-167">Jenis</span><span class="sxs-lookup"><span data-stu-id="ddd69-167">Type</span></span> | <span data-ttu-id="ddd69-168">Deskripsi</span><span class="sxs-lookup"><span data-stu-id="ddd69-168">Description</span></span> |
|-------|------|-------------|
| `summary` | <span data-ttu-id="ddd69-169">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-169">string</span></span> | <span data-ttu-id="ddd69-170">String yang menyediakan deskripsi singkat tentang modul.</span><span class="sxs-lookup"><span data-stu-id="ddd69-170">A string that provides a short description of the module.</span></span> <span data-ttu-id="ddd69-171">Nilai disajikan sebagai tag paragraf HTML dengan ringkasan di teks bagian dalam.</span><span class="sxs-lookup"><span data-stu-id="ddd69-171">The value is expressed as an HTML paragraph tag with the inner text being the summary.</span></span> |
| `levels` | <span data-ttu-id="ddd69-172">larik string</span><span class="sxs-lookup"><span data-stu-id="ddd69-172">array of strings</span></span> | <span data-ttu-id="ddd69-173">Menunjukkan banyaknya pengalaman dalam peran yang diperlukan untuk memahami semua aspek modul ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-173">Indicates how much experience in the role is necessary to understand all aspects of this module.</span></span> |
| `roles` | <span data-ttu-id="ddd69-174">larik string</span><span class="sxs-lookup"><span data-stu-id="ddd69-174">array of strings</span></span> | <span data-ttu-id="ddd69-175">Daftar jabatan yang relevan dengan modul ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-175">A list of the job roles that this module is relevant to.</span></span> |
| `products` | <span data-ttu-id="ddd69-176">larik string</span><span class="sxs-lookup"><span data-stu-id="ddd69-176">array of strings</span></span> | <span data-ttu-id="ddd69-177">Daftar produk relevan yang dicakup dalam modul ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-177">A list of relevant products this module covers.</span></span> |
| `uid` | <span data-ttu-id="ddd69-178">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-178">string</span></span> | <span data-ttu-id="ddd69-179">Pengidentifikasi unik untuk modul ini - nilai ini bersifat unik di seluruh MS Learn.</span><span class="sxs-lookup"><span data-stu-id="ddd69-179">A unique identifier for this module - this value will be unique across all of MS Learn.</span></span> |
| `type` | <span data-ttu-id="ddd69-180">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-180">string</span></span> | <span data-ttu-id="ddd69-181">Tipe data.</span><span class="sxs-lookup"><span data-stu-id="ddd69-181">The type of record.</span></span> <span data-ttu-id="ddd69-182">Nilainya akan selalu 'module'.</span><span class="sxs-lookup"><span data-stu-id="ddd69-182">The value will always be 'module'.</span></span> |
| `title` | <span data-ttu-id="ddd69-183">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-183">string</span></span> | <span data-ttu-id="ddd69-184">Judul modul dalam bahasa yang diminta, atau bahasa Inggris AS sebagai alternatif.</span><span class="sxs-lookup"><span data-stu-id="ddd69-184">The title for the module in the locale requested, or US English as a fallback.</span></span> |
| `duration_in_minutes` | <span data-ttu-id="ddd69-185">integer</span><span class="sxs-lookup"><span data-stu-id="ddd69-185">integer</span></span> | <span data-ttu-id="ddd69-186">Waktu rata-rata yang diperlukan untuk menyelesaikan modul ini dalam hitungan menit.</span><span class="sxs-lookup"><span data-stu-id="ddd69-186">The average time this module takes to complete in minutes.</span></span> |
| `rating` | <span data-ttu-id="ddd69-187">objek</span><span class="sxs-lookup"><span data-stu-id="ddd69-187">object</span></span> | <span data-ttu-id="ddd69-188">Tipe data ini berisi `count`, yaitu jumlah orang yang telah menilai modul, dan `average`, yang merupakan gabungan nilai, yaitu 1-5</span><span class="sxs-lookup"><span data-stu-id="ddd69-188">This contains both `count`, which is the number of people who have rated the module, and `average`, an aggregate of the ratings, which will be 1-5</span></span> |
| `popularity` | <span data-ttu-id="ddd69-189">double</span><span class="sxs-lookup"><span data-stu-id="ddd69-189">double</span></span> | <span data-ttu-id="ddd69-190">Nilai yang dinormalkan dari 0-1 menunjukkan popularitas modul</span><span class="sxs-lookup"><span data-stu-id="ddd69-190">A normalized value from 0-1 indicating the popularity of the module</span></span> | 
| `icon_url` | <span data-ttu-id="ddd69-191">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-191">string</span></span> | <span data-ttu-id="ddd69-192">URL yang sepenuhnya memenuhi syarat untuk gambar **.svg** atau **.png** berukuran 100x100 yang mewakili modul.</span><span class="sxs-lookup"><span data-stu-id="ddd69-192">A fully qualified URL to a 100x100 **.svg** or **.png** image that represents the module.</span></span> |
| `locale` | <span data-ttu-id="ddd69-193">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-193">string</span></span> | <span data-ttu-id="ddd69-194">Bahasa yang digunakan dalam data JSON ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-194">The language this JSON data is written in.</span></span> <span data-ttu-id="ddd69-195">Nilai ini akan menggunakan bahasa yang diminta jika tersedia, jika tidak 'en-us'.</span><span class="sxs-lookup"><span data-stu-id="ddd69-195">This value will be the requested locale if available, or 'en-us' if not.</span></span> |
| `last_modified` | <span data-ttu-id="ddd69-196">tanggal</span><span class="sxs-lookup"><span data-stu-id="ddd69-196">date</span></span> | <span data-ttu-id="ddd69-197">Terakhir kali modul ini mendapat revisi besar.</span><span class="sxs-lookup"><span data-stu-id="ddd69-197">The last time this module had a major revision.</span></span> |
| `url` | <span data-ttu-id="ddd69-198">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-198">string</span></span> | <span data-ttu-id="ddd69-199">URL yang sepenuhnya memenuhi syarat untuk modul di Microsoft Learn dalam bahasa yang diminta.</span><span class="sxs-lookup"><span data-stu-id="ddd69-199">A fully qualified URL to the module in Microsoft Learn in the requested locale.</span></span> |
| `firstUnitUrl` | <span data-ttu-id="ddd69-200">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-200">string</span></span> | <span data-ttu-id="ddd69-201">URL yang sepenuhnya memenuhi syarat untuk unit pertama modul di Microsoft Learn dalam bahasa yang diminta.</span><span class="sxs-lookup"><span data-stu-id="ddd69-201">A fully qualified URL to the first unit of the module in Microsoft Learn in the requested locale.</span></span> |
| `number_of_children` | <span data-ttu-id="ddd69-202">integer</span><span class="sxs-lookup"><span data-stu-id="ddd69-202">integer</span></span> | <span data-ttu-id="ddd69-203">Jumlah halaman (unit) yang dimiliki modul ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-203">The number of pages (units) this module has in it.</span></span> |

### <a name="learning-path-records"></a><span data-ttu-id="ddd69-204">Data jalur pembelajaran</span><span class="sxs-lookup"><span data-stu-id="ddd69-204">Learning path records</span></span>

<span data-ttu-id="ddd69-205">Setiap Jalur pembelajaran akan memiliki bentuk berikut:</span><span class="sxs-lookup"><span data-stu-id="ddd69-205">Each Learning path will have the following form:</span></span>

```json
{
    "summary": "<p sourcefile=\"paths/create-serverless-applications/index.yml\" sourcestartlinenumber=\"1\" jsonPath=\"/summary\">Azure Functions enable the creation of event driven, compute-on-demand systems that can be triggered by various external events. Learn how to leverage functions to execute server-side logic and build serverless architectures.</p>\n",
    "levels": [
        "beginner",
        "intermediate"
    ],
    "roles": [
        "developer",
        "solution-architect"
    ],
    "products": [
        "azure",
        "azure-portal",
        "azure-functions",
        "azure-cosmos-db",
        "azure-cloud-shell"
    ],
    "uid": "learn.create-serverless-applications",
    "type": "learningPath",
    "title": "Create serverless applications",
    "duration_in_minutes": 450,
    "rating": {
        count: 2014,
        average: 4.84
    },
    "popularity": 0.8839785477023878, 
    "icon_url": "https://docs.microsoft.com/learn/achievements/create-serverless-applications.svg",
    "locale": "en-us",
    "last_modified": "2018-12-27T00:00:00Z",
    "url": "https://docs.microsoft.com/en-us/learn/paths/create-serverless-applications",
    "firstModuleUrl": "https://docs.microsoft.com/en-us/learn/modules/choose-azure-service-to-integrate-and-automate-business-processes/",
    "modules": [
        "learn.choose-azure-service-to-integrate-and-automate-business-processes",
        "learn.create-serverless-logic-with-functions",
        "learn.execute-azure-function-with-triggers",
        "learn.chain-azure-functions-data-using-input-output-bindings",
        "learn.azure-create-long-running-serverless-workflow-with-durable-functions",
        "learn-pr.develop-test-deploy-azure-functions-core-tools",
        "learn.develop-test-deploy-azure-functions-with-visual-studio",
        "learn.azure.monitor-github-events-with-a-function-triggered-by-a-webhook",
        "learn.advocates.azure-functions-and-signalr"
    ],
    "number_of_children": 9
}
```

| <span data-ttu-id="ddd69-206">Bidang</span><span class="sxs-lookup"><span data-stu-id="ddd69-206">Field</span></span> | <span data-ttu-id="ddd69-207">Jenis</span><span class="sxs-lookup"><span data-stu-id="ddd69-207">Type</span></span> | <span data-ttu-id="ddd69-208">Deskripsi</span><span class="sxs-lookup"><span data-stu-id="ddd69-208">Description</span></span> |
|-------|------|-------------|
| `summary` | <span data-ttu-id="ddd69-209">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-209">string</span></span> | <span data-ttu-id="ddd69-210">String yang menyediakan deskripsi singkat tentang jalur pembelajaran.</span><span class="sxs-lookup"><span data-stu-id="ddd69-210">A string that provides a short description of the learning path.</span></span> <span data-ttu-id="ddd69-211">Nilai disajikan sebagai tag paragraf HTML dengan ringkasan di teks bagian dalam.</span><span class="sxs-lookup"><span data-stu-id="ddd69-211">The value is expressed as an HTML paragraph tag with the inner text being the summary.</span></span> |
| `levels` | <span data-ttu-id="ddd69-212">larik string</span><span class="sxs-lookup"><span data-stu-id="ddd69-212">array of strings</span></span> | <span data-ttu-id="ddd69-213">Menunjukkan banyaknya pengalaman dalam peran yang diperlukan untuk memahami semua aspek jalur pembelajaran ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-213">Indicates how much experience in the role is necessary to understand all aspects of this learning path.</span></span> <span data-ttu-id="ddd69-214">Larik ini akan berisi satu atau beberapa nilai berdasarkan modul yang disertakan dalam jalur.</span><span class="sxs-lookup"><span data-stu-id="ddd69-214">This array will contain one or more values based on the modules included in the path.</span></span> |
| `roles` | <span data-ttu-id="ddd69-215">larik string</span><span class="sxs-lookup"><span data-stu-id="ddd69-215">array of strings</span></span> | <span data-ttu-id="ddd69-216">Daftar jabatan yang relevan untuk jalur pembelajaran ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-216">A list of the relevant job roles for this learning path.</span></span> |
| `products` | <span data-ttu-id="ddd69-217">larik string</span><span class="sxs-lookup"><span data-stu-id="ddd69-217">array of strings</span></span> | <span data-ttu-id="ddd69-218">Daftar produk relevan yang dicakup dalam jalur pembelajaran ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-218">A list of relevant products this learning path covers.</span></span> |
| `uid` | <span data-ttu-id="ddd69-219">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-219">string</span></span> | <span data-ttu-id="ddd69-220">Pengidentifikasi unik untuk jalur pembelajaran ini - nilai ini bersifat unik di seluruh MS Learn.</span><span class="sxs-lookup"><span data-stu-id="ddd69-220">A unique identifier for this learning path - this value will be unique across all of MS Learn.</span></span> |
| `type` | <span data-ttu-id="ddd69-221">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-221">string</span></span> | <span data-ttu-id="ddd69-222">Tipe data.</span><span class="sxs-lookup"><span data-stu-id="ddd69-222">The type of record.</span></span> <span data-ttu-id="ddd69-223">Nilainya selalu 'learningPath'.</span><span class="sxs-lookup"><span data-stu-id="ddd69-223">The value will always be 'learningPath'.</span></span> |
| `title` | <span data-ttu-id="ddd69-224">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-224">string</span></span> | <span data-ttu-id="ddd69-225">Judul jalur pembelajaran dalam bahasa yang diminta, atau bahasa Inggris AS sebagai alternatif.</span><span class="sxs-lookup"><span data-stu-id="ddd69-225">The title for the learning path in the locale requested, or US English as a fallback.</span></span> |
| `duration_in_minutes` | <span data-ttu-id="ddd69-226">integer</span><span class="sxs-lookup"><span data-stu-id="ddd69-226">integer</span></span> | <span data-ttu-id="ddd69-227">Waktu rata-rata yang diperlukan untuk menyelesaikan jalur pembelajaran ini dalam hitungan menit.</span><span class="sxs-lookup"><span data-stu-id="ddd69-227">The average time this learning path takes to complete in minutes.</span></span> <span data-ttu-id="ddd69-228">Nilai ini merupakan jumlah data dari semua modul yang disertakan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-228">This value is a sum of data from all the modules included.</span></span> |
| `rating` | <span data-ttu-id="ddd69-229">objek</span><span class="sxs-lookup"><span data-stu-id="ddd69-229">object</span></span> | <span data-ttu-id="ddd69-230">Tipe data ini berisi `count`, yaitu jumlah orang yang telah menilai jalur pembelajaran, dan `average`, yang merupakan gabungan nilai, yaitu 1-5</span><span class="sxs-lookup"><span data-stu-id="ddd69-230">This contains both `count`, which is the number of people who have rated the learning path, and `average`, an aggregate of the ratings, which will be 1-5</span></span> |
| `popularity` | <span data-ttu-id="ddd69-231">double</span><span class="sxs-lookup"><span data-stu-id="ddd69-231">double</span></span> | <span data-ttu-id="ddd69-232">Nilai yang dinormalkan dari 0-1 menunjukkan popularitas jalur pembelajaran</span><span class="sxs-lookup"><span data-stu-id="ddd69-232">A normalized value from 0-1 indicating the popularity of the learning path</span></span> | 
| `icon_url` | <span data-ttu-id="ddd69-233">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-233">string</span></span> | <span data-ttu-id="ddd69-234">URL yang sepenuhnya memenuhi syarat untuk gambar **.svg** atau **.png** berukuran 100x100 yang mewakili jalur pembelajaran.</span><span class="sxs-lookup"><span data-stu-id="ddd69-234">A fully qualified URL to a 100x100 **.svg** or **.png** image that represents the learning path.</span></span> |
| `locale` | <span data-ttu-id="ddd69-235">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-235">string</span></span> | <span data-ttu-id="ddd69-236">Bahasa yang digunakan dalam data JSON ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-236">The language this JSON data is written in.</span></span> <span data-ttu-id="ddd69-237">Nilai ini akan menggunakan bahasa yang diminta jika tersedia, jika tidak 'en-us'.</span><span class="sxs-lookup"><span data-stu-id="ddd69-237">This value will be the requested locale if available, or 'en-us' if not.</span></span> |
| `last_modified` | <span data-ttu-id="ddd69-238">tanggal</span><span class="sxs-lookup"><span data-stu-id="ddd69-238">date</span></span> | <span data-ttu-id="ddd69-239">Terakhir kali jalur pembelajaran ini diubah.</span><span class="sxs-lookup"><span data-stu-id="ddd69-239">The last time this learning path was changed.</span></span> |
| `url` | <span data-ttu-id="ddd69-240">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-240">string</span></span> | <span data-ttu-id="ddd69-241">URL yang sepenuhnya memenuhi syarat untuk jalur pembelajaran di Microsoft Learn dalam bahasa yang diminta.</span><span class="sxs-lookup"><span data-stu-id="ddd69-241">A fully qualified URL to the learning path in Microsoft Learn in the requested locale.</span></span> |
| `firstModuleUrl` | <span data-ttu-id="ddd69-242">string</span><span class="sxs-lookup"><span data-stu-id="ddd69-242">string</span></span> | <span data-ttu-id="ddd69-243">URL yang sepenuhnya memenuhi syarat untuk modul pertama jalur pembelajaran di Microsoft Learn dalam bahasa yang diminta.</span><span class="sxs-lookup"><span data-stu-id="ddd69-243">A fully qualified URL to the first module of the learning path in Microsoft Learn in the requested locale.</span></span> |
| `modules` | <span data-ttu-id="ddd69-244">larik string</span><span class="sxs-lookup"><span data-stu-id="ddd69-244">array of strings</span></span> | <span data-ttu-id="ddd69-245">Daftar pengidentifikasi modul (uid) yang disertakan dalam jalur pembelajaran ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-245">The list of module identifiers (uid's) included in this learning path.</span></span> |
| `number_of_children` | <span data-ttu-id="ddd69-246">integer</span><span class="sxs-lookup"><span data-stu-id="ddd69-246">integer</span></span> | <span data-ttu-id="ddd69-247">Jumlah modul yang dimiliki jalur pembelajaran ini.</span><span class="sxs-lookup"><span data-stu-id="ddd69-247">The number of modules this learning path has in it.</span></span> |

### <a name="product-role-and-level-records"></a><span data-ttu-id="ddd69-248">Data produk, peran, dan tingkat</span><span class="sxs-lookup"><span data-stu-id="ddd69-248">Product, role, and level records</span></span>

<span data-ttu-id="ddd69-249">Kumpulan `levels`, `roles`, dan `products` menyediakan nama yang umum untuk nilai yang digunakan dalam data modul dan jalur pembelajaran.</span><span class="sxs-lookup"><span data-stu-id="ddd69-249">The `levels`, `roles`, and `products` collections provide friendly names for the values used in the module and learning path data.</span></span> <span data-ttu-id="ddd69-250">Ketiga kumpulan tersebut memiliki bentuk yang sama:</span><span class="sxs-lookup"><span data-stu-id="ddd69-250">All three collections have the same shape:</span></span>

```json
{
    "id": "unique-id",
    "name": "name-of-item",
    "children": [
        { "id": "unique-id", "name": "name-of-item" },
        { "id": "unique-id", "name": "name-of-item" },
           ...
    ]
}
```

<span data-ttu-id="ddd69-251">`id` akan menyesuaikan nilai untuk tingkat, peran, dan produk yang termasuk dalam setiap modul dan jalur pembelajaran.</span><span class="sxs-lookup"><span data-stu-id="ddd69-251">The `id` will match the values for levels, roles, and products included in each module and learning path.</span></span> <span data-ttu-id="ddd69-252">`name` yang terkait menyediakan nama yang tepat dalam bahasa Inggris untuk entri tersebut.</span><span class="sxs-lookup"><span data-stu-id="ddd69-252">The associated `name` provides a proper name in English for the entry.</span></span> <span data-ttu-id="ddd69-253">Larik `children` bersifat opsional dan memungkinkan hierarkis untuk nilai yang memiliki hubungan turunan seperti produk.</span><span class="sxs-lookup"><span data-stu-id="ddd69-253">The `children` array is optional and enables hierarchical for values that have child relationships such as products.</span></span>

<span data-ttu-id="ddd69-254">Misalnya, berikut adalah sekumpulan peran yang mungkin digunakan:</span><span class="sxs-lookup"><span data-stu-id="ddd69-254">As an example, here is a set of possible roles:</span></span>

```json
{
    ...
    "roles": [
        {
            "id": "administrator",
            "name": "Administrator"
        },
        {
            "id": "ai-engineer",
            "name": "AI Engineer"
        },
        {
            "id": "business-analyst",
            "name": "Business Analyst"
        },
        {
            "id": "developer",
            "name": "Developer"
        },
        ...
    ]
}
```

<span data-ttu-id="ddd69-255">Berikut adalah contoh kumpulan produk, dengan turunan yang disertakan untuk memberikan kategori produk yang lebih spesifik.</span><span class="sxs-lookup"><span data-stu-id="ddd69-255">Here is an example set of products, with children included to provide a more specific product category.</span></span>

```json
{
    ...
    "products": [
        {
            "id": "dotnet",
            "name": ".NET",
            "children": [
                { "id": "dotnet-core", "name": ".NET Core" },
                { "id": "dotnet-standard", "name": ".NET Standard" },
                { "id": "aspnet-core", "name": "ASP.NET Core" },
                { "id": "ef-core", "name": "Entity Framework Core" }
            ]
        },
        {
            "id": "ms-graph",
            "name": "Microsoft Graph"
        },
        {
            "id": "office",
            "name": "Office",
            "children": [
                { "id": "office-365", "name": "Office 365" },
                { "id": "office-add-ins", "name": "Office Add-ins" },
                { "id": "office-teams", "name": "Teams" }
            ]
        },
        {
            "id": "sql-server",
            "name": "SQL Server"
        },
        ...
    ]
}

```

## <a name="catalog-lti-provider"></a><span data-ttu-id="ddd69-256">Penyedia LTI Katalog</span><span class="sxs-lookup"><span data-stu-id="ddd69-256">Catalog LTI Provider</span></span>

<span data-ttu-id="ddd69-257">Ingin mengintegrasikan Catalog API ke dalam Sistem Manajemen Pembelajaran (LMS)?</span><span class="sxs-lookup"><span data-stu-id="ddd69-257">Looking to integrate the Catalog API into a Learning Management System (LMS)?</span></span> <span data-ttu-id="ddd69-258">Lihat [Aplikasi LTI](lti-application.md) sumber terbuka kami.</span><span class="sxs-lookup"><span data-stu-id="ddd69-258">Check out our open sourced [LTI Application](lti-application.md).</span></span>

<span data-ttu-id="ddd69-259">Kami membuat kode referensi yang mengubah Catalog API menjadi penyedia LTI.</span><span class="sxs-lookup"><span data-stu-id="ddd69-259">We created reference code that turns the Catalog API into a LTI provider.</span></span> <span data-ttu-id="ddd69-260">Anda dapat dengan cepat memodifikasi atau menginstal aplikasi secara langsung ke LMS Anda.</span><span class="sxs-lookup"><span data-stu-id="ddd69-260">You can quickly make modifications or install the application directly into your LMS.</span></span> <span data-ttu-id="ddd69-261">Aplikasi LTI memungkinkan Anda mengintegrasikan modul Microsoft Learn ke dalam kurikulum yang ada sekaligus memberikan pengalaman langsung dengan Azure dan teknologi Microsoft lainnya.</span><span class="sxs-lookup"><span data-stu-id="ddd69-261">The LTI application will allow you to integrate Microsoft Learn modules into your existing curricula while providing hands-on experiences with Azure and other Microsoft technology.</span></span> <span data-ttu-id="ddd69-262">Pelajar akan diarahkan dari LMS Anda ke Microsoft Learn untuk mengumpulkan poin pengalaman dan pencapaian, serta melacak kemajuan pada aktivitas pembelajaran.</span><span class="sxs-lookup"><span data-stu-id="ddd69-262">Learners will be routed from your LMS to Microsoft Learn, where they can accrue points and achievements and track progress on learning activities.</span></span>


## <a name="catalog-api-program"></a><span data-ttu-id="ddd69-263">Program Catalog API</span><span class="sxs-lookup"><span data-stu-id="ddd69-263">Catalog API program</span></span>

<span data-ttu-id="ddd69-264">Apakah Anda mengintegrasikan konten Microsoft Learn ke dalam platform pembelajaran Anda?</span><span class="sxs-lookup"><span data-stu-id="ddd69-264">Are you integrating Microsoft Learn content into your learning platform?</span></span> <span data-ttu-id="ddd69-265">Daftar [Program Catalog API (CAP)](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR-4aRF51x15HqVFOq2xnAkBUMUJJWFVZWDdUNFQ0TTRaTlA2VVowRDVFSS4u) agar tim kami dapat membantu memastikan pengalaman integrasi yang terbaik dan mendapatkan masukan Anda terkait versi Catalog API mendatang.</span><span class="sxs-lookup"><span data-stu-id="ddd69-265">Apply for the [Catalog API (CAP) Program](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR-4aRF51x15HqVFOq2xnAkBUMUJJWFVZWDdUNFQ0TTRaTlA2VVowRDVFSS4u) so our team can help ensure the best integration experience and get your input on future versions of the Catalog API.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="ddd69-266">Umpan balik dan Dukungan</span><span class="sxs-lookup"><span data-stu-id="ddd69-266">Feedback and Support</span></span>

<span data-ttu-id="ddd69-267">Catalog API saat ini tersedia tanpa perjanjian tingkat layanan.</span><span class="sxs-lookup"><span data-stu-id="ddd69-267">The Catalog API is currently available without a service level agreement.</span></span> <span data-ttu-id="ddd69-268">Jika memiliki saran atau mengalami masalah saat menggunakan API, Anda dapat [memberikan umpan balik kepada tim kami.](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR_cebFBRf_dAnuWExXCcHVJUQU1PSDBONVc4WDZIN1RDTE1ISk41NlRJNi4u)</span><span class="sxs-lookup"><span data-stu-id="ddd69-268">If you have suggestions or come across a problem using the API, you can [give the team feedback](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR_cebFBRf_dAnuWExXCcHVJUQU1PSDBONVc4WDZIN1RDTE1ISk41NlRJNi4u).</span></span>
