---
category: general
date: 2026-07-27
description: Cara membaca barcode PDF417 di C# dengan cepat. Pelajari cara membaca
  banyak barcode, mendekode gambar, dan mendapatkan metadata Macro PDF417 dalam contoh
  barcode C# lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: id
lastmod: 2026-07-27
og_description: Cara membaca barcode PDF417 di C# dengan panduan langkah demi langkah
  ini. Mendekode gambar, menangani beberapa barcode, dan mengekstrak metadata Macro
  PDF417 dalam contoh siap dijalankan.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Cara Membaca PDF417 di C# – Contoh Kode Bar Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Cara Membaca PDF417 di C# – Contoh Lengkap Barcode
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca PDF417 di C# – Contoh Lengkap Barcode

Pernah bertanya-tanya **cara membaca PDF417** barcode dalam aplikasi C# tanpa membuat rambut Anda rontok? Anda bukan satu-satunya. Baik Anda sedang membangun pemindai logistik, validator tiket, atau hanya perlu mengambil data dari ID yang dienkode PDF417, prosesnya bisa terasa agak misterius pada awalnya.  

Dalam tutorial ini kami akan membahas **contoh barcode c#** yang membaca gambar PDF417, menangani **membaca beberapa barcode** jika ada, dan mengekstrak semua metadata Macro PDF417 yang berguna yang mungkin Anda perlukan.

## Apa yang Akan Anda Bangun

Pada akhir panduan ini Anda akan memiliki program konsol kecil yang:

1. Memuat gambar barcode dari disk.  
2. Mendekode barcode **PDF417** (termasuk Macro PDF417).  
3. Mencetak informasi dasar seperti tipe kode dan teks.  
4. Mengeluarkan seluruh set bidang Macro PDF417 (file ID, segment ID, checksum, dll.).  

Tidak ada layanan eksternal, hanya satu paket NuGet dan beberapa baris C#.

## Prasyarat – Apa yang Anda Butuhkan Sebelum Memulai

- **.NET 6.0** atau lebih baru (kode ini juga berfungsi pada .NET Framework 4.6+).  
- Versi terbaru dari pustaka **Aspose.BarCode for .NET** – instal melalui NuGet (`Install-Package Aspose.BarCode`).  
- File gambar yang berisi barcode PDF417 (demo menggunakan `ExtPDF417Meta.png`).  
- Pemahaman dasar tentang aplikasi konsol C# (jika Anda pernah menulis “Hello World”, Anda sudah siap).

> **Pro tip:** Jika Anda tidak memiliki contoh PDF417, buat satu di situs demo Aspose atau gunakan aplikasi smartphone yang dapat membuat tag PDF417.

## Langkah 1: Siapkan Proyek dan Instal Pustaka

Pertama, buat proyek konsol baru:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Ini akan menambahkan dependensi **contoh barcode c#** yang kita perlukan. Buka `Program.cs` dan ganti kode default dengan kerangka di bawah ini:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## Langkah 2: Inisialisasi Barcode Reader untuk PDF417

Inti dari solusi ini adalah kelas `BarCodeReader`. Kami memberi tahu kelas ini file mana yang akan dipindai dan tipe barcode apa yang kami inginkan—dalam kasus ini `DecodeType.Pdf417` atau varian macro `DecodeType.MacroPdf417`. Menggunakan tipe macro memastikan kami menangkap bidang yang diperluas.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Mengapa menggunakan `MacroPdf417` alih-alih `Pdf417` biasa? Macro PDF417 membawa metadata tambahan (file ID, jumlah segmen, timestamp, dll.) yang banyak aplikasi dunia nyata bergantung padanya—bayangkan manifest pengiriman yang terbagi menjadi beberapa halaman.

## Langkah 3: Baca Semua Barcode yang Ditemukan dalam Gambar

Sebuah gambar tunggal dapat berisi **beberapa barcode**—mungkin QR code di samping PDF417. Metode `ReadBarCodes()` mengembalikan `IEnumerable<BarCodeResult>` yang dapat kita iterasi.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Jika gambar hanya berisi satu PDF417, loop tetap berjalan sekali, menjaga kode tetap fleksibel untuk skenario di masa depan di mana Anda mungkin perlu **membaca beberapa barcode** dari pemindaian yang sama.

## Langkah 4: Tampilkan Informasi Dasar Barcode

Sebelum menyelami bidang macro, ada baiknya menampilkan tipe barcode dan teks yang didekode. Ini membantu Anda memastikan bahwa pembaca memang mengenali PDF417 dan bukan simbol lain.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

## Langkah 5: Ekstrak Metadata Macro PDF417

Properti `Extended` memberikan Anda penjelajahan mendalam ke struktur khusus PDF417. Setiap bidang yang kami cetak di bawah ini langsung berhubungan dengan spesifikasi macro PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Setiap baris menarik bagian berbeda dari payload macro:

- **FileID** – pengidentifikasi unik untuk seluruh set dokumen.  
- **SegmentID** – bagian mana dari file multi‑segmen yang sedang Anda lihat.  
- **SegmentsCount** – total jumlah segmen yang diharapkan.  
- **FileName, Checksum, FileSize** – berguna untuk memvalidasi integritas file yang ditransfer.  
- **TimeStamp, Addressee, Sender** – bidang opsional yang banyak sistem logistik sisipkan.  

Jika salah satu bidang ini tidak ada dalam barcode sumber, pustaka akan mengembalikan `null` atau `0`, yang dapat Anda tangani sesuai kebutuhan.

## Langkah 6: Jalankan Contoh Lengkap

Menggabungkan semuanya, berikut program lengkap yang siap dijalankan:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Output yang Diharapkan

Saat Anda menjalankan program dengan `ExtPDF417Meta.png` yang valid, Anda akan melihat sesuatu seperti:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Jika gambar berisi lebih dari satu barcode,

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode PDF417 – Pengkodean PDF417 Kompak](/barcode/english/net/compact-pdf417-encoding/)
- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}