---
category: general
date: 2026-10-15
description: Buat barcode PNG dengan cepat menggunakan C#. Pelajari cara menghasilkan
  barcode, mengubah baris, mengonfigurasi pengaturan barcode, dan menghasilkan barcode
  PDF417 dalam satu tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode
- how to change rows
- how to configure barcode
- generate pdf417 barcode
language: id
lastmod: 2026-10-15
og_description: Buat barcode PNG di C# dengan cepat. Tutorial ini menunjukkan cara
  menghasilkan barcode, mengubah baris, mengonfigurasi barcode, dan menghasilkan barcode
  PDF417 dengan kode yang jelas.
og_image_alt: Generated PDF417 barcode saved as a PNG file
og_title: Buat PNG Barcode dengan PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG quickly using C#. Learn how to generate barcode,
    change rows, configure barcode settings, and generate PDF417 barcode in a single
    tutorial.
  headline: Create barcode PNG with PDF417 in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Buat PNG Barcode dengan PDF417 di C# – panduan lengkap
url: /id/net/compact-pdf417-encoding/create-barcode-png-with-pdf417-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode PNG dengan PDF417 di C# – panduan lengkap

Jika Anda perlu **create barcode PNG** dari kode C#, panduan ini menunjukkan secara tepat cara melakukannya. Kami akan membahas cara menghasilkan barcode PDF417, mengubah baris, dan mengonfigurasi semua parameter kunci sebelum menyimpan hasilnya sebagai gambar PNG.

Anda akan belajar cara **generate barcode** gambar secara programatis, menyesuaikan tata letak agar sesuai dengan desain Anda, dan memahami opsi-opsi untuk mengonfigurasi tampilan barcode. Tidak diperlukan alat eksternal—hanya pustaka Aspose.BarCode (atau paket barcode .NET yang kompatibel) dan beberapa baris kode.

## Apa yang Anda butuhkan

- .NET 6.0 atau lebih baru (contoh menggunakan .NET 6, tetapi versi .NET terbaru mana pun dapat digunakan)
- Referensi ke paket NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)
- Familiaritas dasar dengan C# dan Visual Studio (atau IDE pilihan Anda)

> **Pro tip:** Jika Anda lebih suka alternatif gratis, antarmuka API yang sama tersedia di pustaka open‑source `ZXing.Net`; namun, potongan kode di bawah ini menargetkan Aspose.BarCode karena menyediakan kontrol tata letak PDF417 secara langsung.

## Langkah 1: Siapkan proyek dan tambahkan pustaka barcode

Buat aplikasi console baru dan tambahkan paket NuGet:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Kemudian buka `Program.cs` dan tambahkan direktif `using` yang diperlukan:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Namespace ini menyediakan kelas `BarcodeGenerator` dan enumerasi `EncodeTypes` yang akan Anda gunakan untuk **generate PDF417 barcode** gambar.

## Langkah 2: Buat barcode PNG – generator dasar

Baris pertama yang dapat dijalankan membuat instance `BarcodeGenerator` yang dikonfigurasi untuk enkoding PDF417. Ini adalah inti dari **how to generate barcode** gambar.

```csharp
// Step 2: Initialize the generator with PDF417 and the data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
{
    // The rest of the configuration goes here
}
```

> **Mengapa ini penting:** Flag `EncodeTypes.Pdf417` memberi tahu pustaka simbol apa yang akan digunakan. Argumen kedua (`"Layout test"`) adalah teks mentah yang akan dienkode ke dalam barcode.

## Langkah 3: Cara mengonfigurasi barcode – atur ukuran modul

Modul (atau dimensi X) mendefinisikan elemen cetak terkecil dari barcode. Menyesuaikannya mengubah ukuran gambar secara keseluruhan tanpa memengaruhi kepadatan data.

```csharp
// Step 3: Set the module size (X dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Mengatur `Pixels = 2` menghasilkan hasil **create barcode PNG** yang kompak dan beresolusi tinggi, yang cocok untuk thumbnail web dan cetakan.

## Langkah 4: Cara mengubah baris – sesuaikan tata letak PDF417

PDF417 memungkinkan Anda mengontrol secara eksplisit jumlah kolom dan baris. Ini adalah langkah yang menjawab **how to change rows** dalam barcode.

```csharp
// Step 4: Define a custom layout – 4 columns and 9 rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // number of data columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // number of rows (the focus of “how to change rows”)
```

> **Kasus tepi:** Jika Anda meminta lebih banyak baris daripada yang dibutuhkan data, pustaka akan secara otomatis menambahkan baris padding. Sebaliknya, meminta terlalu sedikit baris dapat menyebabkan pengecualian karena data tidak dapat muat.

## Langkah 5: Simpan barcode yang dihasilkan sebagai file PNG

Akhirnya, tulis gambar ke disk. Ini menyelesaikan alur kerja **create barcode PNG**.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode PNG saved to: {outputPath}");
```

