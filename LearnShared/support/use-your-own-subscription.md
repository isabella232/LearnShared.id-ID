---
title: Dukungan Microsoft Learn - menggunakan langganan pribadi
description: Cara menjalankan latihan Microsoft Learn di langganan pribadi
author: markjulmar
ms.author: smmark
ms.date: 05/13/2020
ms.topic: article
ms.prod: non-product-specific
breadcrumb_path: toc.yml
ms.openlocfilehash: 0fae340fb9110542eca69e2dfe30abececfbda8d
ms.sourcegitcommit: 7b98b56c8e5bb1bdf66dda665bc9e6f307c65845
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/22/2021
ms.locfileid: "107696249"
---
# <a name="how-to-run-microsoft-learn-exercises-in-your-own-subscription"></a>Cara menjalankan latihan Microsoft Learn di langganan pribadi

Untuk membuat eksperimen dan pembelajaran semudah mungkin, Microsoft Learn menggunakan lingkungan Kotak Pasir. Kotak Pasir memungkinkan Anda melakukan tugas Azure tertentu secara gratis tanpa akun Azure. Namun, lingkungan ini juga mempersulit penyimpanan pekerjaan, pengalihan fungsi untuk penggunaan di lain waktu, atau perluasan di luar batas-batas latihan tertentu. Untuk skenario ini, Anda dapat menjalankan lab di langganan pribadi. 

Anda juga dapat menggunakan pendekatan ini jika lingkungan Kotak Pasir tidak tersedia karena alasan tertentu.

> [!IMPORTANT]
> Ingat bahwa jika menggunakan langganan pribadi, Anda akan dikenai biaya untuk setiap sumber daya yang aktif. Sebaiknya pantau biaya dengan cermat menggunakan fitur analisis biaya di portal Azure, batalkan alokasi VM apa pun yang tidak digunakan, dan pilih paket harga dengan hati-hati untuk menghindari biaya tak terduga.

## <a name="azure-exercises"></a>Latihan Azure

Jika latihan memiliki tombol untuk mengaktifkan Kotak Pasir, Anda harus melakukan langkah-langkah berikut, dan bukan mengaktifkan lingkungan Kotak Pasir baru.

1. Buka jendela Cloud Shell (hanya diperlukan jika latihan menggunakan baris perintah).
1. Buat grup sumber daya.
1. Pastikan Anda telah masuk ke langganan dan direktori yang benar.
1. Gunakan grup sumber daya dalam latihan.
1. Hapus sumber daya jika Anda sudah selesai menggunakannya.

Berikut adalah detail selengkapnya tentang setiap langkah.

### <a name="open-a-cloud-shell"></a>Buka Cloud Shell

Beberapa latihan menggunakan Cloud Shell terintegrasi. Cloud Shell tidak akan tersedia jika Anda tidak mengaktifkan Kotak Pasir. Namun, Anda dapat membuka tab atau jendela Azure Cloud Shell baru dengan URL <https://shell.azure.com>, atau dengan meluncurkan [portal Azure](https://portal.azure.com?azure-portal=true) dan menggunakan ikon Cloud Shell di bar alat bagian atas seperti yang diperlihatkan di bawah ini.

![Gambar memperlihatkan bar alat portal Azure dengan ikon Cloud Shell yang disorot](media/cloud-shell-icon.png)

Pastikan Anda masuk menggunakan kredensial langganan. Semua perintah untuk latihan dapat dijalankan dalam shell ini. Anda dapat memilih bash atau PowerShell sebagai bagian dari pengalaman dan bahkan beralih antar keduanya sesuai kebutuhan.

### <a name="create-a-resource-group"></a>Buat grup sumber daya

Grup sumber daya adalah penampung yang menyimpan sumber daya terkait untuk solusi Azure. Kotak Pasir membuat grup sumber daya secara otomatis. Anda harus membuat grup permanen sendiri untuk menyimpan sumber daya di langganan. Anda dapat membuat grup sumber daya baru menggunakan Azure CLI, PowerShell, atau portal Azure.

#### <a name="azure-cli"></a>Azure CLI

Masuk ke Azure CLI menggunakan perintah `az login`. Pastikan untuk menggunakan kredensial dengan akses ke langganan yang ingin Anda gunakan. Lalu, gunakan perintah berikut di Azure CLI untuk membuat grup sumber daya baru. Ganti `{resourceGroupName}` dengan nama unik yang mudah Anda identifikasi. `{location}` merupakan kawasan Azure terdekat. Anda dapat melihat daftar wilayah yang tersedia dengan perintah az account list-locations.

```bash
az group create --name {resourceGroupName} --location {location}
```

#### <a name="powershell"></a>PowerShell

PowerShell sangat mirip – Anda akan membutuhkan modul Azure PowerShell, dan perlu masuk ke langganan Azure dengan cmdlet `Connect-AzAccount`. Kemudian Anda dapat membuat grup sumber daya baru dengan cmdlet `New-AzResourceGroup` seperti yang diperlihatkan di bawah ini.

```powershell
New-AzResourceGroup -Name {resourceGroupName} -Location {location}
```

#### <a name="azure-portal"></a>portal Microsoft Azure

Terakhir, Anda dapat menggunakan portal Azure untuk membuat grup sumber daya. Di sebagian besar kasus, Anda dapat melakukannya sebagai bagian dari pembuatan sumber daya dengan memilih “Baru” sebagai bagian dari layar pembuatan sumber daya. Atau, Anda dapat membuat grup sumber daya baru dengan langkah-langkah berikut:

