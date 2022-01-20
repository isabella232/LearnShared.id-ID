---
title: Mulai menggunakan layanan Microsoft Learn Organizational Reporting
description: Organisasi dapat menampilkan serta melacak kemajuan dan prestasi pelatihan pengguna mereka menggunakan Microsoft Learn Organizational Reporting.
author: asajohnson
ms.author: asjohnso
ms.date: 10/27/2021
ms.topic: article
ms.prod: non-product-specific
org_reporting: true
breadcrumb_path: toc.yml
ms.openlocfilehash: 0572ccf4a0473b0702adb1373b0fbc45959bd1f7
ms.sourcegitcommit: 1a616355578e6d9ee8a28814c96b4817da4ce016
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "135809151"
---
# <a name="get-started-with-the-microsoft-learn-organizational-reporting-service"></a>Mulai menggunakan layanan Microsoft Learn Organizational Reporting

## <a name="what-is-microsoft-learn-organizational-reporting"></a>Apa itu Microsoft Learn Organizational Reporting?  

Microsoft Learn Organizational Reporting adalah layanan yang tersedia bagi pelanggan perusahaan dan organisasi pendidikan untuk menampilkan kemajuan pelatihan Microsoft Learn dan prestasi individu di dalam penyewa mereka menggunakan [Azure Data Share](https://azure.microsoft.com/services/data-share/). Azure Data Share memungkinkan organisasi berbagi data secara aman dengan beberapa pelanggan dan mitra. Cukup dalam beberapa klik, Anda dapat menyediakan akun pembagian data baru, menambahkan himpunan data, dan mengundang pelanggan dan mitra ke pembagian data Anda. Penyedia data selalu memegang kendali atas data yang telah mereka bagikan dan Azure Data Share memudahkan untuk mengelola dan memantau data yang dibagikan, kapan, dan oleh siapa.

:::image type="content" source="media/invitation-flow.png" alt-text="bagan alur memperlihatkan undangan yang dikirim kepada pengguna dan jepretan layar data yang disimpan di penyimpanan data target.":::

Organisasi dapat membuat dan mengelola bagian data mereka menggunakan UI tanpa kode Azure Data Share.

<div id="org-reporting-container" class="has-margin-top-medium"><button id="org-reporting-button" class="button is-primary">Mulai</button></div>

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

Bagian data adalah sekelompok himpunan data yang dibagikan sebagai satu entitas. Himpunan data dapat berasal dari banyak sumber data Azure yang didukung oleh Azure Data Share. Saat ini, Azure Data Share mendukung Azure Blob Storage dan Azure Data Lake Storage. Kunjungi [halaman terminologi Azure Data Share](/azure/data-share/terminology) terkait elemen layanan ini.

Dalam bagian data, Anda akan memiliki kontrol untuk memperbarui jadwal sinkronisasi, menyinkronkan secara manual, serta meninjau status dan riwayat eksekusi terakhir.  

> [!Important]
> Jika Anda memilih untuk menyinkronkan ke SQL Database dan ingin menggunakan templat Power BI kami di bawah ini tanpa konfigurasi tambahan di Power BI, jangan izinkan Azure Data Share Anda membuat tabel dengan ID penyewa dalam nama. Anda seharusnya dapat menghapus ID penyewa dari nama tabel sebagai bagian dari proses sinkronisasi Azure Data Share. Jika memilih untuk menggunakan konvensi penamaan kustom yang masih dapat menggunakan templat Power BI, Anda hanya perlu mengedit kueri di Power BI untuk menggunakan nama tabel yang benar.

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

Himpunan data **Pengguna** berisi informasi tentang semua pengguna yang direferensikan dalam himpunan data khusus penyewa lainnya. Perlu diperhatikan bahwa himpunan data ini tidak berisi informasi PII. Saat melaporkan, Anda perlu menggabungkan data ini dengan daftar pengguna Azure Active Directory untuk memeriksa daftar informasi pengguna yang lebih lengkap terhadap data lain.  
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

| LearningPathUid | title | url | durationInMinutes | points | iconUrl | levels | products | peran | languages |
|-|-|-|-|-|-|-|-|-|-|
| learn.create-serverless-applications | Membuat aplikasi tanpa server | /learn/paths/create-serverless-applications/ | 517 | 1925 | /learn/achievements/create-serverless-applications.svg | ["beginner","intermediate"] | ["azure","azure-functions","azure-portal","azure-cosmos-db","azure-storage","azure-cloud-shell"] | ["developer","student"] | ["powershell"] |

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

| moduleUid | title | url | iconUrl | durationInMinutes | points | levels | products | peran | languages |
|-|-|-|-|-|-|-|-|-|-|
| learn.languages.powershell-write-first | Tulis kode PowerShell pertama Anda | /learn/modules/powershell-write-first/ | /learn/achievements/powershell/powershell-write-first-code.svg | 17 | 200 | ["beginner"] | ["dotnet"] | ["developer","student"] | ["powershell"] |

#### <a name="hierarchyunit"></a>HierarchyUnit

Himpunan data **HierarchyUnit** berisi informasi katalog tentang semua Unit (bagian Modul) di Microsoft Learn.

Lihat contoh Modul beserta daftar unitnya di situs langsung Microsoft Learn: [Diskusikan konsep dasar Azure](/learn/modules/fundamental-azure-concepts/).  
<br>

| unitUid | title | url | durationInMinutes | points | moduleUid |
|-|-|-|-|-|-|
| learn.azure.query-data-sentinel.1-introduction | Pengantar | /learn/modules/query-data-sentinel/1-introduction/ | 5 | 100 | azure.query-data-sentinel |
| learn.azure.query-data-sentinel.2-exercise-setup | Latihan - Membuat kueri dan memvisualkan data dengan Azure Sentinel Workbooks | /learn/modules/query-data-sentinel/2-exercise-setup/ | 10 | 100 | azure.query-data-sentinel |


## <a name="download-user-list-in-azure-active-directory-portal"></a>Unduh daftar pengguna di portal Azure Active Directory  

Untuk melihat informasi yang lebih lengkap tentang pengguna yang tercantum dalam himpunan data kemajuan dan penyelesaian, Anda harus menggabungkan himpunan data Microsoft Learn dengan informasi pengguna dari Azure Active Directory. Anda bisa mendapatkan daftar pengguna dan informasi mereka dengan mengunduhnya dari portal Azure Active Directory. 

> [!IMPORTANT]
> Untuk mengunduh daftar pengguna dari pusat admin Azure AD, Anda harus masuk dengan pengguna yang ditetapkan ke satu atau beberapa peran administrator tingkat organisasi di Azure AD (minimum memerlukan peran Administrator Pengguna). Pengundang Tamu dan Pengembang Aplikasi tidak dianggap sebagai peran administrator.

Untuk mengunduh daftar pengguna:

1. Masuk ke organisasi Azure AD Anda dengan akun Administrator pengguna di organisasi.
1. Buka **Azure Active Directory > Pengguna**. 
1. Pilih **pengguna yang ingin Anda sertakan dalam unduhan** dengan mencentang kotak di kolom kiri di samping setiap pengguna. *Catatan: Saat ini, tidak ada cara untuk memilih semua pengguna yang akan diekspor. Setiap pengguna harus dipilih satu per satu.*
1. Di Azure AD, pilih  **Pengguna > Unduh pengguna**.
1. Pada halaman **Unduh pengguna**, pilih **Mulai** untuk mendapatkan file CSV yang berisi properti profil pengguna. Jika terjadi kesalahan, Anda dapat mengunduh dan melihat file hasil di halaman Hasil operasi massal. File berisi alasan untuk setiap kesalahan.

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
    - department
    - accountEnabled
    - usageLocation
    - streetAddress
    - status
    - country
    - physicalDeliveryOfficeName
    - city
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

## <a name="power-bi-template-for-sql-db-storage"></a>Templat Power BI untuk penyimpanan SQL DB

Kami telah membuat templat Power BI berdasarkan konfigurasi standar SQL Server dan DB dari Azure Data Share (yaitu pemetaan 1:1 antara himpunan data dan DB). Ini adalah titik awal untuk memvisualisasikan dan melaporkan himpunan data pelaporan organisasi, termasuk pandangan tingkat tinggi serta kemajuan pelatihan tingkat pengguna individu dalam organisasi Anda, tetapi juga dapat diperluas untuk membangun pelaporan lebih lanjut dan digabungkan dengan data lain.

:::image type="content" source="media/orgreporting-pbi-1.png" alt-text="Contoh dasbor Power BI memperlihatkan data penyelesaian Learn tingkat tinggi yang dihasilkan dari Organizational Reporting.":::

:::image type="content" source="media/orgreporting-pbi-2.png" alt-text="Contoh dasbor Power BI memperlihatkan data penyelesaian jalur pembelajaran Learn pengguna yang dihasilkan dari Organizational Reporting.":::

:::image type="content" source="media/orgreporting-pbi-3.png" alt-text="Contoh dasbor Power BI memperlihatkan data penyelesaian modul Learn pengguna yang dihasilkan dari Organizational Reporting.":::

### <a name="requirements-to-use-this-template"></a>Persyaratan untuk menggunakan templat ini:
> [!div class="checklist"]
> * Anda harus mengonfigurasi Azure Data Share untuk memetakan ke SQL Server & DB.
> * Nama tabel SQL DB Anda harus mengikuti nama tabel DB standar dari Azure Data Share dan tidak memiliki ID penyewa yang ditambahkan ke akhir. *Jika Anda memiliki ID penyewa yang ditambahkan ke akhir tabel Anda, atau Anda telah mengganti nama tabel - Anda dapat memodifikasi konfigurasi agar sesuai dengan templat - atau mengedit kueri di Power BI agar sesuai dengan konfigurasi Anda. Instruksi yang tercantum di bawah ini di bagian 'Pemecahan masalah umum'.*
> * Anda telah mengunduh daftar pengguna dari Portal Azure Active Directory Anda. *Jika belum melakukan ini, Anda akan melihat bidang kosong di mana nama pengguna seharusnya tercantum.*
> * Anda harus menginstal [Power BI Desktop](https://powerbi.microsoft.com/downloads/) untuk membuat laporan awal dan melakukan pengeditan selanjutnya. *Pengguna tidak memerlukan Power BI Desktop untuk melihat laporan setelah dipublikasikan.*

### <a name="steps-to-use-this-template"></a>Langkah-langkah untuk menggunakan templat ini

Pertama, Anda harus mengunduh templat dan memasukkan SQL Server dan DB Anda sebagai koneksi:

1. **Unduh templat** dari GitHub repo [mslearn-organizational-template](https://github.com/MicrosoftDocs/mslearn-organizational-reporting/raw/main/pbi-templates/msft-learn-org-report-sqldb-source.pbit). *Catatan: Anda tidak memerlukan akun GitHub untuk mengunduh templat.*
1. **Buka** file.
1. Masukkan **SQL Server dan DB**.
1. Klik **Muat**.

Selanjutnya, Anda perlu mengunggah data pengguna Azure Active Directory dari CSV yang Anda ekspor sebelumnya untuk melihat nama pengguna dan informasi pribadi dengan data.

1. Klik **Dapatkan Data**.
1. Klik **Teks/CSV**.
1. Pilih **File**.
1. Klik **Buka**.
1. Klik **Muat**.
1. Dari Layar Laporan **temukan** tabel **UserAADInfo** di kolom kanan.
1. Klik kanan **UserAADInfo**.
1. Pilih **Edit Kueri**.
1. Dalam daftar tabel, pastikan **UserADDInfo disorot**.
1. Di menu atas di sisi kanan, klik **Tambah Kueri**.
1. Pastikan **Dua tabel** dipilih.
1. Di drop-down **Tabel untuk ditambahkan**, pilih yang Anda buat melalui impor dalam langkah-langkah sebelumnya (sebagian besar dimulai dengan exportUser).
1. Klik **OK**. 

Nama pengguna seharusnya sudah terisi ke dalam laporan.

Ada banyak cara lain untuk membuat laporan ini lebih efisien, seperti mengaktifkan sinkronisasi reguler data pengguna AAD Anda ke dalam tabel yang kemudian ditarik secara dinamis ke dalam laporan ini. Templat ini dimaksudkan untuk menjadi titik awal. Ada juga beberapa [opsi berbagi laporan](/power-bi/fundamentals/desktop-getting-started#share-your-work).

### <a name="troubleshooting-common-issues-when-using-the-template"></a>Memecahkan masalah umum saat menggunakan templat

**Jika Anda membuat nama tabel kustom dan tidak cocok dengan nama tabel di templat Power BI atau nama tabel Anda memiliki ID penyewa ditambahkan ke akhir mereka (dan karena itu, tidak cocok dengan nama tabel dalam templat Power BI):**  

Anda dapat [mengganti nama tabel](/sql/relational-databases/tables/rename-tables-database-engine) agar sesuai dengan templat - atau [mengedit kueri di Power BI menggunakan editor tingkat lanjut](/power-bi/transform-model/desktop-query-overview#advanced-editor) untuk mencocokkan konfigurasi Anda dengan mengganti nama tabel dengan yang ada di pengaturan Anda.

Jika Anda mempertimbangkan untuk mengganti nama tabel SQL DB, pikirkan baik-baik sebelum Anda melakukannya! Jika kueri, tampilan, fungsi yang ditentukan pengguna, prosedur tersimpan, atau program yang ada mengacu pada tabel itu, modifikasi nama akan membuat objek tersebut tidak valid. Anda mungkin harus memperbarui pemetaan Azure Data Share untuk menunjuk ke tabel yang baru diganti namanya.

### <a name="more-power-bi-resources"></a>Sumber daya Power BI lainnya
* [Komunitas Power BI (T&J)](https://community.powerbi.com/)
* [Dokumentasi Power BI](/power-bi/fundamentals/power-bi-overview)
* [Pelatihan Power BI](/learn/browse/?expanded=power-platform&products=power-bi)

## <a name="frequently-asked-questions-faq"></a>Pertanyaan Umum (FAQ)

### <a name="how-can-i-access-this-data-and-what-permissions-are-needed"></a>Bagaimana cara mengakses data ini dan izin apa yang diperlukan?

Anda akan memerlukan izin akses ke tempat langganan bagian data ini disimpan. Bagian [persyaratan](#requirements) di atas adalah tempat yang tepat untuk memulai.

### <a name="what-is-azure-data-share"></a>Apa itu Azure Data Share?  

Azure Data Share memungkinkan organisasi berbagi data secara aman dengan beberapa pelanggan dan mitra. Cukup dalam beberapa klik, Anda dapat menyediakan akun pembagian data baru, menambahkan himpunan data, dan mengundang pelanggan dan mitra ke pembagian data Anda. Penyedia data memegang kendali penuh atas data yang telah mereka bagikan. Azure Data Share memudahkan Anda mengelola dan memantau data yang dibagikan, kapan, dan oleh siapa.

:::image type="content" source="media/invitation-flow.png" alt-text="bagan alur memperlihatkan undangan yang dikirim kepada pengguna dan jepretan layar data yang disimpan di penyimpanan data target.":::

Bagian data adalah sekelompok himpunan data yang dibagikan sebagai satu entitas. Himpunan data dapat berasal dari banyak sumber data Azure yang didukung oleh Azure Data Share. Saat ini, Azure Data Share mendukung Azure Blob Storage dan Azure Data Lake Storage. Kunjungi [halaman terminologi Azure Data Share](/azure/data-share/terminology) terkait elemen layanan ini.

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

Sertifikasi bukan bagian dari data bersama pelanggan saat ini. Kami berupaya untuk menyediakan data melalui layanan ini pada Agustus 2021.  
 
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

Azure Data Share memungkinkan satu penyewa per bagian data untuk layanan pelaporan ini. Setiap berbagi data harus disiapkan per penyewa. Anda dapat menarik data kolektif dari semua bagian data ke laporan PowerBI melalui database SQL tempat data dikelola dengan langkah minimal antar sinkronisasi.
 
### <a name="is-a-data-explorer-available-for-this-data-share-service"></a>Apakah penjelajah data tersedia untuk layanan berbagi data ini?

Pelanggan dapat melihat himpunan data yang tersedia di portal Azure melalui Azure Data Share. Setelah himpunan data dipetakan ke tujuan oleh pelanggan ke penyewa pelanggan, data dapat ditampilkan menggunakan alat yang berlaku untuk setiap tipe tujuan. Misalnya, peralatan terkait SQL dapat digunakan untuk tujuan SQL. 

### <a name="my-data-stopped-syncing-how-do-i-fix-this"></a>Data saya berhenti disinkronkan, bagaimana cara memperbaikinya?

Masalah ini muncul jika Anda membuat berbagi data pelaporan organisasi sebelum 24 Mei 2021. Kami memperbarui layanan dengan cara yang mengharuskan Anda menyiapkan ulang berbagi data dan menyambungkan sumber data baru ke laporan yang sudah ada jika Anda ingin terus menerima data pelaporan organisasi. Anda tidak harus menerima persyaratan baru. Untuk memperbarui koneksi Anda, buka [bagian Penyiapan Pelajari pelaporan organisasi](#setup-learn-organizational-reporting) di atas lalu ikuti langkah-langkahnya.

Setelah itu, Anda akan dapat melihat Azure Data Share baru dari Portal Azure, mirip dengan sebelumnya. Anda juga masih dapat melihat Azure Data Share yang lama di sana, tetapi Anda dapat memilih untuk menghapusnya karena berbagi data yang baru juga menyediakan riwayat lengkap. Jika Anda memiliki pertanyaan tentang hal ini, silakan hubungi tim [Pelaporan Organisasi Microsoft Learn](mailto:learnfororg@microsoft.com).
