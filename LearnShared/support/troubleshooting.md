---
title: Dukungan Microsoft Learn - Memecahkan masalah umum
description: Memecahkan masalah sumber daya Microsoft Learn.
author: Sadadow
ms.author: Saadad
ms.date: 11/01/2019
ms.topic: article
ms.prod: non-product-specific
breadcrumb_path: toc.yml
featureFlags:
- show_feedback_report
ms.openlocfilehash: e79cb811a449e93385c1172f8372f1daa8da3efd
ms.sourcegitcommit: b39b124844477584aae6479ee732f98c5c42ae3c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/30/2021
ms.locfileid: "130961408"
---
# <a name="troubleshooting-known-issues"></a>Memecahkan masalah umum

Kami terus meningkatkan Microsoft Learn, tetapi jika Anda memiliki masalah, coba salah satu langkah pemecahan masalah berikut agar tidak diblokir dengan cepat.

| Pesan kesalahan atau masalah umum | Rekomendasi perbaikan cepat |
| -------------------------------------- |-----------------------|
| "Akun MSA memerlukan langkah verifikasi tambahan." |Akun Microsoft yang digunakan untuk masuk ke Microsoft Docs mungkin memerlukan verifikasi jika Anda belum menggunakan akun tersebut dalam beberapa waktu, atau jika akun memerlukan verifikasi email atau telepon. Anda harus mengatasi masalah akses masuk akun melalui https://support.microsoft.com untuk menggunakannya di Microsoft Docs. |
| "Anda telah menggunakan semua kotak pasir hari ini." | Anda dapat mengaktifkan hingga 4 lingkungan kotak pasir per hari. Setelah menggunakan semua kotak pasir untuk satu hari, Anda harus menunggu selama 24 jam agar dapat mengaktifkan kotak pasir tambahan. <!--Only successful sandbox activations are counted towards your daily limit, so clicking the "Activate Sandbox" button on a module to test if your 24 hours have elapsed will not reset or extend your 24 hours. Need to complete a module, but have used all of your sandboxes for the day? Many module exercises can be completed using your Azure subscription, but charges may apply, and you may need to modify the instructions to work with your subscription.--> |
|  "Terjadi kesalahan tidak terduga" atau "Hmm, terjadi kesalahan."       |  Kesalahan ini akan muncul ketika Anda mengaktifkan kotak pasir.  Pilih tombol **Coba lagi aktifkan kotak pasir,** atau keluar dan masuk kembali ke pengguna Anda sebelum mencoba lagi. |
| "Penukaran undangan gagal."   |   Kembali ke halaman unit dan terima undangan lagi.  |
|Tidak dapat memulai Cloud Shell | Anda harus mengaktifkan cookie pihak ketiga di browser. Lakukan langkah-langkah berikut di browser Anda untuk mengaktifkannya. <br><br>**Edge** - buka **Pengaturan** > **Privasi dan Keamanan** > **Cookie** > **Jangan blokir cookie** <br>**Internet Explorer** - buka **Internet Options** > **Privasi** > **Tingkat Lanjut** > **Terima Cookie Pihak Ketiga** <br>**Firefox** - buka **Alat** > **Opsi** > **Privasi** > **Terima Cookie Pihak Ketiga** <br>**Chrome** - buka **Pengaturan** > **Privasi dan keamanan** > **Pengaturan Konten** > **Cookie**, lalu nonaktifkan "Blokir cookie pihak ketiga."|
| "Anda masuk ke cloud shell dengan akun yang berbeda dari akun yang digunakan di docs." | Pilih **Keluar** di bawah pesan kesalahan. Jika langkah tersebut tetap tidak dapat memperbaiki masalah, coba hapus cache/cookie browser, atau masuk dengan jendela penyamaran.|
| "Cloud Shell melebihi kuota pengguna aktif." | Semua Cloud Shell yang tersedia sedang digunakan. Coba refresh halaman, atau kembali 20 menit kemudian. |
| "Akun atau koneksi Anda ditandai untuk aktivitas tidak biasa. Karena hal ini, kami telah menangguhkan akses Anda ke [lab environment]. Jika Anda merasa kami telah melakukan kesalahan, Anda dapat mengajukan banding untuk mendapatkan akses kembali." | Hal ini dapat terjadi ketika sistem penipuan otomatis kami mendeteksi potensi penyalahgunaan platform, misalnya, kode terlarang, tindakan tak terduga di luar kegiatan laboratorium, atau pemanfaatan sumber daya yang tinggi. Setelah dilarang, semua aktivasi sandbox Microsoft Learn akan diblokir. Gunakan tombol **Banding** untuk mengirimkan permintaan peninjauan. Tim penipuan kami akan memverifikasi aktivitas laboratorium dan membuka blokir sandbox dalam waktu **24-36 jam** jika banding berhasil. |
| "AuthorizationFailed", "tidak memiliki otorisasi untuk melakukan tindakan", atau "grup sumber daya tidak ditemukan" | Coba lagi langkah-langkah tersebut dengan masuk melalui jendela browser privat yang baru. Jika langkah tersebut tetap tidak dapat memperbaiki masalah, coba hapus cache/cookie browser, atau masuk dengan jendela penyamaran.|
| "Pembuatan penyimpanan gagal." |   Jika langkah tersebut tetap tidak dapat memperbaiki masalah, coba hapus cache/cookie browser, atau masuk dengan jendela penyamaran.  |
| "Anda tidak dapat menyediakan sumber daya Azure." | Demi alasan keamanan, pengguna dengan alamat .onmicrosoft.com tidak akan dapat membuka kotak pasir. Anda tidak akan melihat masalah ini jika masuk dengan akun Microsoft pribadi. |
| Azure Cloud Shell akan terbuka tanpa menampilkan pemberitahuan. |   Ini adalah masalah umum di Edge dan Safari. Untuk saat ini, gunakan Chrome untuk mendapatkan pengalaman pengguna terbaik.  |
| Grup sumber daya dinonaktifkan dan tidak dapat melakukan operasi ini, atau grup sumber daya telah dihapus. |   Kotak pasir mesin virtual memiliki batas waktu selama satu jam. <!--, and a four-hour time limit for other sandboxes. The whole module must be finished before it times out.--> Setelah kotak pasir kedaluwarsa, Anda dapat mengaktifkan kotak pasir baru dan memulai modul dari awal. |
| Kemajuan tidak tersimpan. | Kemajuan dapat memakan waktu beberapa detik agar tersimpan dalam sistem kami, sehingga mungkin terlihat seperti tidak langsung tersimpan. Coba refresh halaman setelah beberapa detik. <!--If the issue persists, please reach out to our team.--> |
| Anda tidak mendapatkan lencana/trofi setelah menyelesaikan modul atau jalur pembelajaran. | Masalah ini umumnya terjadi ketika menggunakan Internet Explorer untuk melihat profil. Coba lagi dengan browser lain. |<!--| Penyebaran gagal atau Anda mendapatkan kesalahan "Penyebaran templat gagal karena pelanggaran kebijakan". |   Silakan beri tahu kami dengan mengirimkan pesan kepada tim kami. Sertakan langkah-langkah yang menimbulkan masalah, pesan kesalahan, dan/atau tangkapan layar yang relevan.|-->
| "File atau direktori tersebut tidak ada" |   <!--Please check you are using the right commands.--> Pastikan lokasi dalam struktur folder di dalam modul adalah lokasi yang benar untuk perintah Anda. |
| Sandbox untuk modul ini dinonaktifkan sementara untuk pemeliharaan. |  Kami sedang berupaya meningkatkan modul. Ketika pesan ini dinonaktifkan, Anda dapat menggunakan kembali kotak pasir dalam modul ini. |
| Anda tidak dapat mendaftarkan akun. | Buka browser dalam mode InPrivate/privat, lalu coba daftar lagi. </br><ol> 1. Buka Konsol di browser, Anda dapat membukanya dengan menekan F12. </ol><ol> 2. Di jendela **Konsol**, coba lagi pendaftaran Anda. </ol><ol> 3. Jika tetap gagal, ambil cuplikan layar dari kesalahan yang ditampilkan di jendela **Konsol**. <!--2) Ask user for permission to capture a screen recording of the user's entire registration flow.  You can record the screen in Teams.  This enables the Microsoft Learn team to see the problem visually.--> |
| <div id="account-linking">Menautkan akun pribadi atau kerja.</div> | Silakan ikuti langkah-langkah berikut: </br><ol> 1. Masuk ke profil Anda yang sudah ada </ol><ol> 2. Buka halaman profil </ol><ol> 3. Klik tab Pengaturan </ol><ol> 4. Dalam Manajemen Akun, + klik “Tambahkan akun” </ol><ol> 5. Masuk dengan akun yang Anda tautkan untuk menyelesaikan </ol><ol> Jika menerima pesan yang menampilkan "Anda akan menggabungkan kedua profil ini", artinya akun yang Anda tautkan telah memiliki profil terdaftar. Jika melanjutkan alur, Anda dapat menggabungkan data pengguna dari kedua profil bersama-sama. Lihat [Dapatkah saya menggabungkan dua profil saya menjadi satu](faq.md?pivots=profile) untuk detail selengkapnya.  </ol><ol> Ingat: setiap profil dapat memiliki satu akun pribadi dan hingga lima akun kerja atau sekolah tertaut.  |
| Anda tidak dapat mengaktifkan Kotak Pasir menggunakan akun "onmicrosoft.com".| Ini adalah masalah yang sudah diketahui. Saat ini, akun onmicrosoft.com tidak dapat digunakan untuk mengaktifkan kotak pasir Learn. Silakan masuk dengan akun Microsoft lain, seperti akun Outlook.com, atau buat akun Microsoft baru secara gratis di [Outlook.com](https://outlook.live.com/owa/). <br> Jika Anda membuat profil Learn menggunakan akun onmicrosoft.com, akun Microsoft kedua dapat ditautkan di profil Anda. Buka ke profil Learn, klik "Pengaturan" di menu navigasi sisi kiri, gulir ke "Manajemen Akun" untuk menemukan header "Akun tertaut." Klik "+ Tambahkan akun," lalu ikuti perintah untuk masuk dengan akun Microsoft tambahan. |
| Anda mengalami masalah dengan Cloud Skills Challenge.| Silakan kirimkan alias melalui email kepada dukungan yang disediakan di halaman tantangan Anda. Sertakan URL tantangan dan nama pengguna profil Docs Anda. Catatan: Jika tantangan memiliki pemenang dan hadiah, silakan lihat aturan resmi tantangan Anda. |

> [!NOTE]
> Karena adanya dampak pandemi kesehatan global, sumber daya Azure diprioritaskan untuk organisasi kesehatan dan keselamatan. Anda mungkin mengalami beberapa masalah saat menyebarkan sumber daya yang digunakan dalam latihan. Silakan coba lagi atau pilih wilayah lain. Untuk informasi selengkapnya, lihat postingan blog Azure - [ tanggal 28 Maret: Pembaruan No. 2 terkait kelangsungan layanan cloud Microsoft](https://azure.microsoft.com/blog/update-2-on-microsoft-cloud-services-continuity/).

## <a name="report-feedback"></a>Laporkan umpan balik
Ada tautan untuk melaporkan umpan balik di bagian bawah setiap unit dalam modul Learn. Tautan ini akan memungkinkan Anda untuk menghubungi tim kami tentang konten atau pengalaman Learn.

> [!IMPORTANT]
> Melaporkan umpan balik adalah komunikasi satu arah. Kami akan meninjau dan mengatasi semua masalah yang diterima, namun, kami tidak akan memberikan balasan saat ini.
