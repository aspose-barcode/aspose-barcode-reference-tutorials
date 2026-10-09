---
category: general
date: 2026-09-16
description: Pelajari cara mengatur lebar, cara membuat bar kosong, dan cara mengisi
  bar saat Anda menghasilkan kode batang Planet menggunakan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: id
lastmod: 2026-09-16
og_description: Cara mengatur lebar, membuat bar kosong, dan mengisi bar saat Anda
  menghasilkan kode batang Planet dengan Aspose.BarCode – panduan lengkap langkah
  demi langkah.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Cara mengatur lebar dan menghasilkan kode batang Planet di C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara mengatur lebar dan menghasilkan kode batang Planet di C#
url: /id/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur lebar dan menghasilkan barcode Planet di C#

Jika Anda perlu **cara mengatur lebar** untuk barcode Planet, panduan ini menunjukkan proses lengkapnya. Anda juga akan melihat **cara membuat bar kosong**, **cara mengisi bar**, dan langkah‑langkah tepat untuk **menghasilkan barcode Planet** dengan Aspose.BarCode untuk .NET.

Menghasilkan barcode gaya pos Planet umum dilakukan saat membangun aplikasi label pos atau integrasi layanan pos. Pada akhir tutorial ini Anda akan memiliki program konsol siap‑jalan yang membuat gambar bar terisi dan gambar bar kosong, masing‑masing menggunakan string data yang sama.

## Prasyarat

- .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
- Visual Studio 2022 atau IDE yang kompatibel dengan C#
- Paket NuGet Aspose.BarCode untuk .NET (`Aspose.BarCode`)  
  Instal dengan:

```bash
dotnet add package Aspose.BarCode
```

Tidak ada konfigurasi tambahan yang diperlukan; perpustakaan menangani enkoding gambar secara internal.

## Langkah 1: Buat proyek konsol dan tambahkan perpustakaan

Buka terminal dan jalankan:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Ini akan membuat file `Program.cs` tempat kita akan menulis logika barcode.

## Langkah 2: Tulis kode – cara mengatur lebar dan menghasilkan barcode Planet

Buka `Program.cs` dan ganti isinya dengan contoh lengkap berikut:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Mengapa setiap langkah penting

- **Cara mengatur lebar**: Properti `XDimension.Pixels` secara langsung memengaruhi ukuran fisik setiap bar. Memilih nilai antara 2 hingga 6 piksel menyeimbangkan keterbacaan di layar dan kualitas cetak.
- **Cara membuat kosong**: Menetapkan `FilledBars = false` memberi tahu generator untuk menggambar hanya kontur bar. Gaya ini berguna untuk pencetakan “light‑on‑dark” atau ketika Anda ingin tekstur kertas yang mendasari terlihat.
- **Cara mengisi bar**: Nilai default `FilledBars = true` menghasilkan bar hitam solid, yang merupakan standar untuk kebanyakan pemindai pos.
- **Menghasilkan barcode Planet**: Menggunakan `EncodeTypes.Planet` memilih enkoding khusus yang dibutuhkan oleh United States Postal Service (USPS) untuk barcode Planet.

## Langkah 3: Bangun dan jalankan program

Dari folder proyek jalankan:

```bash
dotnet run
```

Anda akan melihat output konsol serupa dengan:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

Dua file PNG muncul di direktori proyek:

- `PostalPlanetFilledBars.png` – bar hitam solid (gaya default)
- `PostalPlanetEmptyBars.png` – bar kontur (gaya kosong)

Buka keduanya dengan penampil gambar apa saja untuk memverifikasi bahwa lebar bar sesuai dengan pengaturan 4‑piksel dan bahwa versi kosong menampilkan bar yang tidak terisi.

## Pertanyaan umum dan kasus khusus

| Pertanyaan | Jawaban |
|----------|--------|
| *Bisakah saya menggunakan format gambar lain?* | Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` sesuai kebutuhan. |
| *Bagaimana jika barcode menjadi terlalu lebar untuk label saya?* | Kurangi `XDimension.Pixels` (misalnya, menjadi `2`) atau tingkatkan lebar modul printer label. |
| *Apakah saya perlu mengatur `Height` secara manual?* | Perpustakaan secara otomatis menghitung tinggi berdasarkan enkoding. Anda dapat menimpanya dengan `Parameters.Barcode.BarHeight`. |
| *Apakah gaya bar kosong didukung oleh semua printer?* | Sebagian besar printer termal modern menangani kedua gaya terisi dan kosong, tetapi pastikan dengan cetakan percobaan jika Anda menggunakan perangkat lama. |
| *Bagaimana menambahkan keterangan yang dapat dibaca manusia di bawah barcode?* | Gunakan `Parameters.Caption` untuk mengaktifkan dan menata keterangan; set `CaptionAbove` ke `false` untuk menempatkannya di bawah. |

## Tips profesional

- **Gunakan kembali generator yang sama** hanya ketika Anda mempertahankan semua parameter identik. Mengubah `FilledBars` setelah menyimpan tidak memengaruhi gambar yang sudah disimpan, sehingga membuat ulang (seperti yang ditunjukkan) menjamin awal yang bersih.
- **Generasi batch**: Bungkus kode dalam loop dan ubah `data` setiap iterasi untuk membuat serangkaian barcode Planet untuk pengiriman massal.
- **Kinerja**: Untuk ribuan barcode, buat satu instance `BarcodeGenerator`, sesuaikan `XDimension` dan `FilledBars` sesuai kebutuhan, dan gunakan kembali objek tersebut untuk mengurangi alokasi memori.

## Kesimpulan

Anda kini tahu **cara mengatur lebar**, **cara membuat kosong**, **cara mengisi bar**, dan langkah‑langkah tepat untuk **menghasilkan barcode Planet** dengan Aspose.BarCode di C#. Contoh lengkap yang dapat dijalankan menghasilkan file PNG bar terisi dan bar kosong, siap diintegrasikan ke dalam alur kerja label pos apa pun.

Selanjutnya, jelajahi topik terkait seperti **cara menambahkan QR code ke label yang sama**, **menyesuaikan warna barcode**, atau **menyematkan barcode ke dalam dokumen PDF**. Masing‑masing membangun atas dasar fundamental yang dibahas di sini. Selamat coding!


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [How to Create Code128 Barcode with Empty Bars in Java](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}