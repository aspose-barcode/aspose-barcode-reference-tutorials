---
category: general
date: 2026-09-16
description: Pelajari cara menghasilkan barcode dan mengatur ukuran barcode di C#.
  Panduan langkah demi langkah menggunakan Aspose.BarCode untuk membuat gambar Micro
  PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: id
lastmod: 2026-09-16
og_description: Cara menghasilkan barcode di C# dan mengatur ukuran barcode dengan
  Aspose.BarCode. Ikuti tutorial singkat ini untuk menghasilkan PNG Micro PDF417.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Cara menghasilkan barcode di C# – panduan lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Cara menghasilkan barcode di C# dengan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode di C# dengan Aspose.BarCode

Jika Anda perlu mengetahui **cara menghasilkan barcode** dalam proyek .NET, tutorial ini akan memandu Anda melalui seluruh proses menggunakan pustaka Aspose.BarCode. Anda juga akan belajar **cara mengatur ukuran barcode** sehingga gambar cocok dengan UI atau kebutuhan pencetakan Anda.

Panduan ini mencakup semua hal mulai dari menginstal paket NuGet hingga mengonfigurasi simbol Micro PDF417 dan menyimpannya sebagai file PNG. Pada akhir tutorial, Anda akan memiliki contoh kode yang dapat dijalankan dan dapat ditempatkan di aplikasi konsol atau web C# apa pun.

## Apa yang Anda perlukan

- .NET 6.0 atau lebih baru (kode juga berfungsi dengan .NET Framework 4.6+)
- Visual Studio 2022 atau IDE apa pun yang mendukung C#
- Akses internet untuk mengunduh paket NuGet **Aspose.BarCode**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Familiaritas dasar dengan sintaks C#

## Cara menghasilkan barcode dengan Aspose.BarCode

Langkah pertama adalah membuat instance `BarcodeGenerator` yang mengetahui symbology mana yang akan digunakan dan data apa yang akan dienkode.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Mengapa ini penting:** `EncodeTypes.MicroPdf417` memberi tahu pustaka untuk menghasilkan varian PDF417 yang kompak, ideal untuk label kecil atau jejak yang mirip QR‑code. String `"Micro data"` menjadi payload yang dapat dibaca manusia yang disematkan dalam barcode.

## Atur ukuran dan dimensi barcode

Barcode yang dapat dibaca harus memiliki dimensi modul (X) yang tepat dan cukup kolom untuk menampung data. Di sinilah Anda **mengatur ukuran barcode**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** mengontrol lebar bar terkecil (“modul”). Nilai `2` piksel bekerja dengan baik untuk tampilan layar; tingkatkan nilai ini untuk pencetakan resolusi tinggi.
- **Pdf417.Columns** membatasi jumlah kolom vertikal. Format Micro PDF417 hanya mendukung hingga 7 kolom; `4` memberikan ukuran yang seimbang tanpa mengorbankan kapasitas data.

> **Tips profesional:** Jika gambar yang dihasilkan terlalu kecil, naikkan `XDimension.Pixels` menjadi `3` atau `4`. Sebaliknya, untuk ruang UI yang padat, Anda dapat menurunkannya menjadi `1`, tetapi pastikan pemindai yang akan Anda gunakan masih dapat membaca simbol tersebut.

## Simpan gambar barcode

Setelah mengatur ukuran, Anda cukup memberi perintah pada generator untuk menulis gambar ke disk.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

Metode `Save` menerima format apa pun yang didukung oleh Aspose.BarCode (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG bersifat lossless, menjaga tepi tajam yang diperlukan untuk pemindaian yang andal.

**Output yang diharapkan:** Sebuah file bernama `micro.png` akan muncul di direktori kerja proyek. Membukanya akan menampilkan barcode Micro PDF417 berukuran kecil dengan kontras tinggi yang siap diuji dengan pemindai standar apa pun.

## Contoh lengkap

Menggabungkan semua bagian memberikan Anda program mandiri yang dapat dijalankan segera.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Jalankan program (`dotnet run` dari konsol) dan Anda akan melihat pesan konfirmasi. PNG yang dihasilkan dapat disematkan dalam laporan, dicetak pada label produk, atau ditampilkan di halaman web.

## Pertanyaan umum dan kasus tepi

| Pertanyaan | Jawaban |
|---|---|
| **Apakah saya dapat menghasilkan tipe barcode lain?** | Ya. Ganti `EncodeTypes.MicroPdf417` dengan nilai apa pun dari enum `EncodeTypes` (misalnya, `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **Bagaimana jika saya membutuhkan gambar yang lebih besar?** | Tingkatkan `XDimension.Pixels` atau gunakan `generator.Parameters.Image.Width/Height` untuk memaksa ukuran piksel tertentu. |
| **Apakah pustaka mendukung latar belakang transparan?** | Atur `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` sebelum memanggil `Save`. |
| **Bagaimana cara membaca kembali barcode tersebut?** | Gunakan `Aspose.BarCode.BarCodeReader` pada gambar yang disimpan; ia secara otomatis mendeteksi symbology. |
| **Apakah PNG aman untuk pencetakan?** | PNG bersifat lossless, tetapi untuk pencetakan CMYK pertimbangkan menyimpan sebagai TIFF (`BarCodeImageFormat.Tiff`). |

## Kesimpulan

Anda kini tahu **cara menghasilkan barcode** di C# dan **cara mengatur ukuran barcode** menggunakan Aspose.BarCode. Contoh lengkap menunjukkan cara membuat simbol Micro PDF417, menyesuaikan dimensinya, dan mengekspor file PNG. Dengan dasar ini Anda dapat menjelajahi symbology lain, menyesuaikan warna, atau mengintegrasikan pembuatan barcode ke dalam layanan ASP.NET Core.

### Langkah selanjutnya

- Coba hasilkan QR code (`EncodeTypes.QR`) dan bandingkan ukuran modulnya.  
- Bereksperimen dengan `generator.Parameters.Image` untuk menambah margin atau mengubah DPI agar siap cetak.  
- Gabungkan pembuatan barcode dengan **Aspose.PDF** untuk menyematkan gambar langsung ke dalam laporan PDF.

Selamat coding, dan nikmati fleksibilitas yang dibawa Aspose.BarCode ke proyek .NET Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}