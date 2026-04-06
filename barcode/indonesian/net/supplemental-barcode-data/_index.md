---
date: 2026-03-07
description: Pelajari cara membuat kode batang EAN-2 dan melakukan generasi kode batang
  .NET menggunakan Aspose.BarCode untuk .NET. Kuasai penyesuaian data kode batang
  tambahan hari ini!
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: Buat Barcode EAN-2 dengan Aspose.BarCode untuk .NET
url: /id/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Barcode EAN-2 dengan Aspose.BarCode untuk .NET

## Pendahuluan

Jika Anda seorang pengembang .NET yang ingin **membuat barcode EAN-2** dan memanfaatkan kekuatan data barcode tambahan, Anda berada di tempat yang tepat. Dalam panduan komprehensif ini kami akan memandu Anda melalui semua yang perlu Anda ketahui—dari konfigurasi dasar hingga penyetelan ruang di sekitar simbol Anda. Baik Anda sedang membangun sistem inventaris baru maupun meningkatkan aplikasi point‑of‑sale yang sudah ada, menguasai fitur‑fitur ini akan membuat proyek generasi barcode .NET Anda lebih fleksibel dan dapat diandalkan.

## Jawaban Cepat
- **Apa yang dapat saya hasilkan?** Barcode tambahan EAN‑2 dan EAN‑5.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Berapa banyak kode yang diperlukan?** Hanya beberapa baris—Aspose.BarCode menangani pekerjaan berat.  
- **Bisakah saya menyesuaikan spasi?** Ya, Anda dapat mengontrol X‑dimension dan ruang tambahan secara langsung.

## Apa itu data barcode tambahan?

Data barcode tambahan mengacu pada simbol kecil tambahan (EAN‑2, EAN‑5) yang muncul di samping barcode utama, biasanya digunakan untuk nomor edisi, ekstensi harga, atau informasi bantu lainnya. Aspose.BarCode untuk .NET memungkinkan Anda menghasilkan simbol‑simbol ini secara programatis, memberi Anda kontrol penuh atas tampilan dan penempatannya.

## Mengapa menggunakan Aspose.BarCode untuk .NET?

- **Integrasi .NET penuh** – bekerja dengan C#, VB.NET, dan F#.  
- **Rendering berkualitas tinggi** – menghasilkan barcode yang dapat dipindai pada resolusi apa pun.  
- **Kustomisasi luas** – mulai dari tipe simbol hingga X‑dimension, zona tenang, dan ruang tambahan.  
- **Tanpa ketergantungan eksternal** – perpustakaan murni yang dikelola, mudah dideploy.

## Konfigurasi Data Barcode Tambahan

Mari kita mulai dengan menyelami konfigurasi data barcode tambahan. Aspose.BarCode untuk .NET menyediakan alat untuk menghasilkan barcode tambahan dengan mudah, memberi Anda kontrol penuh atas barcode EAN‑2 dan EAN‑5. Tapi bagaimana cara memulainya?

Pertama, unduh dan instal Aspose.BarCode untuk .NET. Anda dapat mencoba versi percobaan gratis untuk menguji fitur‑fiturnya. Setelah semuanya siap, ikuti panduan langkah‑demi‑langkah kami, yang akan membawa Anda melalui proses, memastikan Anda menguasai konfigurasi data barcode tambahan dengan mudah.

Pada akhir bagian ini, Anda akan memiliki pemahaman yang kuat tentang cara membuat barcode EAN‑2 dan EAN‑5, menjadikan Anda pengembang .NET yang lebih serbaguna.

## Cara membuat barcode EAN-2? (Langkah‑Langkah Konfigurasi)

1. **Instansiasi generator barcode** – pilih kelas `BarcodeGenerator` dan atur symbology ke `EncodeTypes.EAN13` (atau tipe utama lainnya).  
2. **Aktifkan bagian tambahan** – set properti `SupplementData` ke string numerik yang diinginkan (misalnya `"12"` untuk tambahan EAN‑2).  
3. **Sesuaikan pengaturan visual** – secara opsional ubah `XDimension`, `BarHeight`, dan `QuietZone` agar sesuai dengan kebutuhan tata letak Anda.  
4. **Simpan atau render** – panggil `Save` untuk menulis gambar ke file atau stream.

