---
category: general
date: 2026-10-02
description: Buat kode batang stacked databars di C# dengan cepat. Pelajari cara mengatur
  XDimension, menyesuaikan rasio aspek, dan mengekspor gambar PNG dengan generator
  kode batang.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: id
lastmod: 2026-10-02
og_description: Buat barcode stacked databars di C# dengan contoh kode lengkap. Sesuaikan
  XDimension, ubah rasio aspek, dan simpan file PNG hanya dalam beberapa baris.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Buat barcode databars bertumpuk di C# – tutorial cepat
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Buat barcode stacked databars di C# – panduan langkah demi langkah
url: /id/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode databars bertumpuk di C# – panduan langkah demi langkah

Jika Anda perlu **membuat barcode databars bertumpuk** dalam proyek .NET, tutorial ini menunjukkan secara tepat cara melakukannya. Anda akan melihat cara mengonfigurasi X‑dimension, mengubah rasio aspek, dan menyimpan hasilnya sebagai file PNG—semua dengan pustaka Aspose.BarCode.

Membuat barcode DataBar bertumpuk tidak memerlukan pipeline grafis yang kompleks. Pada akhir panduan ini Anda akan memiliki dua gambar PNG siap pakai yang menggambarkan rasio aspek yang berbeda, dan Anda akan memahami mengapa parameter tersebut penting untuk keandalan pemindaian.

## Apa yang Anda perlukan

- .NET 6.0 atau lebih baru (kode juga berfungsi dengan .NET Framework 4.6+)
- Visual Studio 2022 atau IDE C# apa pun
- **Aspose.BarCode for .NET** paket NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Izin menulis ke folder tempat file PNG akan disimpan

## Langkah 1: Siapkan proyek dan impor namespace

Buat aplikasi konsol baru (atau tambahkan kode ke proyek yang sudah ada) dan impor namespace yang diperlukan:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Mengapa ini penting:** `Aspose.BarCode.Generation` menyediakan kelas `BarcodeGenerator`, sementara `Aspose.BarCode` berisi enumerasi `BarCodeImageFormat` yang digunakan untuk menyimpan gambar.

## Langkah 2: Inisialisasi generator untuk DataBar omnidirectional bertumpuk

Nilai `EncodeTypes.DatabarStackedOmniDirectional` memilih simbolologi DataBar bertumpuk. String data harus mengikuti format GS1 Application Identifier (AI); di sini kami menggunakan nilai GTIN‑14 dummy.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Mengapa ini penting:** Tipe encode yang dipilih memberi tahu pustaka untuk merender barcode *bertumpuk*, yang penting untuk label berdensitas tinggi di mana ruang vertikal terbatas.

## Langkah 3: Tentukan ukuran modul (X‑dimension) dalam piksel

X‑dimension mengontrol lebar bar terkecil ("modul"). Nilai 2 piksel bekerja baik untuk kebanyakan output resolusi layar.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Mengapa ini penting:** Pemindai menginterpretasikan lebar modul sebagai satuan dasar pengukuran. Nilai terlalu kecil dapat menyebabkan cetakan buram; nilai terlalu besar membuang ruang.

## Langkah 4: Simpan gambar pertama dengan rasio aspek 15

Properti `AspectRatio` memengaruhi hubungan tinggi‑lebar setiap segmen bertumpuk. Rasio aspek 15 adalah nilai default umum untuk aplikasi ritel.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Mengapa ini penting:** Rasio aspek yang lebih rendah menghasilkan barcode yang lebih datar, yang mungkin lebih mudah dipindai pada beberapa bahan label. Format PNG mempertahankan kualitas lossless untuk pengujian.

## Langkah 5: Ubah rasio aspek menjadi 30 dan simpan gambar kedua

