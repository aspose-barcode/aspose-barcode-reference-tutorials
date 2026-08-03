---
category: general
date: 2026-08-03
description: Baca kode batang PDF417 dari gambar menggunakan C# BarCodeReader – contoh
  pembaca kode batang lengkap yang juga menunjukkan cara membaca beberapa kode batang.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: id
lastmod: 2026-08-03
og_description: Baca kode batang PDF417 dengan cepat menggunakan contoh BarCodeReader
  C#. Ikuti panduan langkah demi langkah ini untuk mendekode macro PDF417 dan membaca
  beberapa kode batang dari sebuah gambar.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Baca kode batang PDF417 di C# – contoh lengkap pembaca kode batang
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Baca barcode PDF417 di C# – contoh pembaca barcode
url: /id/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Kode Batang PDF417 di C# – Contoh Pembaca Kode Batang

Jika Anda perlu membaca data kode batang PDF417 dari sebuah gambar, panduan ini menunjukkan cara melakukannya dengan kelas **BarCodeReader** di C#. Anda akan mempelajari contoh pembaca kode batang yang juga menangani macro PDF417 dan dapat membaca beberapa kode batang dalam satu gambar.

Bekerja dengan kode batang sering berarti harus menangani sumber gambar yang berbeda, kondisi pencahayaan yang bervariasi, dan terkadang data komposit seperti segmen macro PDF417. Tutorial ini mencakup semua yang Anda perlukan untuk mendekode kode batang PDF417, mengekstrak bidang‑bidang ekstendednya, dan memproses beberapa kode batang dari gambar yang sama. Pada akhir tutorial Anda akan memiliki program konsol yang dapat dijalankan, yang membaca kode batang dari file gambar dan mencetak informasi detail ke konsol.

## Apa yang Anda Butuhkan

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Versi terbaru paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan kompatibel lain yang menyediakan `BarCodeReader` dan `DecodeType.MacroPdf417`)  
* File gambar yang berisi kode batang PDF417 atau macro PDF417 (contoh menggunakan `ExtPDF417Meta.png`)  
* Editor kode atau IDE seperti Visual Studio 2022  

Tidak ada layanan tambahan atau API eksternal yang diperlukan.

## Menyiapkan Proyek untuk Membaca Kode Batang

1. **Create a new console project**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Add the barcode library**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copy the barcode image**  

   Tempatkan `ExtPDF417Meta.png` (atau gambar apa pun yang berisi kode batang PDF417) ke dalam folder proyek.  
   Untuk tutorial ini kami mengasumsikan file berada di `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Proyek kini siap untuk dikompilasi dan menjalankan contoh pembaca kode batang.

## Cara Membaca Kode Batang PDF417 dengan BarCodeReader

Inti solusi adalah blok `using` yang membuat instance `BarCodeReader`, menentukan `DecodeType.MacroPdf417`, dan mengiterasi setiap kode batang yang terdeteksi. Kode berikut adalah program lengkap yang berdiri sendiri yang dapat Anda tempel ke dalam `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Mengapa ini berhasil**:  

* `DecodeType.MacroPdf417` memberi tahu pembaca untuk mencari ekstensi macro dari PDF417, yang membawa metadata tambahan seperti ID file, jumlah segmen, dan timestamp.  
* Pernyataan `using` menjamin bahwa sumber daya tidak terkelola (handle file, buffer dekoding native) dilepaskan dengan cepat.  
* Loop `foreach` secara otomatis memproses **semua** kode batang yang ada dalam gambar, memenuhi kebutuhan *membaca beberapa kode batang*.

Saat Anda menjalankan program (`dotnet run`), Anda akan melihat output serupa dengan berikut:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Jika gambar berisi lebih dari satu kode batang PDF417, loop akan mencetak blok terpisah untuk setiap kode batang, sehingga memperlihatkan cara **membaca beberapa kode batang** dari satu gambar.

## Membaca Beberapa Kode Batang dari Sebuah Gambar

Instance `BarCodeReader` yang sama dapat mendekode beberapa tipe kode batang sekaligus. Untuk memperluas cakupan dari hanya macro PDF417 ke PDF417 apa pun (atau bahkan QR, Code128, dll.), sesuaikan flag `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* adalah bitmask, sehingga Anda dapat menggabungkan sejumlah format yang didukung. Fleksibilitas ini menjadikan potongan kode tersebut sebuah **contoh pembaca kode batang** yang bekerja untuk berbagai kasus penggunaan, seperti pemindaian label produk, tiket, atau kartu identitas.

## Mengakses Field Macro PDF417 dengan Aman

Macro PDF417 menambahkan serangkaian properti ekstended yang kaya. Namun, tidak setiap kode batang menyertakan semua field. Mengakses properti yang tidak ada dapat memicu `NullReferenceException`. Pendekatan paling aman adalah memverifikasi setiap properti sebelum mencetaknya:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Mengapa ini penting*: Dalam penerapan dunia nyata Anda mungkin menerima kode batang PDF417 biasa yang tidak memiliki data macro. Pemeriksaan defensif memastikan aplikasi Anda tetap berjalan tanpa crash.

## Kesalahan Umum dan Praktik Terbaik

| Issue | Why it happens | Recommended fix |
|-------|----------------|-----------------|
| Image path is incorrect | `BarCodeReader` throws a file‑not‑found exception before any decoding occurs | Use `Path.Combine` and validate the file exists with `File.Exists` |
| Low‑resolution image | The decoder cannot locate barcode edges, resulting in zero detections | Provide a minimum resolution of 300 dpi for reliable results |
| Barcode rotated > 45° | Many libraries assume upright orientation | Enable `reader.RecognitionOptions.RotateImage = true` if the |

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}