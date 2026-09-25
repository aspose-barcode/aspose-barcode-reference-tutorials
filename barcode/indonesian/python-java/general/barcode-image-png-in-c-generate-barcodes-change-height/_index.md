---
category: general
date: 2026-08-15
description: Gambar barcode PNG di C# – pelajari cara menghasilkan barcode pos, membuat
  barcode Planet, dan mengubah tinggi barcode dengan generator sederhana.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: id
lastmod: 2026-08-15
og_description: Tutorial gambar barcode PNG di C# menunjukkan cara menghasilkan barcode
  pos, membuat barcode Planet, dan mengubah tinggi barcode menggunakan API BarcodeGenerator.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Gambar barcode PNG di C# – buat dan sesuaikan barcode
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Gambar barcode PNG di C# menghasilkan barcode, ubah tinggi
url: /id/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gambar barcode PNG di C# – menghasilkan barcode, mengubah tinggi

Jika Anda membutuhkan **barcode image PNG** di C#, panduan ini akan memandu Anda melalui proses lengkap. Anda akan belajar cara menghasilkan barcode pos, membuat barcode Planet, dan mengubah tinggi barcode tanpa meninggalkan IDE Anda.

Menghasilkan barcode PNG yang dapat diandalkan adalah kebutuhan umum untuk label pengiriman, sistem inventaris, dan solusi pengiriman otomatis. Pada akhir tutorial ini Anda akan memiliki potongan kode yang dapat digunakan kembali yang menghasilkan file PNG berkualitas tinggi untuk format Planet dan RM4SCC, serta Anda akan memahami cara menyesuaikan tinggi bar untuk memenuhi spesifikasi pos.

## Apa yang Anda butuhkan

- .NET 6+ atau .NET Framework 4.7.2 (API BarcodeGenerator bekerja dengan runtime .NET terbaru apa pun)  
- Referensi ke paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan kompatibel lain yang menyediakan `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`)  
- Pemahaman dasar tentang sintaks C# dan I/O file  

Tidak ada alat tambahan yang diperlukan; kode ini berjalan di Visual Studio, Rider, atau `dotnet` CLI.

## Barcode image PNG – pembuatan dasar

Langkah pertama adalah membuat **barcode image PNG** dengan dimensi default. Ini menetapkan file dasar yang dapat Anda sesuaikan nanti.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Mengapa ini berhasil:**  
- `EncodeTypes.Planet` memberi tahu generator untuk menggunakan simbol Planet, yang diperlukan untuk banyak layanan pos.  
- `XDimension.Pixels` mengontrol lebar bar terkecil; nilai 4 px menghasilkan barcode yang dapat dibaca pada ukuran label tipikal.  
- Metode `Save` menulis file **barcode image PNG** ke disk, mempertahankan semua informasi vektor sebagai piksel raster.

## Ubah tinggi barcode – menyesuaikan berat visual

Pedoman pos sering kali memerlukan tinggi bar tertentu. Potongan kode berikut menunjukkan cara mengatur tinggi khusus 100 piksel untuk barcode Planet yang sama.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Mengapa Anda mengubah tinggi:**  
Bar yang lebih tinggi meningkatkan keandalan pemindaian pada printer beresolusi rendah, sementara bar yang lebih pendek mengurangi ruang label. Properti `BarHeight.Pixels` memungkinkan Anda menyesuaikan atribut ini secara halus tanpa memengaruhi X‑dimension.

## Hasilkan barcode pos – membuat contoh RM4SCC

Format RM4SCC adalah barcode pos umum lain yang digunakan di Britania Raya. Langkah-langkah pembuatannya mencerminkan contoh Planet, memperkuat pola **barcode generator c#**.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Ubah tinggi barcode – variasi RM4SCC

Seperti barcode Planet, Anda dapat menyesuaikan tinggi bar RM4SCC. Kode di bawah mengatur tinggi menjadi 100 px, menghasilkan **barcode image PNG** kedua untuk string data yang sama.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua langkah menghasilkan satu program mandiri yang membuat empat file PNG:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Buat Barcode Tinggi Kustom – Barcode Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Buat Barcode PNG – Rasio Aspek DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Buat gambar barcode C# – Contoh GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}