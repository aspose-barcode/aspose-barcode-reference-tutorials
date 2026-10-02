---
category: general
date: 2026-08-25
description: Pelajari cara menghasilkan barcode PDF417 di C# dengan generator barcode
  library C# PDF417 – contoh kode langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator C# PDF417
- PDF417 barcode C#
- barcode resolution C#
- Aspose.BarCode PDF417
language: id
lastmod: 2026-08-25
og_description: Hasilkan kode batang PDF417 dalam C# menggunakan generator kode batang
  perpustakaan C# PDF417. Ikuti tutorial singkat ini untuk kode lengkap dan praktik
  terbaik.
og_image_alt: Generated PDF417 barcode example
og_title: Buat kode batang PDF417 di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Learn how to generate PDF417 barcode in C# with the barcode generator
    C# PDF417 library – step-by-step code examples.
  headline: How to generate PDF417 barcode in C# with Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cara menghasilkan barcode PDF417 di C# dengan Barcode Generator
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 di C# dengan Barcode Generator

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan solusi siap‑jalankan. Dengan menggunakan pustaka **barcode generator C# PDF417**, Anda dapat mengontrol dimensi, kolom, baris, dan format gambar hanya dengan beberapa baris kode.

Anda akan belajar cara membuat barcode resolusi tinggi, menyesuaikan tata letak, dan menyimpan hasilnya sebagai file PNG—semua tanpa meninggalkan IDE Anda.

## Apa yang Anda perlukan

- .NET 6.0 atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.6+)
- Paket Aspose.BarCode untuk .NET (pasang via NuGet: `Install-Package Aspose.BarCode`)
- Sebuah folder tempat gambar PNG yang dihasilkan akan disimpan
- Familiaritas dasar dengan sintaks C#

## Langkah 1: Siapkan proyek dan impor namespace

Buat aplikasi console baru (atau tambahkan kode ke proyek yang sudah ada) dan tambahkan directive `using` yang diperlukan:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Namespace `Aspose.BarCode.Generation` menyediakan `BarcodeGenerator`, sementara `Aspose.BarCode` berisi enum `BarCodeImageFormat`.

## Langkah 2: Inisialisasi generator barcode PDF417

Instansiasi `BarcodeGenerator` dengan tipe enkode PDF417 dan teks yang ingin Anda enkode. Contoh ini menggunakan string dengan karakter non‑ASCII untuk mendemonstrasikan dukungan Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Mengapa ini penting:**  
`EncodeTypes.Pdf417` memberi tahu pustaka untuk menghasilkan barcode PDF417, yang merupakan barcode linear bertumpuk ideal untuk menyimpan sejumlah besar data. Menyediakan teks pada saat konstruktor memastikan generator siap merender langsung.

## Langkah 3: Tingkatkan resolusi dengan X‑dimension

X‑dimension (lebar modul) mengontrol berapa banyak piksel yang ditempati setiap bar kecil. Nilai yang lebih besar menghasilkan gambar yang lebih jelas, terutama saat dicetak.

```csharp
// Step 3: Define the module (X) dimension in pixels for better resolution
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Menetapkan `Pixels = 2` memberikan keseimbangan yang baik antara ukuran dan keterbacaan. Anda dapat meningkatkan nilai ini untuk output DPI tinggi, tetapi perhatikan ukuran file yang lebih besar.

## Langkah 4: Hasilkan barcode dengan jumlah kolom tetap

Barcode PDF417 dapat diatur dalam jumlah kolom tertentu. Di sini kami meminta **2 kolom** dan membiarkan pustaka menentukan jumlah baris secara otomatis.

```csharp
// Step 4: Generate a barcode with 2 columns and save it as PNG
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 2;   // columns = 2, rows = auto
barcodeGenerator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
```

**Hasil:** `Pdf417Columns2.png` berisi barcode kompak dengan dua tumpukan vertikal.

## Langkah 5: Biarkan generator menentukan kolom dan tetapkan jumlah baris tetap

Ketika Anda memerlukan jumlah baris tertentu—misalnya, untuk menyesuaikan tinggi label—Anda dapat mengatur baris sementara membiarkan kolom pada *auto*.

```csharp
// Step 5: Generate a barcode with 6 rows (columns set to auto) and save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 0;   // columns = auto
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 6;      // rows = 6
barcodeGenerator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
```

Pustaka menghitung jumlah kolom optimal untuk menampung data dalam enam baris.

## Langkah 6: Tentukan baik kolom maupun baris untuk tata letak khusus

Kadang‑kadang Anda memiliki batasan tata letak yang ketat (misalnya, formulir yang sudah dicetak). Anda dapat secara eksplisit menetapkan kedua dimensi:

```csharp
// Step 6: Generate a barcode with 4 columns and 9 rows, then save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;   // columns = 4
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 9;      // rows = 9
barcodeGenerator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
```

Ini menghasilkan barcode yang persis cocok dengan grid 4 × 9, berguna untuk penyelarasan dengan template fisik.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang mengeksekusi semua lima langkah secara berurutan. Salin ke `Program.cs` dan jalankan proyek.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with sample text containing Unicode characters
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Improve image sharpness
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 1️⃣ Two columns, rows auto
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // explicit auto
            generator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Columns2.png");

            // 2️⃣ Six rows, columns auto
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows6.png");

            // 3️⃣ Custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;
            generator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows9Columns4.png");
        }
    }
}
```

**Output yang diharapkan**

Menjalankan program akan membuat tiga file PNG di folder output proyek:

- `Pdf417Columns2.png` – barcode dengan dua kolom vertikal.
- `Pdf417Rows6.png` – barcode yang diperluas menjadi enam baris.
- `Pdf417Rows9Columns4.png` – barcode yang diatur dalam grid 4 × 9.

Anda dapat membuka salah satu gambar dengan penampil standar untuk memverifikasi bahwa barcode dapat dipindai dengan benar menggunakan aplikasi pemindai PDF417.

## Tips profesional dan jebakan umum

- **Penanganan Unicode**: Generator secara otomatis mengenkode karakter Unicode, tetapi pastikan pemindai target mendukung set karakter yang Anda gunakan.
- **Format gambar**: PNG mempertahankan kualitas lossless. Jika Anda memerlukan format vektor (misalnya, SVG) untuk skala, ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Svg`.
- **Kinerja**: Menggunakan kembali instance `BarcodeGenerator` yang sama (seperti yang ditunjukkan) lebih efisien daripada membuat yang baru untuk setiap tata letak.
- **Penanganan error**: Bungkus pemanggilan `Save` dalam `try/catch` untuk menangkap error I/O, terutama saat menulis ke direktori yang dilindungi.
- **Pertimbangan pencetakan**: Untuk label cetak, tingkatkan `XDimension.Pixels` menjadi 3 atau 4 agar menghindari pixelation pada DPI tipikal (300 dpi).

## Kesimpulan

Sekarang Anda tahu cara **menghasilkan barcode PDF417** di C# menggunakan pustaka **barcode generator C# PDF417**. Tutorial ini mencakup pengaturan resolusi, kontrol kolom/baris, dan penyimpanan gambar.

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java barcode library – Add barcode to PDF using Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}