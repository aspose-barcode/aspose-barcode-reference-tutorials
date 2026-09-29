---
category: general
date: 2026-08-22
description: Tutorial generator barcode C# menunjukkan cara membuat barcode Macro
  PDF417 dengan metadata dan menyimpannya sebagai PNG menggunakan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: id
lastmod: 2026-08-22
og_description: Generator barcode C# memungkinkan Anda menghasilkan barcode Macro
  PDF417 dengan metadata tingkat file lengkap dan mengekspornya sebagai PNG. Ikuti
  panduan ini untuk mengimplementasikan solusi.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: generator kode batang C# – buat kode batang Macro PDF417 langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cara menggunakan generator barcode C# untuk Macro PDF417
url: /id/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan barcode generator C# untuk Macro PDF417

Jika Anda membutuhkan **barcode generator C#** yang dapat menghasilkan simbol Macro PDF417 dengan metadata tingkat‑file, panduan ini menyediakan solusi lengkap yang siap dijalankan. Anda akan melihat cara mengonfigurasi tampilan barcode, menyematkan informasi makro seperti ID file dan jumlah segmen, dan akhirnya menyimpan hasilnya sebagai gambar PNG.

Contoh ini menggunakan pustaka Aspose.BarCode, **C# barcode library** yang banyak dipakai dan mendukung seluruh fitur PDF417. Tidak diperlukan layanan eksternal, dan kode ini bekerja dengan .NET 6 atau yang lebih baru.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6 SDK (atau versi yang lebih baru) terpasang.
* Visual Studio 2022, VS Code, atau IDE C# lainnya.
* Referensi NuGet ke **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Memahami sintaks dasar C# dan konsep barcode PDF417 akan membantu Anda mengikuti langkah‑langkahnya, namun tutorial ini menjelaskan setiap opsi konfigurasi secara detail.

## Apa yang dibahas dalam tutorial ini

* Menginisialisasi instance **barcode generator C#** untuk format Macro PDF417.  
* Menyesuaikan parameter visual seperti dimensi‑X dan jumlah kolom.  
* Menyediakan bidang tingkat‑file Macro PDF417: file ID, segment ID, segment count, file name, checksum, file size, timestamp, addressee, sender, dan terminator.  
* Menyimpan simbol yang dihasilkan sebagai file PNG.  
* Tips menangani kasus tepi seperti ukuran file besar atau timestamp khusus.

Pada akhir artikel ini Anda akan memiliki program mandiri yang menghasilkan barcode Macro PDF417 yang sepenuhnya sesuai standar.

## Langkah 1: Buat instance barcode generator C#

Operasi pertama adalah menginstansiasi `BarcodeGenerator` dengan nilai enum `EncodeTypes.MacroPdf417` dan teks yang ingin Anda enkode. Konstruktor juga menerima string payload, yang menjadi bagian data dari barcode makro.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Mengapa ini penting** – Flag `EncodeTypes.MacroPdf417` memberi tahu Aspose.BarCode untuk memperlakukan simbol sebagai barcode makro, sehingga bidang tambahan yang akan disertakan dapat diaktifkan. Tanpa flag ini pustaka akan menghasilkan barcode PDF417 biasa tanpa metadata tingkat‑file.

## Langkah 2: Sesuaikan tampilan barcode dasar (pengaturan visual PDF417)

Kejelasan visual sangat penting untuk pemindaian yang dapat diandalkan. Dua parameter umum adalah lebar modul (`XDimension`) dan jumlah kolom. Menyetel nilai‑nilai ini menyeimbangkan ukuran dan keterbacaan.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` mengontrol lebar setiap bar hitam/putih. Nilai **2** biasanya cocok untuk sebagian besar printer label.
* `Pdf417.Columns` menentukan berapa banyak kolom yang akan digunakan barcode. Lima kolom menghasilkan simbol yang kompak tanpa mengorbankan kapasitas data.

## Langkah 3: Definisikan informasi tingkat‑file Macro PDF417

Macro PDF417 memperluas format PDF417 standar dengan bidang‑bidang yang menjelaskan cara sebuah file besar dibagi menjadi beberapa segmen barcode. Menyediakan bidang‑bidang ini memastikan pemindai di sisi penerima dapat merekonstruksi file asli.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` harus sama untuk setiap segmen yang termasuk dalam file logis yang sama.
* `MacroPdf417SegmentID` meningkat dari **0** hingga `SegmentsCount‑1`.
* `MacroPdf417SegmentsCount` memberi tahu decoder berapa banyak bagian yang harus diharapkan.
* `MacroPdf417FileName` bersifat opsional namun berguna untuk identifikasi yang dapat dibaca manusia.

