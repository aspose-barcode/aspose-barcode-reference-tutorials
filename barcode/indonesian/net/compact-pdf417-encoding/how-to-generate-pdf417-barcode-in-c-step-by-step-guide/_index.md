---
category: general
date: 2026-09-10
description: Buat kode batang PDF417 dalam C# dengan cepat. Pelajari cara menghasilkan
  PDF417 dan cara mengubah ukuran kode batang dengan Aspose.BarCode dalam hanya beberapa
  baris.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: id
lastmod: 2026-09-10
og_description: Buat kode batang PDF417 di C# secara instan. Tutorial ini menunjukkan
  cara menghasilkan PDF417 dan cara mengubah ukuran kode batang menggunakan Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Buat barcode PDF417 di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cara menghasilkan kode batang PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan PDF417 barcode di C# – panduan langkah demi langkah

Jika Anda perlu **menghasilkan PDF417 barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan melihat contoh singkat yang siap dijalankan yang membuat PDF417 barcode, memungkinkan Anda mengontrol ukurannya, dan menyimpan hasilnya sebagai gambar PNG.

Menghasilkan PDF417 barcode adalah kebutuhan umum untuk sistem inventaris, boarding pass, dan pelacakan dokumen. Dalam tutorial ini kami juga membahas **cara mengubah ukuran barcode** sehingga kode dapat beradaptasi dengan kebutuhan pencetakan atau tampilan layar yang berbeda.

## Prerequisites

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 atau lebih baru (kode juga bekerja dengan .NET Framework 4.6+)
* Visual Studio 2022 atau IDE C# apa pun
* Paket NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Pemahaman dasar tentang aplikasi konsol C#

## Project setup

1. Buat proyek konsol baru:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Tambahkan referensi Aspose.BarCode (lihat prasyarat).  

3. Buka `Program.cs` dan ganti isinya dengan contoh lengkap di bawah ini.

## Step 1: Generate PDF417 barcode

Langkah pertama adalah membuat instance `BarcodeGenerator` yang dikonfigurasi untuk simbol **PDF417**. Objek ini adalah titik masuk untuk semua operasi barcode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Mengapa ini penting* – Nilai enum `EncodeTypes.Pdf417` memberi tahu Aspose.BarCode untuk menggunakan standar PDF417, sementara argumen kedua menyediakan data yang akan dienkode. Generator kini menyimpan objek barcode lengkap yang dapat Anda sesuaikan sebelum disimpan.

## Step 2: How to change barcode size (module size)

PDF417 barcode terdiri dari modul kotak kecil. Menyesuaikan ukuran modul mengubah dimensi keseluruhan gambar tanpa mengubah data yang dienkode.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Mengapa ini penting* – `XDimension` yang lebih besar menghasilkan barcode lebih besar yang cocok untuk pencetakan resolusi tinggi; nilai yang lebih kecil lebih baik untuk tampilan di layar. Nilai default biasanya 1 px, yang dapat terlihat sempit pada monitor modern.

## Step 3: Configure layout – columns and rows

PDF417 memungkinkan Anda menentukan jumlah kolom dan baris, yang memengaruhi bentuk barcode serta kapasitas koreksi kesalahannya.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Mengapa ini penting* – Lebih banyak kolom membuat barcode lebih lebar, sementara lebih banyak baris membuatnya lebih tinggi. Sesuaikan nilai ini agar cocok dengan ruang yang tersedia di UI atau label cetak Anda.

## Step 4: Save the barcode image

Akhirnya, tulis barcode ke sebuah file. Di sini kami menggunakan PNG karena mempertahankan tepi yang tajam dan mendukung transparansi.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Menjalankan program akan membuat `LayoutPdf417.png` di folder output proyek. Gambar akan terlihat seperti ini:

![contoh menghasilkan barcode PDF417 menampilkan 4 kolom dan 9 baris](https://example.com/images/pdf417-sample.png){#barcode-image alt="contoh menghasilkan barcode PDF417 menampilkan 4 kolom dan 9 baris"}

*Tip*: Jika Anda memerlukan format gambar lain (JPEG, BMP, TIFF), ganti `BarCodeImageFormat.Png` dengan nilai enum yang sesuai.

## How to generate PDF417 – alternative data sources

Kode di atas menggunakan string yang ditulis keras `"Layout test"`. Dalam skenario dunia nyata Anda sering mengambil data dari basis data, file, atau input pengguna.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Langkah-langkah lainnya (ukuran, tata letak, penyimpanan) tetap tidak berubah. Ini menunjukkan **cara menghasilkan PDF417** dari sumber dinamis tanpa kompleksitas tambahan.

## Common pitfalls and how to avoid them

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Barcode appears blurry | `XDimension` set too low for the output resolution | Increase `XDimension.Pixels` or save as a vector format like SVG (`BarCodeImageFormat.Svg`) |
| Text does not fit in the chosen layout | Too many characters for the selected rows/columns | Reduce the number of rows/columns or split the data into multiple barcodes |
| Image file not created | Output folder does not exist or write permissions missing | Ensure the directory exists (`Directory.CreateDirectory`) and the app runs with proper rights |

## Verifying the barcode

Setelah menghasilkan gambar, Anda dapat memverifikasinya menggunakan aplikasi pemindai PDF417 apa pun (ponsel memiliki pemindai gratis) atau pembaca bawaan Aspose.BarCode:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Jika output cocok dengan teks asli, proses **menghasilkan PDF417 barcode** berhasil.

## Full, runnable example

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke `Program.cs`. Program ini mencakup semua direktif `using`, penanganan error, dan komentar.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Menjalankan program ini mencetak:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Anda kini memiliki **solusi lengkap yang berdiri sendiri** untuk menghasilkan PDF417 barcode dan mengontrol ukurannya.

## Conclusion

Dalam tutorial ini Anda belajar cara **menghasilkan PDF417 barcode** di C# menggunakan Aspose.BarCode, cara **mengubah ukuran barcode** dengan menyesuaikan X‑dimension, dan cara mengonfigurasi kolom serta baris untuk kontrol tata letak. Anda juga melihat cara memverifikasi hasil secara programatik dan cara menyesuaikan kode untuk data dinamis.

Selanjutnya, Anda mungkin ingin menjelajahi:

* **Cara menghasilkan PDF417** dengan penyetelan tingkat koreksi kesalahan (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Mengekspor ke **format vektor** (SVG, EPS) untuk skala tak terbatas
* Menyematkan barcode dalam dokumen PDF dengan **Aspose.PDF**

Bereksperimenlah dengan berbagai ukuran modul dan opsi tata letak untuk menyesuaikan kebutuhan UI atau pencetakan spesifik Anda. Selamat coding!

## What Should You Learn Next?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menghasilkan Barcode PDF417 dengan Aspose – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [sesuaikan ukuran barcode – panduan C# untuk menghasilkan barcode PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Cara Menyimpan Barcode di C# – Menghasilkan Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}