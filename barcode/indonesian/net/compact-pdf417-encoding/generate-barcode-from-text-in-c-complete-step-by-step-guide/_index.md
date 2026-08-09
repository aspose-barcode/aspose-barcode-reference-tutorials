---
category: general
date: 2026-08-09
description: Hasilkan barcode dari teks di C# dengan Aspose.BarCode. Pelajari cara
  menghasilkan barcode, menangani karakter khusus, dan membuat barcode PDF417 C# dengan
  cepat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- barcode with special characters
- barcode encode types
- create pdf417 barcode c#
language: id
lastmod: 2026-08-09
og_description: Hasilkan barcode dari teks dalam C# menggunakan Aspose.BarCode. Tutorial
  ini menunjukkan cara menghasilkan barcode, mendukung karakter khusus, dan membuat
  barcode PDF417 C# dengan kode lengkap.
og_image_alt: Screenshot of a generated MicroPdf417 barcode saved as PNG
og_title: Hasilkan barcode dari teks di C# – panduan langkah demi langkah cepat
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate barcode from text in C# with Aspose.BarCode. Learn how to
    generate barcode, handle special characters, and create PDF417 barcode C# quickly.
  headline: Generate barcode from text in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose
- encoding
title: Menghasilkan barcode dari teks di C# – panduan langkah demi langkah lengkap
url: /id/net/compact-pdf417-encoding/generate-barcode-from-text-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan barcode dari teks di C# – panduan lengkap langkah demi langkah

Jika Anda perlu **menghasilkan barcode dari teks** dalam aplikasi .NET, panduan ini akan memandu Anda melalui seluruh proses. Anda akan melihat cara menghasilkan barcode, mengelola karakter khusus, dan membuat implementasi barcode PDF417 C# yang langsung dapat digunakan.

Menghasilkan barcode dari teks adalah kebutuhan umum untuk sistem inventaris, platform tiket, dan alur kerja dokumen. Pada akhir tutorial ini Anda akan memiliki aplikasi konsol C# yang dapat dijalankan dan menghasilkan gambar PNG MicroPdf417 menggunakan Aspose.BarCode. Tidak diperlukan layanan eksternal, dan kode ini menangani karakter Unicode seperti “Å”, “©”, dan “é”.

## Prerequisites

- .NET 6.0 SDK atau yang lebih baru (kode ini juga berfungsi dengan .NET Core 3.1 dan .NET Framework 4.7+)
- Visual Studio 2022 (atau IDE apa pun yang mendukung C#)
- **Aspose.BarCode for .NET** paket NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Pengetahuan dasar tentang sintaks C#

## Generate barcode from text – setting up the generator

Langkah pertama adalah membuat instance `BarcodeGenerator` yang mengetahui **tipe enkode barcode** yang Anda inginkan. Pada tutorial ini kami menggunakan `EncodeTypes.MicroPdf417`, yang merupakan varian kompak dari PDF417 cocok untuk string data pendek.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MicroPdf417 with the desired text
        // This demonstrates "generate barcode from text" with Unicode characters.
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Continue with configuration (see next sections)
        ConfigureGenerator(generator);
        SaveBarcode(generator);
    }

    // Configuration is split into its own method for clarity.
    static void ConfigureGenerator(BarcodeGenerator generator)
    {
        // Step 2: Define the X dimension of the barcode modules (in pixels)
        // XDimension controls the width of the smallest bar; 2 px gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Set the number of columns for the PDF417 layout.
        // Fewer columns produce a taller barcode; 4 columns works well for short strings.
        generator.Parameters.Barcode.Pdf417.Columns = 4;
    }

    static void SaveBarcode(BarcodeGenerator generator)
    {
        // Step 4: Save the generated barcode as a PNG image.
        // You can change BarCodeImageFormat to Jpeg, Gif, etc., if needed.
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "MicroPdf417.png"
        );
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Mengapa ini berhasil:**  
- `EncodeTypes.MicroPdf417` memberi tahu pustaka untuk menggunakan keluarga PDF417, memenuhi kebutuhan **create pdf417 barcode c#**.  
- Konstruktor menerima teks mentah, yang merupakan inti dari **generate barcode from text**.  
- Dukungan Unicode sudah built‑in, sehingga karakter seperti “Å” dan “©” dienkode dengan benar, menangani **barcode with special characters**.

## How to generate barcode with special characters

Ketika data Anda berisi simbol non‑ASCII, Anda harus memastikan generator menggunakan enkoding UTF‑8. Aspose.BarCode secara otomatis mendeteksi Unicode, tetapi Anda dapat secara eksplisit mengatur enkoding teks jika mengalami masalah:

```csharp
generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;
```

Menambahkan baris ini sebelum `ConfigureGenerator` menjamin bahwa **barcode with special characters** ditampilkan dengan benar di semua platform.

