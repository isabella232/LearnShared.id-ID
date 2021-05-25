---
title: Mulai menggunakan layanan Microsoft Learn Organizational Reporting
description: Organisasi dapat menampilkan serta melacak kemajuan dan prestasi pelatihan pengguna mereka menggunakan Microsoft Learn Organizational Reporting.
author: asajohnson
ms.author: asjohnso
ms.date: 05/13/2021
ms.topic: article
ms.prod: non-product-specific
org_reporting: true
ms.openlocfilehash: 78d7c75520aab2392e08a1df8f38172873abd145
ms.sourcegitcommit: 1221777ce416add76f0dd3e0988021572ef425c2
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/19/2021
ms.locfileid: "110137854"
---
# <a name="get-started-with-the-microsoft-learn-organizational-reporting-service"></a>Mulai menggunakan layanan Microsoft Learn Organizational Reporting

## <a name="what-is-microsoft-learn-organizational-reporting"></a>Apa itu Microsoft Learn Organizational Reporting?  

Microsoft Learn Organizational Reporting adalah layanan yang tersedia bagi pelanggan perusahaan dan organisasi pendidikan untuk menampilkan kemajuan pelatihan Microsoft Learn dan prestasi individu di dalam penyewa mereka menggunakan [Azure Data Share](https://azure.microsoft.com/services/data-share/). Azure Data Share memungkinkan organisasi berbagi data secara aman dengan beberapa pelanggan dan mitra. Cukup dalam beberapa klik, Anda dapat menyediakan akun pembagian data baru, menambahkan himpunan data, dan mengundang pelanggan dan mitra ke pembagian data Anda. Penyedia data selalu memegang kendali atas data yang telah mereka bagikan dan Azure Data Share memudahkan untuk mengelola dan memantau data yang dibagikan, kapan, dan oleh siapa.

:::image type="content" source="media/invitation-flow.png" alt-text="bagan alur memperlihatkan undangan yang dikirim kepada pengguna dan jepretan layar data yang disimpan di penyimpanan data target.":::

Organisasi dapat membuat dan mengelola bagian data mereka menggunakan UI tanpa kode Azure Data Share.

<!--- <div id="org-reporting-container" class="has-margin-top-medium"><button id="org-reporting-button" class="button is-primary">Get started</button></div>
---->

Sistem ini memungkinkan organisasi untuk mengekstrak, mengubah, dan memuat (ETL) data kemajuan pengguna menjadi himpunan data, untuk diproses lebih lanjut atau ditampilkan dalam alat visualisasi seperti Power BI. Himpunan data dapat disimpan di Azure Data Lake, penyimpanan Azure Blob, database Azure SQL, atau Azure Synapse SQL Pool. Organisasi dapat membuat dan mengelola bagian data mereka menggunakan UI tanpa kode Azure Data Share.

Layanan Organizational Reporting menyertakan informasi kemajuan berikut ini untuk setiap pengguna:

Penyelesaian aktivitas Learn disediakan untuk setiap pengguna termasuk:
- Unit Learn
- Pelajari modul
- Jalur Pembelajaran Learn yang diselesaikan
- Pencapaian yang diperoleh (lencana & trofi)
- Perolehan XP
- *Sertifikasi (segera hadir!)*

Dalam himpunan data, setiap pengguna akan diberi ID objek unik dan informasi pengidentifikasi pribadi (PII) tidak akan disimpan dalam himpunan data. Individu dapat diidentifikasi dengan mengirim ID objek ke layanan Identitas Microsoft. Lihat [himpunan data khusus Penyewa](#tenant-specific-datasets) dan [himpunan data Microsoft Learn untuk](#microsoft-learn-datasets) detail selengkapnya.

### <a name="requirements"></a>Persyaratan

> [!div class="checklist"]
> * Organisasi harus memiliki langganan Azure untuk membuat Azure Data Share.  
> * Pengguna yang meminta layanan ini atas nama organisasi harus melampirkan akun Azure Active Directory (AAD) penyewa organisasi.
> * Akun AAD pengguna akan memerlukan akses ke portal Azure penyewa.

> [!NOTE]
> Dengan menggunakan layanan berbagi data ini, Anda menerima dan menyetujui **[Perjanjian Akses dan Berbagi Data Microsoft Learn](/legal/learn/reporting/terms)** untuk mengizinkan Microsoft berbagi data Learn dengan organisasi Anda untuk pengguna Learn yang masuk dengan ID penyewa organisasi Anda.

## <a name="setup-learn-organizational-reporting"></a>Siapkan Learn Organizational Reporting  


> [!NOTE]
> Layanan Microsoft Learn Organizational Reporting dihentikan untuk sementara untuk onboarding baru. Jika memiliki pertanyaan, silakan hubungi dukungan di learnfororg@microsoft.com.

Membuat instans Learn Organizational Reporting untuk organisasi Anda memerlukan beberapa langkah: 

1. Buka [halaman dokumentasi Learn Organizational Reporting](/learn/support/org-reporting) (halaman tempat Anda berada sekarang).
1. Klik tombol 'Mulai' berwarna biru di bawah ini.
1. Lakukan autentikasi dengan akun kerja, jika Anda belum diautentikasi.
1. Terima perjanjian lisensi.  
1. Pilih tipe data target (SQL, data lake, atau blob).
1. Atur jadwal sinkronisasi.

Setelah dibuat, Anda dapat menampilkan Azure Data Share dari portal Azure.

### <a name="demo-walkthrough-of-creating-and-setting-up-a-new-organizational-reporting-data-share"></a>Demo: Panduan untuk membuat dan menyiapkan berbagi data pelaporan organisasi baru  

Berikut adalah tutorial langkah demi langkah tentang pembuatan dan penyiapan berbagi data baru di layanan ini. Gunakan video ini sebagai panduan saja karena detail langganan dan penyewa Anda mungkin berbeda.  

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Mzq1]

## <a name="manage-your-data-share"></a>Kelola berbagi data Anda 

Bagian data adalah sekelompok himpunan data yang dibagikan sebagai satu entitas. Himpunan data dapat berasal dari beberapa sumber data Azure yang didukung oleh Azure Data Share. Saat ini, Azure Data Share mendukung Azure Blob Storage dan Azure Data Lake Storage. Kunjungi [halaman terminologi Azure Data Share](/azure/data-share/terminology) terkait elemen layanan ini.

Dalam bagian data, Anda akan memiliki kontrol untuk memperbarui jadwal sinkronisasi, menyinkronkan secara manual, serta meninjau status dan riwayat eksekusi terakhir.  

:::image type="content" source="media/Data Share items.JPG" alt-text="Cuplikan layar portal Azure di panel konfigurasi Data Share menyoroti pengaturan jepretan layar Pemicu.":::

Selain itu, Anda dapat menambahkan penerima ke bagian data yang sudah ada.  

1. Masuk ke bagian data terkirim.  
1. Di Azure Data Share, buka bagian terkirim, lalu pilih tab  **Undangan** . Yang tercantum di sini adalah semua penerima undangan untuk bagian data ini. Untuk menambahkan penerima baru, pilih **Tambahkan Penerima**.

    :::image type="content" source="media/Add_recipient.png" alt-text="Cuplikan layar portal Azure di panel konfigurasi Data Share menyoroti tombol Tambahkan Penerima.":::

1. Panel akan muncul di sisi kanan halaman. Pilih **Tambahkan Penerima** , lalu isi email penerima baru Anda di baris yang kosong. Tambahkan penerima sebanyak yang Anda inginkan.

    :::image type="content" source="media/Add_recipient_invitation.png" alt-text="Kontrol Tambahkan penerima di portal Azure untuk mengirim pemberitahuan email.":::

1. Pilih **Tambahkan dan kirim undangan.** Penerima baru akan menerima email undangan ke bagian data ini. 

## <a name="data-dictionary"></a>Kamus data

Buka bagian:  
* [Himpunan data khusus penyewa](/learn/support/org-reporting#tenant-specific-datasets)
* [Himpunan data Microsoft Learn](/learn/support/org-reporting#microsoft-learn-datasets)

### <a name="tenant-specific-datasets"></a>Himpunan data khusus penyewa

Data khusus penyewa disediakan oleh himpunan data **Prestasi**, **Kemajuan**, dan **Pengguna**.

#### <a name="achievements"></a>Penghargaan  

Himpunan data **Prestasi** berisi informasi tentang semua penghargaan yang diperoleh pengguna dalam penyewa ini, umumnya sebagai hasil atas penyelesaian modul dan jalur pembelajaran. Setelah menyelesaikan modul, pengguna akan mendapatkan lencana dan setelah menyelesaikan jalur pembelajaran, mereka akan mendapatkan trofi.

Prestasi Pengguna ditampilkan di situs langsung dengan melihat profil pengguna. ([Contoh](/users/ashley/))  
<br>

| UserId | AwardType | AwardUid | Alasan | SourceType | SourceUid | AwardedOn |
|-|-|-|-|-|-|-|
| *{guid}* | Lencana | learn.intro-to-compute.badge | badge.module.basic.completed | Modul | learn.intro-to-compute | *{datetimeoffset}* |
| *{guid}* | Trofi | learn.cloud-foundations.trophy | trophy.path.basic.completed | JalurPembelajaran | learn.cloud-foundations | *{datetimeoffset}* |

#### <a name="progress"></a>Progres

Himpunan data **Kemajuan** berisi informasi tentang jumlah poin XP yang diperoleh pengguna dalam penyewa ini dari menyelesaikan sebagian konten (unit individu, seluruh modul, jalur pembelajaran, dll). Setiap konten berbeda, sehingga pengguna dapat memperoleh lebih banyak poin jika konten yang diakses memiliki interaktivitas, atau jika mereka menyelesaikan kuis 100% untuk pertama kalinya.  
<br>

| UserID | Alasan | SourceType | SourceUid | XP | AwardedOn |
|-|-|-|-|-|-|
| *{guid}* | dasar.unit.titik.selesai | Unit | learn.intro-to-compute.1-introduction | 100 | *{datetimeoffset}* |
| *{guid}* | points.module.basic.completed | Modul | learn.create-azure-account | 200 | *{datetimeoffset}* |
| *{guid}* | points.path.basic.completed | LearningPath | learn.cloud-foundations | 2100 | *{datetimeoffset}* |

#### <a name="users"></a>Pengguna

Himpunan data **Pengguna** berisi informasi tentang semua pengguna yang direferensikan dalam himpunan data khusus penyewa lainnya. Perlu diperhatikan, himpunan data ini tidak berisi informasi PII. Anda perlu menggabungkannya dengan daftar pengguna Azure Active Directory untuk memeriksa daftar informasi pengguna yang lebih lengkap terhadap data lain.  
<br>

| tenantId | userId | AADObjectId | CreatedOn |
|-|-|-|-|
| *{guid}* | *{guid}* | *{guid}* | *{datetimeoffset}* |

### <a name="microsoft-learn-datasets"></a>Himpunan data Microsoft Learn

Data Microsoft Learn (tidak terkait dengan penyewa individu tertentu) disediakan oleh himpunan data **JalurPembelajaranHierarki**, **ModulJalurPembelajaranHierarki**, **ModulHierarki**, dan **Unit Hierarki**.

#### <a name="hierarchylearningpath"></a>HierarchyLearningPath

Himpunan data **HierarchyLearningPath** berisi informasi katalog tentang semua Jalur Pembelajaran di Microsoft Learn.

Lihat contoh Jalur Pembelajaran di situs langsung Microsoft Learn: [Dasar-dasar Microsoft Power Platform](/learn/paths/power-plat-fundamentals/).  
<br>

| LearningPathUid | title | url | durationInMinutes | points | iconUrl | levels | products | peran |
|-|-|-|-|-|-|-|-|-|
| learn.accessibility-fundamentals | Dasar aksesibilitas | /learn/paths/accessibility-fundamentals/ | 145 | 700 | /learn/achievements/accessibility-features.svg | ["beginner"] | ["m365"] | ["administrator","student"] |
| learn.administer-containers-in-azure | Memberikan wadah di Azure | /learn/paths/administer-containers-in-azure/ | 310 | 1225 | /learn/achievements/administer-containers-in-azure.svg | ["beginner"] | ["azure","azure-container-instances","azure-container-registry"] | ["administrator"] |

#### <a name="hierarchylearningpathmodule"></a>HierarchyLearningPathModule

Himpunan data **HierarchyLearningPathModule** berisi pemetaan Modul ke Jalur Pembelajaran. *(Catatan: Modul dapat menjadi bagian dari beberapa jalur pembelajaran.)*

Lihat contoh Jalur Pembelajaran beserta daftar modulnya di situs langsung Microsoft Learn: [Dasar-dasar Microsoft Power Platform](/learn/paths/power-plat-fundamentals/).  
<br>

| LearningPathUid | ModuleUid |
|-|-|
| learn.security-ops-sentinel | azure.query-data-sentinel |
| learn.architect-data-platform | learn.access-data-with-cosmos-db-and-sql-api |

#### <a name="hierarchymodule"></a>HierarchyModule

Himpunan data **HierarchyModule** berisi informasi katalog tentang semua Modul (kursus) di Microsoft Learn.

Lihat contoh Modul di situs langsung Microsoft Learn: [Diskusikan konsep dasar Azure](/learn/modules/fundamental-azure-concepts/).  
<br>

| moduleUid | title | url | iconUrl | durationInMinutes | points | levels | products | peran |
|-|-|-|-|-|-|-|-|-|
| azure.query-data-sentinel | Membuat kueri, memvisualkan, dan memantau data di Azure Sentinel | /learn/modules/query-data-sentinel/ | /learn/achievements/query-data-sentinel.svg | 48 | 200 | ["beginner"] | ["azure"] | ["solution-architect"] |
| learn.access-data-with-cosmos-db-and-sql-api | Menyisipkan dan membuat kueri data dalam database Azure Cosmos DB | /learn/modules/access-data-with-cosmos-db-and-sql-api/ | /learn/achievements/access-data-with-cosmos-db-and-sql-api.svg | 58 | 200 | ["beginner"] | ["azure","azure-cosmos-db","azure-clis","azure-portal"] | ["developer","solution-architect"] |

#### <a name="hierarchyunit"></a>HierarchyUnit

Himpunan data **HierarchyUnit** berisi informasi katalog tentang semua Unit (bagian Modul) di Microsoft Learn.

Lihat contoh Modul beserta daftar unitnya di situs langsung Microsoft Learn: [Diskusikan konsep dasar Azure](/learn/modules/fundamental-azure-concepts/).  
<br>

| unitUid | title | url | durationInMinutes | points | moduleUid |
|-|-|-|-|-|-|
| learn.azure.query-data-sentinel.1-introduction | Pengantar | /learn/modules/query-data-sentinel/1-introduction/ | 5 | 100 | azure.query-data-sentinel |
| learn.azure.query-data-sentinel.2-exercise-setup | Latihan - Membuat kueri dan memvisualkan data dengan Azure Sentinel Workbooks | /learn/modules/query-data-sentinel/2-exercise-setup/ | 10 | 100 | azure.query-data-sentinel |


## <a name="download-user-list-in-azure-active-directory-portal"></a>Unduh daftar pengguna di portal Azure Active Directory  

Untuk melihat informasi yang lebih lengkap tentang pengguna yang tercantum dalam himpunan data kemajuan dan penyelesaian, Anda harus menggabungkan himpunan data Microsoft Learn dengan informasi pengguna dari Azure Active Directory. Anda dapat melakukannya dengan mengunduh daftar pengguna dari portal Azure Active Directory. 

> [!IMPORTANT]
> Untuk mengunduh daftar pengguna dari pusat admin Azure AD, Anda harus masuk dengan pengguna yang ditetapkan ke satu atau beberapa peran administrator tingkat organisasi di Azure AD (minimum memerlukan peran Administrator Pengguna). Pengundang Tamu dan Pengembang Aplikasi tidak dianggap sebagai peran administrator.

Untuk mengunduh daftar pengguna:

1. Masuk ke organisasi Azure AD Anda dengan akun Administrator pengguna di organisasi.
1. Buka **Azure Active Directory > Pengguna**. 
1. Pilih **pengguna yang ingin Anda sertakan dalam unduhan** dengan mencentang kotak di kolom kiri di samping setiap pengguna. *Catatan: Saat ini, tidak ada cara untuk memilih semua pengguna yang akan diekspor. Setiap pengguna harus dipilih satu per satu.*
1. Di Azure AD, pilih  **Pengguna > Unduh pengguna**.
1. Pada halaman **Unduh pengguna**, pilih **Mulai** untuk mendapatkan file CSV yang berisi properti profil pengguna. Jika ada kesalahan, Anda dapat mengunduh dan melihat file hasil di halaman hasil operasi Massal. File berisi alasan untuk setiap kesalahan.

    :::image type="content" source="media/Download_csv.png" alt-text="Portal Azure memperlihatkan tombol untuk mengunduh file CSV pengguna.":::

    File yang diunduh akan berisi daftar pengguna yang difilter.

    Atribut pengguna berikut disertakan:

    - userPrincipalName
    - displayName
    - nama belakang
    - mail
    - givenName
    - objectId
    - userType
    - jabatan
    - departemen
    - accountEnabled
    - usageLocation
    - streetAddress
    - status
    - negara
    - physicalDeliveryOfficeName
    - kota
    - postalCode
    - telephoneNumber
    - seluler
    - authenticationAlternativePhoneNumber
    - authenticationEmail
    - alternateEmailAddress
    - ageGroup
    - consentProvidedForMinor
    - legalAgeGroupClassification

Lihat langkah-langkah dan detail selengkapnya di artikel [Mengunduh daftar pengguna di portal Azure Active Directory](/azure/active-directory/enterprise-users/users-bulk-download).

## <a name="example-power-bi-report"></a>Contoh laporan Power BI

Kami membuat contoh laporan Power BI untuk memvisualkan manfaat data ini untuk melaporkan kemajuan pelatihan individu di organisasi Anda. Kami menampilkan tampilan gabungan dari pelatihan yang dilakukan dalam MS Learn dan pemahaman yang lebih mendetail tentang jalur pembelajaran tertentu seperti Azure Fundaments, jalur pembelajaran kami yang paling populer.  

Berikut adalah langkah-langkah awal untuk mengekspor data ini:  

1. Masuk ke Power BI
1. File -> Dapatkan Data -> Pilih sumber (hubungkan ke himpunan data atau db SQL).  

Lihat detail selengkapnya tentang cara menerapkan di Power BI di sini: [Tutorial: Menghubungkan himpunan data ke database SQL Server](/power-bi/connect-data/service-gateway-sql-tutorial#connect-a-dataset-to-a-sql-server-database)

:::image type="content" source="media/Organization Reporting Power BI1.jpg" alt-text="Contoh dasbor Power BI memperlihatkan data penyelesaian modul Learn pengguna yang dihasilkan dari Organizational Reporting.":::

:::image type="content" source="media/Organization Reporting Power BI2.jpg" alt-text="Contoh dasbor Power BI memperlihatkan data penyelesaian jalur pembelajaran Learn pengguna yang dihasilkan dari Organizational Reporting.":::

## <a name="frequently-asked-questions-faq"></a>Pertanyaan Umum (FAQ)

### <a name="how-can-i-access-this-data-and-what-permissions-are-needed"></a>Bagaimana cara mengakses data ini dan izin apa yang diperlukan?

Anda akan memerlukan izin akses ke tempat langganan bagian data ini disimpan. Bagian [persyaratan](#requirements) di atas adalah tempat yang tepat untuk memulai.

### <a name="what-is-azure-data-share"></a>Apa itu Azure Data Share?  

Azure Data Share memungkinkan organisasi berbagi data secara aman dengan beberapa pelanggan dan mitra. Cukup dalam beberapa klik, Anda dapat menyediakan akun pembagian data baru, menambahkan himpunan data, dan mengundang pelanggan dan mitra ke pembagian data Anda. Penyedia data memegang kendali penuh atas data yang telah mereka bagikan. Azure Data Share memudahkan Anda mengelola dan memantau data yang dibagikan, kapan, dan oleh siapa.

:::image type="content" source="media/invitation-flow.png" alt-text="bagan alur memperlihatkan undangan yang dikirim kepada pengguna dan jepretan layar data yang disimpan di penyimpanan data target.":::

Bagian data adalah sekelompok himpunan data yang dibagikan sebagai satu entitas. Himpunan data dapat berasal dari beberapa sumber data Azure yang didukung oleh Azure Data Share. Saat ini, Azure Data Share mendukung Azure Blob Storage dan Azure Data Lake Storage. Kunjungi [halaman terminologi Azure Data Share](/azure/data-share/terminology) terkait elemen layanan ini.

Tautan cepat untuk referensi:

- [Apa itu Azure Data Share?](/azure/data-share/overview)
- [Terminologi Azure Data Share](/azure/data-share/terminology)
- [Berbagi data menggunakan Azure Data Share](/azure/data-share/share-your-data?tabs=azure-portal)
- [Berbagi dan menerima data dari Azure SQL Database](/azure/data-share/how-to-share-from-sql)
- [Memantau Azure Data Share](/azure/data-share/how-to-monitor)

### <a name="is-the-data-anonymized-in-these-datasets"></a>Apakah data dianonimkan dalam himpunan data ini?

Data PII tidak disertakan dalam himpunan data yang dapat mengungkapkan informasi pengidentifikasi pribadi. Meskipun demikian, Anda dapat menambahkan informasi pengguna dari [portal Azure Active Directory.](/azure/active-directory/enterprise-users/users-bulk-download)

Dalam himpunan data pengguna, Anda dapat menampilkan ‘ID objek’ sebagai data terpisah. Dalam Azure AD, Anda dapat mengunduh daftar lengkap pengguna dalam penyewa secara massal. Daftar tersebut mencakup atribut seperti: ID objek, alamat email, dan nama tampilan.

### <a name="does-that-data-report-progress-in-a-learning-module-or-learning-path"></a>Apakah data tersebut melaporkan kemajuan dalam modul pembelajaran atau jalur pembelajaran?

Kemajuan akan melaporkan jenis sumber berikut melalui Kemajuan: JalurPembelajaran, Modul, Unit.

### <a name="are-certifications-earned-by-an-individual-viewable-in-this-data"></a>Apakah sertifikasi yang diperoleh oleh individu dapat ditampilkan dalam data ini?

Sertifikasi bukan bagian dari data bersama pelanggan saat ini. Kami berupaya untuk menyediakan data melalui layanan ini pada Musim Semi 2021.  
 
### <a name="can-i-request-different-data-attributes-or-a-subset-of-this-data"></a>Dapatkah saya meminta atribut data lain atau subset data ini?

Himpunan data khusus pelanggan yang disediakan untuk pelanggan mencakup pencapaian, kemajuan, dan pengguna untuk penyewa mereka. Hierarki data yang dipelajari juga disediakan. Pelanggan dapat memetakan beberapa atau semua himpunan data ini sesuai kebutuhan. 
 
### <a name="is-more-than-one-data-share-available-for-this-service-per-tenant"></a>Apakah lebih dari satu berbagi data tersedia untuk layanan ini per penyewa?

Azure Data Share sebagai layanan akan mengizinkan satu bagian data antara dua penyewa yang terhubung. Jika bagian data sudah dibuat untuk layanan ini, Anda akan diarahkan ke bagian data penyewa untuk melihat.
 
### <a name="is-there-a-cost-for-my-organization-for-this-service"></a>Apakah organisasi saya perlu mengeluarkan biaya untuk menggunakan layanan ini?

Data yang digunakan dari Azure Data Share akan dikenakan biaya yang terkait dengan penyimpanan data dalam langganan yang sudah ada milik pelanggan, tetapi pelanggan Microsoft Azure tidak akan mendapat tagihan terpisah.  

### <a name="who-can-request-this-service-on-behalf-of-their-tenant"></a>Siapa yang dapat meminta layanan ini atas nama penyewa mereka?

Setiap orang dengan akun organisasi tertaut dapat membuat bagian data, hanya pengguna dengan izin akses kontributor ke langganan penyewa yang dapat mengakses bagian data yang tersedia.

### <a name="can-i-change-the-mapping-or-data-store-type-once-a-data-share-is-set"></a>Dapatkah saya mengubah tipe penyimpanan data atau pemetaan setelah berbagi data diatur?

Pemetaan data dapat dibatalkan dan dipetakan ulang untuk setiap himpunan data di dalam bagian data sesuai kebutuhan.

### <a name="how-does-syncing-work-for-this-service"></a>Bagaimana cara kerja sinkronisasi untuk layanan ini?

Operasi sinkronisasi menyalin data dari sumber Microsoft Learn ke tujuan apa pun yang dikonfigurasi oleh pelanggan, baik tujuan tersebut adalah SQL, CSV, atau tipe tujuan apa pun yang didukung oleh Azure Data Share.

### <a name="will-i-be-able-to-connect-this-data-share-to-my-learning-management-system-lms"></a>Apakah saya dapat menghubungkan berbagi data ini ke Sistem Manajemen Pembelajaran (LMS) saya?

Ya, selama pelanggan dapat bekerja dengan salah satu tipe tujuan Azure Data Share.

### <a name="my-organization-has-multiple-tenants-how-does-this-reporting-service-support-this-scenario"></a>Organisasi saya memiliki beberapa penyewa, bagaimana cara layanan pelaporan ini mendukung skenario ini?

Azure Data Share memungkinkan satu penyewa per bagian data untuk layanan pelaporan ini. Setiap bagian data harus disiapkan per penyewa. Anda dapat menarik data kolektif dari semua bagian data ke laporan PowerBI melalui database SQL tempat data dikelola dengan langkah minimal antar sinkronisasi.
 
### <a name="is-a-data-explorer-available-for-this-data-share-service"></a>Apakah penjelajah data tersedia untuk layanan berbagi data ini?

Pelanggan dapat melihat himpunan data yang tersedia di portal Azure melalui Azure Data Share. Setelah himpunan data dipetakan ke tujuan oleh pelanggan ke penyewa pelanggan, data dapat ditampilkan menggunakan alat yang berlaku untuk setiap tipe tujuan. Misalnya, peralatan terkait SQL dapat digunakan untuk tujuan SQL. 
