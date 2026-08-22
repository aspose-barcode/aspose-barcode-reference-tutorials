---
category: general
date: 2026-08-22
description: Pelajari cara menghasilkan barcode pos di C# dan mengontrol tinggi bar,
  dimensi X, serta format gambar menggunakan perpustakaan generator barcode C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- barcode generator c#
- barcode x dimension
- barcode image format
- change barcode width
language: id
lastmod: 2026-08-22
og_description: Hasilkan kode batang pos dalam C# dengan kontrol penuh atas tinggi
  bar, dimensi X, dan format gambar. Ikuti tutorial langkah demi langkah ini untuk
  membuat simbol pos yang sempurna.
og_image_alt: Example of a generated postal barcode with custom bar height in C#
og_title: Buat barcode pos di C# – panduan lengkap dengan ukuran khusus
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate postal barcode in C# and control bar height,
    X dimension, and image format using the barcode generator C# library.
  headline: How to generate postal barcode in C# with custom dimensions
  type: TechArticle
tags:
- barcode
- C#
- image processing
title: Cara menghasilkan kode batang pos di C# dengan dimensi khusus
url: /id/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode pos di C# dengan dimensi khusus

Jika Anda perlu menghasilkan barcode pos di C#, panduan ini menunjukkan alur kerja lengkapnya. Anda akan melihat cara mengontrol tinggi bar, menyesuaikan dimensi X barcode, dan memilih format gambar barcode yang tepat.

Barcode pos digunakan oleh layanan pos di seluruh dunia, dan implementasi yang handal harus menghasilkan dimensi yang konsisten di berbagai simbol. Dalam tutorial ini Anda akan belajar menggunakan kelas **BarcodeGenerator**, mengubah lebar barcode, dan menyimpan hasilnya sebagai PNG, JPEG, atau format lain yang didukung.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 atau yang lebih baru terpasang  
* Referensi ke paket NuGet **Aspose.BarCode** (atau perpustakaan generator barcode C# yang kompatibel)  
* Familiaritas dasar dengan sintaks C# dan Visual Studio atau IDE pilihan Anda  

Anda tidak memerlukan layanan eksternal apa pun; kode dijalankan sepenuhnya di mesin klien.

## Langkah 1: Siapkan proyek dan impor namespace

Buat aplikasi konsol baru dan tambahkan perpustakaan barcode. Pernyataan `using` berikut memberi Anda akses ke generator dan enum format‑gambar.

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator, EncodeTypes, etc.
using Aspose.BarCode;               // Contains BarCodeImageFormat
```

Kelas `BarcodeGenerator` adalah inti dari API generator barcode C#. Ia membuat objek yang menyimpan semua parameter rendering.

## Langkah 2: Hasilkan barcode pos dasar dengan dimensi default

Contoh pertama membuat barcode Planet menggunakan tinggi bar default. Ini memperlihatkan konfigurasi minimal yang diperlukan untuk menghasilkan barcode pos.

```csharp
// Create a Planet barcode with the default bar height
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X dimension) to 4 pixels – this defines the narrow bar size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG using the default bar height
barcodeGenerator.Save("PostalPlanetDefault.png", BarCodeImageFormat.Png);
```

*Mengapa ini berhasil*: Ketika Anda mengabaikan properti `BarHeight`, perpustakaan menerapkan tinggi standar yang ditetapkan untuk simbol yang dipilih. `XDimension` mengontrol **dimensi X barcode**, yang secara langsung memengaruhi lebar keseluruhan simbol.

## Langkah 3: Ubah lebar barcode dan tingkatkan tinggi bar

Seringkali Anda memerlukan bar yang lebih tinggi untuk memenuhi pedoman pengiriman tertentu. Kode berikut menetapkan tinggi bar khusus sebesar 100 piksel sambil mempertahankan dimensi X yang sama.

```csharp
// Re‑use the generator for a custom height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Increase the bar height to 100 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save using the same PNG format
barcodeGenerator.Save("PostalPlanetHeight100.png", BarCodeImageFormat.Png);
```

*Mengapa menyesuaikan tinggi*: Properti `BarHeight` mengontrol ukuran vertikal setiap bar. Untuk layanan pos yang mengharuskan tinggi minimum, menetapkan nilai ini memastikan kepatuhan tanpa memengaruhi proses enkoding.

## Langkah 4: Hasilkan barcode RM4SCC dengan pengaturan default

RM4SCC adalah simbol pos umum lainnya. Kode di bawah ini meniru contoh Planet tetapi mengganti enum `EncodeTypes`.

```csharp
// Create an RM4SCC barcode with default bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG; default height is applied automatically
barcodeGenerator.Save("PostalRM4SCCDefault.png", BarCodeImageFormat.Png);
```

Karena perpustakaan secara otomatis memilih tinggi default yang tepat untuk RM4SCC, Anda memperoleh gambar yang sesuai standar dengan satu baris kode.

## Langkah 5: Ubah tinggi bar untuk barcode RM4SCC

Jika sistem pengiriman mengharuskan bar yang lebih tinggi, Anda dapat memodifikasi tinggi persis seperti yang Anda lakukan untuk Planet.

```csharp
// RM4SCC barcode with a custom 100‑pixel bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the result; you may also choose JPEG, BMP, or TIFF
barcodeGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
```

*Tip*: Enum **format gambar barcode** mencakup `Jpeg`, `Bmp`, `Tiff`, dan `Gif`. Pilih format yang sesuai dengan pipeline pemrosesan downstream Anda.

## Langkah 6: Jelajahi format gambar lain dan sesuaikan dimensi secara halus

Berikut ini cuplikan kode ringkas yang memperlihatkan cara mengganti format output dan bereksperimen dengan berbagai dimensi X.

```csharp
string[] formats = { "Png", "Jpeg", "Bmp", "Tiff" };
int[] xDims = { 2, 3, 4, 5 };

