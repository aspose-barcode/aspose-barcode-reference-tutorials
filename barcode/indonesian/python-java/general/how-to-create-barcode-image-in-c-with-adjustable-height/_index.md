---
category: general
date: 2026-09-07
description: Pelajari cara membuat gambar barcode di C# dan sesuaikan tinggi, lebar,
  serta formatnya untuk menghasilkan file PNG barcode dengan cepat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: id
lastmod: 2026-09-07
og_description: Buat gambar barcode di C# dan pelajari cara mengatur dimensi barcode,
  mengubah tinggi barcode, serta menghasilkan file PNG barcode untuk aplikasi apa
  pun.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Buat gambar barcode di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Cara membuat gambar barcode di C# dengan tinggi yang dapat disesuaikan
url: /id/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode di C# dengan tinggi yang dapat disesuaikan

Jika Anda perlu membuat gambar barcode di C# untuk sistem point‑of‑sale atau pelacak inventaris, panduan ini menunjukkan alur kerja lengkap. Anda akan melihat cara mengatur parameter barcode, mengubah tinggi barcode, dan menghasilkan file PNG barcode yang memenuhi persyaratan visual.

Membuat gambar barcode adalah tugas umum saat mengintegrasikan perangkat pemindai, mencetak label, atau membangun dasbor pelaporan. Pada akhir tutorial ini Anda akan memiliki potongan kode yang dapat digunakan kembali yang memungkinkan Anda menyesuaikan X‑dimension, tinggi, dan format output barcode tanpa meninggalkan IDE Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 (atau lebih baru) terinstal – kode dapat dikompilasi dengan SDK .NET terbaru apa pun.
* Referensi ke pustaka **Aspose.BarCode** (tersedia melalui NuGet `Aspose.BarCode`).
* Familiaritas dasar dengan aplikasi konsol C#.

Persyaratan ini memastikan contoh dapat dijalankan langsung di Windows, Linux, atau macOS.

## Langkah 1: Siapkan proyek dan impor pustaka

Buat proyek konsol baru dan tambahkan paket barcode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Sekarang buka *Program.cs* dan tambahkan direktif `using` yang diperlukan:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Impor ini memberi Anda akses ke `BarcodeGenerator`, `EncodeTypes`, dan enum format‑gambar yang diperlukan untuk **membuat file gambar barcode**.

## Langkah 2: Inisialisasi generator dengan simbolologi yang diinginkan

Baris kode pertama membuat `BarcodeGenerator` yang mengetahui tipe barcode apa yang akan dienkode. Pada contoh ini kami menggunakan simbolologi DataBar Omni‑Directional, tetapi Anda dapat mengganti `EncodeTypes.DatabarOmniDirectional` dengan tipe lain yang didukung oleh Aspose.BarCode.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

String `"(01)12345678901231"` mengikuti format GS1 Application Identifier, yang banyak retailer butuhkan. Menginisialisasi generator adalah fondasi untuk setiap operasi **cara mengatur barcode** yang akan datang.

## Langkah 3: Cara mengatur dimensi barcode – X‑dimension dan tinggi

### 3.1 Sesuaikan lebar bar tipis (X‑dimension)

X‑dimension mengontrol ketebalan bar paling tipis. Nilai **2 pixel** menghasilkan tampilan yang lebih halus, berguna ketika Anda memerlukan label yang kompak.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Ubah tinggi barcode untuk keseimbangan visual

Tinggi bar menentukan seberapa tinggi barcode tampil. Di bawah ini kami menampilkan dua tinggi umum—30 pixel untuk label kecil dan 60 pixel untuk tampilan yang lebih besar. Ini memperlihatkan **cara menyesuaikan tinggi barcode** secara programatik.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Langkah 4: Hasilkan file PNG barcode dengan tinggi yang berbeda

