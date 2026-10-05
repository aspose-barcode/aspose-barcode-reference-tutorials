---
category: general
date: 2026-09-16
description: Pelajari cara membuat barcode macro PDF417 dalam C# dengan Aspose.BarCode
  – panduan langkah demi langkah yang mencakup tata letak, dimensi X, dan metadata
  macro.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- Aspose.BarCode for .NET
- C# barcode generation
- PDF417 column layout
- macro PDF417 file segmentation
- barcode X-dimension setting
language: id
lastmod: 2026-09-16
og_description: Buat barcode macro PDF417 dalam C# dengan Aspose.BarCode. Ikuti tutorial
  ini untuk menghasilkan barcode tersegmentasi, mengontrol dimensi X, dan mengatur
  tata letak kolom.
og_image_alt: Screenshot of a generated macro PDF417 barcode created with C#
og_title: Buat kode batang macro PDF417 di C# – panduan lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to create macro PDF417 barcode in C# with Aspose.BarCode
    – step‑by‑step guide covering layout, X‑dimension, and macro metadata.
  headline: How to create macro PDF417 barcode in C# using Aspose.BarCode
  type: TechArticle
tags:
- Aspose
- C#
- Barcode
- PDF417
title: Cara membuat barcode macro PDF417 di C# menggunakan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode macro PDF417 di C# menggunakan Aspose.BarCode

Jika Anda perlu **membuat barcode macro PDF417** dalam aplikasi .NET, panduan ini menunjukkan langkah‑langkah tepatnya. Anda akan melihat cara mengonfigurasi tampilan visual, mendefinisikan tata letak PDF417, dan menyematkan metadata macro‑PDF417 sehingga barcode dapat dibagi menjadi beberapa file.

Membuat barcode macro PDF417 umum dilakukan ketika Anda ingin mengkodekan dokumen besar (misalnya, PDF multi‑halaman) menjadi serangkaian barcode yang dapat dipindai dan dirakit kembali nanti. Tutorial ini membahas contoh lengkap yang dapat dijalankan, menjelaskan mengapa setiap pengaturan penting, dan menyoroti jebakan umum.

Pada akhir artikel Anda akan memiliki program C# yang berfungsi penuh yang menghasilkan gambar barcode macro PDF417, siap dicetak atau ditampilkan dalam UI. Tidak diperlukan alat eksternal selain perpustakaan **Aspose.BarCode for .NET**.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+).  
* Lisensi Aspose.BarCode for .NET yang valid (atau kunci evaluasi sementara).  
* Visual Studio 2022, VS Code, atau IDE apa pun yang kompatibel dengan C#.

Jika Anda baru dalam **pembuatan barcode C#**, Anda mungkin ingin membaca artikel quick‑start Aspose.BarCode terlebih dahulu, tetapi langkah‑langkah di bawah ini sudah lengkap.

## Langkah 1: Buat generator barcode untuk membuat barcode macro PDF417

Objek pertama yang Anda perlukan adalah `BarcodeGenerator`. Objek ini memberi tahu Aspose.BarCode simbol apa yang akan digunakan dan teks mentah apa yang akan dikodekan.

```csharp
using Aspose.BarCode.Generation;

// The EncodeTypes enum contains all supported symbologies.
// EncodeTypes.MacroPdf417 selects the macro PDF417 mode.
var generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for macro PDF417");
```

**Mengapa ini penting:** Memilih `MacroPdf417` memberi tahu mesin untuk menyematkan bidang macro tambahan (ID file, ID segmen, dll.) yang memungkinkan segmentasi file. Tanpa mode ini Anda akan mendapatkan barcode PDF417 biasa yang tidak dapat dirakit kembali menjadi file multi‑segmen.

## Langkah 2: Atur X‑dimension barcode (penampilan visual)

X‑dimension mengontrol lebar modul terkecil (“piksel” barcode). Menyesuaikannya memengaruhi baik keterbacaan maupun ukuran cetak.

```csharp
// Set the module width to 2 pixels. Smaller values produce denser barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa Anda harus menyesuaikan X‑dimension:** X‑dimension yang terlalu kecil dapat membuat barcode tidak terbaca pada pemindai beresolusi rendah, sementara nilai yang terlalu besar membuang ruang. **Pengaturan X‑dimension barcode** sangat penting untuk macro PDF417 karena setiap segmen menambahkan baris data tambahan.

## Langkah 3: Konfigurasikan tata letak kolom PDF417

PDF417 memungkinkan Anda menentukan berapa banyak kolom (yaitu, codewords per baris) yang harus dimiliki barcode. Lebih banyak kolom menghasilkan barcode yang lebih pendek tetapi meningkatkan resolusi cetak yang dibutuhkan.

```csharp
// Choose a column count that balances size and readability.
// 5 columns is a good starting point for screen display.
generator.Parameters.Barcode.Pdf417.Columns = 5;
```

**Mengapa jumlah kolom relevan:** **Tata letak kolom PDF417** secara langsung memengaruhi tinggi barcode. Ketika Anda memiliki banyak segmen macro, jumlah kolom yang kompak mencegah gambar akhir menjadi terlalu tinggi.

## Langkah 4: Tambahkan metadata macro PDF417 untuk segmentasi file

Macro‑PDF417 menggunakan beberapa bidang untuk mengidentifikasi dan merakit kembali file asli. Anda harus mengatur setiap bidang secara konsisten di semua segmen.

```csharp
// Unique identifier for the whole file (must be the same for every segment)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

