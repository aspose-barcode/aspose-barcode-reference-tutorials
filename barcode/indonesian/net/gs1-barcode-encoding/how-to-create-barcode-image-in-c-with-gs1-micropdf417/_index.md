---
category: general
date: 2026-11-14
description: Pelajari cara membuat gambar barcode di C# menggunakan Aspose.BarCode.
  Panduan langkah demi langkah ini mencakup pengaturan generator barcode C#, format
  GS1, dan ekspor PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: id
lastmod: 2026-11-14
og_description: Buat gambar barcode di C# dengan cepat. Ikuti panduan ini untuk belajar
  cara menghasilkan barcode, menggunakan generator barcode C#, dan mengekspor PNG
  GS1 MicroPDF417.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Buat gambar barcode di C# – panduan lengkap untuk GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Cara membuat gambar barcode di C# dengan GS1 MicroPDF417
url: /id/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode di C# dengan GS1 MicroPDF417

Jika Anda perlu **membuat gambar barcode** di C#, panduan ini menunjukkan solusi lengkap yang siap dijalankan. Anda akan melihat **cara menghasilkan data barcode** yang mengikuti standar GS1, mengonfigurasi generator, dan mengekspor file PNG berkualitas tinggi.

Tutorial ini mencakup semua hal mulai dari menginstal pustaka yang diperlukan hingga menangani jebakan format data yang umum. Pada akhir tutorial Anda akan dapat menghasilkan **gambar barcode dari data** dengan hanya beberapa baris kode, dan Anda akan memahami mengapa setiap pengaturan penting.

## Prasyarat

* .NET 6.0 atau lebih baru terinstal (kode ini juga bekerja dengan .NET Framework 4.7+).
* IDE seperti Visual Studio 2022 atau Visual Studio Code.
* Paket NuGet **Aspose.BarCode for .NET**. Instal dengan:

```bash
dotnet add package Aspose.BarCode
```

* Pemahaman dasar tentang sintaks C# dan format GS1 Application Identifier (AI).

> **Pro tip:** Jaga versi pustaka tetap terbaru; rilis terbaru menambahkan dukungan untuk simbol barcode yang lebih baru dan peningkatan kinerja.

## Membuat gambar barcode dengan BarcodeGenerator

Bagian ini berisi implementasi inti. Kode membuat instance **barcode generator c#**, mengonfigurasi X‑dimension untuk keterbacaan, dan menyimpan hasilnya sebagai file PNG.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Mengapa setiap baris penting

* **EncodeTypes.MicroPdf417** memberi tahu pustaka untuk menggunakan simbol GS1 MicroPDF417, yang kompak dan ideal untuk pemindaian seluler.
* **data string** harus dimulai dengan GS1 AI `(01)` untuk Global Trade Item Number (GTIN) diikuti oleh `(21)` untuk nomor seri. Jika formatnya tidak benar, generator akan melempar pengecualian.
* **XDimension.Pixels** mengontrol lebar bar terkecil. Nilai yang lebih besar meningkatkan keterbacaan pada tampilan beresolusi rendah, sementara nilai yang lebih kecil mengurangi ukuran gambar.
* **BarCodeImageFormat.Png** menghasilkan gambar lossless, mempertahankan tepi tajam yang diperlukan untuk pemindaian yang dapat diandalkan.

Menjalankan program akan membuat `GS1MicroPdf417.png` di desktop Anda. Membuka file tersebut menampilkan barcode hitam‑putih yang padat yang mengkodekan GTIN `12345678901234` dan serial `ABC123`.

## Cara menghasilkan barcode menggunakan GS1 MicroPDF417

Jika Anda baru dalam format GS1, berikut adalah aturan penting:

| GS1 AI | Makna                     | Contoh               |
|--------|---------------------------|----------------------|
| (01)   | Global Trade Item Number  | 12345678901234       |
| (21)   | Serial number (optional)  | ABC123               |

Ketika Anda menggabungkan AI dengan nilainya, bungkus setiap AI dalam tanda kurung dan letakkan nilai tepat setelahnya. String yang dihasilkan dapat diteruskan ke **barcode generator c#** tanpa encoding lebih lanjut.

### Jebakan umum

