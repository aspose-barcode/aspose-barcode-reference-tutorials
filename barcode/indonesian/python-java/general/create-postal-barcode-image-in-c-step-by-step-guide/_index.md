---
category: general
date: 2026-08-03
description: Buat gambar barcode pos dengan cepat menggunakan C#. Pelajari cara menghasilkan
  barcode pos, mengatur dimensi barcode, dan menghasilkan barcode Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: id
lastmod: 2026-08-03
og_description: Buat gambar barcode pos di C# dengan tutorial lengkap ini; pelajari
  cara mengatur dimensi barcode, menghasilkan barcode Planet, dan membuat barcode
  RM4SCC.
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: Buat gambar kode batang pos di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: Buat gambar kode batang pos di C# – panduan langkah demi langkah
url: /id/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat gambar barcode pos di C# – panduan langkah demi langkah

Jika Anda perlu **membuat gambar barcode pos** di C#, panduan ini menunjukkan cara melakukannya secara tepat. Kami akan membahas **cara menghasilkan barcode pos**, **cara mengatur dimensi barcode**, dan cara **menghasilkan barcode planet** untuk standar pos yang umum.

Anda akan selesai dengan dua file PNG siap pakai—satu barcode Planet dan satu barcode RM4SCC—masing‑masing setinggi 100 px. Tidak diperlukan alat tambahan selain pustaka Aspose.BarCode untuk .NET.

## Prasyarat

* .NET 6 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
* Visual Studio 2022 atau IDE C# apa pun
* Paket NuGet **Aspose.BarCode** (pustaka yang menyediakan `BarcodeGenerator`)

## Langkah 1: Instal pustaka barcode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode`, yang berisi `BarcodeGenerator` dan enumerasi `EncodeTypes` yang diperlukan untuk barcode pos.

## Langkah 2: Tentukan folder output

Membuat jalur output yang dapat diandalkan mencegah kesalahan runtime ketika folder belum ada.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*Mengapa ini penting*: `Directory.CreateDirectory` bersifat idempotent—hanya membuat folder jika belum ada, sehingga menghindari pengecualian pada eksekusi berikutnya.

## Langkah 3: Konfigurasikan dimensi barcode umum

Menetapkan X‑dimension (lebar satu bar) dan tinggi bar keseluruhan memungkinkan Anda mengontrol ukuran visual gambar yang dihasilkan.

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**Cara mengatur dimensi barcode**: Properti `Parameters.Barcode.XDimension.Pixels` menentukan lebar bar sempit, sementara `Parameters.Barcode.BarHeight.Pixels` menentukan tinggi penuh. Sesuaikan nilai‑nilai ini agar memenuhi spesifikasi layanan pengiriman Anda.

## Langkah 4: Hasilkan barcode Planet

Planet adalah barcode pos yang banyak digunakan di Britania Raya. Kode berikut membuat barcode Planet setinggi 100 px dan menyimpannya sebagai PNG.

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**Mengapa ini berhasil**: `EncodeTypes.Planet` memberi tahu generator untuk menggunakan simbol Planet. Metode `Save` menulis file PNG ke jalur yang ditentukan, mempertahankan dimensi yang telah kita setel sebelumnya.

## Langkah 5: Hasilkan barcode RM4SCC

RM4SCC adalah standar barcode pos Belanda. Kode di bawah ini meniru contoh Planet, memperlihatkan **cara menghasilkan barcode pos** dengan tipe berbeda namun dengan dimensi yang sama.

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

Kedua file PNG kini berada di folder `Barcodes`. Membukanya akan menampilkan barcode bersih setinggi 100 px siap untuk dicetak atau disisipkan dalam dokumen.

## Kode sumber lengkap

Berikut adalah program lengkap yang dapat dijalankan untuk **membuat file gambar barcode pos** bagi standar Planet dan RM4SCC.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### Output yang diharapkan

Menjalankan program akan mencetak jalur file dan membuat dua file PNG:

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

Setiap gambar setinggi 100 px, dengan lebar bar sempit 4 pixel, sesuai dengan dimensi yang telah kita setel.

## Tips praktis dan jebakan umum

* **Izin folder** – Jika program dijalankan dengan akun terbatas, pastikan folder target dapat ditulisi.
* **Dimensi berbeda** – Untuk membuat barcode yang lebih tinggi, tingkatkan `barHeightPixels`. Untuk resolusi lebih halus, turunkan `xDimensionPixels`, tetapi pertahankan ≥ 2 agar tidak muncul artefak rendering.
* **Simbolologi pos lainnya** – Aspose.BarCode juga mendukung `EncodeTypes.Postnet` dan `EncodeTypes.AustralianPost`. Ganti nilai `EncodeTypes` dan pertahankan logika dimensi yang sama.
* **Format gambar** – Gunakan `BarCodeImageFormat.Jpeg` untuk ukuran file lebih kecil bila kualitas lossless tidak diperlukan.

## Kesimpulan

Anda kini tahu cara **membuat file gambar barcode pos** di C# dengan mengonfigurasi dimensi, memilih simbolologi yang tepat, dan menyimpan hasilnya sebagai PNG. Tutorial ini mencakup **cara menghasilkan barcode pos**, memperlihatkan **menghasilkan barcode planet**, dan menjelaskan **cara mengatur dimensi barcode** untuk output yang konsisten.

Selanjutnya, jelajahi **penyesuaian warna barcode**, menambahkan **teks yang dapat dibaca manusia**, atau mengintegrasikan gambar ke dalam faktur PDF. Pola yang sama berlaku untuk tipe barcode lain yang didukung Aspose.BarCode, memungkinkan Anda memperluas solusi ini menjadi alur kerja otomatisasi pos yang lengkap.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang dapat dijalankan dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}