// Segment identification – start counting at 1
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;

// Total number of segments that will be generated
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 3;

// Original file name (optional but helpful for the reassembly process)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

// CCITT‑16 checksum – Aspose can calculate it automatically,
// but you can also provide a custom value if needed.
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 4321;
```

**Mengapa setiap bidang diperlukan:**

| Field | Purpose |
|-------|---------|
| **MacroPdf417FileID** | Mengikat semua segmen secara unik; pemindai menggunakannya untuk mengelompokkan barcode. |
| **MacroPdf417SegmentID** | Menunjukkan nomor segmen saat ini (berbasis 1). |
| **MacroPdf417SegmentsCount** | Memberitahu pemindai berapa banyak segmen yang diharapkan. |
| **MacroPdf417FileName** | Nama yang dapat dibaca manusia secara opsional yang muncul setelah perakitan kembali. |
| **MacroPdf417Checksum** | Memvalidasi integritas data di seluruh segmen; checksum yang tidak cocok menyebabkan kegagalan perakitan kembali. |

Saat Anda menghasilkan segmen tambahan, hanya `MacroPdf417SegmentID` yang berubah (2, 3, …). Semua bidang lain tetap sama.

## Langkah 5: Simpan gambar barcode

Akhirnya, tulis barcode ke sebuah file. Enum `BarCodeImageFormat` memungkinkan Anda memilih PNG, JPEG, BMP, dll.

```csharp
// Ensure the output directory exists or create it beforehand.
string outputPath = @"C:\Barcodes\MacroPdf417.png";

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
```

**Hasil:** Program ini membuat gambar PNG (`MacroPdf417.png`) yang berisi barcode macro PDF417 yang lengkap. Anda dapat membuka file tersebut di penampil gambar apa pun atau menyematkannya dalam laporan PDF.

---

![Barcode Macro PDF417 yang dihasilkan oleh Aspose.BarCode dalam C#](placeholder-image.png "Barcode Macro PDF417 yang dibuat dengan C#")

*Teks alt gambar (untuk SEO dan aksesibilitas):* **buat barcode macro PDF417** – tangkapan layar barcode macro PDF417 yang dihasilkan dengan C#.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan. Program ini mencakup semua direktif `using` yang diperlukan dan metode `Main` minimal.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1. Initialize the generator for macro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for macro PDF417");

            // 2. Visual appearance – X‑dimension
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3. Layout – number of columns
            generator.Parameters.Barcode.Pdf417.Columns = 5;

            // 4. Macro metadata – file segmentation
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;          // segment 1 of 3
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 3;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 4321;

            // 5. Save the barcode image
            string outputPath = @"C:\Barcodes\MacroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Output yang diharapkan:** File PNG bernama `MacroPdf417.png` yang berisi barcode yang, ketika dipindai dengan pembaca yang mendukung macro‑PDF417, merakit kembali data asli dan melaporkan nama file `myFile.pdf`.

## Pertanyaan umum & penanganan kasus tepi

| Question | Answer |
|----------|--------|
| *Apakah saya perlu menghitung checksum secara manual?* | Aspose.BarCode dapat menghitung checksum secara otomatis jika Anda menghilangkan `MacroPdf417Checksum`. Berikan nilai hanya ketika Anda memiliki checksum yang telah dihitung sebelumnya dari sumber lain. |
| *Bagaimana jika file saya melebihi kapasitas data maksimum dari satu segmen PDF417?* | Bagi data menjadi beberapa segmen dan tingkatkan `MacroPdf417SegmentID` untuk masing‑masing. Jaga agar `MacroPdf417SegmentsCount` tetap konsisten di semua segmen. |
| *Apakah saya dapat menghasilkan semua segmen dalam sebuah loop?* | Ya. Bungkus langkah 1‑5 dalam sebuah loop `for`, memperbarui hanya `MacroPdf417SegmentID` dan nama file output untuk setiap iterasi. |
| *Resolusi apa yang harus saya gunakan untuk pencetakan?* | Minimal 300 dpi disarankan untuk barcode macro PDF417, terutama ketika X‑dimension diatur ke 2 piksel. |
| *Apakah PNG format terbaik?* | PNG mempertahankan kualitas lossless, yang ideal untuk pemindaian barcode. JPEG dapat digunakan untuk ukuran file lebih kecil tetapi mungkin menimbulkan artefak kompresi. |

## Kesimpulan

Anda sekarang tahu cara **membuat barcode macro PDF417** di C# dengan Aspose.BarCode, mengontrol **X‑dimension barcode**, mengonfigurasi **tata letak kolom PDF417**, dan menyematkan metadata **segmentasi file macro PDF417** yang diperlukan. Contoh lengkap ini menunjukkan pendekatan siap produksi yang dapat Anda adaptasi

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}