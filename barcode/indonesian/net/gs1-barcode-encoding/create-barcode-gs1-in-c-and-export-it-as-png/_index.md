---
category: general
date: 2026-09-29
description: Buat barcode GS1 di C# dan hasilkan gambar PNG barcode menggunakan BarcodeGenerator.
  Ikuti panduan langkah demi langkah untuk mengekspor gambar barcode secara efisien.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: id
lastmod: 2026-09-29
og_description: Buat barcode GS1 di C# dan hasilkan file PNG barcode dengan BarcodeGenerator.
  Ikuti panduan lengkap ini untuk mengekspor gambar barcode dengan cepat.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Buat barcode GS1 di C# – ekspor sebagai PNG dalam hitungan menit
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Buat barcode GS1 di C# dan ekspor sebagai PNG
url: /id/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode GS1 di C# dan ekspor sebagai PNG

Jika Anda perlu **membuat barcode GS1** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan melihat solusi singkat yang menghasilkan gambar PNG barcode dan mengekspor gambar barcode ke disk, semuanya dengan kelas Aspose.BarCode `BarcodeGenerator`.

Membuat barcode GS1 adalah kebutuhan umum untuk sistem inventaris, pengiriman, dan titik penjualan. Pada akhir tutorial ini Anda akan dapat menulis program C# kecil yang membuat barcode MicroPDF417 yang mematuhi standar GS1 dan menyimpannya sebagai file PNG berkualitas tinggi.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* **.NET 6** (atau versi .NET yang lebih baru) terpasang.
* **Visual Studio 2022** atau IDE apa pun yang mendukung C#.
* Paket NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – menyediakan API `BarcodeGenerator` yang digunakan dalam contoh.
* Pemahaman dasar tentang sintaks C#.

> **Pro tip:** Gunakan edisi komunitas gratis Aspose.BarCode saat bereksperimen; versi lengkap menghilangkan watermark evaluasi.

## Langkah 1 – Buat barcode GS1 dengan BarcodeGenerator

Hal pertama yang Anda perlukan adalah menginstansiasi `BarcodeGenerator` untuk format *MicroPDF417* dan memberinya string data GS1. Identifier Aplikasi GS1 (AI) dibungkus dalam tanda kurung, mis. `(01)` untuk GTIN‑14 dan `(21)` untuk nomor seri.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Mengapa ini penting:**  
`EncodeTypes.MicroPdf417` secara otomatis memperlakukan input sebagai data GS1 ketika string berisi AI yang valid. Ini memastikan barcode yang dihasilkan mematuhi spesifikasi GS1 tanpa konfigurasi tambahan.

## Langkah 2 – Atur dimensi barcode untuk ukuran optimal

Ukuran visual barcode dikendalikan oleh **X‑dimension** (lebar satu modul). Menyesuaikan `XDimension.Pixels` memungkinkan Anda menyetel ukuran gambar akhir sambil mempertahankan keterbacaan.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Cara menghasilkan barcode PNG** – X‑dimension tidak memengaruhi data yang dikodekan; hanya mengubah dimensi fisik gambar yang dihasilkan. Jika Anda memerlukan barcode yang lebih besar untuk pencetakan resolusi tinggi, tingkatkan nilai ini (mis., `3` atau `4`).

## Langkah 3 – Hasilkan barcode PNG dan ekspor gambar barcode

Sekarang Anda dapat merender barcode dan menuliskannya ke file PNG. Metode `Save` menerima jalur target dan format gambar yang diinginkan.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Apa yang terjadi di balik layar:**  
`BarcodeGenerator.Save` meraster barcode menjadi bitmap, menerapkan X‑dimension yang Anda setel sebelumnya, dan mengkodekan bitmap sebagai file PNG. File yang dihasilkan dapat langsung digunakan di halaman web, dicetak pada label, atau disematkan dalam PDF.

## Contoh kode sumber lengkap

Berikut adalah aplikasi konsol lengkap yang dapat Anda salin, tempel, dan jalankan. Ia menunjukkan **cara menghasilkan file PNG barcode**, **mengekspor gambar barcode**, serta mencakup penanganan kesalahan dasar.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Output yang diharapkan

Saat Anda menjalankan program, Anda akan melihat:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Membuka file PNG menampilkan barcode **GS1 MicroPDF417** yang jelas, yang mengkodekan GTIN‑14 `12345678901234` dan nomor seri `ABC123`. Memindainya dengan pemindai yang kompatibel dengan GS1 akan mengembalikan string data asli.

## Kesulitan umum dan praktik terbaik

| Masalah | Mengapa terjadi | Cara menghindarinya |
|-------|----------------|-----------------|
| **Format AI yang salah** | Kurangnya tanda kurung atau urutan yang salah membuat barcode tidak menjadi GS1. | Selalu bungkus setiap AI dengan tanda kurung, misalnya `(01)`. |
| **X‑dimension terlalu kecil** | Barcode menjadi tidak terbaca pada perangkat beresolusi rendah. | Pertahankan `XDimension.Pixels` ≥ 2 untuk kebanyakan printer; tingkatkan untuk output DPI tinggi. |
| **Folder output tidak ada** | `Save` melempar `DirectoryNotFoundException`. | Gunakan `Directory.CreateDirectory` sebelum memanggil `Save`. |
| **Menggunakan EncodeType yang salah** | Beberapa tipe (mis., `Code128`) tidak mendukung data GS1 secara langsung. | Pilih `EncodeTypes.MicroPdf417` atau tipe yang kompatibel dengan GS1. |
| **Referensi NuGet hilang** | Kesalahan waktu kompilasi seperti `The type or namespace name 'Aspose' could not be found`. | Instal paket `Aspose.BarCode` melalui NuGet. |

## Memperluas contoh

* **Format gambar yang berbeda** – Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Gif`, atau `Bmp` jika Anda membutuhkan format lain.
* **Output resolusi lebih tinggi** – Atur `generator.Parameters.ImageResolution.DpiX` dan `DpiY` sebelum menyimpan.
* **Menyematkan dalam PDF** – Gunakan `Aspose.Pdf` untuk menempatkan PNG ke dalam faktur atau label PDF.

## Kesimpulan

Anda kini tahu cara **membuat barcode GS1** di C# menggunakan `BarcodeGenerator` Aspose.BarCode, **menghasilkan barcode PNG**, dan **mengekspor gambar barcode** ke sistem file. Panduan ini mencakup setiap langkah—dari menginisialisasi generator dengan data GS1, menyesuaikan X‑dimension, hingga menyimpan file PNG akhir—serta membahas kesalahan umum dan menawarkan ide perpanjangan.

Silakan bereksperimen dengan Identifier Aplikasi GS1 lainnya, simbol barcode yang berbeda, atau gambar beresolusi lebih tinggi. Setelah menguasai dasar-dasar ini, menghasilkan barcode yang sesuai standar untuk inventaris, pengiriman, atau ritel menjadi bagian rutin dari kotak peralatan .NET Anda.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat Gambar Barcode GS1 di C# – Cara Cepat Menghasilkan Barcode C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Buat barcode PNG di C# – panduan langkah demi langkah](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Buat gambar barcode di C# – panduan pemrograman lengkap](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}