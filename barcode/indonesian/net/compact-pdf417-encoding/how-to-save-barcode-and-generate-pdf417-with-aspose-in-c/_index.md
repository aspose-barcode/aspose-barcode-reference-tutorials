---
category: general
date: 2026-09-29
description: Cara menyimpan barcode menggunakan Aspose.BarCode di C# dan mempelajari
  cara menghasilkan PDF417 dengan metadata makro. Ikuti panduan langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: id
lastmod: 2026-09-29
og_description: Cara menyimpan barcode menggunakan Aspose.BarCode di C# sangat sederhana.
  Tutorial ini menunjukkan cara menghasilkan PDF417 dengan metadata makro dan mengatur
  semua parameter yang diperlukan.
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Cara menyimpan barcode dengan Aspose – Panduan pembuatan PDF417
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Cara menyimpan barcode dan menghasilkan PDF417 dengan Aspose di C#
url: /id/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menyimpan barcode dan menghasilkan PDF417 dengan Aspose di C#

Cara menyimpan barcode menggunakan Aspose.BarCode di C# adalah kebutuhan umum ketika Anda perlu menyematkan data dalam file gambar. Panduan ini membawa Anda melalui proses lengkap menghasilkan barcode PDF417 dengan macro‑metadata dan menyimpan hasilnya sebagai gambar PNG. Pada akhir tutorial Anda akan mengetahui **cara menghasilkan PDF417**, **cara mengatur opsi PDF417**, dan yang paling penting, **cara menyimpan file barcode** secara programatik.

Anda akan melihat contoh lengkap yang dapat dijalankan yang mencakup setiap langkah—dari menambahkan paket NuGet Aspose.BarCode hingga mengonfigurasi bidang macro seperti file ID, jumlah segmen, dan checksum. Tidak diperlukan dokumentasi eksternal; kode dapat disalin ke proyek konsol baru dan langsung dijalankan. Tutorial ini mengasumsikan Anda telah menginstal Visual Studio 2022 (atau yang lebih baru) dan .NET 6.0.

## Prasyarat

- .NET 6.0 SDK (atau versi .NET apa pun yang didukung oleh Aspose.BarCode 23.11+)
- Visual Studio 2022, VS Code, atau IDE C# pilihan Anda
- **Aspose.BarCode for .NET** paket NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Pengetahuan dasar tentang sintaks C# dan aplikasi konsol

> **Pro tip:** Gunakan lisensi evaluasi pengembang gratis dari Aspose jika Anda belum memiliki lisensi komersial. Evaluasi ini berfungsi tanpa perubahan kode.

## Cara menyimpan barcode – contoh lengkap

Kode berikut membuat barcode **Macro PDF417**, mengisi semua bidang macro, dan menyimpan gambar sebagai `ExtPDF417Meta.png`. Semua direktif `using` yang diperlukan sudah disertakan sehingga Anda dapat menempelkan potongan kode langsung ke `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### Mengapa setiap langkah penting

1. **Membuat generator** – Konstruktor `BarcodeGenerator` menerima tipe barcode (`EncodeTypes.MacroPdf417`) dan data yang akan dienkode. Macro PDF417 adalah varian khusus yang membawa informasi transfer file, itulah mengapa kami kemudian mengisi bidang macro.
2. **Pengaturan tampilan** – `XDimension.Pixels` mengontrol lebar bar tipis; menyesuaikannya mengubah ukuran gambar secara keseluruhan tanpa memengaruhi integritas data. `Pdf417.Columns` menentukan tata letak matriks barcode.
3. **Metadata macro** – Properti-properti ini (`MacroPdf417FileID`, `MacroPdf417SegmentID`, dll.) penting ketika Anda perlu membagi file besar menjadi beberapa segmen barcode. Menyetelnya dengan benar memastikan pemindai dapat merekonstruksi file asli.
4. **Menyimpan gambar** – Metode `Save` menulis barcode yang dihasilkan ke disk. Anda dapat memilih format apa pun yang didukung (`Png`, `Jpeg`, `Bmp`, dll.). Baris ini menunjukkan operasi **cara menyimpan barcode** yang diminta secara tepat.

> **Pertanyaan umum:** *Bagaimana jika saya membutuhkan format gambar yang berbeda?*  
> Ubah `BarCodeImageFormat.Png` menjadi `BarCodeImageFormat.Jpeg` (atau nilai enum lain yang didukung) dan sesuaikan ekstensi file sesuai.

## Cara menghasilkan PDF417 dengan metadata macro

Jika Anda hanya membutuhkan PDF417 biasa (tanpa data macro), Anda dapat melewatkan bagian macro dan tetap menggunakan generator dasar:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

Kode di atas menggambarkan **cara menghasilkan PDF417** dengan cepat. Perhatikan bahwa enum `EncodeTypes.Pdf417` memilih versi non‑macro.

## Cara mengatur PDF417 – opsi lanjutan

Aspose.BarCode menyediakan banyak parameter khusus PDF417. Berikut beberapa yang mungkin Anda perlukan:

| Properti | Deskripsi | Nilai tipikal |
|----------|-----------|----------------|
| `Pdf417.Columns` | Jumlah kolom per baris | 1‑30 (default 3) |
| `Pdf417.Rows` | Jumlah baris (dihitung otomatis jika 0) | 0‑90 |
| `Pdf417.ErrorLevel` | Tingkat koreksi error (0‑8) | 2‑4 untuk keseimbangan ukuran/kekuatan |
| `Pdf417.RowsPerStrip` | Baris per strip untuk barcode besar | 0 (otomatis) |
| `Pdf417.Pdf417MacroFileID` | Pengidentifikasi untuk file saat menggunakan macro | Integer 32‑bit apa saja |

Menetapkan nilai-nilai ini mengikuti pola yang sama seperti yang ditunjukkan pada **Langkah 2** dari contoh utama. Sesuaikan nilai tersebut sebelum memanggil `Save`.

## Output yang diharapkan

Menjalankan program lengkap akan membuat `ExtPDF417Meta.png` di direktori kerja executable. Gambar tersebut berisi barcode PDF417 resolusi tinggi dengan semua bidang macro tersemat. Memindai gambar dengan pemindai yang mendukung PDF417 (atau aplikasi seluler) akan mengembalikan string data asli `"Åspóse.Barcóde©"` beserta metadata macro (file ID, segment ID, dll.).

![Barcode disimpan sebagai PNG – contoh cara menyimpan barcode](ExtPDF417Meta.png "Cara menyimpan barcode sebagai PNG dengan metadata macro PDF417")

*Teks alt gambar:* **cara menyimpan barcode sebagai PNG dengan metadata macro PDF417** (sesuai kata kunci utama).

## Kesimpulan

Dalam tutorial ini Anda mempelajari **cara menyimpan barcode** menggunakan Aspose.BarCode, **cara menghasilkan PDF417**, **cara mengatur parameter PDF417**, dan **cara menghasilkan barcode dengan Aspose** untuk skenario biasa maupun yang mendukung macro.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Barcode PDF417 dengan Aspose – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cara Menghasilkan Gambar Barcode PDF417 di C# dengan Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cara menghasilkan barcode di C# dengan Aspose.BarCode dan menambahkan metadata](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}