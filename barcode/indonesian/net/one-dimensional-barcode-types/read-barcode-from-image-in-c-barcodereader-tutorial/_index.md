---
category: general
date: 2026-08-15
description: Baca kode batang dari gambar dalam C# menggunakan BarCodeReader. Pelajari
  cara membaca beberapa kode batang di C#, membaca kode batang PDF417, dan lihat contoh
  lengkap BarCodeReader C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: id
lastmod: 2026-08-15
og_description: Baca kode batang dari gambar di C# dengan panduan langkah demi langkah.
  Temukan cara membaca beberapa kode batang di C#, mendekode simbol PDF417, dan menjalankan
  contoh lengkap BarCodeReader C#.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Baca kode batang dari gambar di C# – Tutorial BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Baca kode batang dari gambar di C# – Tutorial BarCodeReader
url: /id/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membaca barcode dari gambar di C# – Tutorial BarCodeReader

Jika Anda perlu **membaca barcode dari gambar** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya dengan kelas `BarCodeReader`. Anda juga akan melihat cara **membaca beberapa barcode C#**, mendekode simbol PDF417, dan mendapatkan contoh lengkap **C# BarCodeReader** yang dapat Anda salin ke proyek Anda.

Tutorial ini mencakup setiap langkah—dari menambahkan paket NuGet yang diperlukan hingga mencetak bidang PDF417 yang diperluas—sehingga Anda selesai dengan program konsol yang dapat dijalankan. Tidak diperlukan dokumentasi eksternal; semua kode dan penjelasan disertakan.

## Apa yang Anda perlukan

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru (kode berfungsi dengan .NET Core dan .NET Framework)
* Visual Studio 2022 atau editor yang kompatibel dengan C#
* Paket NuGet `Aspose.BarCode` (atau perpustakaan setara yang menyediakan `BarCodeReader`)
* File gambar yang berisi barcode Macro PDF417 (misalnya `ExtPDF417Meta.png`)

Memiliki prasyarat ini memastikan contoh dapat dikompilasi tanpa konfigurasi tambahan.

## Membaca barcode dari gambar dengan BarCodeReader

Langkah pertama adalah membuat instance `BarCodeReader` yang menunjuk ke file gambar dan memberi tahu perpustakaan jenis barcode apa yang harus dicari.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Mengapa ini berhasil:**  
`BarCodeReader` membuka gambar, memindai untuk `DecodeType` yang ditentukan, dan mengembalikan koleksi objek `BarCodeResult`. Setiap hasil berisi data barcode umum (`CodeTypeName`, `CodeText`) dan, untuk Macro PDF417, objek `Extended.Pdf417` yang menampilkan semua bidang tambahan yang didefinisikan oleh standar.

## Membaca beberapa barcode C# dalam satu gambar

Kadang-kadang sebuah gambar berisi lebih dari satu barcode (misalnya, QR code di samping PDF417). Untuk menangani skenario ini, cukup hilangkan `DecodeType` yang eksplisit atau gunakan `DecodeType.AllSupported` dan iterasi melalui hasilnya.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Mengapa Anda memerlukan ini:**  
Menentukan `AllSupported` memberi tahu mesin untuk mencoba setiap format barcode yang diketahui, yang menjamin Anda menangkap setiap simbol dalam gambar. Ini adalah pendekatan yang disarankan ketika Anda tidak dapat memprediksi jenis barcode sebelumnya.

## Cara membaca barcode PDF417 menggunakan C#

Jika Anda hanya peduli pada format PDF417 klasik (non‑macro), ubah `DecodeType` menjadi `Pdf417`. Sisanya tetap sama, kecuali bidang yang diperluas tidak tersedia.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Mengapa ini penting:**  
PDF417 klasik tidak menampilkan properti khusus macro, sehingga blok `Extended.Pdf417` tidak diperlukan. Menggunakan `DecodeType` yang tepat juga mempercepat pemindaian karena perpustakaan melewatkan algoritma yang tidak didukung.

## Contoh lengkap C# BarCodeReader yang dapat Anda salin

Berikut adalah program lengkap yang menggabungkan tiga skenario menjadi satu aplikasi konsol yang mudah dijalankan. Ganti `YOUR_DIRECTORY/ExtPDF417Meta.png` dengan jalur sebenarnya ke gambar Anda.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Output yang diharapkan

Ketika gambar contoh berisi barcode Macro PDF417, konsol akan mencetak sesuatu yang mirip dengan:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Jika gambar hanya berisi PDF417 biasa, bagian “Macro PDF417” akan kosong, dan bagian “Classic PDF417” akan menampilkan teks yang terdekripsi.

## Kesimpulan

Anda kini tahu cara **membaca barcode dari gambar** di C# menggunakan `BarCodeReader`, cara **membaca beberapa barcode C#** dalam satu file, dan langkah‑langkah tepat untuk **membaca barcode PDF417**—baik varian macro maupun klasik. Contoh lengkap **C# BarCodeReader** siap ditempelkan ke proyek .NET apa pun, dan Anda dapat memperluasnya untuk menangani format lain atau mengintegrasikannya ke dalam pipeline pemrosesan gambar yang lebih besar.

**Langkah selanjutnya**

* Jelajahi pola penanganan error seperti `try / catch` di sekitar blok pembaca.  
* Eksperimen dengan objek `ReaderParameters` untuk menyesuaikan kecepatan dan akurasi deteksi.  
* Gabungkan pembacaan barcode dengan perpustakaan pra‑pemrosesan gambar (

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode yang lengkap dan berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Baca barcode DataMatrix C# – Hasilkan Mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Baca Barcode dari Gambar – Menguasai Ekstraksi Region Barcode di Java dengan Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}