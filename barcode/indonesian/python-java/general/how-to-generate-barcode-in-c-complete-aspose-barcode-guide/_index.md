---
category: general
date: 2026-07-21
description: Cara menghasilkan barcode dengan cepat menggunakan Aspose.BarCode untuk
  C#. Pelajari cara membuat barcode dengan Aspose, sesuaikan rasio aspek, dan simpan
  PNG dalam hitungan menit.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: id
lastmod: 2026-07-21
og_description: Cara menghasilkan barcode menggunakan Aspose.BarCode untuk C#. Panduan
  langkah demi langkah ini menunjukkan cara membuat barcode dengan Aspose, menyesuaikan
  pengaturan, dan mengekspor gambar.
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: Cara Membuat Barcode di C# – Tutorial Cepat Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: Cara Membuat Barcode di C# – Panduan Lengkap Aspose.BarCode
url: /id/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Barcode di C# – Panduan Lengkap Aspose.BarCode

Pernah bertanya-tanya **bagaimana cara menghasilkan barcode** dalam aplikasi .NET tanpa berurusan dengan kode gambar tingkat‑rendah? Anda tidak sendirian. Dalam banyak proyek perusahaan kami perlu **membuat barcode dengan Aspose** untuk faktur, label pengiriman, atau pelacakan inventaris, dan perpustakaan ini membuatnya terasa sangat mudah.

Dalam tutorial ini kami akan membahas contoh dunia nyata yang membuat barcode DataBar Stacked Omnidirectional, menyesuaikan rasio aspeknya, dan menyimpan dua file PNG. Pada akhir tutorial Anda akan memiliki program konsol yang siap dijalankan dan pemahaman yang jelas tentang properti utama yang dapat Anda kontrol.

## Apa yang Akan Anda Pelajari

- Menyiapkan Aspose.BarCode dalam proyek C# (NuGet, dasar lisensi)
- Menginisialisasi generator **DataBar stacked omnidirectional**
- Menyesuaikan X‑dimension (ukuran piksel) dan rasio aspek
- Menyimpan barcode sebagai gambar PNG
- Memperluas contoh ke tipe barcode lain atau format output

Tidak diperlukan pengalaman sebelumnya dengan Aspose—hanya SDK .NET 6 (atau lebih baru) yang berfungsi dan IDE favorit Anda.

## Prasyarat

| Requirement | Reason |
|-------------|--------|
| .NET 6 SDK or newer | Fitur bahasa modern dan pembuatan proyek yang mudah |
| Visual Studio 2022 (or VS Code) | IDE untuk membangun dan melakukan debugging |
| Aspose.BarCode for .NET NuGet package | Perpustakaan inti yang melakukan pekerjaan berat |
| A valid Aspose license (or evaluation) | Menghapus watermark evaluasi dan membuka semua fitur |

Jika Anda belum menginstal paket NuGet, jalankan:

```bash
dotnet add package Aspose.BarCode
```

Sekarang semuanya siap, mari kita selami kode.

## Langkah 1: Buat Proyek Konsol Baru

Pertama, buat aplikasi konsol baru. Buka terminal dan ketik:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Ini akan membuat `Program.cs` dan file `.csproj`. Buka proyek di editor Anda dan tambahkan referensi Aspose seperti yang ditunjukkan di atas.

## Langkah 2: Inisialisasi BarcodeGenerator

Inti dari proses ini adalah kelas `BarcodeGenerator`. Kami akan meminta simbol **DataBar stacked omnidirectional** dan memberikannya string contoh GS1‑128.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**Mengapa ini penting:** `EncodeTypes.DatabarStackedOmniDirectional` menghasilkan barcode yang kompak dan berkapasitas tinggi, ideal untuk label kecil. String data mengikuti GS1 Application Identifier `(01)` untuk nilai GTIN‑14, yang diharapkan oleh banyak sistem rantai pasokan.

## Langkah 3: Sesuaikan Rasio Aspek dan Simpan Gambar

Aspose.BarCode memungkinkan Anda menyesuaikan **rasio aspek** simbol DataBar melalui `Parameters.Barcode.DataBar.AspectRatio`. Mengubah nilai ini mengubah proporsi lebar‑ke‑tinggi visual, yang dapat penting untuk menyesuaikan barcode ke dalam label berukuran tetap.

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**Penjelasan setiap baris**

