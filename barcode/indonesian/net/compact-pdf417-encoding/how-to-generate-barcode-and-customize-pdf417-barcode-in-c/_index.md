---
category: general
date: 2026-09-19
description: Cara menghasilkan barcode di C# dengan panduan langkah demi langkah.
  Pelajari cara menyesuaikan pengaturan barcode PDF417 dan membuat gambar barcode
  yang dapat langsung digunakan oleh pengembang C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: id
lastmod: 2026-09-19
og_description: Cara menghasilkan barcode di C# dengan petunjuk detail. Sesuaikan
  parameter barcode PDF417 dan buat gambar barcode yang dapat digunakan proyek C#
  hari ini.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Cara menghasilkan barcode dan menyesuaikan barcode PDF417 di C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Cara menghasilkan barcode dan menyesuaikan barcode PDF417 di C#
url: /id/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode dan menyesuaikan barcode PDF417 di C#

Jika Anda perlu **cara menghasilkan barcode** dalam aplikasi .NET, tutorial ini menunjukkan solusi lengkap yang siap‑jalan. Anda akan belajar cara menyesuaikan dimensi barcode PDF417, memilih jumlah kolom, dan akhirnya **membuat gambar barcode C#** yang dapat langsung disematkan dalam proyek.

Menghasilkan barcode tidak memerlukan pipeline build yang kompleks. Pada akhir panduan ini Anda akan memiliki file PNG yang berisi barcode MicroPDF417 dengan ukuran dan resolusi yang tepat sesuai kebutuhan Anda.

## Prerequisites

Anda harus memiliki hal‑hal berikut terpasang sebelum memulai:

* .NET 6.0 SDK atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.6+)
* Visual Studio 2022 (atau editor C# apa pun yang Anda sukai)
* Paket NuGet Aspose.BarCode untuk .NET – instal dengan  
  `dotnet add package Aspose.BarCode`

Tidak ada alat eksternal tambahan yang diperlukan.

## Step 1: Set up the project and import namespaces

Buat proyek konsol baru dan tambahkan referensi Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Buka `Program.cs` dan tambahkan direktif `using` yang diperlukan:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Namespace ini menyediakan kelas‑kelas yang memungkinkan Anda **cara menghasilkan barcode** dan mengontrol opsi khusus PDF417.

## Step 2: Initialise the MicroPDF417 generator with the desired text

Baris pertama membuat instance `BarcodeGenerator` yang dikonfigurasi untuk simbolik MicroPDF417. Konstruktor menerima tipe enkoding dan string data yang ingin Anda enkode.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Mengapa ini penting:** MicroPDF417 adalah varian kompak dari standar PDF417 penuh, ideal untuk label kecil atau layar seluler. Menginisialisasi generator dengan `EncodeTypes` yang tepat memastikan perpustakaan menggunakan algoritma enkoding yang sesuai.

## Step 3: Customize the X‑dimension (module width) for finer resolution

X‑dimension mengontrol lebar satu modul barcode (garis hitam atau putih terkecil). Menetapkannya ke nilai piksel rendah menghasilkan gambar dengan resolusi lebih tinggi.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa ini penting:** X‑dimension yang lebih besar membuat barcode lebih mudah dibaca oleh pemindai beresolusi rendah, sementara nilai yang lebih kecil memadatkan lebih banyak data dalam ruang terbatas. Sesuaikan nilai ini berdasarkan lingkungan pemindaian.

## Step 4: Define the number of columns to control barcode size

MicroPDF417 mendukung 1‑4 kolom. Lebih banyak kolom menghasilkan barcode yang lebih pendek dan lebar; lebih sedikit kolom menghasilkan barcode yang lebih tinggi dan sempit.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Mengapa ini penting:** Memilih jumlah kolom yang tepat memungkinkan Anda menempatkan barcode dalam elemen UI atau label cetak tertentu tanpa harus melakukan skala manual.

## Step 5: Save the barcode as a PNG image

Akhirnya, tuliskan barcode yang dihasilkan ke disk. PNG mempertahankan kualitas lossless, yang penting untuk pemindaian yang tajam.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Jika direktori target tidak ada, metode `Save` akan melempar `ArgumentException`. Anda dapat mencegahnya dengan pemeriksaan sederhana:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Full source code

Menggabungkan semua bagian, berikut adalah program lengkap yang dapat dijalankan:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Menjalankan program ini menghasilkan file bernama **MicroPdf417.png** yang terlihat seperti tangkapan layar di bawah (gambar dihilangkan untuk singkat). Barcode tersebut mengenkode teks *Sample* dan menghormati pengaturan X‑dimension serta kolom yang Anda tentukan.

## Customizing other PDF417 options

Meskipun panduan ini berfokus pada parameter **customize pdf417 barcode** yang memengaruhi ukuran, Aspose.BarCode menawarkan banyak pengaturan tambahan yang mungkin Anda perlukan:

| Properti | Tujuan | Nilai tipikal |
|----------|--------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Mengontrol jumlah baris (tinggi) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Menetapkan tingkat koreksi error (lebih tinggi = lebih toleran) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Menghasilkan barcode terpotong (tanpa pola berhenti) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Memilih kompaksi numerik, teks, atau byte | `CompactionModes.Numeric`, dll. |

**Pro tip:** Saat Anda memerlukan barcode yang pas pada lebar tetap, mulailah dengan meningkatkan `Columns` dan menurunkan `XDimension`. Jika pemindai melaporkan simbol yang terlewat, naikkan `ErrorLevel` untuk meningkatkan redundansi.

## Handling edge cases

* **Teks terlalu panjang untuk MicroPDF417:** Varian Micro mendukung hingga 1 KB data. Jika string Anda melebihi batas ini, beralihlah ke simbolik `Pdf417` penuh dengan mengubah `EncodeTypes.MicroPdf417` menjadi `EncodeTypes.Pdf417`.
* **Format gambar tidak didukung:** `BarCodeImageFormat` juga mendukung `Jpeg`, `Bmp`, dan `Gif`. Pilih format yang sesuai dengan pipeline pemrosesan Anda.
* **Path lintas‑platform:** Gunakan `Path.Combine` alih‑alih menulis backslash secara hard‑coded ketika menargetkan Linux atau macOS.

## Verifying the barcode

Anda dapat memverifikasi gambar yang dihasilkan dengan aplikasi pemindai barcode standar (seluler atau desktop). Pemindai harus mengembalikan teks asli **Sample**. Jika gagal:

1. Pastikan X‑dimension tidak diatur di bawah 1 pixel (beberapa pemindai tidak dapat menyelesaikan modul sub‑pixel).
2. Pastikan file output tidak rusak—jalankan kembali program dan bandingkan ukuran file.
3. Tingkatkan `ErrorLevel` untuk meningkatkan toleransi.

## Conclusion

Anda kini tahu **cara menghasilkan barcode** di C# menggunakan Aspose.BarCode, cara **customize pdf417 barcode** dimensi dan jumlah kolom, serta cara **membuat gambar barcode C#** yang dapat langsung disematkan dalam proyek. Contoh lengkap ini memperlihatkan alur kerja praktis dari penyiapan proyek hingga output PNG akhir.

Selanjutnya, jelajahi simbolik lain seperti QR, Code128, atau DataMatrix dengan mengganti nilai enum `EncodeTypes`. Menyesuaikan parameter tambahan seperti `Resolution` atau `Margin` memungkinkan Anda menyetel setiap barcode secara optimal untuk aplikasi spesifik Anda.

Selamat coding, dan biarkan barcode Anda memperkuat proyek otomasi berikutnya!

## What Should You Learn Next?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}