Meningkatkan rasio aspek membuat setiap segmen bertumpuk menjadi lebih tinggi, yang dapat meningkatkan keandalan pemindaian pada latar belakang dengan kontras rendah.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Mengapa ini penting:** Retailer atau mitra logistik yang berbeda mungkin memerlukan dimensi barcode tertentu. Menyediakan kedua versi memungkinkan Anda membandingkan kinerja pemindaian dengan cepat.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke `Program.cs`. Program ini dapat dikompilasi dan dijalankan tanpa modifikasi setelah menginstal paket NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Output yang diharapkan

Menjalankan program akan membuat dua file di folder eksekusi:

| Nama file                     | Rasio aspek | Deskripsi visual |
|-------------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png`    | 15           | Barcode bertumpuk lebih pendek dan lebih datar |
| `DatabarAspectRatio30.png`    | 30           | Barcode bertumpuk lebih tinggi dan lebih memanjang |

Anda dapat membuka file PNG dengan penampil gambar apa pun untuk memverifikasi bahwa barcode terrender dengan benar.

![Contoh barcode databars bertumpuk](placeholder-image.png){alt="Contoh barcode databars bertumpuk"}

## Pertanyaan umum dan kasus tepi

| Pertanyaan | Jawaban |
|----------|--------|
| **Bisakah saya menggunakan X‑dimension yang berbeda?** | Ya. Nilai tipikal berkisar antara 1 hingga 4 piksel. Nilai yang lebih besar meningkatkan ukuran barcode tetapi dapat meningkatkan keterbacaan pada printer beresolusi rendah. |
| **Bagaimana jika saya membutuhkan simbolologi yang berbeda?** | Ganti `EncodeTypes.DatabarStackedOmniDirectional` dengan nilai `EncodeTypes` lain, seperti `DatabarStacked` (non‑omnidirectional) atau `DatabarLimited`. |
| **Bagaimana cara mengubah format output?** | Gunakan `BarCodeImageFormat.Jpeg`, `Gif`, atau `Bmp` pada pemanggilan `Save`. |
| **Apakah format GTIN‑14 wajib?** | Simbolologi DataBar mengharapkan string numerik yang diawali dengan AI yang sesuai (misalnya, `(01)` untuk GTIN‑14). Sesuaikan data sesuai dengan kasus penggunaan Anda. |
| **Bagaimana dengan pengaturan DPI?** | Generator menghormati properti `Resolution`. Untuk cetakan beresolusi tinggi, atur `barcodeGen.Parameters.ImageResolution.DpiX` dan `DpiY` sesuai kebutuhan. |

## Tips profesional

- **Batch generation:** Bungkus logika penyimpanan dalam loop dan berikan daftar GTIN untuk menghasilkan ribuan barcode secara otomatis.
- **Validation:** Gunakan `barcodeGen.Validate()` sebelum menyimpan untuk menangkap data yang tidak valid lebih awal.
- **Performance:** Menggunakan kembali instance `BarcodeGenerator` yang sama (hanya mengubah parameter) lebih cepat daripada membuat objek baru untuk setiap gambar.

## Langkah selanjutnya

Sekarang Anda dapat **membuat barcode databars bertumpuk** dengan rasio aspek khusus, pertimbangkan untuk mengeksplorasi:

- Menambahkan teks yang dapat dibaca manusia di bawah barcode (`barcodeGen.Parameters.Barcode.CodeText`).
- Mengekspor ke **PDF** untuk lembar label yang dapat dicetak (`BarCodeImageFormat.Pdf`).
- Mengintegrasikan generator ke dalam API web untuk menyajikan barcode sesuai permintaan.
- Bereksperimen dengan **kata kunci sekunder** lain seperti *C# barcode generator* dan *barcode aspect ratio* untuk menyempurnakan implementasi Anda bagi perangkat keras tertentu.

Selamat coding, dan nikmati fleksibilitas yang diberikan Aspose.BarCode untuk proyek barcode C# Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat barcode databar bertumpuk di C# – panduan langkah demi langkah](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [barcode databar bertumpuk omnidirectional di C# – Panduan Lengkap](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Cara membuat gambar PNG databar dengan C# dan Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}