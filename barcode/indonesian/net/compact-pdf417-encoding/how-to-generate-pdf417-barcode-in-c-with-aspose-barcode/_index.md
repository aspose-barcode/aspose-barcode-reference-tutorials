---
category: general
date: 2026-11-27
description: Pelajari cara menghasilkan barcode PDF417 di C# menggunakan Aspose.BarCode.
  Sesuaikan dimensi, atur jumlah kolom, dan simpan sebagai PNG dalam beberapa baris
  kode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: id
lastmod: 2026-11-27
og_description: Buat kode batang PDF417 dalam C# secara instan. Tutorial ini menunjukkan
  cara mengatur dimensi, jumlah kolom, dan menyimpan hasilnya sebagai gambar PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Membuat barcode PDF417 di C# – panduan cepat dengan Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cara menghasilkan barcode PDF417 di C# dengan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 di C# dengan Aspose.BarCode

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan solusi singkat, menyeluruh. Anda akan melihat cara membuat barcode, menyesuaikan ukurannya, dan menulis hasilnya ke file PNG—semua dengan library Aspose.BarCode.

Membuat barcode PDF417 umum ketika Anda harus mengkodekan data dalam jumlah besar untuk dipindai pada perangkat seluler, boarding pass, atau label inventaris. Pada akhir tutorial ini Anda akan memiliki program konsol siap‑jalankan yang menghasilkan gambar PNG berkualitas tinggi.

## Prerequisites

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Versi terbaru **Aspose.BarCode untuk .NET** (paket NuGet `Aspose.BarCode`)  
* IDE atau editor (Visual Studio, VS Code, Rider, dll.)  

Kode ini bekerja di Windows, Linux, dan macOS karena Aspose.BarCode bersifat lintas‑platform.

## Langkah 1: Buat proyek konsol baru

Buka terminal dan jalankan:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Ini membuat proyek C# minimal bernama **Pdf417Demo** dan menambahkan dependensi `Aspose.BarCode`.

## Langkah 2: Tulis kode pembuatan barcode

Buka **Program.cs** dan ganti isinya dengan yang berikut:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Mengapa setiap baris penting

* **BarcodeGenerator** – kelas inti yang membuat gambar barcode. Menetapkan `EncodeTypes.Pdf417` memilih simbol PDF417.  
* **XDimension.Pixels** – menentukan lebar bar terkecil. Nilai yang lebih kecil memperkecil gambar; nilai yang lebih besar meningkatkan keterbacaan pada pemindai beresolusi rendah.  
* **Pdf417.Columns** – mengontrol jumlah kolom data. Lebih banyak kolom menghasilkan barcode yang lebih pendek namun lebih tinggi; lebih sedikit kolom membuatnya lebih lebar.  
* **ErrorCorrectionLevel** – level yang lebih tinggi menambahkan data redundan, membuat barcode tahan terhadap kerusakan dengan mengorbankan ukuran.  
* **Save(..., BarCodeImageFormat.Png)** – menulis gambar ke disk dalam format PNG, format loss‑less yang ideal untuk pemrosesan lebih lanjut atau penyematan dalam dokumen.

## Langkah 3: Bangun dan jalankan program

Dari terminal, jalankan:

```bash
dotnet run
```

Anda akan melihat:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

File bernama **Pdf417Basic.png** muncul di folder proyek. Membukanya menampilkan barcode PDF417 yang jelas yang mengkodekan teks *“Sample text for PDF417 barcode”*.

![Barcode PDF417 yang dihasilkan disimpan sebagai file PNG](pdf417-barcode-example.png "Barcode PDF417 yang dihasilkan dalam format PNG")

*Image alt text: screenshot of a generated PDF417 barcode saved as a PNG file, demonstrating the result of the generate PDF417 barcode tutorial.*  
*Teks alt gambar: tangkapan layar barcode PDF417 yang dihasilkan disimpan sebagai file PNG, menunjukkan hasil tutorial menghasilkan barcode PDF417.*

## Langkah 4: Variasi umum dan kasus tepi

### Mengubah data yang dikodekan

Ganti argumen kedua `BarcodeGenerator` dengan string UTF‑8 apa pun, misalnya:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

Generator secara otomatis membagi data ke baris dan kolom.

### Menyesuaikan ukuran gambar tanpa mengurangi kualitas

Jika Anda memerlukan gambar lebih besar untuk pencetakan, tingkatkan `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Menangani input yang sangat panjang

PDF417 dapat mengkodekan hingga 1 850 karakter. Untuk string yang sangat panjang, Anda mungkin ingin meningkatkan jumlah kolom:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Jika konten melebihi kapasitas maksimum, Aspose.BarCode akan melempar `ArgumentException`. Bungkus kode pembuatan dalam blok try‑catch untuk menampilkan pesan error yang ramah.

### Menyimpan dalam format lain

Aspose.BarCode mendukung BMP, JPEG, TIFF, dan SVG. Ubah formatnya seperti ini:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Langkah 5: Verifikasi barcode

Anda dapat memastikan barcode valid dengan memindainya menggunakan aplikasi pembaca PDF417 apa pun (mis., aplikasi kamera smartphone yang mendukung pemindaian barcode). Teks yang didekode harus cocok dengan string yang Anda berikan ke generator.

Jika pemindaian gagal:

* Pastikan gambar tidak terkompresi (gunakan PNG atau SVG lossless).  
* Verifikasi bahwa `ErrorCorrectionLevel` cukup tinggi untuk lingkungan yang dimaksud.  
* Periksa bahwa dimensi barcode sesuai dengan resolusi pemindai.

## Kesimpulan

Anda kini tahu cara **menghasilkan barcode PDF417** di C# menggunakan Aspose.BarCode, menyesuaikan dimensinya, mengatur jumlah kolom, dan mengekspor hasilnya sebagai gambar PNG. Pendekatan ini bekerja untuk berbagai skenario, mulai dari tiket seluler hingga manajemen inventaris.

Selanjutnya, Anda mungkin ingin menjelajahi:

* **Membaca** barcode PDF417 dengan `BarCodeReader`.  
* Menghasilkan simbol lain seperti QR Code atau DataMatrix.  
* Menyematkan PNG ke dalam PDF, laporan, atau halaman web.  

Silakan bereksperimen dengan level koreksi error, format gambar, dan payload data yang berbeda untuk menyesuaikan kebutuhan proyek Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menghasilkan barcode PDF417 di C# dengan Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Cara menghasilkan barcode PDF417 dan merendernya sebagai PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Cara menghasilkan barcode PDF417 di C# dan mengatur ukuran barcode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}