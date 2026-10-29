---
category: general
date: 2026-10-28
description: Buat barcode dari teks di C# dengan Aspose.BarCode. Pelajari cara menghasilkan
  gambar barcode PDF417, mengatur kolom, menyesuaikan dimensi X, dan mengaktifkan
  mode kompak.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: id
lastmod: 2026-10-28
og_description: Buat barcode dari teks di C# menggunakan Aspose.BarCode. Tutorial
  ini menunjukkan cara menghasilkan gambar barcode PDF417, menyesuaikan ukuran, kolom,
  dan mode kompak.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Buat barcode dari teks di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Cara membuat barcode dari teks di C# menggunakan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode dari teks di C# menggunakan Aspose.BarCode

Jika Anda perlu **membuat barcode dari teks** dalam aplikasi .NET, panduan ini menyediakan solusi siap‑jalankan. Anda akan melihat cara **menghasilkan gambar barcode PDF417**, mengontrol lebar modul, jumlah kolom, dan mengaktifkan mode kompak tanpa meninggalkan IDE Anda.

Tutorial ini mencakup semua yang diperlukan untuk kode **generate barcode C#**, mulai dari instalasi pustaka hingga menyimpan file PNG akhir. Pada akhir tutorial Anda dapat menyematkan barcode PDF417 berkapasitas tinggi dalam laporan, tiket, atau label inventaris.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau editor apa pun yang mendukung .NET)  
* Akses internet untuk mengunduh paket NuGet Aspose.BarCode untuk .NET  

Item-item ini cukup untuk mengompilasi dan menjalankan contoh pada Windows, Linux, atau macOS.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Pustaka yang menggerakkan pembuatan barcode adalah **Aspose.BarCode untuk .NET**. Instal dengan .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode`, yang berisi kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini.

## Langkah 2: Buat proyek konsol dan tambahkan kode

Buat proyek konsol baru dan ganti `Program.cs` yang dihasilkan dengan kode berikut. Program ini mendemonstrasikan cara **membuat barcode dari teks** dan menyimpannya sebagai **gambar barcode PDF417**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Mengapa setiap baris penting

* **`EncodeTypes.Pdf417`** memilih simbol PDF417, yang ideal untuk mengkodekan sejumlah besar data dalam format dua‑dimensi.  
* **`XDimension.Pixels = 2`** mengurangi lebar modul, membuat barcode lebih padat dan lebih cocok untuk ruang terbatas.  
* **`Pdf417.Columns = 3`** mengontrol jumlah kolom data vertikal; jumlah yang lebih sedikit menghasilkan barcode yang lebih tinggi namun lebih sempit.  
* **`Pdf417.Truncate = true`** mengaktifkan mode kompak, memotong kolom yang tidak terpakai di sisi kanan. Ini adalah pengaturan kunci yang mengubah PDF417 biasa menjadi **gambar barcode PDF417 kompak**.  

## Langkah 3: Bangun dan jalankan proyek

Jalankan perintah berikut di direktori proyek:

```bash
dotnet build
dotnet run
```

Setelah program selesai, Anda akan melihat pesan konsol yang mengonfirmasi lokasi file. Buka `CompactPdf417.png` dengan penampil gambar apa pun untuk memverifikasi hasilnya.

**Output yang diharapkan** – PNG berkontras tinggi yang menampilkan barcode PDF417 kompak yang mengkodekan string `Åspóse.Barcóde©`. Memindai gambar dengan pembaca barcode standar mengembalikan teks asli, mengonfirmasi bahwa **generate pdf417 barcode** berhasil.

## Langkah 4: Menyesuaikan barcode untuk berbagai skenario

Meskipun contoh ini menggunakan jumlah kolom tetap dan X‑dimension, Anda dapat menyesuaikan generator untuk kebutuhan lain:

| Skenario | Penyesuaian |
|----------|------------|
| Payload data lebih besar | Increase `Pdf417.Columns` or set `Pdf417.Rows` manually |
| Keandalan pemindaian lebih tinggi | Raise `XDimension.Pixels` to 3 or 4 |
| Format gambar berbeda | Replace `BarCodeImageFormat.Png` with `Jpeg` or `Bmp` |
| Latar belakang transparan | Set `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Opsi-opsi ini memungkinkan Anda **generate barcode C#** solusi yang cocok untuk aplikasi seluler, laporan desktop, atau layanan web.

## Langkah 5: Menangani kasus tepi dan praktik terbaik

* **Dukungan Unicode** – Generator secara otomatis mengkodekan karakter Unicode, tetapi pastikan string sumber Anda dienkode UTF‑8 jika Anda membacanya dari file.  
* **Teks besar** – PDF417 dapat mengkodekan hingga 1.850 karakter alfanumerik. Jika Anda melebihi batas ini, pustaka akan melemparkan pengecualian; bagi data menjadi beberapa barcode atau beralih ke simbol dengan kapasitas lebih tinggi.  
* **Penanganan error** – Bungkus kode generasi dalam blok `try/catch` untuk menangkap `BarCodeException` dan memberikan pesan error yang ramah.  
* **Kinerja** – Menghasilkan banyak barcode dalam loop akan lebih efisien dengan menggunakan satu instance `BarcodeGenerator` dan hanya memperbarui `CodeText` di antara iterasi.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Daftar sumber lengkap

Berikut adalah program lengkap yang berdiri sendiri yang dapat Anda salin ke `Program.cs`. Tidak diperlukan file tambahan.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Menjalankan program ini membuat **gambar barcode pdf417** yang ditampilkan pada ilustrasi di bawah.

![Barcode PDF417 kompak yang dibuat dari teks menggunakan C#](/images/compact-pdf417.png){.img-fluid alt="contoh membuat barcode dari teks yang menampilkan gambar barcode PDF417 kompak"}

*Deskripsi gambar: File PNG menampilkan barcode PDF417 kompak yang mengkodekan string “Åspóse.Barcóde©”.*  

## Kesimpulan

Anda kini tahu cara **membuat barcode dari teks** di C# dan menghasilkan **gambar barcode PDF417** dengan dimensi khusus dan mode kompak. Contoh ini menunjukkan langkah-langkah penting untuk **generate barcode C#**, menangani data Unicode, dan menyesuaikan parameter visual untuk berbagai skenario penyebaran.

Selanjutnya, jelajahi topik terkait seperti **generate QR code in C#**, **add barcode to PDF documents**, atau **embed barcodes in ASP.NET Core APIs**. Masing‑masing topik ini dibangun di atas dasar `BarcodeGenerator` yang sama yang dibahas di sini.

Selamat coding, dan nikmati mengintegrasikan barcode ke dalam solusi .NET Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Hasilkan Barcode PDF417 di C# – Buat Barcode PDF417 C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Cara menghasilkan barcode PDF417 dengan Aspose.BarCode di C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Cara membuat gambar barcode PDF417 di C# – panduan lengkap](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}