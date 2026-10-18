---
category: general
date: 2026-10-18
description: Pelajari cara membaca barcode dari gambar di C# dengan Aspose.BarCode,
  mencakup ekstraksi metadata Macro PDF417 dan kode contoh lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: id
lastmod: 2026-10-18
og_description: Cara membaca barcode dari gambar menggunakan C# Aspose.BarCode. Ikuti
  tutorial langkah demi langkah ini untuk mengekstrak metadata Macro PDF417 dan menangani
  skenario umum.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Cara membaca barcode dari gambar di C# – panduan lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membaca barcode dari gambar di C# menggunakan Aspose.BarCode
url: /id/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca barcode dari gambar di C# menggunakan Aspose.BarCode

Jika Anda perlu **cara membaca barcode dari gambar** dalam aplikasi .NET, panduan ini menunjukkan langkah‑langkah tepat dengan Aspose.BarCode. Baik Anda memproses dokumen yang dipindai, kwitansi, atau label inventaris, Anda akan melihat cara membaca barcode, mengambil metadata Macro PDF417, dan menangani kasus tepi yang umum.

Membaca barcode dari gambar adalah tugas rutin, tetapi mengekstrak bidang Macro PDF417 yang diperluas menambahkan lapisan kompleksitas. Tutorial ini mencakup alur kerja lengkap, mulai dari penyiapan proyek hingga contoh yang dapat dijalankan sepenuhnya, sehingga Anda dapat menyalin‑tempel kode dan melihat hasil secara langsung.

## Apa yang akan Anda pelajari

- Cara menyiapkan Aspose.BarCode untuk proyek C#.
- Cara yang benar untuk menginstansiasi **C# barcode reader** untuk gambar Macro PDF417.
- Cara mengiterasi setiap barcode yang terdeteksi dan menampilkan informasi dasar.
- Cara mengakses **Macro PDF417 metadata** seperti file ID, segment ID, dan checksum.
- Tips untuk menangani metadata yang hilang, gambar besar, dan kesalahan decoding yang umum.

**Prerequisites**

- .NET 6.0 (atau yang lebih baru) terpasang.  
- Pemahaman dasar tentang C# dan Visual Studio (semua IDE dapat digunakan).  
- File gambar yang berisi barcode Macro PDF417 (misalnya `ExtPDF417Meta.png`).  

## Langkah 1: Instal Aspose.BarCode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menyertakan **BarCodeReader class**, yang mengimplementasikan fungsionalitas **C# barcode reader** yang dibutuhkan untuk tutorial ini.

## Langkah 2: Siapkan lingkungan pengembangan

Buat aplikasi console baru jika Anda belum memilikinya:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Tambahkan perintah `using` di bagian atas `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Namespace ini mengekspos **BarCodeReader class** dan enumerasi `DecodeType` yang diperlukan untuk decoding Macro PDF417.

## Langkah 3: Inisialisasi BarCodeReader untuk Macro PDF417

Inti dari **cara membaca barcode dari gambar** adalah membuat instance `BarCodeReader` yang menargetkan `DecodeType` tertentu. Untuk Macro PDF417 Anda harus menggunakan `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Mengapa ini penting:**  
Memilih `DecodeType.MacroPdf417` memberi tahu perpustakaan untuk mencari format Macro PDF417 yang diperluas, yang berisi bidang tambahan di luar data barcode dasar. Jika Anda menggunakan `DecodeType.Pdf417` yang umum, bidang tambahan tersebut akan diabaikan.

## Langkah 4: Iterasi barcode yang terdeteksi

Sebuah gambar tunggal dapat berisi beberapa barcode. Metode `ReadBarCodes()` mengembalikan koleksi enumerable dari objek `BarCodeResult`. Loop melalui mereka untuk menampilkan informasi dasar setiap barcode:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` memberi tahu Anda simbol barcode yang tepat (mis., “MacroPdf417”), sementara `CodeText` berisi string yang terdekripsi.

## Langkah 5: Ekstrak dan tampilkan metadata Macro PDF417

Ketika barcode adalah Macro PDF417, properti `Extended.Pdf417` menyediakan sekumpulan bidang metadata yang lengkap. Akses mereka secara langsung seperti ditunjukkan di bawah:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Bidang-bidang ini memberi Anda semua yang diperlukan untuk merekonstruksi file multi‑segment asli, memverifikasi integritas, dan mengaitkan barcode dengan dokumen atau pengirim tertentu.

### Output konsol yang diharapkan

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Jika gambar tidak berisi barcode Macro PDF417, objek `Extended.Pdf417` akan menjadi `null`. Lindungi kode Anda dari hal ini untuk menghindari `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Langkah 6: Menangani kesalahan umum dan kasus tepi

### Gambar besar

Membaca gambar yang sangat besar dapat mengonsumsi memori yang signifikan. Gunakan overload `BarcodeReader` yang menerima `ReaderParameters` untuk membatasi ukuran maksimum gambar:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Metadata yang hilang atau rusak

Jika ada bidang Macro yang hilang, properti yang bersangkutan akan mengembalikan `null` atau `0`. Catat kasus ini dan putuskan apakah barcode harus dianggap tidak lengkap.

### Beberapa tipe barcode dalam satu gambar

Jika sebuah gambar dapat berisi format barcode lain, Anda dapat mengirimkan array nilai `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Pendekatan ini menjaga logika **cara membaca barcode dari gambar** tetap fleksibel tanpa mengorbankan kinerja.

## Langkah 7: Kode sumber lengkap

Berikut adalah program lengkap yang siap dijalankan. Ganti `YOUR_DIRECTORY/ExtPDF417Meta.png` dengan path ke gambar Anda sendiri.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Jalankan program dengan:

```bash
dotnet run
```

Anda akan melihat tipe barcode, teks terdekripsi, dan semua bidang Macro PDF417 yang tersedia dicetak ke konsol.

## Kesimpulan

Dalam tutorial ini Anda mempelajari **cara membaca barcode dari gambar** menggunakan Aspose.BarCode untuk C#. Panduan ini mencakup penyiapan **C# barcode reader**,

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Baca barcode dari gambar C# – panduan lengkap dengan Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Cara membuat barcode macro PDF417 di C# menggunakan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cara membaca barcode PDF417 c# – panduan lengkap langkah‑demi‑langkah](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}