1. Masuk ke [portal Azure](https://portal.azure.com/?azure-portal=true).
1. Pilih **+ Buat sumber daya** dari bar samping sebelah kiri.
1. Ketik “Grup sumber daya” dalam kotak pencarian, lalu pilih dari hasil yang muncul.
1. Pilih **Buat** di halaman deskripsi.
1. Pilih langganan Anda, beri nama untuk grup sumber daya yang baru, lalu pilih lokasi (kawasan) tempat Anda ingin membuat grup.
1. Pilih **Tinjau + Buat** dan selesaikan pembuatan grup.

### <a name="verify-the-selected-azure-subscription-and-directory"></a>Verifikasi langganan dan direktori Azure yang dipilih

Jika Anda menggunakan portal Azure selama latihan, pastikan untuk menggunakan kredensial langganan yang benar. Dalam beberapa kasus, tautan dalam instruksi mungkin akan mengarahkan Anda ke direktori **Microsoft Learn**. Tautan ini tidak akan berfungsi karena Anda tidak memiliki izin untuk membuat sumber daya.

Setelah masuk, periksa akun Anda saat ini di sudut kanan atas portal Azure. Jika tidak melihat nama perusahaan yang benar di bawah nama Anda, Anda mungkin berada di direktori yang salah. Pilih nama Anda, lalu pilih **Beralih Direktori** untuk mengubah direktori saat ini.

![Cuplikan layar memperlihatkan menu Beralih Direktori di portal Azure](media/portal-switch-directory.png)

### <a name="using-the-resource-group"></a>Menggunakan grup sumber daya

Di sepanjang instruksi latihan, Anda akan menemukan referensi ke grup yang telah dibuat sebelumnya, yang sering kali dicantumkan sebagai `"[sandbox resource group name]"` dalam langkah-langkah latihan atau sampel kode. Nilai tempat penampung ini akan diganti dengan nama asli setelah Anda mengaktifkan Kotak Pasir. Nilai ini haru diganti setiap kali Anda melihatnya dengan nama grup sumber daya Anda. Misalnya, jika Anda membuat grup sumber daya bernama `learn-rg`, pastikan untuk menggunakan nama tersebut setiap kali Anda melihat tempat penampung.

> [!IMPORTANT]
> Pastikan untuk menggunakan grup sumber daya yang sama untuk semua sumber daya yang Anda buat dalam latihan. Hal ini guna memudahkan Anda melacak biaya serta membersihkan semuanya ketika sudah selesai menggunakannya.

### <a name="delete-the-resources-when-you-are-finished"></a>Hapus sumber daya ketika sudah selesai

Setelah latihan selesai di langganan Anda, semua sumber daya akan terus aktif hingga Anda menghapusnya. **Kemampuan penghapusan otomatis tidak tersedia saat Anda menggunakan langganan pribadi.** Ketika Anda sudah siap untuk menghapus semua sumber daya, gunakan langkah-langkah berikut:

#### <a name="azure-cli"></a>Azure CLI

Gunakan perintah berikut di Azure CLI untuk menghapus grup sumber daya dan semua sumber daya yang terkait. Ganti `{resourceGroupName}` dengan nama grup sumber daya yang telah Anda buat.

```bash
az group delete -n {resourceGroupName}
```

#### <a name="powershell"></a>PowerShell

PowerShell sangat mirip.

```powershell
Remove-AzResourceGroup -Name {resourceGroupName}
```

#### <a name="azure-portal"></a>portal Microsoft Azure

Terakhir, Anda dapat menggunakan portal Azure untuk menghapus grup sumber daya. Gunakan langkah-langkah berikut.

1. Masuk ke [portal Azure](https://portal.azure.com/?azure-portal=true).
1. Ketikkan nama grup sumber daya Anda ke dalam kotak Pencarian di bagian atas.
1. Pilih grup sumber daya untuk memperlihatkan detail. Anda akan melihat semua sumber daya yang telah dibuat.
1. Pilih **Hapus grup sumber daya** dari bar alat. Jawab pemberitahuan "Apakah Anda yakin", lalu klik **Hapus** untuk menyelesaikan proses.

## <a name="microsoft-dynamics-365-sales-customer-service-field-service--marketing-exercises"></a>Latihan Microsoft Dynamics 365 Sales, Customer Service, Field Service & Marketing

Sebelum memulai latihan, mintalah [lingkungan uji coba](https://trials.dynamics.com/Dynamics365/signup/) dari Microsoft dan gunakan himpunan data sampel yang telah disediakan.

Jika Anda mengubah data sampel dan mengalami masalah pada lab berikutnya, ikuti instruksi berikut untuk [mengatur ulang data sampel lingkungan Anda](https://docs.microsoft.com/power-platform/admin/add-remove-sample-data).

## <a name="microsoft-dynamics-365-finance-supply-chain-management-and-commerce-exercises"></a>Latihan Microsoft Dynamics 365 Finance, Supply Chain Management, dan Commerce

Sebelum memulai latihan, mintalah [lingkungan percobaan](https://trials.dynamics.com/Dynamics365/signup/) Dynamics 365 Finance & Operations dari Microsoft dan gunakan himpunan data sampel yang telah disediakan.

Setelah modul selesai, Anda dapat mengikuti instruksi ini untuk [memperbarui data demo Anda](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/generate-demo-data-packages) guna mengatur ulang data untuk modul berikutnya.
