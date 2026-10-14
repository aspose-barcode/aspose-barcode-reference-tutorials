---
category: general
date: 2026-10-14
description: Pelajari cara menghasilkan pdf417 dengan Aspose.BarCode, menambahkan
  teks khusus, metadata makro, dan mengekspor hasilnya sebagai PNG dalam tutorial
  C# langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Pelajari cara menghasilkan pdf417 dengan Aspose.BarCode. Panduan ini
  menunjukkan langkah demi langkah cara menambahkan teks khusus, metadata makro, dan
  menyimpan barcode sebagai gambar PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Cara menghasilkan pdf417 – panduan lengkap C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Cara menghasilkan pdf417 – panduan lengkap C#
url: /id/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan pdf417 – panduan lengkap C# 

Jika Anda perlu **menghasilkan pdf417** untuk simbol MacroPdf417, tutorial ini akan memandu Anda melalui seluruh proses. Anda akan melihat cara mengonfigurasi opsi khusus macro, menyematkan teks Unicode khusus, dan menyimpan barcode sebagai gambar PNG. Pada akhir panduan, Anda akan memiliki potongan kode C# siap pakai yang dapat ditempatkan ke proyek .NET apa pun, baik itu aplikasi konsol, layanan Windows, atau mikro‑layanan berbasis cloud.

## Jawaban cepat
- **Perpustakaan apa yang saya perlukan?** Aspose.BarCode untuk .NET (mendukung lebih dari 70 simbol).  
- **Apakah saya dapat menambahkan karakter Unicode?** Ya – API sepenuhnya mendukung string UTF‑8 seperti `"Åspóse.Barcóde©"`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi Aspose.BarCode yang valid diperlukan untuk penggunaan tak terbatas; evaluasi gratis cukup untuk pengujian.  
- **Versi .NET mana yang didukung?** .NET 6+, .NET 5, .NET Core 3.1, dan .NET Framework 4.7+.  
- **Apakah PNG format terbaik untuk pencetakan?** PNG mempertahankan kualitas lossless dan ideal untuk pencetakan barcode resolusi tinggi.

## Apa itu pdf417?
`PDF417` adalah barcode linear bertumpuk yang dapat mengkodekan hingga sekitar 1 700 karakter per simbol. Ia banyak digunakan untuk tiket transportasi, kartu identitas, dan pelacakan inventaris karena dapat menyimpan data dalam jumlah besar dalam format yang kompak dan dapat dibaca mesin.

## Mengapa menggunakan Aspose.BarCode untuk menghasilkan pdf417?
Aspose.BarCode mendukung **lebih dari 70 simbol barcode**, memproses file hingga **2 GB** tanpa memuat seluruh dokumen ke memori, dan menjamin **kepatuhan 100 % dengan ISO/IEC 15438**. Dalam pengujian benchmark, perpustakaan ini membuat barcode MacroPdf417 berukuran penuh dalam waktu kurang dari **150 ms** pada laptop pengembangan tipikal, sehingga cukup cepat untuk skenario server dengan throughput tinggi.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* **.NET 6.0 atau lebih baru** (kode juga dapat dijalankan pada .NET Framework 4.7+).  
* **Lisensi Aspose.BarCode untuk .NET yang valid** (versi percobaan gratis cukup untuk pengembangan).  
* **Visual Studio 2022** atau IDE C# lain yang Anda sukai.  
* Familiaritas dasar dengan sintaks C# dan konsep berorientasi objek.  

Tidak ada paket NuGet tambahan yang diperlukan selain **Aspose.BarCode**.

## Cara menghasilkan pdf417 dengan opsi macro?

Muat `BarcodeGenerator` dengan enum `EncodeTypes.MacroPdf417`, atur ukuran modul, konfigurasikan bidang macro, dan akhirnya simpan gambar. Langkah‑langkah berikut menunjukkan urutan tepat yang harus Anda ikuti untuk menghindari jebakan umum.

### Langkah 1: instal paket NuGet Aspose.BarCode

