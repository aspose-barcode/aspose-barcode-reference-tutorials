---
category: general
date: 2026-11-20
description: Pelajari cara membuat barcode macro PDF417 dalam C# menggunakan Aspose.BarCode.
  Panduan ini mencakup metadata, parameter, dan penyimpanan gambar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: id
lastmod: 2026-11-20
og_description: Buat kode batang macro PDF417 di C# dengan Aspose.BarCode. Ikuti tutorial
  lengkap ini untuk mengatur metadata, mengonfigurasi parameter, dan mengekspor PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Buat barcode macro PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cara membuat barcode macro PDF417 dengan Aspose.BarCode di C#
url: /id/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat macro PDF417 barcode dengan Aspose.BarCode di C#

Jika Anda perlu **membuat barcode macro PDF417** dalam aplikasi .NET, tutorial ini menunjukkan langkah‑langkah tepatnya. Anda akan melihat cara mengonfigurasi metadata khusus macro, menyesuaikan pengaturan visual, dan menyimpan hasilnya sebagai file PNG.

Membuat barcode macro PDF417 berguna ketika Anda ingin membagi kumpulan data besar ke beberapa simbol sambil mempertahankan pengidentifikasi seluruh file. Pada contoh di bawah ini kami menggunakan pustaka Aspose.BarCode, yang menyediakan API yang fluent untuk semua fitur PDF417.

Pada akhir panduan ini Anda akan memiliki program konsol siap‑jalankan yang menghasilkan gambar barcode berisi informasi macro lengkap.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru terpasang.
* Visual Studio 2022 (atau IDE apa pun yang mendukung C#).
* Paket NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Inisialisasi generator barcode untuk macro PDF417

Langkah pertama adalah membuat instance `BarcodeGenerator` dengan nilai enum `EncodeTypes.MacroPdf417`. Ini memberi tahu pustaka untuk memperlakukan barcode sebagai simbol macro PDF417.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Mengapa ini penting*: Memilih `MacroPdf417` mengaktifkan semua properti terkait macro pada objek parameter `Pdf417`.

## Langkah 2: Atur tampilan visual dasar

Barcode yang dapat dibaca dimulai dengan ukuran modul dan jumlah kolom yang tepat. Properti `XDimension.Pixels` mengontrol lebar satu modul, sementara `Pdf417.Columns` menentukan berapa banyak kolom data yang ada di setiap baris.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Menyesuaikan nilai‑nilai ini memengaruhi keandalan pemindai serta ukuran gambar.

## Langkah 3: Tentukan detail identifikasi file macro

Macro PDF417 memerlukan pengidentifikasi file, pengidentifikasi segmen, dan total jumlah segmen. Ketiga bidang ini memungkinkan pemindai untuk menyusun kembali kumpulan data asli.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Parameter **macro PDF417** ini adalah inti dari fungsi macro. Tanpa mereka, pemindai tidak dapat menghubungkan simbol‑simbol bersama.

## Langkah 4: Tambahkan metadata macro opsional

Selain pengidentifikasi wajib, format macro mendukung bidang tambahan seperti checksum, ukuran file, timestamp, penerima, pengirim, dan flag terminator. Menyediakan data ini meningkatkan deteksi kesalahan dan memberikan konteks bagi sistem hilir.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Tips profesional*: Jika alur kerja Anda tidak memerlukan bidang tertentu, Anda dapat membiarkannya dengan nilai default. Pustaka akan menghilangkan elemen data yang bersangkutan dari barcode.

## Langkah 5: Simpan gambar barcode

Setelah mengonfigurasi semua parameter, panggil `Save` untuk mengekspor barcode. Contoh ini menyimpan file PNG di direktori yang ditentukan pengguna.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Ketika program selesai, `ExtPDF417Meta.png` berisi barcode macro PDF417 yang mengkodekan teks `"Åspóse.Barcóde©"` bersama semua metadata macro.

## Kode sumber lengkap

Berikut adalah program lengkap yang berdiri sendiri. Salin ke proyek konsol baru dan jalankan setelah menginstal paket NuGet Aspose.BarCode.

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
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Output yang diharapkan

Menjalankan program mencetak baris konfirmasi serupa dengan:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Membuka file PNG menampilkan barcode yang padat dan kontras tinggi. Memindainya dengan pemindai yang kompatibel dengan PDF417 mengembalikan teks asli beserta semua bidang macro.

## Pertanyaan umum dan kasus tepi

### Bagaimana jika saya membutuhkan lebih dari 20 segmen?

Properti `MacroPdf417SegmentsCount` dapat diatur hingga `255`. Pastikan sistem penerima dapat menangani jumlah segmen yang lebih besar, dan pertimbangkan untuk membagi data menjadi jumlah simbol yang dapat dikelola.

### Bagaimana checksum memengaruhi pemindaian?

Checksum CCITT‑16 (`MacroPdf417Checksum`) menyediakan lapisan pemeriksaan kesalahan tambahan. Jika pemindai mendeteksi ketidaksesuaian, ia akan menolak barcode. Anda dapat menghilangkan checksum jika alur kerja Anda tidak memerlukannya.

### Bisakah saya menghasilkan barcode PDF417 macro tanpa Aspose?

Ya, pustaka lain (mis., ZXing.Net, Dynamsoft) mendukung PDF417, tetapi bidang khusus macro seringkali tidak ada. Aspose.BarCode menawarkan implementasi paling lengkap untuk metadata macro.

### Format gambar apa yang didukung untuk penyimpanan?

Metode `Save` menerima format apa pun yang didefinisikan dalam `BarCodeImageFormat`, seperti `Png`, `Jpeg`, `Gif`, `Bmp`, dan `Tiff`. Pilih format yang sesuai dengan alur pemrosesan hilir Anda.

## Kesimpulan

Anda sekarang tahu cara **membuat barcode macro PDF417** di C# menggunakan Aspose.BarCode. Tutorial ini mencakup inisialisasi generator, pengaturan visual, pengidentifikasi file macro, metadata opsional, dan ekspor gambar. Dengan dasar ini Anda dapat menyematkan macro PDF dalam sistem inventaris, pelacakan dokumen, atau skenario apa pun yang memerlukan transmisi data tersegmentasi.

Langkah selanjutnya meliputi bereksperimen dengan nilai `XDimension` yang berbeda untuk resolusi lebih tinggi, menambahkan penyesuaian tingkat koreksi kesalahan, atau mengintegrasikan barcode ke dalam API web yang mengembalikan aliran PNG secara langsung. Untuk topik terkait, lihat tutorial tentang **contoh generator barcode**, **parameter macro PDF417**, dan penanganan **metadata macro PDF417**.

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat gambar barcode PDF417 di C# dengan opsi Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Baca barcode dari gambar C# – panduan lengkap dengan Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Cara Membuat Barcode PDF417 dengan Aspose – Panduan Langkah‑per‑Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}