---
category: general
date: 2026-08-06
description: Cara menyimpan gambar barcode di C# menggunakan MicroPdf417 dengan emulasi
  Code 128. Pelajari cara menghasilkan barcode PDF417 dan menyesuaikan pengaturannya.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- barcode generator with code128
language: id
lastmod: 2026-08-06
og_description: Cara menyimpan gambar barcode di C# dengan cepat menggunakan MicroPdf417
  dan emulasi Code 128. Ikuti panduan ini untuk menghasilkan barcode PDF417 dan menyesuaikan
  output.
og_image_alt: Screenshot of generated MicroPdf417 barcode saved as PNG
og_title: Cara menyimpan gambar barcode di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to save barcode images in C# using MicroPdf417 with Code 128 emulation.
    Learn how to generate PDF417 barcodes and customize settings.
  headline: How to save barcode images in C# – complete guide
  type: TechArticle
- description: How to save barcode images in C# using MicroPdf417 with Code 128 emulation.
    Learn how to generate PDF417 barcodes and customize settings.
  name: How to save barcode images in C# – complete guide
  steps:
  - name: Why this code works
    text: '* **Single generator instance** – Re‑using `BarcodeGenerator` avoids repeated
      memory allocation and keeps configuration consistent across modes. * **XDimension**
      – Setting the pixel size to 2 yields a clear, readable image without inflating
      file size. * **IsCode128Emulation** – Enables Code 128‑styl'
  - name: Changing the image format
    text: The `BarCodeImageFormat` enum supports PNG, JPEG, BMP, and TIFF. Replace
      `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` if you need a smaller
      file size for web delivery.
  - name: Generating a full‑size PDF417 instead of MicroPdf417
    text: 'If your use case requires the larger PDF417 standard, instantiate the generator
      with `EncodeTypes.Pdf417`:'
  - name: Handling special characters
    text: "The group separator (`\x1D`) is required for Application Identifiers. If
      your data contains other control characters, escape them using Unicode notation
      (e.g., `\x1C` for file separator) to avoid runtime errors."
  - name: License considerations
    text: 'Running the code without a license triggers a watermark on the generated
      images. Apply your license early in `Main`:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cara menyimpan gambar barcode di C# – panduan lengkap
url: /id/net/compact-pdf417-encoding/how-to-save-barcode-images-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menyimpan gambar barcode di C# – panduan lengkap

Jika Anda perlu **how to save barcode** gambar dalam aplikasi .NET, tutorial ini menunjukkan solusi siap‑jalankan. Anda akan belajar cara menghasilkan barcode PDF417, menerapkan emulasi Code 128, dan menulis file PNG yang dihasilkan ke disk.

Contoh ini menggunakan pustaka Aspose.BarCode untuk .NET, yang mendukung MicroPdf417, Code 128, dan banyak standar lainnya. Pada akhir panduan Anda dapat menghasilkan file barcode untuk Mode 908, 909, 910, dan 911, dan Anda akan memahami cara menyesuaikan parameter visual untuk pemindaian optimal.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE apa pun yang mendukung C#)  
* Lisensi aktif Aspose.BarCode untuk .NET (versi percobaan gratis cukup untuk pengembangan)  

Tutorial ini mengasumsikan pemahaman dasar tentang proyek konsol C#.

## Langkah 1: Buat proyek konsol baru dan tambahkan paket BarCode

Buka terminal dan jalankan perintah berikut:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Perintah `dotnet add package` mengunduh pustaka Aspose.BarCode terbaru, yang berisi kelas yang Anda perlukan untuk **how to generate pdf417** barcode.

## Langkah 2: Tulis program lengkap