## Langkah 4: Atur metadata makro tambahan

Selain informasi file inti, spesifikasi memperbolehkan bidang tambahan seperti checksum, ukuran file, timestamp, addressee, sender, dan flag terminator. Mengisi bidang‑bidang ini meningkatkan integritas data dan jejak audit.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` menyediakan checksum CCITT 16‑bit untuk seluruh file; decoder dapat memverifikasi integritas setelah rekonstruksi.
* `MacroPdf417FileSize` harus mencerminkan jumlah byte tepat dari file asli; nilai yang lebih besar dari `2^31‑1` memerlukan bidang 64‑bit, yang ditangani otomatis oleh Aspose.
* `MacroPdf417TimeStamp` mencatat kapan barcode dibuat. Gunakan UTC untuk menghindari ambiguitas zona waktu.
* `MacroPdf417Addressee` dan `MacroPdf417Sender` adalah string bebas yang dapat menyimpan informasi routing.
* `MacroPdf417Terminator` menandakan bahwa ini adalah segmen terakhir; set ke `Set` untuk bagian akhir, jika tidak biarkan default (`NotSet`).

**Tips kasus tepi** – Jika ukuran file Anda melebihi 4 GB, bagi konten menjadi beberapa segmen makro dan sesuaikan `SegmentsCount` secara tepat. Pustaka akan mengelola bidang ukuran besar tanpa overflow.

## Langkah 5: Simpan barcode sebagai gambar PNG

Langkah terakhir menuliskan simbol yang dihasilkan ke disk. PNG mempertahankan dimensi piksel secara tepat dan didukung luas oleh perangkat pemindai.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang dapat ditulis oleh proses yang sedang berjalan. Enum `BarCodeImageFormat.Png` memastikan output lossless.

**Mengapa PNG?** – Format raster seperti PNG menjaga tepi modul tetap tajam, yang penting bagi pemindai yang mengandalkan kontras tinggi. Jika Anda memerlukan format vektor, Aspose juga mendukung `Pdf` dan `Svg`.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin ke aplikasi console. Program ini mencakup direktif `using` yang diperlukan serta metode `Main`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Output yang diharapkan

Menjalankan program akan membuat file bernama **MacroPdf417.png** di direktori kerja proyek. Membuka gambar tersebut menampilkan barcode PDF417 yang kompak dengan bidang makro yang disematkan. Memindai gambar dengan pembaca yang kompatibel dengan PDF417 (misalnya ZXing, decoder Aspose.BarCode) mengembalikan payload `"Sample text"` asli beserta metadata makro.

## Pertanyaan umum dan pemecahan masalah

| Pertanyaan | Jawaban |
|------------|---------|
| *Bagaimana jika barcode terlalu besar untuk label target?* | Kurangi `XDimension.Pixels` atau tingkatkan `Pdf417.Columns`. Kedua parameter memengaruhi ukuran keseluruhan. |
| *Bisakah saya menghasilkan gambar vektor alih‑alih PNG?* | Ya. Panggil `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` untuk output yang dapat diskalakan. |
| *Bagaimana cara memverifikasi checksum setelah pemindaian?* | Decoder Aspose.BarCode secara otomatis memvalidasi `MacroPdf417Checksum` dan melaporkan ketidaksesuaian di objek `MacroPdf417Result`. |
| *Apakah pustaka ini kompatibel dengan .NET Core?* | Paket NuGet mendukung .NET Standard 2.0+, yang mencakup .NET Core, .NET 5, .NET 6, dan versi selanjutnya. |
| *Bagaimana jika saya perlu menyematkan data biner alih‑alih teks?* | Konversi payload biner ke Base64 atau gunakan overload `EncodeTypes.MacroPdf417` yang menerima array byte. |

## Pro tips untuk penggunaan produksi

* **Cache generator** –


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to read barcode from PDF in Java using Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Create Codabar Barcode with Aspose.Barcode – Generator & Reader API](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}