foreach (var fmt in formats)
{
    foreach (var x in xDims)
    {
        barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = x;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 80; // consistent height

        // Dynamically choose the format enum
        BarCodeImageFormat imageFormat = (BarCodeImageFormat)Enum.Parse(
            typeof(BarCodeImageFormat), fmt, true);

        string fileName = $"Planet_X{x}_{fmt}.png";
        barcodeGenerator.Save(fileName, imageFormat);
    }
}
```

*Mengapa iterasi*: Loop ini menghasilkan matriks gambar yang menggambarkan bagaimana **mengubah lebar barcode** (melalui dimensi X) memengaruhi tampilan keseluruhan. Ini juga menunjukkan bahwa generator yang sama dapat menghasilkan berbagai **format gambar barcode** tanpa perubahan kode tambahan.

## Kesalahan umum dan cara menghindarinya

| Masalah | Penyebab | Solusi |
|-------|--------|-----|
| Bar terlalu tipis | Dimensi X diatur ke 1 piksel atau lebih rendah | Atur `XDimension.Pixels` minimal 2 untuk keterbacaan |
| Gambar blur | Menyimpan sebagai JPEG dengan kompresi tinggi | Gunakan `BarCodeImageFormat.Png` untuk output lossless |
| Ukuran tidak sesuai saat cetak | DPI tidak dipertimbangkan | Atur `barcodeGenerator.Parameters.ImageResolution.Dpi` jika printer mengharapkan DPI tertentu |
| Simbol salah | Menggunakan `EncodeTypes.Planet` untuk data RM4SCC | Pilih nilai `EncodeTypes` yang tepat sesuai spesifikasi layanan pos |

## Verifikasi output

Setelah menjalankan kode, buka salah satu file PNG yang dihasilkan. Anda harus melihat barcode berbentuk persegi panjang yang jelas dengan bar vertikal yang seragam. Tinggi bar akan sesuai dengan nilai yang Anda tetapkan (misalnya, 100 piksel), dan lebar total akan mencerminkan **dimensi X barcode** yang Anda konfigurasikan.

Jika Anda perlu menyematkan gambar dalam halaman web, format PNG bekerja secara native di browser. Untuk laporan PDF, Anda dapat mengonversi PNG menjadi array byte dan menyisipkannya menggunakan perpustakaan PDF.

## Contoh lengkap – semua langkah dalam satu program

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Directory for output files
        const string outDir = @"C:\Barcodes\";

        // 1. Planet barcode – default height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, null, "PlanetDefault.png");

        // 2. Planet barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, 100, "PlanetHeight100.png");

        // 3. RM4SCC barcode – default height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, null, "RM4SCCDefault.png");

        // 4. RM4SCC barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, 100, "RM4SCCHeight100.png");
    }

    /// <summary>
    /// Creates a barcode image with optional custom height.
    /// </summary>
    static void GenerateBarcode(string folder, EncodeTypes type, string data,
                                int xDim, int? barHeight, string fileName)
    {
        var generator = new BarcodeGenerator(type, data);
        generator.Parameters.Barcode.XDimension.Pixels = xDim;

        if (barHeight.HasValue)
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight.Value;

        generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
    }
}
```

Menjalankan program ini menghasilkan empat file PNG di `C:\Barcodes\`. Setiap file memperlihatkan kombinasi berbeda dari **menghasilkan barcode pos**, **dimensi X barcode**, dan **format gambar barcode**.

## Kesimpulan

Anda kini tahu cara menghasilkan barcode pos di C# dan mengendalikan tinggi bar, lebar modul, serta format output secara penuh. Dengan menyesuaikan **dimensi X barcode** dan menggunakan **format gambar barcode** yang tepat, Anda dapat memenuhi spesifikasi pengiriman apa pun dan mengintegrasikan simbol ke dalam aplikasi desktop, web, atau mobile.

Selanjutnya, jelajahi fitur lanjutan seperti menambahkan teks yang dapat dibaca manusia, menerapkan palet warna, atau menyematkan barcode dalam dokumen PDF. Topik‑topik tersebut melibatkan konsep **generator barcode C#** yang sama yang baru saja Anda kuasai, sehingga Anda dapat memperluas fondasi ini dengan percaya diri.

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}