- `outputPath` menunjuk ke folder tempat file PNG akan disimpan. `Directory.CreateDirectory` memastikan folder tersebut ada bahkan pada mesin baru.
- `AspectRatio = 15` menghasilkan barcode yang relatif tinggi; `AspectRatio = 30` memperlebar secara horizontal.
- `generator.Save(...)` menulis gambar ke disk. Enum `BarCodeImageFormat.Png` memastikan kualitas lossless.
- `Console.WriteLine` memberikan umpan balik langsung saat Anda menjalankan program.

### Output yang Diharapkan

Saat Anda menjalankan `dotnet run`, Anda akan melihat sesuatu seperti:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

Buka kedua file PNG berdampingan; Anda akan memperhatikan gambar kedua jauh lebih lebar sementara tinggi tetap sama. Kedua gambar dapat dipindai dengan pembaca barcode standar.

## Langkah 4: Jalankan Contoh Lengkap

Berikut adalah **sumber lengkap yang dapat dijalankan** dalam satu blok untuk kemudahan salin‑tempel:

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Kompilasi dan jalankan:

```bash
dotnet run
```

Voilà—dua PNG barcode yang terrender sempurna muncul di `GeneratedBarcodes/`.

## Langkah 5: Memperluas Contoh (Opsional)

Sekarang Anda **tahu cara menghasilkan barcode** dengan Aspose, Anda mungkin bertanya: *Apa lagi yang dapat saya sesuaikan?* Berikut beberapa ide cepat:

| Property | What it does | Typical use‑case |
|----------|--------------|------------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | Mengubah ukuran teks yang dapat dibaca manusia | Font lebih besar untuk pemindai genggam |
| `generator.Parameters.Barcode.ImageFormat` | Format output global (PNG, JPEG, BMP, dll.) | JPEG untuk ukuran yang ramah web |
| `generator.Parameters.Barcode.Color` | Menetapkan warna latar depan | Kategori berwarna |
| `generator.Save(..., BarCodeImageFormat.Svg)` | Output vektor untuk skala tak terbatas | PDF siap cetak |

Untuk bereksperimen, cukup tambahkan baris yang sesuai sebelum setiap pemanggilan `Save`.

## Kesalahan Umum & Tips Profesional

- **Penempatan lisensi:** Jika Anda menggunakan lisensi berbayar, panggil `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` sebelum membuat generator. Lupa melakukan ini akan meninggalkan watermark pada gambar.
- **String data tidak valid:** Simbologi DataBar mengharapkan data GS1 numerik. Menyediakan karakter alfabetik akan memunculkan `ArgumentException`.
- **Keamanan thread:** Instance `BarcodeGenerator` **tidak** thread‑safe. Buat instance baru per thread jika Anda menghasilkan barcode secara paralel.
- **Ukuran gambar vs kemampuan pemindai:** `XDimension.Pixels` yang sangat tinggi dapat menghasilkan gambar besar yang sulit dibaca oleh beberapa pemindai. Uji dengan perangkat keras target Anda.

## Kesimpulan

Kami baru saja membahas **cara menghasilkan barcode** di C# menggunakan Aspose.BarCode, mulai dari penyiapan proyek hingga menyimpan dua gambar dengan rasio aspek yang berbeda. Langkah kunci—inisialisasi generator, konfigurasi X‑dimension dan rasio aspek, serta pemanggilan `Save`—membentuk pola yang dapat diulang untuk tipe barcode apa pun yang didukung Aspose.

Sekarang Anda dapat **membuat barcode dengan Aspose** untuk faktur, label pengiriman, atau tag inventaris, dan Anda memiliki dasar yang kuat untuk menjelajahi fitur lebih lanjut seperti warna, font khusus, atau output SVG. Jangan ragu untuk menyesuaikan kode, bereksperimen dengan `EncodeTypes` lain, dan mengintegrasikan generator ke dalam layanan yang sudah ada.

Ada pertanyaan atau ingin melihat gaya barcode tertentu? Tinggalkan komentar di bawah, dan selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara Menyesuaikan Barcode - Rasio Aspek Codablock F dengan Aspose.BarCode untuk .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}