---
category: general
date: 2026-08-25
description: Buat barcode RM4SCC C# dengan kode langkah demi langkah dan pelajari
  cara mengatur tinggi barcode untuk ukuran yang tepat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: id
lastmod: 2026-08-25
og_description: Buat barcode RM4SCC C# dengan Aspose.BarCode dan pelajari cara mengatur
  tinggi barcode untuk kontrol yang tepat dalam aplikasi .NET Anda.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Buat barcode RM4SCC C# – panduan mengatur tinggi barcode
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Buat kode batang RM4SCC C# dan atur tinggi kode batang
url: /id/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode RM4SCC C# dan atur tinggi barcode

Buat barcode RM4SCC C# dengan cepat menggunakan pustaka Aspose.BarCode. Tutorial ini menunjukkan **cara mengatur tinggi barcode** dan menyesuaikan properti visual lainnya sehingga barcode pas dengan tata letak Anda secara tepat.

Anda akan melihat program konsol lengkap yang siap‑jalan dan menghasilkan tiga file PNG:

* barcode Planet dengan tinggi default (untuk perbandingan)  
* barcode RM4SCC dengan tinggi manual 100 px  
* barcode Planet dengan bar kosong (tidak terisi)  

Contoh ini mengasumsikan Anda memiliki Visual Studio 2022 (atau IDE .NET 6+ apa pun) serta lisensi atau salinan evaluasi Aspose.BarCode untuk .NET yang valid.

## Prerequisites

| Requirement | Reason |
|-------------|--------|
| .NET 6 SDK (atau lebih baru) | Menyediakan runtime untuk aplikasi konsol |
| Paket NuGet Aspose.BarCode untuk .NET | Menyediakan `BarcodeGenerator`, `EncodeTypes`, dan API ekspor gambar |
| Pengetahuan dasar C# | Diperlukan untuk memahami alur kode |

Instal paket NuGet dengan:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Jika Anda menjalankan kode tanpa lisensi, gambar yang dihasilkan akan berisi watermark Aspose kecil.

## Step 1: Set up the project structure

Buat proyek konsol baru dan tambahkan direktif `using` yang diperlukan:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

Pernyataan `using` memberi Anda akses ke kelas generator barcode dan enum format PNG.

## Step 2: Define the output folder

Pilih folder tempat file PNG akan disimpan. Folder harus ada sebelum Anda memanggil `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Membuat direktori secara programatik menghindari *FileNotFoundException* ketika kode dijalankan di mesin baru.

## Step 3: Generate a Planet barcode with the default height (baseline)

Barcode Planet bukan fokus panduan ini, tetapi memberikan baseline visual untuk dibandingkan dengan barcode RM4SCC yang diatur secara manual.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Mengapa ini penting:*  
`XDimension` menentukan lebar satu bar. Menjaga nilai ini konstan sambil mengubah `BarHeight` mengisolasi efek tinggi.

## Step 4: **Create RM4SCC barcode C#** – set a manual height

Sekarang kita menangani tugas utama: **membuat barcode RM4SCC C#** dan secara eksplisit mengontrol tingginya.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### How to set barcode height

Properti `BarHeight` berada di bawah `Parameters.Barcode`. Properti ini menerima nilai `float` yang diekspresikan dalam **pixel**, **point**, atau **milimeter** tergantung pada `Unit` yang Anda pilih (`Pixels`, `Points`, `Millimeters`). Pada contoh ini kami menggunakan `Pixels` karena format outputnya PNG.

Jika Anda memerlukan tinggi dalam milimeter, ubah unit terlebih dahulu:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Step 5: Generate a Planet barcode with empty (unfilled) bars

Langkah ini memperlihatkan properti berguna lainnya—`FilledBars`. Menetapkannya ke `false` menghasilkan barcode “hollow”, yang dapat berguna untuk keperluan desain.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Full, runnable program

Salin kode berikut ke dalam `Program.cs`. Bangun dan jalankan proyek; tiga file PNG akan muncul di folder `GeneratedBarcodes`.



## What Should You Learn Next?

Tutorial berikut membahas topik terkait yang memperluas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang dapat dijalankan dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat barcode code128 Java dan mengatur tinggi bar](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Cara membuat zona diam barcode .NET untuk Code 16K menggunakan Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cara membuat barcode Aztec dengan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}