Buka proyek Anda di Visual Studio, lalu jalankan perintah berikut di Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode`, yang berisi kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini.

### Langkah 2: buat generator barcode untuk MacroPdf417

`BarcodeGenerator` adalah kelas inti yang digunakan untuk menghasilkan barcode di Aspose.BarCode.  
Baris pertama membuat instance `BarcodeGenerator` yang menargetkan simbol **MacroPdf417** dan menyematkan teks khusus yang ingin Anda enkode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`BarcodeGenerator` adalah kelas inti Aspose.BarCode untuk membuat barcode apa pun; ia menyimpan semua opsi enkoding dan pengaturan rendering.

### Langkah 3: definisikan ukuran modul dasar

`XDimension` menentukan lebar satu modul (piksel) dalam barcode.  
Ukuran modul mengontrol kepadatan visual barcode. Nilai piksel `2` menghasilkan gambar tajam yang mencetak dengan baik pada printer label standar.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Meningkatkan nilai membuat barcode lebih besar, sementara menurunkannya dapat menyebabkan masalah pemindaian pada perangkat beresolusi rendah.

### Langkah 4: konfigurasikan opsi tata letak khusus macro PDF417

`Columns` menentukan jumlah kolom data dalam barcode PDF417.  
MacroPdf417 memerlukan beberapa parameter tambahan. Pengaturan ini memungkinkan Anda membagi data menjadi beberapa file, mengidentifikasi setiap segmen, dan memverifikasi integritas.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Properti `Columns` memengaruhi lebar barcode, sementara bidang macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) memungkinkan sistem hilir menyusun kembali data asli dengan benar.

### Langkah 5: tambahkan metadata macro tambahan

`MacroPdf417Terminator` menunjukkan apakah segmen saat ini adalah segmen terakhir dalam rangkaian macro.  
Aspose.BarCode memungkinkan Anda menyematkan bidang macro opsional seperti checksum, ukuran file, timestamp, dan informasi pengirim/penerima. Bidang‑bidang ini berguna untuk jejak audit dan deteksi kesalahan.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

Checksum melindungi dari kesalahan transmisi, sementara timestamp dan bidang pengirim memberikan konteks untuk pemrosesan hilir. Menetapkan `MacroPdf417Terminator` ke `Set` menandakan bahwa ini adalah segmen akhir dalam rangkaian macro.

### Langkah 6: simpan barcode sebagai gambar PNG

`Save` menulis gambar barcode yang dihasilkan ke file dalam format yang ditentukan.  
Akhirnya, tulis barcode yang dihasilkan ke disk. PNG mempertahankan kualitas lossless, yang ideal untuk pemindaian.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Setelah kode selesai, file `ExtPDF417Meta.png` berisi barcode MacroPdf417 resolusi tinggi yang mengenkode teks khusus dan semua metadata macro.

#### Output yang diharapkan

Membuka `ExtPDF417Meta.png` menampilkan barcode berorientasi vertikal dengan baris dan kolom yang jelas. Memindai gambar dengan pembaca PDF417 apa pun mengembalikan string asli **Åspóse.Barcóde©** serta bidang macro yang Anda konfigurasikan (file ID, segment ID, checksum, dll.).

## Cara menghasilkan pdf417 tanpa opsi macro?

Untuk membuat barcode PDF417 standar, Anda hanya perlu mengatur simbol ke `EncodeTypes.Pdf417`, menyediakan teks yang akan dienkode, secara opsional menyesuaikan parameter ukuran seperti `XDimension` dan `Columns`, lalu memanggil `Save`. Pendekatan ini mengabaikan semua properti khusus macro, menghasilkan barcode satu segmen yang cocok untuk kebanyakan aplikasi.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Potongan kode ini menunjukkan **cara menghasilkan pdf417** dengan cepat ketika fungsi macro tidak diperlukan. Jawaban langsung: buat `BarcodeGenerator` dengan `EncodeTypes.Pdf417`, atur `CodeText`, secara opsional sesuaikan `XDimension` dan `Columns`, lalu panggil `Save` dengan format gambar yang diinginkan.

## Jebakan umum dan tips profesional

| Masalah | Mengapa terjadi | Solusi |
|-------|----------------|-----|
| Barcode terlalu kecil untuk dipindai | X‑dimension diatur ke 1 piksel atau kolom terlalu banyak | Gunakan setidaknya `2` piksel untuk `XDimension` dan pertahankan kolom antara `3` dan `9` untuk ukuran label tipikal |
| Karakter Unicode muncul sebagai � | Ketidaksesuaian enkoding dalam file proyek | Pastikan file proyek disimpan sebagai UTF-8 dan file sumber memiliki BOM yang tepat |
| Bidang macro diabaikan oleh pemindai | `MacroPdf417Terminator` tidak diatur untuk segmen terakhir | Atur `MacroPdf417Terminator = Pdf417MacroTerminator.Set` pada segmen akhir |
| File gambar rusak | Stream output tidak ditutup dengan benar | Gunakan pernyataan `using` (seperti yang ditunjukkan) untuk menjamin disposisi generator |

## Contoh lengkap yang dapat dijalankan

`BarcodeGenerator` adalah kelas yang membuat gambar barcode.  
Salin kode berikut ke aplikasi konsol baru dan jalankan. Program akan membuat barcode, menyimpannya, dan mencetak jalur output ke konsol.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Menjalankan program mencetak baris serupa dengan:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Buka file tersebut untuk memverifikasi output visual.

## Pertanyaan yang sering diajukan

**T: Bisakah saya menggunakan kode ini dalam API web ASP.NET Core?**  
J: Ya. Kelas `BarcodeGenerator` yang sama berfungsi di runtime .NET apa pun, termasuk ASP.NET Core, selama assembly `Aspose.BarCode` direferensikan.

**T: Apakah Aspose.BarCode mendukung format gambar lain?**  
J: Tentu. Anda dapat menyimpan ke PNG, JPEG, BMP, TIFF, dan bahkan SVG dengan memberikan nilai enum `BarCodeImageFormat` yang sesuai ke metode `Save`.

**T: Seberapa besar data yang dapat dienkode?**  
J: Satu simbol PDF417 dapat menampung hingga 1 700 karakter; dengan MacroPdf417 Anda dapat membagi data ke beberapa segmen, secara efektif mendukung panjang tak terbatas.

**T: Apakah ada cara menambahkan warna pada barcode?**  
J: Ya. Atur properti `ForeColor` dan `BackColor` pada `BarcodeGenerator` sebelum memanggil `Save` untuk menghasilkan barcode berwarna.

**T: Bagaimana jika saya perlu menyematkan barcode langsung ke PDF?**  
J: Gunakan Aspose.PDF untuk menyisipkan gambar PNG atau SVG yang dihasilkan ke halaman PDF, atau gunakan fitur ekspor PDF bawaan Aspose.BarCode.

## Kesimpulan

Anda kini tahu **cara menghasilkan pdf417** untuk simbol MacroPdf417, menyematkan teks Unicode khusus, mengonfigurasi metadata macro, dan mengekspor hasilnya sebagai gambar PNG. Pola yang sama memungkinkan Anda menghasilkan barcode PDF417 biasa ketika opsi macro tidak diperlukan, dan Anda dapat menyesuaikan kode untuk format barcode lain yang didukung Aspose.BarCode. Bereksperimenlah dengan nilai `XDimension` yang berbeda, jumlah kolom, dan kombinasi bidang macro untuk menyempurnakan barcode sesuai printer atau pemindai spesifik Anda.

Selanjutnya, jelajahi topik terkait seperti **membuat barcode dengan teks khusus** untuk QR code, menambahkan filter warna dengan parameter `Color`, atau menyematkan barcode langsung ke dokumen PDF menggunakan Aspose.PDF. Fleksibilitas Aspose.BarCode memungkinkan Anda menangani segala hal mulai dari barcode satu baris sederhana hingga barcode macro multi‑segmen yang kompleks dengan hanya beberapa baris kode C#.

Selamat coding, dan nikmati keandalan yang dibawa Aspose.BarCode ke solusi barcode .NET Anda!

## Apa yang harus Anda pelajari selanjutnya?

Tutorial berikut mencakup topik terkait yang erat kaitannya dengan teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Terakhir diperbarui:** 2026-10-14  
**Diuji dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Create Macro Pdf417 Barcode With Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Adjust Barcode Size C Guide To Generate Pdf417 Barcodes](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Read Barcode From Image C Complete Guide With Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}