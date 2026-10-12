---
category: general
date: 2026-10-12
description: Cara mengatur tinggi barcode dan menghasilkan barcode DataBar dalam C#
  menggunakan Aspose.BarCode. Ikuti panduan langkah demi langkah dengan kode lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: id
lastmod: 2026-10-12
og_description: Cara mengatur tinggi barcode di C# dan menghasilkan barcode DataBar
  dengan Aspose.BarCode. Pelajari kode lengkapnya, mengapa setiap langkah penting,
  dan cara mengubah tinggi barcode.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Cara mengatur tinggi barcode dan menghasilkan barcode DataBar di C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara mengatur tinggi barcode, menghasilkan barcode DataBar di C#
url: /id/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur tinggi barcode, menghasilkan barcode DataBar di C#

Jika Anda perlu **how to set barcode** dimensi secara programatis, panduan ini menunjukkan langkah‑langkah tepatnya. Anda akan belajar cara menghasilkan DataBar Omni‑directional barcode, menyesuaikan tingginya, dan menyimpan kedua versi sebagai file PNG.

Mengubah tinggi bar barcode adalah kebutuhan umum ketika Anda mengintegrasikan barcode ke dalam struk, label produk, atau layar seluler. Contoh di bawah ini menggunakan pustaka Aspose.BarCode, yang mendukung seluruh rentang simbol GS1 DataBar.

## Apa yang akan Anda capai

* **how to set barcode** height untuk DataBar Omni‑directional barcode  
* kode **generate barcode c#** yang membuat dua gambar dengan tinggi yang berbeda  
* memahami simbol **how to create databar** dan mengapa tinggi bar penting  
* menerapkan logika **change barcode height** tanpa membuat ulang generator  

Tidak diperlukan alat eksternal selain paket NuGet Aspose.BarCode dan runtime .NET 6+.

## Prasyarat

* .NET 6 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau editor C# apa pun)  
* Aspose.BarCode untuk .NET – instal melalui `dotnet add package Aspose.BarCode`  

> **Pro tip:** Gunakan lisensi percobaan gratis dari Aspose jika Anda tidak memiliki kunci komersial; API berfungsi dengan cara yang sama.

## Langkah 1: Instal paket Aspose.BarCode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode`, yang berisi kelas `BarcodeGenerator` yang akan kita gunakan untuk membuat gambar **generate barcode c#**.

## Langkah 2: Buat generator barcode DataBar

Tindakan konkret pertama untuk parameter **how to set barcode** adalah menginstansiasi `BarcodeGenerator` dengan simbol dan string data yang diinginkan.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Mengapa ini penting:* `EncodeTypes.DatabarOmniDirectional` menghasilkan DataBar yang kompak dan omnidirectional yang dapat dipindai dari sudut mana pun—ideal untuk label kecil.

## Langkah 3: Atur parameter barcode umum (termasuk tinggi bar awal)

Sekarang kita mengatur **how to set barcode** X‑dimension dan tinggi bar sebelum menyimpan gambar pertama.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimension mengontrol lebar keseluruhan setiap bar; pengaturan 2‑pixel menghasilkan gambar yang dapat dibaca dan tajam pada kebanyakan layar. Langkah **change barcode height** nanti akan menggunakan kembali generator yang sama, menghemat waktu dan memori.

## Langkah 4: Simpan gambar barcode pertama (tinggi 30‑pixel)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

File `DatabarHeight30.png` kini berisi barcode DataBar dengan tinggi bar 30‑pixel.

## Langkah 5: Ubah hanya tinggi bar menjadi 60 pixel

Untuk mendemonstrasikan **change barcode height**, kami mengubah hanya properti `BarHeight`. Semua pengaturan lain tetap tidak berubah, yang merupakan cara paling efisien untuk menghasilkan beberapa ukuran dari satu generator.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Langkah 6: Simpan gambar barcode kedua (tinggi 60‑pixel)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG, masing‑masing dengan tinggi bar yang berbeda tetapi data dan X‑dimension yang identik.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke dalam aplikasi console baru (`dotnet new console`) dan jalankan segera.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Output yang diharapkan

Menjalankan program menghasilkan dua file di direktori kerja executable:

* `DatabarHeight30.png` – barcode DataBar dengan bar setinggi 30‑pixel.  
* `DatabarHeight60.png` – barcode yang sama, tetapi setiap bar dua kali lebih tinggi.

Kedua gambar dapat dibuka di penampil gambar apa pun atau disematkan langsung ke PDF, halaman HTML, atau label cetak.

## Mengapa menyesuaikan tinggi bar penting

* **Scanning reliability:** Beberapa pemindai kesulitan dengan bar yang sangat pendek pada media beresolusi rendah; meningkatkan tinggi meningkatkan deteksi.  
* **Design constraints:** Aplikasi seluler mungkin memerlukan barcode kompak (30 px) sementara struk cetak mungkin memerlukan yang lebih besar (60 px).  
* **Regulatory compliance:** Beberapa industri mewajibkan tinggi bar minimum untuk simbol GS1 DataBar.

Dengan menggunakan kembali instance `BarcodeGenerator` yang sama, Anda menghindari beban tambahan untuk mem‑parse ulang string data, yang sangat menguntungkan dalam lingkungan dengan throughput tinggi.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian yang disarankan |
|-----------|-------------------|
| Membutuhkan X‑dimension yang berbeda | Ubah `XDimension.Pixels` sebelum `Save` pertama. |
| Menginginkan simbol yang berbeda (mis., DataBar Stacked) | Gunakan `EncodeTypes.DatabarStacked` saat membuat `BarcodeGenerator`. |
| Harus menyematkan barcode ke dalam PDF | Gunakan `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` dan tambahkan stream ke pustaka PDF. |
| Menjalankan pada .NET Framework 4.6 | Kode yang sama berfungsi; cukup referensikan assembly Aspose.BarCode yang sesuai. |

## Tips profesional untuk menghasilkan barcode yang andal

* **Cache the generator** ketika Anda menghasilkan banyak barcode dengan data yang sama tetapi ukuran berbeda.  
* **

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan dan Menyesuaikan Tinggi Barcode untuk One-Dimensional Databar menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Cara membuat gambar PNG databar dengan C# dan Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Cara menghasilkan barcode dengan ukuran khusus dan menyimpan gambar dalam C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}