* **Kurang tanda kurung** – Generator memperlakukan string sebagai data mentah dan tidak akan menerapkan pemeriksaan GS1.
* **Melebihi batas panjang** – MicroPDF417 mendukung hingga 155 karakter. Pangkas spasi yang tidak diperlukan.
* **Karakter tidak valid** – Hanya karakter numerik yang diizinkan untuk GTIN; serial dapat mencakup huruf kapital dan angka.

## Menyesuaikan gambar barcode dari data

Selain X‑dimension dasar, Aspose.BarCode menawarkan banyak penyesuaian visual. Berikut beberapa penyesuaian yang dapat Anda terapkan tergantung pada kebutuhan proyek Anda.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Setiap pengaturan bersifat opsional; nilai default sudah menghasilkan **gambar barcode** yang bersih dan dapat dipindai. Bereksperimen dengan warna dan resolusi hanya setelah memastikan pemindai masih dapat membaca kode.

## Menyimpan barcode dalam format lain

Meskipun PNG adalah format paling umum untuk web dan seluler, Anda mungkin memerlukan JPEG, BMP, atau SVG. Metode `Save` menerima nilai `BarCodeImageFormat` apa pun.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG mengurangi ukuran file tetapi memperkenalkan artefak kompresi yang dapat memengaruhi keterbacaan.
* SVG mempertahankan kualitas vektor dan ideal untuk desain web responsif.

## Memverifikasi barcode yang dihasilkan

Cara cepat untuk memastikan langkah **create barcode image** berhasil adalah dengan menggunakan aplikasi pemindai seluler yang mendukung GS1 MicroPDF417. Pindai PNG yang disimpan; aplikasi harus menampilkan:

```
GTIN: 12345678901234
Serial: ABC123
```

Jika pemindai melaporkan kesalahan, periksa kembali format AI dan nilai X‑dimension.

## Contoh lengkap – program konsol mandiri

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan tanpa modifikasi (kecuali langkah instalasi NuGet).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

Saat Anda menjalankan program, konsol mencetak jalur file lengkap, dan PNG muncul di desktop Anda. Contoh ini menunjukkan **cara menghasilkan data barcode**, menyesuaikan tampilan, dan mengekspor **gambar barcode dari data** dalam alur kerja tunggal yang terpadu.

## Pertanyaan yang sering diajukan

| Pertanyaan | Jawaban |
|------------|---------|
| *Apakah saya dapat menghasilkan simbol GS1 lainnya?* | Ya. Ganti `EncodeTypes.MicroPdf417` dengan `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix`, dll., dan sesuaikan string data sesuai. |
| *Bagaimana jika data saya melebihi kapasitas MicroPDF417?* | Beralih ke simbol PDF417 reguler, yang mendukung payload lebih panjang. |
| *Apakah saya memerlukan lisensi untuk Aspose.BarCode?* | Lisensi evaluasi gratis dapat digunakan untuk pengembangan. Untuk produksi, beli lisensi untuk menghilangkan watermark evaluasi. |
| *Apakah PNG cocok untuk pencetakan pada label?* | Tingkatkan `ImageResolution` menjadi 300 dpi atau lebih, dan pertimbangkan menyimpan sebagai TIFF untuk printer industri. |

## Kesimpulan

Anda sekarang tahu cara **membuat gambar barcode** di C# menggunakan pendekatan **barcode generator c#**, memformat data untuk skenario **create gs1 barcode**, dan mengekspor hasilnya sebagai PNG atau tipe gambar lainnya. Contoh lengkap menunjukkan setiap langkah—dari persiapan data hingga penyesuaian visual—sehingga Anda dapat mengintegrasikan pembuatan barcode ke dalam aplikasi .NET apa pun.

Selanjutnya, jelajahi topik terkait seperti **barcode image from data** untuk kode QR, menambahkan beberapa barcode ke satu PDF, atau mengotomatisasi pembuatan batch untuk sistem inventaris. Bereksperimen dengan nilai X‑dimension dan format gambar yang berbeda untuk menemukan titik optimal bagi lingkungan pemindaian Anda.

Selamat coding, dan biarkan aplikasi Anda mulai **membuat gambar barcode** yang berfungsi secara andal di dunia nyata!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat gambar barcode dengan Aspose.Barcode di C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Cara membuat gambar barcode pos di C# menggunakan Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [Cara membuat gambar barcode PDF417 di C# – panduan lengkap](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}