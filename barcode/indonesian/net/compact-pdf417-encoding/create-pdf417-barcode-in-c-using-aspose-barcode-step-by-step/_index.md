---
category: general
date: 2026-10-18
description: Pelajari cara membuat barcode PDF417 di C# dengan Aspose.BarCode. Tutorial
  ini mencakup pembuatan PDF417 dasar, kompak, makro, dan mikro dengan kode lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: id
lastmod: 2026-10-18
og_description: Buat kode batang PDF417 di C# dengan Aspose.BarCode. Ikuti panduan
  ini untuk menghasilkan kode batang PDF417 dasar, kompak, makro, dan mikro langkah
  demi langkah.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Buat kode batang PDF417 di C# – tutorial lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Membuat barcode PDF417 di C# menggunakan Aspose.BarCode – panduan langkah demi
  langkah
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat barcode PDF417 di C# menggunakan Aspose.BarCode – panduan langkah‑demi‑langkah

Jika Anda perlu **membuat barcode PDF417** dalam aplikasi .NET, tutorial ini akan memandu Anda melalui seluruh proses. Anda akan melihat cara menghasilkan barcode dasar, mengaktifkan mode kompak, menambahkan metadata makro, dan menghasilkan varian mikro—semua dengan penjelasan yang jelas dan kode yang dapat dijalankan.

Pembuatan barcode PDF417 umum digunakan dalam logistik, tiket, dan manajemen dokumen. Pada akhir panduan ini Anda akan dapat mengintegrasikan pembuatan barcode ke dalam proyek C# mana pun tanpa alat eksternal.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7+)
* Visual Studio 2022 atau IDE C# apa saja
* Paket NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Izin menulis ke folder tempat file PNG yang dihasilkan akan disimpan

Tidak ada konfigurasi tambahan yang diperlukan; perpustakaan menangani semua detail enkoding tingkat‑rendah.

## Langkah 1: Membuat barcode PDF417 dasar

Langkah pertama membuat barcode PDF417 standar dengan ukuran dan jumlah kolom yang dapat disesuaikan.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Mengapa pengaturan ini penting**

* `XDimension.Pixels` mengontrol ukuran fisik setiap elemen barcode. Nilai 2 menghasilkan gambar yang jelas pada kebanyakan layar dan printer.
* `Pdf417.Columns` menentukan berapa banyak kolom data yang dimiliki barcode. Lebih sedikit kolom mengurangi lebar; lebih banyak kolom meningkatkan kapasitas data.

Menjalankan kode akan membuat `Pdf417Basic.png`, yang terlihat seperti simbol PDF417 tipikal dengan tiga kolom data dan satu kolom metadata lengkap di sisi kanan.

## Langkah 2: Mengaktifkan mode kompak (dipotong)

Mode kompak menghapus kolom metadata di sebelah kanan, sehingga barcode menjadi lebih sempit. Ini berguna ketika ruang terbatas namun data masih dapat direkonstruksi dari baris yang tersisa.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Mengapa dipotong?**  
Ketika `Truncate` bernilai `true`, generator tidak menyertakan kolom opsional di sebelah kanan yang menyimpan koreksi‑error dan metadata tingkat‑file. Barcode yang dihasilkan menggunakan lebih sedikit kolom namun tetap dapat dipindai oleh kebanyakan pembaca PDF417.

## Langkah 3: Membuat barcode Macro PDF417 dengan metadata tingkat‑file

Macro PDF417 memperluas format standar dengan pengidentifikasi segmen, memungkinkan dokumen besar dibagi menjadi beberapa barcode. Ini berguna untuk mengenkode string panjang atau file multi‑halaman.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Penjelasan bidang makro**

| Properti | Tujuan |
|----------|--------|
| `MacroPdf417FileID` | Pengidentifikasi unik untuk seluruh file; semua segmen berbagi nilai ini. |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (dimulai dari 1). |
| `MacroPdf417SegmentsCount` | Total jumlah segmen yang membentuk kumpulan data lengkap. |

Pemindai yang memahami Macro PDF417 dapat menyusun kembali data asli dengan membaca semua segmen dan menggunakan pengidentifikasi tersebut.

## Langkah 4: Membuat barcode Micro PDF417 untuk data singkat

Micro PDF417 adalah versi kompak yang dirancang untuk muatan kecil (hingga 90 karakter). Ia membatasi rentang kolom menjadi 1‑4, sehingga barcode cocok untuk label kecil atau perangkat dengan area tampilan terbatas.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Kapan menggunakan Micro PDF417**  
Gunakan varian ini ketika payload data singkat dan Anda memerlukan barcode sekecil mungkin. Ini ideal untuk tag inventaris, kartu akses, atau skenario apa pun di mana ruang tampilan sangat terbatas.

## Contoh lengkap yang dapat dijalankan

Berikut adalah aplikasi konsol mandiri yang menghasilkan keempat tipe barcode dalam satu kali eksekusi. Salin kode ke proyek C# baru, ganti `YOUR_DIRECTORY` dengan jalur folder yang ada, lalu jalankan.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Output yang diharapkan**

Menjalankan program akan membuat empat file PNG di folder yang ditentukan:

* `Pdf417Basic.png` – barcode standar dengan tiga kolom
* `CompactPdf417.png` – data yang sama, kolom kanan dipotong
* `MacroPdf417.png` – barcode makro yang berisi metadata segmen
* `MicroPdf417.png` – barcode mikro kompak untuk string pendek

Buka salah satu gambar dengan penampil gambar; Anda akan melihat pola PDF417 yang berbeda. Memindainya dengan pembaca barcode seluler (misalnya ZXing, Scandit) akan mengembalikan string teks asli.

## Pertanyaan umum dan tips

* **Bagaimana jika barcode terlihat buram?**  
  Tingkatkan `XDimension.Pixels` menjadi 3 atau 4. Ukuran modul yang lebih besar menghasilkan gambar beresolusi tinggi, meskipun ukuran file menjadi lebih besar.

* **Bisakah saya menghasilkan SVG alih-alih PNG?**  
  Ya. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Svg` pada pemanggilan `Save`.

* **Apakah saya harus mengatur level koreksi‑error secara manual?**  
  Aspose.BarCode secara otomatis memilih level optimal. Untuk kasus penggunaan khusus Anda dapat menyesuaikan `Pdf417.ErrorCorrectionLevel`.

* **Bagaimana cara menyematkan barcode ke dalam dokumen PDF?**  
  Gunakan `Aspose.Pdf` untuk menambahkan PNG atau SVG yang dihasilkan sebagai elemen gambar pada halaman PDF.

* **Apakah perpustakaan ini thread‑safe?**  
  Setiap instance `BarcodeGenerator` bersifat independen; Anda dapat membuat generator pada banyak thread tanpa berbagi state.

## Kesimpulan

Sekarang Anda tahu cara **membuat barcode PDF417** di C# menggunakan Aspose.BarCode, mencakup varian dasar, kompak, makro, dan mikro.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut membahas topik terkait yang memperluas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}