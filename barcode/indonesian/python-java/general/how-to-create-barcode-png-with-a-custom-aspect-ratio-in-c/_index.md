---
category: general
date: 2026-10-05
description: Buat PNG barcode dalam C# dan pelajari cara mengatur rasio aspek 15 untuk
  barcode DataBar omnidirectional yang ditumpuk.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: id
lastmod: 2026-10-05
og_description: Buat barcode PNG dengan C# dan temukan cara mengatur rasio aspek 15
  untuk barcode DataBar omnidirectional yang bertumpuk dalam beberapa langkah.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Buat barcode PNG di C# – tutorial mengatur rasio aspek 15
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Cara membuat PNG barcode dengan rasio aspek khusus di C#
url: /id/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PNG dengan rasio aspek khusus di C#

Jika Anda perlu **membuat barcode PNG** di C#, panduan ini menunjukkan **cara mengatur rasio aspek** 15 untuk barcode DataBar omnidirectional yang ditumpuk. Kami akan membahas setiap panggilan API, menjelaskan mengapa rasio aspek penting, dan memberi Anda contoh lengkap yang dapat dijalankan dan langsung dimasukkan ke proyek .NET apa pun.

Membuat gambar barcode adalah kebutuhan umum untuk sistem inventaris, label pengiriman, dan aplikasi point‑of‑sale ritel. Pada akhir tutorial ini Anda akan memiliki file PNG yang memenuhi spesifikasi visual tepat yang dibutuhkan oleh mitra bisnis Anda. Tanpa alat eksternal, tanpa penyuntingan gambar manual—hanya kode.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 atau lebih baru (contoh menggunakan .NET 6 tetapi dapat bekerja dengan .NET 5+)
* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET)
* Paket NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Izin menulis ke folder tempat Anda ingin menyimpan file PNG

Persyaratan ini minimal; kode yang sama bekerja di .NET Core, .NET Framework, atau aplikasi konsol.

## Membuat barcode PNG dengan Aspose.BarCode

Langkah pertama adalah menginstansiasi kelas `BarcodeGenerator` dengan tipe barcode yang tepat. Pada kasus ini kami menggunakan `EncodeTypes.DatabarStackedOmniDirectional`, yang menghasilkan DataBar yang ditumpuk dan dapat dibaca dari arah manapun.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Mengapa ini penting:* Konstruktor menerima dua argumen—**simbol barcode** dan **string data**. Format DataBar mengharuskan adanya identifier aplikasi GS1, itulah mengapa data contoh dimulai dengan `(01)`.

## Cara mengatur rasio aspek untuk DataBar yang ditumpuk

Lebar visual DataBar dikendalikan oleh properti **rasio aspek**. Rasio yang lebih tinggi membuat bar menjadi lebih lebar, yang dapat meningkatkan keandalan pemindaian pada printer beresolusi rendah.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` menentukan ukuran satu modul (bar atau spasi terkecil). Menjaga nilai ini pada 2 px menghasilkan gambar tajam dan berdensitas tinggi yang cocok untuk kebanyakan printer label.

## Mengatur rasio aspek 15 – penjelasan kode

Sekarang kami menerapkan persyaratan **set aspect ratio 15**. Ini adalah inti tutorial dan menunjukkan panggilan API tepat yang Anda perlukan.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Mengapa 15?* Rasio aspek default untuk DataBar yang ditumpuk adalah 12. Menaikkannya menjadi 15 memperlebar setiap bar sebesar 25 %, yang sering sesuai dengan spesifikasi penyedia logistik yang mengharuskan barcode lebih lebar untuk pemindaian lebih cepat.

## Menyimpan barcode sebagai PNG

Setelah generator dikonfigurasi, langkah terakhir adalah menulis gambar ke disk. Metode `Save` menerima jalur file dan enum format gambar.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Format PNG mempertahankan kualitas lossless, memastikan barcode ditampilkan persis seperti yang dirancang pada layar atau printer apa pun.

## Contoh lengkap dan output yang diharapkan

Berikut adalah program lengkap yang dapat Anda salin ke metode `Main` aplikasi konsol. Program ini mencakup semua langkah yang dijelaskan di atas, plus pesan verifikasi singkat.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Output yang diharapkan**

Menjalankan program akan membuat file bernama `DatabarAspectRatio15.png` yang berisi barcode DataBar yang ditumpuk lebar dan jelas. Saat Anda membuka PNG tersebut, Anda akan melihat barcode yang diregangkan secara horizontal namun tetap mematuhi spesifikasi GS1 DataBar.

![Barcode PNG dengan rasio aspek 15](barcode-aspect15.png)

*Teks alt gambar:* **membuat barcode PNG yang menampilkan DataBar yang ditumpuk dengan rasio aspek 15**

### Tips dan jebakan umum

| Situasi | Rekomendasi |
|-----------|----------------|
| **Gambar terlihat buram** | Tingkatkan `XDimension.Pixels` menjadi 3 px atau lebih, tetapi pertahankan ukuran gambar keseluruhan di bawah 500 px untuk menghindari file berukuran terlalu besar. |
| **Pemindai tidak dapat membaca kode** | Pastikan string data mengikuti format GS1 (`(01)` sebagai awalan). Juga, pastikan resolusi printer minimal 300 dpi. |
| **Butuh format file lain** | Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif`—API mendukung semua format raster utama. |
| **Menjalankan di aplikasi web** | Gunakan `generator.Save(Stream, BarCodeImageFormat.Png)` untuk menulis langsung ke respons HTTP tanpa menyentuh sistem file. |

### Memperluas contoh

* **Beberapa barcode dalam satu gambar:** Buat instance `BarcodeGenerator` tambahan dan gambar mereka pada satu `Bitmap` menggunakan `Graphics`.  
* **Menambahkan teks yang dapat dibaca manusia:** Atur `generator.Parameters.Caption.Visible = true` dan sesuaikan font melalui `generator.Parameters.Caption.Font`.  
* **Rasio aspek dinamis:** Ambil nilai rasio dari file konfigurasi atau basis data untuk menghasilkan barcode dengan lebar bervariasi secara dinamis.

## Kesimpulan

Dalam tutorial ini Anda belajar cara **membuat barcode PNG** di C# dan secara tepat **mengatur rasio aspek** 15 untuk barcode DataBar omnidirectional yang ditumpuk. Kode lengkap yang dapat dijalankan menunjukkan setiap panggilan API yang diperlukan, menjelaskan mengapa setiap pengaturan penting, dan memberikan tips praktis untuk penerapan di dunia nyata.  

Selanjutnya, Anda dapat menjelajahi **cara mengatur rasio aspek** untuk tipe barcode lain (misalnya QR Code atau Code 128) atau mengintegrasikan generator ke layanan ASP .NET Core yang mengembalikan gambar barcode sesuai permintaan. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to create databar PNG images with C# and Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}