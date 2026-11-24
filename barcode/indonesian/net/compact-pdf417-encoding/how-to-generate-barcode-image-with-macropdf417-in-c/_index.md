---
category: general
date: 2026-11-23
description: Pelajari cara menghasilkan gambar barcode menggunakan Aspose.BarCode
  untuk .NET dengan metadata MacroPdf417 dalam C#. Ikuti panduan langkah demi langkah
  lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: id
lastmod: 2026-11-23
og_description: Cara menghasilkan gambar barcode menggunakan Aspose.BarCode untuk
  .NET. Tutorial ini menunjukkan konfigurasi metadata MacroPdf417 dan pembuatan barcode
  dengan C#.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Cara menghasilkan gambar barcode dengan MacroPdf417 di C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Cara menghasilkan gambar barcode dengan MacroPdf417 di C#
url: /id/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan gambar barcode dengan MacroPdf417 di C#

Jika Anda perlu **menghasilkan gambar barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya dengan **Aspose.BarCode for .NET**. Kami akan menjelaskan cara membuat **barcode MacroPdf417**, mengonfigurasi metadata-nya, dan menyimpan hasilnya sebagai file PNG.

Tutorial ini mencakup semua hal mulai dari menginstal perpustakaan hingga menulis program konsol lengkap yang dapat dijalankan. Pada akhir tutorial Anda akan memiliki contoh kode siap pakai yang menghasilkan gambar barcode berkualitas tinggi, dan Anda akan memahami cara **mengatur metadata barcode**, memilih **format gambar barcode**, serta mengatasi masalah umum. Tidak diperlukan pengalaman sebelumnya dengan Aspose—hanya pengetahuan dasar tentang C#.

## Instal Aspose.BarCode untuk .NET

Sebelum Anda dapat **menghasilkan gambar barcode**, Anda memerlukan paket NuGet Aspose.BarCode.

1. Buka terminal atau Package Manager Console di Visual Studio.  
2. Jalankan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode.Generation`, yang berisi kelas `BarcodeGenerator` yang digunakan untuk **pembuatan barcode C#**.

> **Pro tip:** Gunakan versi stabil terbaru (per November 2026 versi saat ini adalah 24.11) untuk mendapatkan fitur terbaru dan perbaikan bug.

## Buat instance BarcodeGenerator

Langkah kode pertama membuat `BarcodeGenerator` yang dikonfigurasi untuk tipe **barcode MacroPdf417** dan menyediakan string data yang ingin Anda enkode.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

Blok `using` memastikan generator dibuang dengan benar, melepaskan sumber daya yang tidak dikelola.

## Konfigurasikan tampilan dasar

Barcode yang dapat dibaca dimulai dengan dimensi yang masuk akal. Di sini kami mengatur lebar piksel setiap modul (`XDimension`) dan jumlah kolom untuk matriks PDF417.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Mengapa nilai‑nilai ini?*  
- **XDimension** mengontrol ketebalan setiap bar; 2 piksel bekerja dengan baik untuk tampilan layar dan sebagian besar printer.  
- **Columns** memengaruhi lebar keseluruhan; jumlah kolom yang kecil membuat barcode tetap kompak sambil mempertahankan kapasitas koreksi kesalahan.

## Atur metadata barcode (spesifik MacroPdf417)

MacroPdf417 memungkinkan Anda menyematkan informasi tingkat file langsung ke dalam barcode. Di sinilah Anda **mengatur metadata barcode** seperti ID file, ID segmen, dan cap waktu.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Apa arti masing‑masing properti

| Property | Purpose |
|----------|---------|
| **MacroPdf417FileID** | Pengidentifikasi unik untuk file logis yang menjadi milik barcode. |
| **MacroPdf417SegmentID** | Indeks segmen saat ini (berbasis 0). |
| **MacroPdf417SegmentsCount** | Jumlah total segmen yang membentuk seluruh file. |
| **MacroPdf417FileName** | Nama file sumber yang dapat dibaca manusia. |
| **MacroPdf417Checksum** | Checksum CCITT‑16 opsional untuk verifikasi integritas data. |
| **MacroPdf417FileSize** | Ukuran yang diharapkan dari file asli dalam byte. |
| **MacroPdf417TimeStamp** | Tanggal dan waktu barcode dibuat – berguna untuk pelacakan versi. |
| **MacroPdf417Addressee / Sender** | String khusus yang dapat berisi informasi routing. |
| **MacroPdf417Terminator** | Menunjukkan apakah segmen ini adalah yang terakhir (`Set`) atau tidak (`Unset`). |

> **Edge case:** Jika Anda berencana membagi dokumen besar menjadi banyak segmen, pertahankan `SegmentsCount` konsisten di semua barcode yang dihasilkan. Jumlah yang tidak cocok akan menyebabkan kegagalan decoding.

## Pilih format gambar barcode dan simpan

Aspose mendukung banyak **format gambar barcode** (PNG, JPEG, BMP, TIFF, dll.). PNG bersifat loss‑less dan bekerja dengan baik untuk sebagian besar skenario web dan cetak.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Ganti `YOUR_DIRECTORY` dengan folder absolut atau relatif di mana aplikasi memiliki izin menulis.

Saat program dijalankan, Anda akan melihat pesan konsol yang mengonfirmasi lokasi file. Buka file PNG dengan penampil gambar apa pun—Anda akan melihat **barcode MacroPdf417** yang tajam yang mengenkode teks yang diberikan serta metadata yang Anda definisikan.

### Output yang diharapkan

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

Ukuran file gambar akan kira‑kira 30‑40 KB, tergantung pada `XDimension` dan jumlah kolom yang dipilih.

## Verifikasi barcode dan pemecahan masalah

1. **Pemeriksaan visual** – Barcode harus menampilkan serangkaian kolom bertumpuk dengan zona tenang (margin putih) di sekelilingnya.  
2. **Uji decoding** – Gunakan aplikasi pemindai barcode atau kelas Aspose.BarCode `BarCodeReader` untuk membaca kembali gambar dan memastikan semua bidang metadata tersemat dengan benar.  



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Buat gambar barcode PDF417 dengan Aspose.BarCode di C# – panduan langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Cara menghasilkan barcode dengan teks khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Cara membaca barcode dari gambar menggunakan C# dengan Aspose.BarCode – panduan langkah demi langkah](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}