### 4.1 Simpan gambar pertama (tinggi 30 px)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Tingkatkan tinggi dan simpan gambar kedua

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Kedua pemanggilan `Save` ini memperlihatkan **menghasilkan file PNG barcode** dengan dimensi yang berbeda sambil menggunakan instance generator yang sama. Format gambar secara eksplisit diatur ke PNG, yang mempertahankan kualitas lossless—ideal untuk pencetakan atau tampilan di layar.

## Langkah 5: Contoh lengkap yang dapat dijalankan

Menggabungkan semua menjadi satu metode `Main` yang dapat Anda salin ke proyek konsol C# mana pun:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

Menjalankan program ini menghasilkan dua file PNG di folder output proyek:

* `DatabarBarHeight30Pixels.png` – barcode kompak 30 px.
* `DatabarBarHeight60Pixels.png` – barcode lebih besar 60 px.

Kedua file tersebut berisi **gambar barcode yang dibuat** yang dapat disematkan dalam HTML, dicetak pada label, atau dikirim ke aplikasi seluler untuk dipindai.

## Pertanyaan umum dan penanganan kasus tepi

| Pertanyaan | Jawaban |
|----------|--------|
| **Bagaimana jika saya memerlukan format gambar yang berbeda?** | Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`, `Bmp`, atau `Gif`. Pustaka secara otomatis menangani konversinya. |
| **Bisakah saya mengubah warna latar depan/latar belakang?** | Ya. Gunakan `generator.Parameters.Barcode.ForeColor` dan `BackColor` untuk mengatur nilai `System.Drawing.Color` sebelum memanggil `Save`. |
| **Bagaimana cara menghasilkan barcode tanpa menyimpannya ke file?** | Panggil `generator.GenerateBarCodeImage()` untuk memperoleh objek `System.Drawing.Image`, lalu alirkan langsung ke respons atau basis data. |
| **Bagaimana jika string data melebihi batas simbolologi?** | Generator akan melempar `ArgumentException`. Validasi panjang input atau potong sesuai spesifikasi simbolologi. |
| **Apakah ada cara untuk memproses batch banyak barcode?** | Bungkus langkah‑langkah tersebut dalam loop `foreach` yang memperbarui `generator.CodeText` dan `BarHeight` untuk setiap item, lalu panggil `Save` dengan nama file unik. |

Menangani skenario ini membuat tutorial **cara menyesuaikan barcode** menjadi lebih kuat untuk proyek dunia nyata.

## Tips profesional untuk menghasilkan barcode yang andal

* **Cache generator** ketika Anda membuat banyak barcode dengan tipe yang sama; penggunaan kembali objek mengurangi beban alokasi.
* **Atur `Resolution`** (`generator.Parameters.ImageResolution.Dpi`) jika Anda memerlukan PNG beresolusi tinggi untuk pencetakan.
* **Validasi data GS1** sebelum menetapkannya ke `CodeText` untuk menghindari kesalahan enkoding yang dapat menyebabkan kegagalan pemindaian.
* **Uji pada pemindai sebenarnya** setelah mengubah tinggi atau X‑dimension—beberapa perangkat lama memiliki persyaratan ukuran minimum.

## Kesimpulan

Anda kini tahu cara **membuat gambar barcode** di C#, **cara mengatur dimensi barcode**, **cara menyesuaikan tinggi barcode**, dan **menghasilkan file PNG barcode** untuk setiap kebutuhan visual. Dengan menyesuaikan `XDimension` dan `BarHeight` Anda dapat menghasilkan barcode yang kompak atau besar tanpa mengubah data dasarnya.

Selanjutnya, jelajahi topik terkait seperti **mengubah tinggi barcode** secara dinamis berdasarkan input pengguna, menyematkan barcode dalam laporan PDF menggunakan Aspose.PDF, atau beralih ke pembuatan QR‑code dengan `EncodeTypes.QR`. Bereksperimenlah dengan simbolologi dan format output yang berbeda untuk menguasai pembuatan barcode di C#.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}