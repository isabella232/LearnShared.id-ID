---
title: Manfaatkan Microsoft Learn di organisasi Anda
description: Kami telah menyediakan beberapa layanan yang bisa Anda gunakan untuk memanfaatkan Microsoft Learn di organisasi Anda dengan lebih efektif.
author: asajohnson
ms.author: asjohnso
ms.date: 11/05/2021
ms.topic: article
ms.prod: non-product-specific
breadcrumb_path: toc.yml
ms.openlocfilehash: adf5125ba41dbb600f9423c420da2c21acf36922
ms.sourcegitcommit: 1a616355578e6d9ee8a28814c96b4817da4ce016
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "135808967"
---
# <a name="leverage-microsoft-learn-in-your-organization"></a>Manfaatkan Microsoft Learn di organisasi Anda

Microsoft Learn adalah platform pelatihan online gratis yang menyediakan pembelajaran interaktif untuk produk Microsoft dan banyak lagi. Tujuan kami adalah membantu Anda mahir menggunakan teknologi kami dan mempelajari lebih banyak keterampilan menggunakan konten interaktif langsung yang menarik dan dipandu sesuai peran dan tujuan Anda. Pelajari selengkapnya dalam [video ini](https://channel9.msdn.com/Blogs/One-Dev-Minute/What-is-Microsoft-Learn).

Meski pengguna organisasi Anda dapat mengakses situs secara langsung dan tidak perlu membuat akun jika mereka tidak mau, kami telah menyediakan beberapa layanan yang bisa Anda gunakan untuk menggunakan Microsoft Learn di organisasi Anda secara lebih efektif. Jika pengguna membuat akun dan masuk (tanpa biaya), pengguna dapat melacak penyelesaian mereka dan berbagi pencapaian, dan organisasi dapat menggunakan **satu atau lebih** fitur ini untuk memungkinkan skenario integrasi yang lebih dalam di lingkungan mereka.

## <a name="available-services"></a>Layanan yang tersedia

* [Learn Catalog API](catalog-api.md): Memungkinkan Anda mengirim kueri berbasis web ke Microsoft Learn dan mendapatkan kembali detail tentang semua konten Learn yang diterbitkan, seperti judul, produk yang tercakup, tingkat, tautan ke pelatihan, dan metadata lainnya. Anda kemudian dapat mengambil informasi ini dan menampilkannya di situs Anda sendiri atau pengalaman sistem manajemen pembelajaran (LMS) sehingga pengguna Anda dapat mengaksesnya tepat pada waktunya ketika melakukan tugas atau ditampilkan berdampingan dengan konten pelatihan lainnya.
* [Learn Organizational Reporting](org-reporting.md): Memungkinkan Anda untuk memisahkan dan melaporkan individu dalam informasi kemajuan dan penyelesaian organisasi Anda untuk konten Microsoft Learn (modul dan jalur pembelajaran).
* [Learn LMS LTI Application](lti-application.md): Memungkinkan Anda menghubungkan LMS (Sistem Manajemen Pembelajaran) dengan dukungan LTI (Learning Tools Interoperability) ke katalog Microsoft Learn, sehingga pengguna dapat mengakses konten Microsoft Learn dari LMS Anda.

## <a name="current-service-capabilities"></a>Kemampuan layanan saat ini

| Skenario | API Katalog | Pelaporan Organisasi | Aplikasi LTI |
| --- | --- | --- | --- |
| Tautkan ke konten pelatihan di sistem Anda sendiri | Ya | Ya | Ya |
| Sematkan (render) konten pelatihan di sistem Anda sendiri* | Tidak | Tidak | Tidak |
| Kueri informasi katalog pelatihan Microsoft Learn (metadata) | Ya | Ya | Ya |
| Laporan tentang kemajuan dan penyelesaian Microsoft Learn pengguna | Tidak | Ya | Tidak |
| Laporan tentang sertifikasi Microsoft yang diberikan* | Tidak | Tidak | Tidak |
| Koneksi ke sistem manajemen pembelajaran organisasi Anda | Ya | Ya | Ya |
| Akses Menyeluruh dari sistem organisasi ke Microsoft Learn* | Tidak | Tidak | Ya |

**Pada peta strategi.*

## <a name="example-scenarios"></a>Skenario contoh

Pada tingkat tinggi, layanan Learn Catalog API dan Learn Organizational Reporting memungkinkan organisasi yang menggunakan Microsoft Learn untuk menyerap katalog Microsoft Learn ke dalam sistem mereka, sehingga mereka dapat mengarahkan pengguna ke pelatihan, lalu melaporkan apa yang telah dicoba dan diselesaikan pengguna. Aplikasi Learn LMS LTI hanyalah variasi dari konfigurasi tersebut, tetapi telah melakukan pekerjaan awal untuk mengaktifkan fitur-fitur ini untuk skenario tertentu (aplikasi LMS yang mendukung LTI). Ada banyak variasi cara menerapkan layanan ini, tergantung pada kebutuhan dan lingkungan internal organisasi Anda. Berikut ini adalah skenario yang paling umum.

![Diagram aliran data dari Microsoft Learn menggunakan pelaporan organisasi dan Catalog API ke sistem organisasi.](./media/integrations-scenarios-high-level.png)

### <a name="1---report-on-your-users-microsoft-learn-training-progress-and-completion-reporting-only"></a>#1 - Melaporkan kemajuan dan penyelesaian pelatihan Microsoft Learn pengguna Anda. (Hanya melaporkan)

Jika Anda hanya perlu melaporkan kemajuan dan penyelesaian pelatihan Microsoft Learn pengguna organisasi, maka Anda harus menggunakan layanan Microsoft Learn Organizational Reporting. Layanan Organizational Reporting melibatkan pengaturan satu kali untuk mengonfigurasi alur dari Microsoft ke organisasi Anda menggunakan Azure Data Share, dan kemudian Anda akan secara teratur menerima kemajuan pengguna dan data penyelesaian di lingkungan Anda sehari sekali dan dapat melaporkannya menggunakan metode yang Anda inginkan.

Beberapa organisasi meminta database SQL secara langsung untuk mendapatkan data yang mereka inginkan, beberapa menyerapnya ke dalam sistem pelaporan lain seperti Power BI, Tableau, atau LMS, sehingga mereka dapat menampilkannya dengan informasi pelatihan lainnya, dan beberapa hanya menggunakan templat Power BI standar kami sebagai solusi pelaporan yang mudah. **Metode termudah adalah menyimpannya dalam database SQL dan menggunakan templat pelaporan Power BI kami. Anda cukup membuka templat laporan Power BI, memasukkan server SQL dan nama DB Anda, dan laporan akan secara otomatis terisi dengan data. Semuanya dimodelkan dan dibangun sebelumnya, sehingga akan memberi Anda semua pelaporan standar yang sama seperti kebanyakan Sistem Manajemen Pembelajaran (LMS) dan tidak perlu memperbarui apa pun di pihak Anda ke depan.**

![Diagram aliran data himpunan data pelaporan organisasi Microsoft Learn dan sistem organisasi. Data pelaporan organisasi diterima melalui Azure Data Share dan disimpan menggunakan SQL DB, Blob Storage, dll. Anda dapat menggunakan proses ETL untuk menyimpannya dengan data pelatihan lain, lalu melaporkan langsung dari database tersebut, atau menggunakan proses ETA untuk langsung mengimpornya ke sistem lain untuk pelaporan, atau menggunakan templat Power BI kami untuk terhubung ke penyimpanan SQL DB Anda untuk mendapatkan pelaporan langsung data Microsoft Learn organisasi Anda.](./media/integrations-scenarios-report-only.png)

### <a name="2---promote-content-to-your-users-and-report-on-their-completion-ingest-catalog-and-report"></a># 2 - Mempromosikan konten kepada pengguna Anda dan laporkan penyelesaiannya. (Serap katalog dan laporan)

Menyerap katalog Microsoft Learn ke situs atau sistem organisasi sendiri, kemudian juga melaporkan konten Microsoft Learn apa yang telah diselesaikan penggunanya adalah skenario paling umum untuk organisasi, tetapi juga memiliki variasi paling banyak. Pada tingkat tertinggi, organisasi menyerap katalog Microsoft Learn ke dalam sistem mereka, sehingga mereka dapat mengarahkan pengguna ke pelatihan, lalu melaporkan apa yang telah dicoba dan diselesaikan pengguna.

Terkadang, pengalaman situs organisasi yang diaktifkan adalah situs internal, di mana modul atau jalur pembelajaran Learn tertentu akan sangat membantu – seperti tautan ke modul Dynamics 365 pada halaman bantuan internal untuk instans Dynamics 365 Anda – atau tautan ke jalur pembelajaran Azure Fundamentals dari halaman SharePoint tim teknisi Anda. Atau, mungkin ada dalam sistem khusus pelatihan Anda sendiri.

Pada saat ini, satu-satunya pelaporan adalah melalui layanan Organizational Reporting kami (tidak ada API pelaporan real-time yang tersedia untuk diaktifkan di situs Anda). Layanan ini memberikan penyegaran data penyelesaian sekali sehari yang dapat Anda laporkan menggunakan alat Anda sendiri, seperti Excel, Power BI, kueri SQL langsung, dll, atau Anda bisa menjadi kreatif dan juga menyerap data penyelesaian dalam pengalaman situs yang tercantum di atas sehingga di samping pelatihan, Anda dapat menunjukkan apakah pengguna telah menyelesaikan pelatihan juga.

![Diagram aliran data antara Microsoft Learn dan organisasi ketika ingin menyerap katalog ke dalam sistem mereka sendiri dan kemudian melaporkan data penyelesaian. Organisasi menyerap data pelaporan organisasi ke dalam metode pelaporan menggunakan fitur pelaporan organisasi dan kemudian melaporkan data ini secara terpisah, atau digabung dengan data pelatihan lainnya. Organisasi membuat kueri Catalog API dan menyerap pengalaman mereka sendiri. Kemudian, situs atau sistem organisasi, seperti Sistem Manajemen Pembelajaran mengirim pengguna ke Microsoft Learn untuk mengikuti pelatihan - biasanya melalui tautan langsung ke konten yang direkomendasikan organisasi.](./media/integrations-scenarios-ingest-report.png)

### <a name="3---connect-microsoft-learn-with-your-learning-management-system-lms-ingest-catalog-only-or-ingest-catalog-and-report"></a># 3 - Menghubungkan Microsoft Learn dengan Sistem Manajemen Pembelajaran (LMS) Anda. (Hanya menyerap katalog atau Menyerap katalog dan laporan)

Ada dua cara utama untuk menghubungkan Sistem Manajemen Pembelajaran (LMS) Anda dengan Microsoft Learn: dengan menggunakan layanan secara langsung atau melalui aplikasi LTI kami. Jika organisasi Anda memutuskan untuk menggunakan layanan secara langsung, maka Anda akan merujuk ke Skenario #2 yang tercantum di atas. Jika organisasi Anda memiliki LMS yang mendukung LTI, maka Anda dapat menggunakan aplikasi LTI sumber terbuka kami yang mengerjakan pekerjaan awal dari mengintegrasikan Learn Catalog API dengan LMS Anda.

Aplikasi LTI akan memungkinkan Anda untuk lebih mudah menyerap katalog ke LMS Anda, sehingga Anda dapat membuat permukaan dan menetapkan konten kepada pengguna Anda. Aplikasi ini juga menyediakan pelacakan penyelesaian terbatas dan SSO, meskipun kami merekomendasikan agar pelaporan resmi dilakukan menggunakan layanan Organizational Reporting kami.

![Diagram aliran data antara Microsoft Learn dan organisasi saat menggunakan aplikasi LTI Learn. Organisasi menyerap data pelaporan organisasi ke dalam metode pelaporan menggunakan fitur pelaporan organisasi dan dapat melaporkan data ini secara terpisah atau digabung dengan data pelatihan lainnya. Aplikasi LTI Learn membuat kueri Catalog API dan menyerapnya untuk digunakan di LMS organisasi. Organisasi menggunakan aplikasi LTI Learn, sehingga mereka dapat menyerap pelatihan ke LMS dan menetapkan kepada pengguna, dll. LMS organisasi mengirim pengguna ke Microsoft Learn untuk mengikuti pelatihan - biasanya melalui tautan langsung ke konten yang direkomendasikan organisasi. Akhirnya, pengguna organisasi mengikuti pelatihan di Microsoft Learn.](./media/integrations-scenarios-lti-app.png)
## <a name="frequently-asked-questions"></a>Pertanyaan Umum

**Q: Apakah pengguna harus masuk untuk mengakses Learn?**

Nomor. Pengguna dapat mengakses konten Learn tanpa mengautentikasi, meski mereka tidak akan dapat menggunakan lab praktik Azure Sandbox di Learn. Selain itu, jika mereka tidak masuk, catatan penyelesaian mereka tidak akan disimpan.

**T: Bagaimana jika pengguna saya mengikuti pelatihan dengan akun pribadi?**

Catatan penyelesaian mereka masih akan disimpan dengan akun mereka, tetapi tidak akan tersedia dalam himpunan data Organizational Reporting. Mereka dapat menautkan akun yang ada ke Akun Organisasi mereka dan pada saat itu, data penyelesaian akan tersedia untuk organisasi (mereka tidak perlu mengikuti pelatihan lagi).

**T: Apakah saya memerlukan akun Azure untuk menggunakan ini?**

Anda tidak memerlukan akun Azure untuk menggunakan layanan Catalog API, tetapi Anda memerlukannya untuk menggunakan layanan Organizational Reporting atau Aplikasi LMS LTI. 

**T: Berapa biaya Learn dan fitur-fitur ini?**

Tidak ada biaya bagi pengguna dan organisasi untuk menggunakan Learn. Semua layanan tersebut bersifat gratis, meski Anda mungkin dikenakan biaya untuk biaya penyimpanan saat menyimpan catatan penyelesaian organisasi.

**T: Apakah Microsoft Learn Mendukung Akses Menyeluruh (SSO)?**

Tidak langsung saat ini. Aplikasi Learn LMS LTI menyediakan pengalaman SSO terbatas bagi pengguna, tetapi SSO belum tersedia dari sistem lain. SSO saat ini ada di peta strategi kami.

**T: Siapa dapat saya hubungi jika memiliki pertanyaan tentang layanan-layanan ini?**

Email [learnfororg@microsoft.com](mailto:learnfororg@microsoft.com). 

**FAQ yang lebih rinci untuk setiap fitur dapat ditemukan di artikel dokumentasi masing-masing fitur: [Microsoft Learn General](faq.md?pivots=general[), [Catalog API](catalog-api.md), [Organizational Reporting](org-reporting.md#frequently-asked-questions-faq), [LMS LTI Application](lti-application.md).**