---
category: general
date: 2026-08-09
description: Contoh barcode Aspose yang menunjukkan cara menggunakan generator barcode
  C# untuk membuat Macro PDF417 dengan dukungan metadata lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: id
lastmod: 2026-08-09
og_description: Contoh barcode Aspose menunjukkan penggunaan generator barcode C#
  untuk menghasilkan barcode Macro PDF417 yang mencakup ID file, data segmen, stempel
  waktu, dan metadata lainnya.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Contoh barcode Aspose – buat Macro PDF417 dengan C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Contoh barcode Aspose: menghasilkan Macro PDF417 dalam C#'
url: /id/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contoh barcode Aspose: menghasilkan Macro PDF417 dalam C#

Jika Anda membutuhkan **aspose barcode example** yang membuat barcode Macro PDF417, panduan ini menunjukkan cara melakukannya dengan **barcode generator C#**. Anda akan melihat setiap pengaturan yang diperlukan, mulai dari dimensi dasar hingga set lengkap bidang metadata Macro PDF417, dan Anda akan mendapatkan gambar PNG yang siap untuk pemrosesan selanjutnya.

Tutorial ini mencakup alur kerja lengkap, menjelaskan mengapa setiap parameter penting, dan menyediakan contoh kode yang siap dijalankan. Tidak diperlukan referensi eksternal; Anda dapat menyalin kode, menyesuaikan nilai, dan menjalankannya segera.

## Prasyarat

- .NET 6.0 (atau lebih baru) terpasang  
- Visual Studio 2022 atau IDE yang kompatibel dengan C# apa pun  
- Lisensi yang valid untuk **Aspose.BarCode for .NET** (versi percobaan gratis berfungsi untuk contoh ini)  

Tambahkan paket NuGet Aspose.BarCode ke proyek Anda:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Buat instance barcode generator C# 

Langkah pertama adalah menginstansiasi `BarcodeGenerator` dengan nilai enum `EncodeTypes.MacroPdf417` dan teks yang ingin Anda enkode. Teks dapat berisi karakter Unicode, yang ditangani secara otomatis oleh pustaka.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Mengapa ini penting*: `EncodeTypes.MacroPdf417` memberi tahu mesin untuk menghasilkan simbol Macro PDF417, yang mendukung data tersegmentasi dan metadata tingkat file tambahan. Pernyataan `using` menjamin bahwa sumber daya yang tidak dikelola dibebaskan setelah gambar disimpan.

## Langkah 2: Tentukan tampilan dasar barcode

Barcode Macro PDF417 terdiri dari modul persegi. Mengontrol ukuran modul dan jumlah kolom memengaruhi keterbacaan serta ukuran file.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Mengapa ini penting*: `XDimension.Pixels` menentukan kepadatan visual; nilai 2 pixel bekerja baik untuk tampilan layar sambil menjaga gambar tetap kecil. Sesuaikan jumlah kolom agar sesuai dengan batasan tata letak Anda—lebih banyak kolom menghasilkan barcode yang lebih lebar dan lebih pendek.

## Langkah 3: Atur metadata khusus Macro PDF417

Macro PDF417 memperluas format PDF417 standar dengan bidang yang memungkinkan rekonstruksi file besar dari beberapa segmen barcode. Setiap bidang bersifat opsional, tetapi mengaturnya menunjukkan kemampuan penuh API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Mengapa ini penting*:  
- `MacroPdf417FileID` menghubungkan semua segmen yang termasuk dalam file logis yang sama.  
- `MacroPdf417SegmentID` dan `MacroPdf417SegmentsCount` memungkinkan decoder menyusun kembali fragmen dengan benar.  
- `MacroPdf417Checksum` menyediakan pemeriksaan integritas cepat tanpa mendekode seluruh payload.  
- `MacroPdf417FileSize` dan `MacroPdf417TimeStamp` memungkinkan sistem hilir memverifikasi bahwa file yang direkonstruksi cocok dengan yang asli.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` berguna dalam skenario logistik atau pertukaran dokumen.  
- Menetapkan `MacroPdf417Terminator` ke `Set` menandai barcode ini sebagai segmen akhir, yang menyederhanakan algoritma rekonstruksi.

## Langkah 4: Simpan gambar barcode yang dihasilkan

Akhirnya, tulis barcode ke file PNG. Anda dapat memilih format yang didukung mana pun (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Mengapa ini penting*: PNG mempertahankan data piksel lossless, memastikan pemindai membaca pola modul tepat yang Anda konfigurasikan. Mengubah format dapat memengaruhi kualitas visual dan ukuran file.

### Output yang Diharapkan

Menjalankan program lengkap menghasilkan file bernama **ExtPDF417Meta.png**. Membuka gambar menampilkan barcode Macro PDF417 berbentuk persegi panjang dengan teks “Åspóse.Barcóde©” yang terenkode, dan kepadatan visual sesuai dengan dimensi X 2‑pixel yang Anda atur. Memindai gambar dengan pembaca yang kompatibel dengan PDF417 mengembalikan semua bidang metadata yang didefinisikan pada Langkah 3.

## Contoh lengkap yang berfungsi

Salin kode di bawah ini ke proyek konsol baru (`dotnet new console`) dan ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang ada di mesin Anda.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Jalankan program (`dotnet run`). Setelah eksekusi, verifikasi bahwa file PNG muncul di lokasi yang Anda tentukan. Gunakan aplikasi pembaca barcode apa pun yang mendukung Macro PDF417 untuk memastikan metadata tersemat dengan benar.

## Variasi umum dan kasus tepi

- **Format gambar yang berbeda**: Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Tiff` jika sistem hilir Anda lebih menyukai format lain.  
- **Mengubah ukuran modul**: Nilai `XDimension.Pixels` yang lebih besar meningkatkan keandalan pemindaian pada pemindai beresolusi rendah tetapi meningkatkan ukuran gambar.  
- **Beberapa segmen**: Untuk menghasilkan file multi‑segmen, buat serangkaian barcode, tingkatkan `MacroPdf417SegmentID` untuk masing‑masing, dan pertahankan `MacroPdf417FileID` konstan. Hanya segmen terakhir yang harus memiliki `MacroPdf417Terminator` diatur.  
- **Dukungan Unicode**: Generator secara otomatis mengenkode karakter Unicode; pastikan string sumber Anda menggunakan enkoding UTF-8 jika Anda membacanya dari file eksternal.  
- **Penanganan kesalahan**: Bungkus blok `using` dalam try‑catch untuk menangkap `BarCodeException` untuk parameter tidak valid (mis., jumlah kolom di luar jangkauan).

## Tips profesional

- **Kinerja**: Gunakan kembali satu instance `BarcodeGenerator` saat membuat banyak barcode dengan pengaturan yang sama; hanya ubah properti `CodeText` di antara penyimpanan.  
- **Perkiraan ukuran file**: Bidang `MacroPdf417FileSize` harus sesuai dengan jumlah byte payload asli; ketidaksesuaian dapat menyebabkan kegagalan validasi hilir.  
- **Pengujian**: Validasi barcode yang dihasilkan dengan decoder bawaan Aspose (`BarCodeReader`) dan pemindai pihak ketiga untuk memastikan interoperabilitas.

## Kesimpulan

Contoh **aspose barcode** ini

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}