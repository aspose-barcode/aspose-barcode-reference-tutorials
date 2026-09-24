---
category: general
date: 2026-07-15
description: Cara membaca barcode PDF417 dengan C# dan membaca beberapa barcode dari
  sebuah gambar. Pelajari cara membaca gambar barcode di C# dengan kode terperinci
  dan tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: id
lastmod: 2026-07-15
og_description: Cara membaca kode batang PDF417 di C# dengan cepat. Panduan ini menunjukkan
  cara membaca beberapa kode batang dari satu gambar dan mendekode setiap properti.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Cara Membaca PDF417 di C# – Contoh Kode Lengkap & Penjelasan
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Cara Membaca PDF417 di C# – Panduan Lengkap Langkah demi Langkah
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca PDF417 di C# – Panduan Lengkap Langkah‑per‑Langkah

Pernah bertanya-tanya **cara membaca PDF417** dari sebuah gambar menggunakan C#? Anda tidak sendirian. Kebanyakan pengembang menemui kendala ketika harus mengambil bidang Macro‑PDF417 yang diperluas dari dokumen yang dipindai. Kabar baiknya? Dengan hanya beberapa baris kode Anda dapat mendekode PDF417, membaca beberapa barcode dalam satu gambar, dan mengambil setiap properti tersembunyi yang ditawarkan spesifikasi.

Dalam tutorial ini kami akan membahas contoh dunia nyata yang menunjukkan **cara membaca PDF417**, cara **membaca beberapa barcode** dari satu file, dan mengapa kode **read barcode image C#** terlihat seperti itu. Pada akhir tutorial Anda akan memiliki aplikasi console siap‑jalankan yang mencetak setiap informasi yang mungkin Anda perlukan—file ID, segment ID, checksum, timestamp, dan lain‑lain.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru (kode ini bekerja dengan .NET Core dan .NET Framework juga).  
* Visual Studio 2022 (atau editor apa pun yang Anda sukai).  
* Paket NuGet **Aspose.BarCode for .NET** – ini adalah pustaka yang benar‑benarnya mengurai PDF417.  
* Sebuah gambar contoh yang berisi barcode Macro‑PDF417 (misalnya `ExtPDF417Meta.png`).  

Tidak diperlukan konfigurasi tambahan; pustaka ini sudah menyertakan semua decoder yang Anda perlukan.

## Langkah 1: Instal Aspose.BarCode

Buka folder proyek Anda di terminal dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah itu mengambil versi stabil terbaru (per Juli 2026 versi 23.12). Jika Anda lebih suka Package Manager Console di dalam Visual Studio, gunakan:

```powershell
Install-Package Aspose.BarCode
```

> **Tip pro:** kunci versi (`23.12.0`) di file `.csproj` Anda untuk menghindari perubahan yang merusak secara tidak sengaja di kemudian hari.

## Langkah 2: Buat Kerangka Aplikasi Console

Buat proyek console baru jika Anda belum memilikinya:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Ganti `Program.cs` yang dihasilkan secara otomatis dengan kode di bawah ini. Kami akan menjelaskan setiap blok pada bagian berikutnya.

## Langkah 3: Tulis Kode Lengkap “Cara Membaca PDF417”

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
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Mengapa Kode Ini Berfungsi

* **`BarCodeReader`** adalah kelas inti yang memproses gambar, mendeteksi barcode, dan mengembalikan koleksi objek `BarCodeResult`.  
* Menyertakan **`DecodeType.MacroPdf417`** memberi tahu pustaka untuk memperlakukan Macro‑PDF417 secara khusus; tetap mengembalikan simbol PDF417 biasa, yang memenuhi kebutuhan **read multiple barcodes**.  
* Objek **`Extended.Pdf417.MacroPdf417`** menyimpan setiap bidang opsional yang didefinisikan oleh standar ISO/IEC 15438 – di sinilah Anda mendapatkan `FileID`, `SegmentID`, `Checksum`, dll.  
* Blok `using` menjamin sumber daya native dibebaskan, mencegah kebocoran memori pada layanan yang berjalan lama.

## Langkah 4: Jalankan Aplikasi dan Verifikasi Output

Dari terminal:

```bash
dotnet run
```

Anda akan melihat sesuatu seperti:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Jika gambar berisi lebih dari satu barcode, loop akan mencetak baris pemisah (`----------------------------------------`) dan melanjutkan ke hasil berikutnya—tepat seperti yang terlihat pada **read multiple barcodes** dalam praktik.

## Pertanyaan Umum & Kasus Tepi

### Bagaimana jika gambar memiliki simbol Macro‑PDF417 dan PDF417 biasa?

Pemanggilan `BarCodeReader` yang sama akan mengembalikan keduanya. Anda dapat membedakannya dengan memeriksa `result.CodeType` (`MacroPdf417` vs `Pdf417`). Properti ekstensi akan `null` untuk PDF417 biasa, sehingga pengecekan `if (macro != null)` mencegah `NullReferenceException`.

### Barcode saya diputar atau miring—apakah pembaca tetap berfungsi?

Aspose.BarCode menyertakan kompensasi rotasi dan distorsi bawaan. Selama barcode setidaknya 30 % lebar gambar, decoder biasanya berhasil. Untuk kasus ekstrem Anda dapat mengaktifkan `reader.Options.AllowInvertedBarcodes = true;` sebelum memanggil `ReadBarCodes()`.

### Bagaimana cara menangani batch besar gambar?

Bungkus logika pembacaan dalam loop `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Pola `using` memastikan sumber daya native setiap gambar dibebaskan sebelum iterasi berikutnya, menjaga penggunaan memori tetap rendah.

## Daftar Sumber Lengkap (Siap Salin‑Tempel)

Berikut seluruh program dalam satu blok untuk salin‑tempel cepat. Tidak ada dependensi tersembunyi—hanya paket NuGet Aspose.BarCode.

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
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Ringkasan – Apa yang Telah Dibahas

* **Cara membaca PDF417** menggunakan Aspose.BarCode di C#.  
* Langkah‑langkah tepat untuk **read multiple barcodes** dari satu gambar.  
* Cara **read barcode image C#** dan mengekstrak setiap bidang Macro‑PDF417.  
* Tips untuk rotasi, pemrosesan batch, dan menangani data ekstensi yang hilang.

## Langkah Selanjutnya & Topik Terkait

* **Encode PDF417** – buat barcode Macro‑PDF417 Anda sendiri dengan `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – menggunakan kelas `BarCodeReader` yang sama.  
* **Integrate with ASP.NET Core** – expose endpoint web yang menerima gambar yang di‑upload dan mengembalikan JSON dengan bidang yang terdekripsi.  

Silakan bereksperimen: ubah jalur gambar, letakkan PDF417 biasa ke folder yang sama, atau ubah flag `DecodeType` untuk melihat bagaimana pustaka berperilaku. Semakin banyak Anda bermain, semakin nyaman Anda akan menjadi dengan skenario **read barcode image C#**.

Punya gambar sulit yang tidak dapat didekode? Tinggalkan komentar di bawah atau buka issue di repositori GitHub proyek contoh. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑per‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Baca barcode DataMatrix C# – Hasilkan Mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}