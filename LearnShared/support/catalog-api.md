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
# <a name="microsoft-learn-catalog-api"></a>Microsoft Learn Catalog API

Microsoft Learn Catalog API memungkinkan Anda mengirim kueri berbasis web ke Microsoft Learn dan mendapatkan detail tentang konten yang diterbitkan seperti judul, produk yang dibahas, dan tautan ke pelatihan. Pelanggan dapat menggunakan informasi yang diberikan dan menampilkannya dalam sistem manajemen pembelajaran (LMS) mereka dengan konten pelatihan lainnya.

> [!NOTE]
> Pelanggan dapat menggunakan API ini untuk menampilkan informasi tentang pelatihan yang tersedia, tetapi pelatihan harus diselesaikan di Microsoft Learn.

Catalog API ditawarkan berdasarkan [Ketentuan Penggunaan API Microsoft.](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use) Halaman ini menyediakan detail teknis terkait API dan cara menginterpretasikan informasi yang ditampilkan.

## <a name="modules-and-learning-paths"></a>Modul dan Jalur Pembelajaran

Konten di Microsoft Learn diatur menurut dua elemen: yaitu _modul_ dan _jalur pembelajaran_.

### <a name="modules"></a>Modul

_Modul_ adalah konten pelatihan yang sebenarnya. Satu modul terdiri dari beberapa halaman web yang menjelaskan tentang layanan atau teknologi dan sering kali memberikan beberapa bentuk interaktivitas untuk mencoba teknologi tersebut. Setiap modul memiliki metadata terkait untuk dengan cepat mengidentifikasi target modulnya, isi yang dibahas, dan waktu yang diperlukan untuk menyelesaikannya. Detail ini dapat ditemukan di ubin grafis pada [halaman penelusuran Microsoft Learn](https://docs.microsoft.com/learn/browse), seperti yang diperlihatkan dalam cuplikan layar berikut ini.

![Cuplikan layar memperlihatkan satu modul dengan semua detail dari situs web Microsoft Learn](media/module-details.png)

### <a name="learning-paths"></a>Jalur Pembelajaran

_Jalur pembelajaran_ adalah kumpulan modul terkait yang disajikan dalam urutan tertentu sehingga modul tersebut saling melengkapi untuk mengajarkan topik yang lebih luas. Jalur pembelajaran juga menyertakan metadata deskriptif yang mirip dengan modul, seperti yang ditunjukkan pada cuplikan layar dari halaman penelusuran di bawah ini.

![Cuplikan layar memperlihatkan jalur pembelajaran dari situs web Microsoft Learn](media/learning-path-details.png)

## <a name="api-endpoint"></a>Titik akhir API

Microsoft Learn Catalog API adalah API Web berbasis REST yang memberikan respons dalam kode JSON.

Untuk meminta katalog lengkap modul dan jalur pembelajaran, kirim permintaan GET ke:

```html
https://docs.microsoft.com/api/learn/catalog/
```

> [!IMPORTANT]
> Permintaan harus menggunakan protokol HTTPS.

### <a name="query-parameters"></a>Parameter kueri

Berikut adalah parameter kueri yang dapat disertakan dalam permintaan. Kolom **Wajib diisi** menunjukkan bahwa Anda harus menentukan parameter. Anda harus mengodekan nilai parameter kueri ke dalam URL.

| Nama | Nilai | Jenis | Diperlukan |
|------|-------|------|----------|
| bahasa | Kode bahasa yang valid dari [daftar bahasa yang didukung](https://docs.microsoft.com/locale/), misalnya 'id-id'. Metadata yang diberikan akan disajikan dalam bahasa yang diminta jika tersedia. Jika parameter ini tidak ditentukan, default 'id-id' akan digunakan. | string | Tidak |

## <a name="api-response"></a>Respons API

Layanan dapat mengembalikan kode status HTTP berikut.

| Kode status | Deskripsi |
|-------------|-------------|
| 200 | Berhasil. Isi respons mencakup data dalam kode JSON. |
| 400 | Salah satu parameter kueri tidak valid atau tidak ditemukan. |
| 404 | URL tidak ditemukan di server. |
| 500 | Kesalahan server tidak terduga. |
| 503 | Layanan tidak tersedia untuk sementara. |

Respons yang berhasil akan mencakup detail tentang semua modul dan jalur pembelajaran, seperti yang ditunjukkan di bawah ini.

> [!TIP]
> Sebaiknya simpan respons dan refresh tampilan data secara berkala, tidak hanya ketika diperlukan.

### <a name="response-body"></a>Isi respons

Isi respons yang sukses akan dikodekan dalam JSON dan memiliki lima bagian:

```json
{
    "modules": [ ... ],
    "learningPaths": [ ... ],
    "products": [ ... ],
    "roles": [ ... ],
    "levels": [ ... ]
}
```

Setiap larik memiliki satu atau beberapa objek dalam kode JSON yang berisi data khusus untuk bagian respons tersebut.

1. `modules`: adalah larik modul yang diterbitkan.
1. `learningPaths`: adalah larik jalur pembelajaran yang diterbitkan.
1. `levels`: adalah larik kemungkinan tingkat audiens.
1. `roles`: adalah larik kemungkinan jabatan.
1. `products`: adalah larik produk dan layanan yang tercakup dalam modul yang diterbitkan.

### <a name="module-records"></a>Data modul

Setiap modul akan memiliki bentuk berikut:

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

| Bidang | Jenis | Deskripsi |
|-------|------|-------------|
| `summary` | string | String yang menyediakan deskripsi singkat tentang modul. Nilai disajikan sebagai tag paragraf HTML dengan ringkasan di teks bagian dalam. |
| `levels` | larik string | Menunjukkan banyaknya pengalaman dalam peran yang diperlukan untuk memahami semua aspek modul ini. |
| `roles` | larik string | Daftar jabatan yang relevan dengan modul ini. |
| `products` | larik string | Daftar produk relevan yang dicakup dalam modul ini. |
| `uid` | string | Pengidentifikasi unik untuk modul ini - nilai ini bersifat unik di seluruh MS Learn. |
| `type` | string | Tipe data. Nilainya akan selalu 'module'. |
| `title` | string | Judul modul dalam bahasa yang diminta, atau bahasa Inggris AS sebagai alternatif. |
| `duration_in_minutes` | integer | Waktu rata-rata yang diperlukan untuk menyelesaikan modul ini dalam hitungan menit. |
| `rating` | objek | Tipe data ini berisi `count`, yaitu jumlah orang yang telah menilai modul, dan `average`, yang merupakan gabungan nilai, yaitu 1-5 |
| `popularity` | double | Nilai yang dinormalkan dari 0-1 menunjukkan popularitas modul | 
| `icon_url` | string | URL yang sepenuhnya memenuhi syarat untuk gambar **.svg** atau **.png** berukuran 100x100 yang mewakili modul. |
| `locale` | string | Bahasa yang digunakan dalam data JSON ini. Nilai ini akan menggunakan bahasa yang diminta jika tersedia, jika tidak 'en-us'. |
| `last_modified` | tanggal | Terakhir kali modul ini mendapat revisi besar. |
| `url` | string | URL yang sepenuhnya memenuhi syarat untuk modul di Microsoft Learn dalam bahasa yang diminta. |
| `firstUnitUrl` | string | URL yang sepenuhnya memenuhi syarat untuk unit pertama modul di Microsoft Learn dalam bahasa yang diminta. |
| `number_of_children` | integer | Jumlah halaman (unit) yang dimiliki modul ini. |

### <a name="learning-path-records"></a>Data jalur pembelajaran

Setiap Jalur pembelajaran akan memiliki bentuk berikut:

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

| Bidang | Jenis | Deskripsi |
|-------|------|-------------|
| `summary` | string | String yang menyediakan deskripsi singkat tentang jalur pembelajaran. Nilai disajikan sebagai tag paragraf HTML dengan ringkasan di teks bagian dalam. |
| `levels` | larik string | Menunjukkan banyaknya pengalaman dalam peran yang diperlukan untuk memahami semua aspek jalur pembelajaran ini. Larik ini akan berisi satu atau beberapa nilai berdasarkan modul yang disertakan dalam jalur. |
| `roles` | larik string | Daftar jabatan yang relevan untuk jalur pembelajaran ini. |
| `products` | larik string | Daftar produk relevan yang dicakup dalam jalur pembelajaran ini. |
| `uid` | string | Pengidentifikasi unik untuk jalur pembelajaran ini - nilai ini bersifat unik di seluruh MS Learn. |
| `type` | string | Tipe data. Nilainya selalu 'learningPath'. |
| `title` | string | Judul jalur pembelajaran dalam bahasa yang diminta, atau bahasa Inggris AS sebagai alternatif. |
| `duration_in_minutes` | integer | Waktu rata-rata yang diperlukan untuk menyelesaikan jalur pembelajaran ini dalam hitungan menit. Nilai ini merupakan jumlah data dari semua modul yang disertakan. |
| `rating` | objek | Tipe data ini berisi `count`, yaitu jumlah orang yang telah menilai jalur pembelajaran, dan `average`, yang merupakan gabungan nilai, yaitu 1-5 |
| `popularity` | double | Nilai yang dinormalkan dari 0-1 menunjukkan popularitas jalur pembelajaran | 
| `icon_url` | string | URL yang sepenuhnya memenuhi syarat untuk gambar **.svg** atau **.png** berukuran 100x100 yang mewakili jalur pembelajaran. |
| `locale` | string | Bahasa yang digunakan dalam data JSON ini. Nilai ini akan menggunakan bahasa yang diminta jika tersedia, jika tidak 'en-us'. |
| `last_modified` | tanggal | Terakhir kali jalur pembelajaran ini diubah. |
| `url` | string | URL yang sepenuhnya memenuhi syarat untuk jalur pembelajaran di Microsoft Learn dalam bahasa yang diminta. |
| `firstModuleUrl` | string | URL yang sepenuhnya memenuhi syarat untuk modul pertama jalur pembelajaran di Microsoft Learn dalam bahasa yang diminta. |
| `modules` | larik string | Daftar pengidentifikasi modul (uid) yang disertakan dalam jalur pembelajaran ini. |
| `number_of_children` | integer | Jumlah modul yang dimiliki jalur pembelajaran ini. |

### <a name="product-role-and-level-records"></a>Data produk, peran, dan tingkat

Kumpulan `levels`, `roles`, dan `products` menyediakan nama yang umum untuk nilai yang digunakan dalam data modul dan jalur pembelajaran. Ketiga kumpulan tersebut memiliki bentuk yang sama:

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

`id` akan menyesuaikan nilai untuk tingkat, peran, dan produk yang termasuk dalam setiap modul dan jalur pembelajaran. `name` yang terkait menyediakan nama yang tepat dalam bahasa Inggris untuk entri tersebut. Larik `children` bersifat opsional dan memungkinkan hierarkis untuk nilai yang memiliki hubungan turunan seperti produk.

Misalnya, berikut adalah sekumpulan peran yang mungkin digunakan:

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

Berikut adalah contoh kumpulan produk, dengan turunan yang disertakan untuk memberikan kategori produk yang lebih spesifik.

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

## <a name="catalog-lti-provider"></a>Penyedia LTI Katalog

Ingin mengintegrasikan Catalog API ke dalam Sistem Manajemen Pembelajaran (LMS)? Lihat [Aplikasi LTI](lti-application.md) sumber terbuka kami.

Kami membuat kode referensi yang mengubah Catalog API menjadi penyedia LTI. Anda dapat dengan cepat memodifikasi atau menginstal aplikasi secara langsung ke LMS Anda. Aplikasi LTI memungkinkan Anda mengintegrasikan modul Microsoft Learn ke dalam kurikulum yang ada sekaligus memberikan pengalaman langsung dengan Azure dan teknologi Microsoft lainnya. Pelajar akan diarahkan dari LMS Anda ke Microsoft Learn untuk mengumpulkan poin pengalaman dan pencapaian, serta melacak kemajuan pada aktivitas pembelajaran.


## <a name="catalog-api-program"></a>Program Catalog API

Apakah Anda mengintegrasikan konten Microsoft Learn ke dalam platform pembelajaran Anda? Daftar [Program Catalog API (CAP)](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR-4aRF51x15HqVFOq2xnAkBUMUJJWFVZWDdUNFQ0TTRaTlA2VVowRDVFSS4u) agar tim kami dapat membantu memastikan pengalaman integrasi yang terbaik dan mendapatkan masukan Anda terkait versi Catalog API mendatang.

## <a name="feedback-and-support"></a>Umpan balik dan Dukungan

Catalog API saat ini tersedia tanpa perjanjian tingkat layanan. Jika memiliki saran atau mengalami masalah saat menggunakan API, Anda dapat [memberikan umpan balik kepada tim kami.](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR_cebFBRf_dAnuWExXCcHVJUQU1PSDBONVc4WDZIN1RDTE1ISk41NlRJNi4u)