> *Tip pro:* Pastikan panjang data tambahan tepat 2 digit untuk EAN‑2 dan 5 digit untuk EAN‑5; jika tidak, barcode dapat menjadi tidak terbaca.

## Kustomisasi Ruang Barcode Tambahan

Dalam dunia barcode, kemampuan kustomisasi adalah kunci, dan di sinilah Aspose.BarCode untuk .NET bersinar. Sekarang, mari fokus pada kustomisasi ruang barcode tambahan. Aspek ini berhubungan dengan pengendalian X‑Dimension dan ruang tambahan pada barcode Anda.

Sekali lagi, Anda akan memulai dengan menginstal Aspose.BarCode untuk .NET dan memanfaatkan versi percobaan gratis. Kemudian, ikuti panduan kami tentang cara menyesuaikan ruang pada barcode Anda. Kustomisasi ini sangat berguna untuk berbagai aplikasi, mulai dari manajemen inventaris hingga sistem point‑of‑sale.

Kebebasan menyesuaikan barcode sesuai kebutuhan spesifik Anda adalah keahlian berharga, dan bagian ini akan memastikan Anda siap menggunakannya.

## Bagaimana cara menyesuaikan ruang tambahan?

- **X‑Dimension** – menentukan lebar satu modul; nilai yang lebih besar meningkatkan ukuran keseluruhan barcode.  
- **Supplement Space** – jarak antara barcode utama dan bagian tambahan; sesuaikan melalui properti `SupplementSpace`.  
- **Quiet Zone** – margin kosong wajib di sekitar seluruh barcode; pertahankan setidaknya 10 X‑Dimension unit untuk pemindaian yang handal.

Eksperimen dengan pengaturan ini dalam proyek percobaan hingga Anda mencapai keseimbangan visual yang dibutuhkan oleh perangkat pemindai Anda.

## Kasus Penggunaan Umum

| Skenario | Mengapa data tambahan berguna |
|----------|------------------------------|
| **Ekstensi harga ritel** | EAN‑5 dapat mengkodekan informasi harga langsung pada label. |
| **Nomor edisi majalah** | EAN‑2 mengidentifikasi edisi, memungkinkan penyortiran cepat. |
| **Logistik & pelacakan** | Menambahkan supplement kecil pada barcode utama memberikan data rute tambahan tanpa memperbesar ukuran label. |

## Tutorial Data Barcode Tambahan
### [Konfigurasi Data Barcode Tambahan](./supplemental-barcode-data-configuration/)
Hasilkan data barcode tambahan dengan Aspose.BarCode untuk .NET. Kustomisasi barcode EAN-2 dan EAN-5 dengan mudah. Panduan langkah demi langkah untuk pengembang .NET.
### [Kustomisasi Ruang Barcode Tambahan](./supplemental-barcode-space-customization/)
Sesuaikan barcode dengan mudah menggunakan Aspose.BarCode untuk .NET. Kontrol X-Dimension dan ruang tambahan. Coba versi percobaan gratis!

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menghasilkan EAN‑2 dan EAN‑5 dengan kode yang sama?**  
J: Ya. Cukup ubah panjang `SupplementData` (2 digit untuk EAN‑2, 5 digit untuk EAN‑5) dan perpustakaan akan merender simbol yang tepat.

**T: Apakah saya harus menghitung nilai checksum untuk supplement?**  
J: Tidak. Aspose.BarCode secara otomatis menghitung dan menambahkan checksum yang diperlukan untuk Anda.

**T: Apakah ada batas berapa banyak barcode yang dapat saya hasilkan dalam sebuah loop?**  
J: Perpustakaan dioptimalkan untuk generasi massal; cukup perhatikan penggunaan memori saat menangani koleksi gambar yang sangat besar.

**T: Bagaimana cara menyisipkan barcode ke dalam dokumen PDF atau Word?**  
J: Simpan barcode sebagai gambar (PNG, JPEG, dll.) lalu sisipkan menggunakan API generasi dokumen pilihan Anda (misalnya Aspose.PDF atau Aspose.Words).

**T: Bagaimana jika pemindai saya tidak dapat membaca bagian tambahan?**  
J: Pastikan `SupplementSpace` setidaknya 2 X‑Dimension unit dan zona tenang memenuhi spesifikasi pemindai.

---

**Terakhir Diperbarui:** 2026-03-07  
**Diuji Dengan:** Aspose.BarCode untuk .NET 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}