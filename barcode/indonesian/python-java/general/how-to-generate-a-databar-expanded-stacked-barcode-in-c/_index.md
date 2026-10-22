---
category: general
date: 2026-10-21
description: Hasilkan gambar barcode databar expanded stacked di C# menggunakan BarcodeGenerator.
  Ikuti panduan langkah demi langkah ini untuk membuat gambar barcode, menyesuaikan
  baris dan kolom, serta mengekspor file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: id
lastmod: 2026-10-21
og_description: Buat barcode databar expanded stacked di C# dengan tutorial ini. Pelajari
  cara menggunakan BarcodeGenerator, mengatur baris dan kolom, serta menyimpan gambar
  PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Membuat barcode databar expanded stacked di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara menghasilkan barcode databar expanded stacked di C#
url: /id/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode databar expanded stacked di C#

Jika Anda perlu menghasilkan barcode **databar expanded stacked** di C#, panduan ini akan menunjukkan cara melakukannya. Simbologi databar expanded stacked ideal untuk mengkodekan sejumlah besar data dalam bentuk yang kompak, dan Anda dapat membuat gambar hanya dengan beberapa baris kode. Anda juga akan belajar cara **menghasilkan gambar barcode** dalam berbagai format dan menyesuaikan baris atau kolom untuk lingkungan pemindaian Anda.

Tutorial ini mencakup semua yang Anda perlukan untuk mulai menghasilkan barcode databar: menginstal pustaka yang diperlukan, menyiapkan folder output, membuat barcode dengan baris atau kolom khusus, dan menyimpan hasilnya sebagai file PNG. Pada akhir tutorial, Anda akan dapat **membuat barcode databar** secara programatis dan menyesuaikan kode untuk format gambar lain atau skenario runtime.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau lebih baru (kode juga berfungsi dengan .NET Core 3.1 dan .NET Framework 4.7+)
* Lingkungan pengembangan seperti Visual Studio 2022, Visual Studio Code, atau Rider
* Akses internet untuk menginstal paket NuGet **Barcode Generator C#** (Aspose.BarCode for .NET)

> **Pro tip:** Jika Anda menggunakan pipeline CI/CD, tambahkan referensi paket NuGet ke file proyek Anda agar build dapat direproduksi.

## Instal pustaka Barcode Generator C# library

Contoh ini menggunakan pustaka Aspose.BarCode, yang menyediakan kelas `BarcodeGenerator` dan enumerasi `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan versi stabil terbaru ke proyek Anda. Setelah instalasi, Anda dapat mengimpor namespace dalam file C# Anda:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Siapkan folder output

Path file yang dapat diandalkan mencegah kesalahan runtime ketika pustaka mencoba menulis gambar. Kode berikut membuat direktori jika belum ada:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Mengapa ini penting:** Mencoba menyimpan ke direktori yang tidak ada akan melempar `IOException`. Membuat folder terlebih dahulu membuat kode lebih kuat untuk pengembangan lokal maupun lingkungan produksi.

## Menghasilkan gambar barcode databar expanded stacked

### Generasi barcode dasar

Cara paling sederhana untuk menghasilkan gambar **databar expanded stacked** adalah dengan menginstansiasi `BarcodeGenerator` dengan nilai `EncodeTypes` yang diinginkan dan payload teks biasa.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Menjalankan potongan kode menghasilkan `DatabarBasic.png` di folder *Barcodes*. Gambar tersebut berisi simbol databar expanded stacked standar dengan tata letak default (4 kolom × 4 baris).

### Menyesuaikan kolom – membuat barcode databar dengan 4 kolom

Anda dapat mengontrol jumlah kolom menggunakan properti `Parameters.Barcode.DataBar.Columns`. Contoh berikut membuat barcode dengan **4 kolom** sambil mempertahankan jumlah baris default.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

File yang dihasilkan, **DatabarCols4.png**, terlihat seperti ini:

![Databar expanded stacked barcode with 4 columns](databar_cols4.png "Databar expanded stacked barcode with 4 columns – generated with C#")

*Image alt text (og_image_alt):* **Sample databar expanded stacked barcode image generated with C#** – ini memenuhi persyaratan SEO untuk teks alt gambar.

### Menyesuaikan baris – membuat barcode databar dengan 3 baris

Demikian pula, Anda dapat menyesuaikan jumlah baris melalui `Parameters.Barcode.DataBar.Rows`. Kode di bawah ini menghasilkan barcode dengan **3 baris** dan jumlah kolom default (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

File **DatabarRows3.png** berisi simbol databar expanded stacked yang sedikit lebih pendek secara vertikal, yang dapat berguna untuk label dengan ruang terbatas.

### Mengekspor ke format lain

Jika Anda membutuhkan tipe gambar lain (misalnya JPEG, BMP, atau SVG), ganti `BarCodeImageFormat.Png` dengan nilai enum yang sesuai:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

Pustaka ini juga mendukung format vektor seperti SVG, yang ideal untuk pencetakan resolusi tinggi.

## Skenario lanjutan

### Menyimpan ke memory stream

Kadang-kadang Anda ingin menyematkan barcode langsung ke respons web atau PDF tanpa menyentuh sistem file. Gunakan `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Menangani input tidak valid

`BarcodeGenerator` memvalidasi payload terhadap simbologi yang dipilih. Jika data mengandung karakter terlarang, `ArgumentException` akan dilempar. Bungkus kode generasi dalam blok try‑catch untuk memberikan pesan error yang ramah:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Menskalakan gambar barcode

Anda dapat mengubah ukuran gambar tanpa mengubah data yang dikodekan dengan mengatur `Parameters.Image.Width` dan `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Menskalakan berguna ketika barcode harus memenuhi persyaratan DPI tertentu untuk pemindai.

## Contoh lengkap yang berfungsi

Berikut adalah aplikasi konsol lengkap yang siap dijalankan dan menunjukkan semua langkah yang dibahas:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Output yang diharapkan**


## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara mengatur kolom untuk barcode Databar Expanded Stacked – panduan lengkap C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Cara membuat contoh generator barcode di C# dengan DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [panduan barcode databar expanded stacked – cara menghasilkan dan mengatur ukurannya di C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}