Buat file bernama `Program.cs` (ganti yang sudah ada) dan tempelkan kode di bawah ini. Program ini memperlihatkan **barcode generator with code128** emulasi dan menunjukkan beberapa cara untuk **how to save barcode** gambar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be written.
            // Change this path to a location that exists on your machine.
            string outputPath = @"C:\Barcodes\";

            // -----------------------------------------------------------------
            // Step 2.1: Create a MicroPdf417 generator with an FNC1 alphanumeric indicator.
            // This demonstrates **how to generate pdf417** barcodes that start with
            // an Application Identifier (AI) followed by data.
            // -----------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "a\u001d1222322323"); // 'a' = alphanumeric indicator, \u001d = group separator

            // -----------------------------------------------------------------
            // Step 2.2: Adjust visual settings.
            // The XDimension controls module size; Columns limits the number of
            // data columns; IsCode128Emulation enables Code 128 style rendering.
            // These settings are essential for a **barcode generator with code128**
            // emulation that still produces a PDF417 symbol.
            // -----------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.IsCode128Emulation = true;

            // -----------------------------------------------------------------
            // Step 2.3: Save the first barcode (Mode 908 – FNC1 + alphanumeric indicator).
            // This is the core of **how to save barcode** images in PNG format.
            // -----------------------------------------------------------------
            generator.Save($"{outputPath}MicroPdf417_Code128_908.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved Mode 908 barcode.");

            // -----------------------------------------------------------------
            // Step 2.4: Switch to the numeric indicator for Mode 909 and save.
            // Changing the CodeText property reuses the same generator instance,
            // which is more efficient than creating a new object.
            // -----------------------------------------------------------------
            generator.CodeText = "99\u001d1222322323";
            generator.Save($"{outputPath}MicroPdf417_Code128_909.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved Mode 909 barcode.");

            // -----------------------------------------------------------------
            // Step 2.5: Use a generic Code 128 string for Modes 910/911 and save.
            // This illustrates a **barcode generator with code128** scenario where
            // the payload follows a pure Code 128 format.
            // -----------------------------------------------------------------
            generator.CodeText = "123456789012345678";
            generator.Save($"{outputPath}MicroPdf417_Code128_910.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved Mode 910 barcode.");

            Console.WriteLine("All barcodes have been saved successfully.");
        }
    }
}
```

### Mengapa kode ini berhasil

* **Single generator instance** – Menggunakan kembali `BarcodeGenerator` menghindari alokasi memori berulang dan menjaga konfigurasi tetap konsisten di semua mode.  
* **XDimension** – Menetapkan ukuran piksel menjadi 2 menghasilkan gambar yang jelas dan dapat dibaca tanpa memperbesar ukuran file.  
* **IsCode128Emulation** – Mengaktifkan pola bar gaya Code 128 di dalam simbol PDF417, yang dapat dibaca lebih andal oleh beberapa pemindai.  
* **Save method** – Overload `Save` yang Anda lihat adalah cara kanonik untuk **how to save barcode** file; ia menulis gambar langsung ke sistem file dalam format yang Anda tentukan.

## Langkah 3: Jalankan program dan verifikasi output

Bangun dan jalankan proyek:

```bash
dotnet run
```

Setelah konsol mencetak pesan konfirmasi, buka folder yang Anda tentukan di `outputPath`. Anda harus melihat empat file PNG:

* `MicroPdf417_Code128_908.png` – Indikator FNC1 + alfanumerik  
* `MicroPdf417_Code128_909.png` – Indikator FNC1 + numerik  
* `MicroPdf417_Code128_910.png` – payload Code 128 murni  

Setiap gambar berisi simbol MicroPdf417 yang dapat dipindai oleh pembaca barcode standar. Jika pemindai gagal membaca sebuah file, pertimbangkan untuk meningkatkan `XDimension.Pixels` atau menyesuaikan `Pdf417.Columns` agar cocok dengan resolusi perangkat target.

## Langkah 4: Variasi umum dan kasus tepi

### Mengubah format gambar

`enum` `BarCodeImageFormat` mendukung PNG, JPEG, BMP, dan TIFF. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` jika Anda memerlukan ukuran file yang lebih kecil untuk pengiriman web.

### Menghasilkan PDF417 ukuran penuh alih-alih MicroPdf417

Jika kasus penggunaan Anda memerlukan standar PDF417 yang lebih besar, buat instance generator dengan `EncodeTypes.Pdf417`:

```csharp
var fullSizeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "your data");
```

Ingat untuk menyesuaikan `Pdf417.Rows` dan `Pdf417.Columns` agar memenuhi spesifikasi ISO/IEC 15417.

### Menangani karakter khusus

Pemisa grup (`\u001d`) diperlukan untuk Application Identifiers. Jika data Anda berisi karakter kontrol lain, escape mereka menggunakan notasi Unicode (misalnya, `\u001c` untuk pemisah file) untuk menghindari kesalahan runtime.

### Pertimbangan lisensi

Menjalankan kode tanpa lisensi akan menambahkan watermark pada gambar yang dihasilkan. Terapkan lisensi Anda di awal `Main`:

```csharp
var license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

## Langkah 5: Tips untuk penggunaan produksi

* **Batch processing** – Bungkus logika penyimpanan dalam loop yang membaca baris dari CSV atau basis data; gunakan kembali instance `BarcodeGenerator` yang sama untuk kinerja.  
* **Thread safety** – `BarcodeGenerator` tidak thread‑safe. Buat instance terpisah per thread jika Anda memparalelkan pembuatan barcode.  
* **Error handling** – Bungkus pemanggilan `Save` dalam blok `try…catch` untuk menangkap pengecualian I/O, terutama saat menulis ke jaringan bersama.  

## Kesimpulan

Anda sekarang tahu cara **how to save barcode** gambar di C# menggunakan Aspose.BarCode, cara **how to generate pdf417** simbol dengan emulasi Code 128, dan cara mengonfigurasi **barcode generator with code128** untuk berbagai mode. Contoh lengkap yang dapat dijalankan ini memperlihatkan setiap langkah mulai dari penyiapan proyek hingga file PNG akhir.

Selanjutnya, jelajahi topik terkait seperti **embedding barcodes in PDF documents**, **creating QR codes with custom colors**, atau **integrating barcode generation into ASP.NET Core APIs**. Ekstensi ini dibangun di atas prinsip yang sama yang dibahas di sini dan memungkinkan Anda mengotomatisasi berbagai alur kerja pemindaian.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menghasilkan Barcode PDF417 – Pengkodean PDF417 Kompak](/barcode/english/net/compact-pdf417-encoding/)
- [Cara Menyimpan PNG menggunakan DataMatrix C40 dengan Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Cara Menghasilkan Barcode - Jenis Barcode Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}