### Practical tip
Jika output terlihat berantakan, periksa apakah font yang digunakan oleh renderer barcode mendukung glyph yang diperlukan. Anda dapat menyematkan font TrueType khusus melalui:

```csharp
generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";
```

## Barcode encode types you can choose

Aspose.BarCode mendukung puluhan **tipe enkode barcode**, masing‑masing cocok untuk kasus penggunaan yang berbeda:

| Encode type                | Kasus penggunaan umum                |
|----------------------------|--------------------------------------|
| `EncodeTypes.Code128`      | Label pengiriman, inventaris         |
| `EncodeTypes.QR`           | Pembayaran seluler, URL              |
| `EncodeTypes.Pdf417`       | SIM driver, boarding pass            |
| `EncodeTypes.MicroPdf417`  | Payload data kecil, ruang terbatas   |
| `EncodeTypes.DataMatrix`   | Item sangat kecil, kepadatan data tinggi |

Mengubah tipe enkode semudah mengganti nilai enum di konstruktor:

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Fleksibilitas ini memungkinkan Anda menjawab pertanyaan tentang **barcode encode types** tanpa meninggalkan IDE.

## Create PDF417 barcode C# – final steps and verification

Setelah mengonfigurasi generator, bagian terakhir dari **create pdf417 barcode c#** adalah menyimpan gambar dan mengonfirmasi hasilnya.

```csharp
// Save as PNG (lossless, ideal for further processing)
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Jalankan program (`dotnet run`) dan Anda akan melihat pesan konsol serupa dengan:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\MicroPdf417.png
```

Buka file PNG; Anda akan melihat barcode MicroPdf417 yang tajam yang mengenkripsi string “Åspóse.Barcóde©”. Memindainya dengan pemindai barcode seluler (misalnya ZXing) mengembalikan teks asli, membuktikan bahwa **generate barcode from text** berfungsi bahkan dengan karakter khusus.

### Edge case: very long text

MicroPdf417 memiliki kapasitas data maksimum 1 KB. Jika input Anda melebihi batas ini, pustaka akan melempar `ArgumentException`. Untuk menanganinya secara elegan:

```csharp
try
{
    generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Data too long for MicroPdf417: {ex.Message}");
}
```

Untuk payload yang lebih besar, beralihlah ke `EncodeTypes.Pdf417` penuh atau `EncodeTypes.DataMatrix`.

## Common pitfalls and how to avoid them

| Masalah                               | Penyebab                                 | Solusi |
|---------------------------------------|------------------------------------------|--------|
| Barcode terlihat buram                | XDimension terlalu rendah (mis., 1 px)   | Tingkatkan `XDimension.Pixels` menjadi 2‑3 px |
| Karakter Unicode menjadi `?`          | Enkoding teks default adalah ASCII       | Atur `TextEncoding = Encoding.UTF8` |
| File gambar tidak dibuat              | Direktori output tidak ada               | Gunakan `Directory.CreateDirectory` sebelum `Save` |
| Pemindai tidak dapat membaca barcode  | Terlalu banyak kolom untuk data pendek   | Kurangi `Pdf417.Columns` (mis., 3‑4) |

## Full source code (ready to copy)

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create the generator – this is the core of "generate barcode from text"
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Ensure Unicode characters are handled correctly
        generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;

        // Optional: set a font that contains the required glyphs
        generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";

        // Configure visual appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Prepare output directory
        string outputDir = Path.Combine(Environment.CurrentDirectory, "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "MicroPdf417.png");

        // Save the barcode image
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
        catch (ArgumentException ex)
        {
            Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
        }
    }
}
```

**Output yang diharapkan:** sebuah file bernama `MicroPdf417.png` yang berada di folder `output`, berisi barcode MicroPdf417 yang jelas dan mengenkripsi string asli dengan karakter khusus.

## Conclusion

Anda kini tahu cara **menghasilkan barcode dari teks** di C# menggunakan Aspose.BarCode, cara menangani **barcode with special characters**, dan cara **create pdf417 barcode c#** dengan kontrol penuh atas opsi enkoding. Dengan menyesuaikan **barcode encode types** Anda dapat menghasilkan QR code, Code128, DataMatrix, atau format lain yang didukung.

Selanjutnya, jelajahi topik berikut untuk memperdalam keahlian barcode Anda:

- **Cara menghasilkan barcode** secara batch untuk ribuan catatan (gunakan `Parallel.ForEach` untuk kecepatan)
- Menyesuaikan warna dan menambahkan logo di dalam barcode
- Mengintegrasikan pembuatan barcode ke dalam API ASP.NET Core untuk pengiriman gambar secara real‑time
- Menggunakan pustaka lain seperti ZXing.Net atau IronBarcode sebagai alternatif open‑source

Silakan bereksperimen dengan dimensi, pengaturan kolom, dan tipe enkode yang berbeda. Selamat coding, semoga aplikasi Anda dapat memindai dengan sempurna!

## What Should You Learn Next?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}