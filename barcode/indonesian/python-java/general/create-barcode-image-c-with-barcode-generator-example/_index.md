---
category: general
date: 2026-09-10
description: Buat gambar barcode C# dengan cepat menggunakan contoh generator barcode
  C# yang menunjukkan cara mengatur dimensi dan menyimpan file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: id
lastmod: 2026-09-10
og_description: Buat gambar barcode C# dengan contoh generator barcode yang singkat.
  Pelajari cara mengatur ukuran, tinggi, dan mengekspor file PNG dalam hitungan menit.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Buat gambar barcode C# – contoh generator langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Buat gambar barcode C# dengan contoh generator barcode
url: /id/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat gambar barcode C# dengan contoh generator barcode

Jika Anda perlu **create barcode image C#** untuk pelabelan produk, pelacakan inventaris, atau pemindaian seluler, panduan ini menunjukkan solusi lengkap. Anda akan melihat **barcode generator example C#** yang mengonfigurasi lebar modul, tinggi bar, dan menyimpan file PNG hanya dalam beberapa baris kode.

Tutorial ini mencakup semua hal mulai dari menginstal pustaka yang diperlukan hingga menjalankan program konsol yang siap‑dikompilasi. Pada akhir tutorial, Anda akan memiliki dua file PNG barcode—satu dengan tinggi bar 30‑pixel dan satu lagi dengan tinggi bar 60‑pixel—siap digunakan dalam aplikasi .NET apa pun.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau versi lebih baru terinstal  
* Lingkungan pengembangan seperti Visual Studio 2022 atau VS Code  
* Paket NuGet **Aspose.BarCode** (kode menggunakan `BarcodeGenerator` dari pustaka ini)  

Anda dapat menambahkan paket dengan perintah CLI berikut:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Siapkan proyek konsol

Buat proyek konsol baru dan referensikan pustaka barcode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Perintah tersebut membuat file `Program.cs` tempat Anda akan menempatkan kode **barcode generator example C#**.

## Langkah 2: Tulis program lengkap untuk menghasilkan barcode

Ganti isi `Program.cs` dengan contoh lengkap yang dapat dijalankan di bawah ini. Program ini menunjukkan cara **create barcode image C#** dengan dimensi khusus dan cara menyimpan hasilnya sebagai file PNG.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Mengapa setiap baris penting

* **EncodeTypes.DatabarOmniDirectional** – memilih simbol DataBar Omnidirectional, yang mengkodekan data numerik dan banyak digunakan dalam ritel.  
* **XDimension.Pixels = 2** – mengatur lebar modul; nilai yang lebih kecil menghasilkan barcode yang lebih kompak.  
* **BarHeight.Pixels** – mengontrol tinggi visual bar. Menyesuaikan nilai ini memungkinkan Anda membuat barcode yang sesuai dengan berbagai ukuran label.  
* **Save method** – menulis barcode ke file PNG, format yang mempertahankan tepi tajam dan bekerja dengan sebagian besar pustaka gambar.

## Langkah 3: Bangun dan jalankan program

Jalankan perintah berikut dari folder proyek:

```bash
dotnet run
```

Setelah program selesai, Anda akan melihat dua file PNG di subfolder `output`:

* `DatabarBarHeight30Pixels.png` – tinggi bar 30‑pixel  
* `DatabarBarHeight60Pixels.png` – tinggi bar 60‑pixel  

Kedua gambar berisi data yang sama tetapi berbeda dalam tinggi visual, menggambarkan bagaimana **barcode generator example C#** dapat disesuaikan untuk berbagai kebutuhan label.

## Langkah 4: Verifikasi barcode yang dihasilkan

Buka file PNG dengan penampil gambar apa pun. Anda harus melihat barcode DataBar yang jelas dan kontras tinggi. Untuk memastikan barcode dapat dibaca, Anda dapat menggunakan aplikasi pemindai seluler (mis., aplikasi berbasis ZXing) atau pustaka desktop seperti **Aspose.BarCode** dalam mode decode:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Jika outputnya cocok dengan `(01)12345678901231`, proses pembuatan berhasil.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian | Potongan kode |
|-----------|------------|--------------|
| **Simbol yang berbeda** (mis., QR, Code128) | Ubah nilai `EncodeTypes` | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Format gambar khusus** (JPEG, BMP) | Gunakan enum `BarCodeImageFormat` yang berbeda | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Data dinamis** (input pengguna) | Ganti string yang dikodekan secara tetap dengan variabel | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Panjang data tidak valid** | Tangkap `ArgumentException` yang dilemparkan oleh generator | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Tips pro: selalu validasi panjang input untuk simbol yang dipilih; Aspose.BarCode akan melemparkan pengecualian jika data tidak memenuhi spesifikasi.

## Daftar periksa pemecahan masalah

* **Directory not found** – Helper `SaveBarcode` membuat folder `output` secara otomatis, tetapi pastikan aplikasi memiliki izin menulis.  
* **Unexpected image size** – Verifikasi bahwa `XDimension.Pixels` dan `BarHeight.Pixels` telah diatur sebelum memanggil `Save`. Mengubah nilai ini setelah penyimpanan tidak memengaruhi file yang sudah ditulis.  
* **Unreadable barcode** – Pastikan string yang dikodekan mengikuti format GS1 saat menggunakan simbol DataBar. Kurangnya tanda kurung atau Application Identifier yang salah menyebabkan kegagalan decoding.

## Kesimpulan

Anda sekarang tahu cara **create barcode image C#** menggunakan **barcode generator example C#** yang praktis. Program lengkap mengatur lebar modul, menyesuaikan tinggi bar, dan menyimpan file PNG dengan kode minimal. Dari sini Anda dapat menjelajahi fitur tambahan seperti kustomisasi warna, ekspor PDF multi‑halaman, atau pembuatan real‑time dalam API web ASP.NET Core.

**Next steps**

* Eksperimen dengan simbol lain (`EncodeTypes.Code128`, `EncodeTypes.QR`) untuk memperluas opsi pemindaian Anda.  
* Integrasikan generator ke dalam layanan web yang mengembalikan gambar barcode sesuai permintaan.  
* Gabungkan barcode dengan metadata produk dalam faktur PDF menggunakan Aspose.PDF.

Selamat coding, dan nikmati fleksibilitas yang diberikan C# untuk pembuatan gambar barcode!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Contoh Generator Barcode di C# – Atur Kolom, Baris & Ekspor Gambar](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Buat gambar barcode C# – Contoh GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Contoh Generator Barcode – Bangun Gambar DataBar di C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}