Saat Anda menjalankan program, Anda akan melihat file bernama `Pdf417_4x9.png` di folder proyek. Gambar tersebut berisi barcode PDF417 dengan tepat 4 kolom dan 9 baris, dirender dengan modul 2‑pixel.

### Contoh lengkap yang dapat dijalankan

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
        {
            // Configure module size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Custom layout: 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save as PNG
            string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Expected output** (console):

```
Barcode PNG saved to: C:\Path\To\BarcodeDemo\Pdf417_4x9.png
```

Buka file PNG dan Anda akan melihat barcode PDF417 yang bersih siap untuk dipindai.

## Cara menghasilkan barcode dengan data berbeda

Jika Anda perlu **generate barcode** untuk string lain, cukup ganti argumen kedua dari konstruktor `BarcodeGenerator`:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "New data payload"))
{
    // Keep the same configuration or adjust as needed
}
```

Langkah konfigurasi yang sama (ukuran modul, baris, kolom) berlaku, memungkinkan Anda menggunakan kembali kode untuk beberapa payload.

## Cara mengubah baris secara dinamis berdasarkan panjang konten

Terkadang jumlah baris harus menyesuaikan panjang teks yang dienkode. Anda dapat menghitung jumlah baris yang aman sebelum membuat generator:

```csharp
int estimatedRows = (int)Math.Ceiling(text.Length / (double)(columns * 2)); // rough estimate
generator.Parameters.Barcode.Pdf417.Rows = Math.Max(3, estimatedRows);
```

Potongan kode ini memastikan Anda tidak pernah meminta kurang dari tiga baris (minimum pustaka) sambil meningkatkan untuk data yang lebih panjang.

## Cara mengonfigurasi barcode untuk format gambar berbeda

Meskipun tutorial ini berfokus pada PNG, Anda dapat beralih ke JPEG, BMP, atau TIFF dengan mengubah enum `BarCodeImageFormat`:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

PNG tetap pilihan terbaik untuk kualitas loss‑less, terutama ketika barcode akan dicetak.

## Kesalahan umum dan pemecahan masalah

| Gejala | Penyebab kemungkinan | Perbaikan |
|---------|----------------------|-----------|
| Barcode terlihat buram | Dimensi X terlalu besar atau skala gambar setelah disimpan | Pertahankan `XDimension.Pixels` ≤ 3 untuk penggunaan di layar, atau tingkatkan dengan format vektor (PDF) |
| Pemindai tidak dapat membaca barcode | Terlalu sedikit baris untuk panjang data | Tingkatkan `Pdf417.Rows` atau biarkan pustaka mengatur ukuran otomatis dengan menghilangkan pengaturan baris eksplisit |
| `ArgumentOutOfRangeException` saat menyimpan | Direktori output tidak ada | Pastikan `outputPath` mengarah ke folder yang valid atau buat dengan `Directory.CreateDirectory` |

## Ringkasan

Tutorial ini menunjukkan cara **create barcode PNG** file di C# menggunakan simbol PDF417. Anda telah belajar:

- **How to generate barcode** dengan kelas `BarcodeGenerator`
- **How to change rows** dan kolom untuk mengontrol tata letak
- **How to configure barcode** pengaturan seperti ukuran modul dan format gambar
- Cara **generate PDF417 barcode** dan menyimpannya sebagai gambar PNG

Anda sekarang memiliki blok kode yang dapat digunakan kembali yang dapat Anda sesuaikan untuk payload data berbeda, format gambar, atau kebutuhan tata letak.

## Langkah Selanjutnya

- Bereksperimen dengan `Pdf417.ErrorCorrectionLevel` untuk meningkatkan keandalan pemindaian pada cetakan kualitas rendah.  
- Gabungkan beberapa barcode menjadi satu PDF menggunakan Aspose.PDF untuk pembuatan label batch.  
- Jelajahi simbol lain (`EncodeTypes.Code128`, `EncodeTypes.QR`) dengan mengganti nilai enum—ini selaras dengan kata kunci sekunder **generate pdf417 barcode** sambil menunjukkan kemampuan yang lebih luas.

Selamat coding, dan nikmati membuat barcode PNG yang tajam untuk setiap aplikasi!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)
- [How to generate PDF417 barcodes in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [How to create barcode PNG with a custom aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}