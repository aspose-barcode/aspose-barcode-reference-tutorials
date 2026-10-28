---
category: general
date: 2026-10-28
description: Cara menghasilkan barcode dengan teks khusus menggunakan Aspose.BarCode
  – panduan langkah demi langkah untuk pengembang .NET dalam membuat gambar barcode
  Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: id
lastmod: 2026-10-28
og_description: Cara menghasilkan barcode dengan teks khusus di .NET menggunakan Aspose.BarCode.
  Ikuti panduan lengkap ini untuk membuat dan menyimpan barcode Macro PDF417.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Cara menghasilkan barcode dengan teks khusus – tutorial Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Cara menghasilkan barcode dengan teks khusus menggunakan Aspose.BarCode untuk
  .NET
url: /id/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode dengan teks khusus menggunakan Aspose.BarCode untuk .NET

Menghasilkan barcode dengan teks khusus adalah kebutuhan yang sering muncul ketika Anda perlu menyematkan pengidentifikasi, cap waktu, atau metadata lainnya langsung ke dalam kode visual. Tutorial ini menunjukkan cara menghasilkan barcode Macro PDF417 yang membawa teks khusus dan serangkaian metadata lengkap, menggunakan perpustakaan **Aspose.BarCode** untuk .NET.

Anda akan belajar cara mengonfigurasi generator, menerapkan teks khusus, mengatur bidang spesifik Macro PDF417, dan menyimpan hasilnya sebagai gambar PNG. Tidak diperlukan alat eksternal—hanya paket NuGet Aspose.BarCode dan lingkungan pengembangan .NET.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terinstal  
* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET)  
* **Aspose.BarCode for .NET** paket NuGet (`Install-Package Aspose.BarCode`)  

Prasyarat ini memastikan kode dapat dikompilasi dan dijalankan tanpa konfigurasi tambahan.

## Langkah 1: Instal paket Aspose.BarCode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan versi stabil terbaru Aspose.BarCode ke proyek Anda, memberi Anda akses ke kelas `BarcodeGenerator` dan semua parameter terkait.

## Langkah 2: Buat aplikasi konsol baru

Buat aplikasi konsol minimal yang akan menampung logika pembuatan barcode:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Mengapa setiap baris penting

* **EncodeTypes.MacroPdf417** – memilih simbolologi Macro PDF417, yang mendukung data tersegmentasi dan metadata.  
* **XDimension.Pixels** – mengontrol ukuran setiap modul; nilai 2 pixel menghasilkan gambar yang jelas dan dapat dipindai.  
* **Pdf417.Columns** – mengurangi lebar keseluruhan, membuat barcode lebih kompak untuk label cetak.  
* **MacroPdf417* properties** – menyematkan informasi tingkat file (ID, jumlah segmen, cap waktu, dll.) langsung ke dalam barcode. Kemampuan ini unik untuk Macro PDF417 dan sering digunakan dalam sistem logistik atau manajemen dokumen.  
* **Save(..., BarCodeImageFormat.Png)** – menulis file PNG lossless, mempertahankan tepi barcode yang tajam untuk pemindaian yang andal.

## Langkah 3: Jalankan program dan verifikasi output

Bangun dan jalankan aplikasi konsol:

```bash
dotnet run
```

Program ini membuat `ExtPDF417Meta.png` di direktori kerja proyek. Membuka file tersebut menampilkan barcode Macro PDF417 yang mengkodekan teks **“Åspóse.Barcóde©”** bersama dengan metadata yang Anda berikan.

**Output yang diharapkan** – gambar PNG serupa dengan yang di bawah ini:

![how to generate barcode example output PNG image showing a Macro PDF417 barcode](ExtPDF417Meta.png)

*Teks alt gambar (“how to generate barcode example output PNG image”) memperkuat kata kunci utama untuk aksesibilitas dan SEO.*

## Variasi umum dan kasus tepi

### Menggunakan tipe barcode yang berbeda

Jika Anda perlu **menghasilkan barcode teks khusus** untuk kode QR alih-alih Macro PDF417, ganti `EncodeTypes.MacroPdf417` dengan `EncodeTypes.QR`. Struktur parameter lainnya tetap sama, tetapi kode QR tidak mendukung bidang metadata Macro.

### Menangani karakter Unicode

Contoh ini sudah mencakup karakter Unicode (`Å`, `ó`, `©`). Aspose.BarCode menangani input UTF‑8 secara langsung, tetapi Anda harus memastikan file sumber disimpan dengan encoding UTF‑8 untuk menghindari peringatan saat kompilasi.

### Menyimpan ke format gambar lain

Aspose.BarCode mendukung BMP, JPEG, TIFF, dan SVG selain PNG. Ubah nilai enum `BarCodeImageFormat` sesuai kebutuhan:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Set data besar

Macro PDF417 dapat membagi data ke beberapa segmen. Ketika teks melebihi kapasitas satu segmen, tingkatkan `MacroPdf417SegmentID` dan pertahankan `MacroPdf417SegmentsCount` konsisten di semua bagian yang dihasilkan. Pendekatan ini penting untuk skenario **create barcode aspose** di mana muatan lebih besar daripada yang dapat ditampung satu barcode.

### Penanganan kesalahan

Bungkus logika pembuatan dalam blok try‑catch untuk menampilkan masalah runtime seperti jalur file tidak valid atau karakter yang tidak didukung:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Tips profesional untuk pembuatan barcode yang andal

* **Validasi barcode** setelah pembuatan menggunakan `BarCodeReader`. Langkah tambahan ini memastikan data yang dikodekan sesuai dengan harapan Anda.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Pertahankan X‑dimension antara 2 – 4 pixel** untuk kebanyakan pemindai. Nilai yang lebih kecil dapat menghasilkan gambar yang tidak dapat dibaca pada perangkat beresolusi rendah.

* **Hindari nama file yang terlalu panjang** pada `MacroPdf417FileName`. Spesifikasi membatasi bidang ini hingga 32 karakter.

* **Gunakan cap waktu yang konsisten** (UTC) saat menghasilkan beberapa segmen untuk mempermudah pemrosesan selanjutnya.

## Kesimpulan

Anda kini tahu **cara menghasilkan barcode** dengan teks khusus menggunakan Aspose.BarCode untuk .NET, cara mengonfigurasi metadata Macro PDF417, dan cara menyimpan hasilnya sebagai gambar PNG. Contoh lengkap yang dapat dijalankan menunjukkan setiap langkah yang diperlukan—dari menginstal paket NuGet hingga menangani karakter Unicode dan menyimpan output.

Dari sini Anda dapat:

* **Menghasilkan barcode teks khusus** untuk simbol lainnya (QR, DataMatrix, dll.)  
* **Membuat alur kerja barcode Aspose** yang memproses ribuan gambar secara batch  
* Mengintegrasikan kode pembuatan barcode ke dalam layanan ASP.NET Core, layanan Windows, atau Azure Functions  

Bereksperimen dengan parameter yang berbeda, jelajahi bidang metadata tambahan, dan gabungkan barcode ke dalam pipeline otomatisasi dokumen Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generate barcode from text using Aspose.BarCode – C# Guide](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [How to use Aspose.BarCode to create DataMatrix code text in .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}