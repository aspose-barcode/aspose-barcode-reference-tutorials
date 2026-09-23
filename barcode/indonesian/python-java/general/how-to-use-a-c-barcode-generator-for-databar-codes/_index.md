---
category: general
date: 2026-09-23
description: Tutorial generator barcode C# menunjukkan cara menghasilkan gambar barcode
  dengan rasio aspek khusus menggunakan pustaka Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: id
lastmod: 2026-09-23
og_description: Panduan generator barcode C# memandu Anda cara menghasilkan gambar
  barcode, menyesuaikan rasio aspek, dan mengekspor file PNG menggunakan Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Buat kode batang berkualitas tinggi dengan generator kode batang C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Cara menggunakan generator barcode C# untuk kode DataBar
url: /id/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan generator barcode C# untuk kode DataBar

Jika Anda membutuhkan **c# barcode generator** yang dapat menghasilkan simbol DataBar stacked Omni‑Directional, panduan ini memberikan solusi lengkap yang siap dijalankan. Anda akan melihat cara menghasilkan gambar barcode, mengontrol dimensi X, dan mengubah rasio aspek tanpa meninggalkan IDE.

Membuat barcode adalah kebutuhan umum untuk sistem inventaris, label pengiriman, dan aplikasi point‑of‑sale. Pada akhir tutorial ini Anda dapat membuat file PNG dengan rasio aspek apa pun yang Anda pilih, dan Anda akan memahami cara menyesuaikan kode untuk tipe barcode lainnya.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau editor C# lain yang Anda sukai)  
* Referensi NuGet ke **Aspose.BarCode** – perpustakaan yang menyediakan kelas `BarcodeGenerator`  

Anda tidak memerlukan perpustakaan grafis terpisah; Aspose.BarCode menangani enkoding gambar secara internal.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan versi stabil terbaru dari perpustakaan ke file proyek Anda, sehingga kelas `BarcodeGenerator` tersedia untuk digunakan.

## Langkah 2: Tentukan folder output

Pilih folder tempat file PNG yang dihasilkan akan disimpan. Menggunakan jalur absolut atau relatif bekerja dengan cara yang sama, tetapi jalur relatif membuat proyek lebih portabel.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Membuat direktori secara programatik mencegah error runtime jika folder belum ada.

## Langkah 3: Buat instance generator barcode C# dengan data contoh

Konstruktor `BarcodeGenerator` memerlukan dua argumen: tipe barcode dan string data. Untuk simbol DataBar stacked Omni‑Directional Anda gunakan `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

String data mengikuti format GS1 Application Identifier. Enum `EncodeTypes` berisi lebih dari 150 standar barcode; Anda dapat beralih ke tipe lain dengan mengubah nilai enum.

## Langkah 4: Atur dimensi X (ukuran piksel) untuk barcode

Dimensi X mengontrol lebar bar paling sempit. Nilai piksel 2 menghasilkan gambar tajam beresolusi tinggi yang cocok untuk kebanyakan layar.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Menyesuaikan dimensi X bersifat opsional, tetapi memberi Anda kontrol detail atas kepadatan visual barcode.

## Langkah 5: Hasilkan barcode dengan rasio aspek 15 dan simpan sebagai PNG

Properti `AspectRatio` milik sub‑objek `DataBar`. Mengubah nilai ini meregangkan atau memampatkan barcode secara vertikal sambil mempertahankan data yang terenkode.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Metode `Save` menulis barcode ke jalur file yang ditentukan. Enum `BarCodeImageFormat.Png` memastikan kompresi lossless.

![contoh output generator barcode c#](generated_barcode_example.png)

*Gambar: barcode yang dihasilkan dengan rasio aspek 15.*

## Langkah 6: Ubah rasio aspek menjadi 30 dan hasilkan gambar kedua

Menggunakan kembali instance `BarcodeGenerator` yang sama menghindari alokasi objek baru. Cukup perbarui `AspectRatio` dan panggil `Save` lagi.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG yang hanya berbeda pada skala vertikal. Teknik ini berguna ketika Anda memerlukan data yang sama untuk label dengan ukuran berbeda.

## Variasi umum dan kasus tepi

### Beralih ke tipe barcode lain

Jika Anda memerlukan QR code, Code 128, atau PDF417, ganti nilai enum di konstruktor:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Semua langkah konfigurasi lainnya (dimensi X, penyimpanan) tetap sama.

### Menangani karakter yang tidak didukung

`BarcodeGenerator` memvalidasi string input terhadap simbol yang dipilih. Menyertakan karakter ilegal akan melempar `ArgumentException`. Bungkus pembuatan dalam blok try‑catch untuk memberikan pesan error yang ramah:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Mengekspor ke format gambar lain

Aspose.BarCode mendukung BMP, JPEG, TIFF, dan SVG. Ubah argumen kedua pada `Save` sesuai kebutuhan:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Output resolusi tinggi untuk pencetakan

Saat mencetak pada printer ber‑DPI tinggi, tingkatkan dimensi X dan opsional atur properti `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Pengaturan ini menghasilkan file yang lebih besar tetapi mempertahankan tepi yang tajam pada media fisik.

## Output yang diharapkan

Menjalankan program lengkap menghasilkan file berikut di dalam `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – kode DataBar dengan tinggi standar  
* `DatabarAspectRatio30.png` – versi yang diperpanjang secara vertikal  

Kedua gambar berisi data GS1 yang sama, dan Anda dapat memverifikasinya dengan aplikasi pemindai barcode apa pun.

## Kode sumber lengkap

Salin kode di bawah ini ke proyek konsol baru (`dotnet new console`) dan jalankan. Program akan mencetak pesan status ke konsol serta menulis file PNG ke disk.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Menjalankan program menghasilkan output konsol serupa dengan:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Kesimpulan

Anda kini memiliki **c# barcode generator** yang dapat membuat simbol DataBar stacked Omni‑Directional, menyesuaikan dimensi X, dan mengekspor file PNG dengan rasio aspek khusus. Pola yang sama berlaku untuk semua simbol barcode lain yang didukung Aspose.BarCode, memudahkan integrasi pembuatan barcode ke dalam solusi inventaris, pengiriman, atau point‑of‑sale.

Jika Anda ingin mengeksplorasi lebih lanjut, coba:

* Menghasilkan QR code atau simbol PDF417 (`how to generate barcode` untuk aplikasi seluler)  
* Mengekspor ke SVG untuk grafik web yang dapat diskalakan  
* Menyematkan gambar yang dihasilkan langsung ke dalam faktur PDF menggunakan Aspose.PDF  

Bereksperimenlah dengan nilai `AspectRatio`, ukuran dimensi X, dan format output yang berbeda untuk mencocokkan kebutuhan spesifik Anda.


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}