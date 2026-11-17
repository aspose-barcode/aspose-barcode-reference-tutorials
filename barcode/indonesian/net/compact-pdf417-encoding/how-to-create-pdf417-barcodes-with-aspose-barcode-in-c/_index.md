---
category: general
date: 2026-11-17
description: Cara membuat barcode PDF417 menggunakan Aspose.BarCode – panduan langkah
  demi langkah yang juga menunjukkan cara membuat barcode Aspose di C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: id
lastmod: 2026-11-17
og_description: Cara membuat barcode PDF417 menggunakan Aspose.BarCode. Tutorial ini
  memandu Anda melalui langkah-langkah tepat untuk membuat barcode Aspose, mengonfigurasi
  metadata Macro PDF417, dan menyimpan gambar.
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: Cara membuat kode batang PDF417 dengan Aspose.BarCode – panduan lengkap
  C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: Cara membuat kode batang PDF417 dengan Aspose.BarCode di C#
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PDF417 dengan Aspose.BarCode di C#

Jika Anda perlu **cara membuat PDF417** barcode untuk inventaris, pengiriman, atau pelacakan dokumen, panduan ini menunjukkan langkah‑langkah tepat dengan Aspose.BarCode. Anda akan melihat cara membuat barcode aspose, mengonfigurasi bidang Macro PDF417, dan mengekspor hasilnya sebagai gambar PNG—semua dalam satu program C# yang dapat dijalankan.

Membuat barcode PDF417 umum dilakukan ketika Anda harus mengkodekan sejumlah besar data dalam format yang kompak dan dapat dibaca mesin. Aspose.BarCode membuat proses ini sederhana, memungkinkan Anda menyesuaikan dimensi, kolom, dan seluruh set metadata Macro PDF417. Pada akhir tutorial ini Anda akan memiliki contoh lengkap yang berdiri sendiri dan dapat dimasukkan ke proyek .NET mana pun.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7+).
* Lisensi Aspose.BarCode untuk .NET yang valid (evaluasi gratis dapat digunakan untuk pengujian).
* Visual Studio 2022, VS Code, atau IDE kompatibel C# lainnya.
* Pemahaman dasar tentang sintaks C# dan pernyataan `using`.

> **Tip pro:** Jika Anda menjalankan contoh tanpa lisensi, Aspose akan menambahkan watermark kecil pada gambar yang dihasilkan.

## Cara membuat barcode PDF417 dengan Aspose.BarCode

Bagian‑bagian berikut membagi implementasi menjadi empat langkah jelas. Setiap langkah mencakup cuplikan kode, penjelasan **mengapa** kode tersebut diperlukan, dan tip praktis yang dapat Anda terapkan pada proyek Anda sendiri.

### Langkah 1: Siapkan proyek dan impor Aspose.BarCode

Buat proyek konsol baru dan tambahkan paket NuGet Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Kemudian buka `Program.cs` dan tambahkan namespace yang diperlukan:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

**Mengapa ini penting:** Mengimpor `Aspose.BarCode.Generation` memberi Anda akses ke `BarcodeGenerator` dan enumerasi `EncodeTypes`, yang merupakan kelas inti untuk pembuatan barcode.

### Langkah 2: Inisialisasi `BarcodeGenerator` untuk Macro PDF417

Konstruktor `BarcodeGenerator` menerima jenis barcode dan teks yang ingin Anda enkode. Untuk Macro PDF417 Anda menggunakan `EncodeTypes.MacroPdf417`.

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

**Mengapa ini penting:** Pernyataan `using` memastikan bahwa sumber daya tidak terkelola (seperti handle GDI+) dibebaskan dengan cepat, mencegah kebocoran memori pada layanan yang berjalan lama.

### Langkah 3: Konfigurasikan tampilan dan metadata Macro PDF417

#### 3.1 Sesuaikan parameter visual

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 Isi bidang Macro PDF417

Macro PDF417 memungkinkan Anda membagi dokumen besar menjadi beberapa segmen barcode. Bidang‑bidang di bawah ini bersifat opsional tetapi sering diperlukan untuk sistem logistik atau manajemen dokumen.

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

**Mengapa bidang ini berguna:**  
* **FileID** mengikat semua segmen bersama, memungkinkan rekonstruksi.  
* **SegmentID** dan **SegmentsCount** memberi tahu pemindai urutan dan kapan rangkaian selesai.  
* **Checksum** dan **FileSize** menyediakan pemeriksaan integritas cepat tanpa harus mendekode seluruh payload.

> **Waspada:** `MacroPdf417FileID` harus unik per dokumen logis. Menggunakan kembali ID yang sama untuk file yang tidak terkait dapat menyebabkan kesalahan rekonstruksi.

### Langkah 4: Simpan gambar barcode

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

**Mengapa PNG?** PNG mempertahankan data piksel secara tepat tanpa artefak kompresi, yang ideal untuk pemindai barcode yang mengandalkan tepi tajam.

### Contoh lengkap yang dapat dijalankan

Menggabungkan semuanya, berikut program lengkap yang dapat Anda kompilasi dan jalankan segera:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Output yang diharapkan:** Setelah menjalankan program, Anda akan menemukan `MacroPdf417.png` di folder proyek. Membuka gambar tersebut menampilkan barcode PDF417 yang padat dan kontras tinggi yang mengenkode “Sample text for PDF417” beserta metadata makro yang Anda berikan.

## Pertanyaan umum dan penanganan kasus tepi

| Pertanyaan | Jawaban |
|------------|---------|
| *Bisakah saya menghasilkan beberapa segmen dalam loop?* | Ya. Tingkatkan `MacroPdf417SegmentID` untuk setiap iterasi, pertahankan `MacroPdf417FileID` konstan, dan perbarui `MacroPdf417SegmentsCount` hanya setelah Anda mengetahui total jumlah segmen. |
| *Bagaimana jika data melebihi satu simbol PDF417?* | Macro |

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to create a micro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}