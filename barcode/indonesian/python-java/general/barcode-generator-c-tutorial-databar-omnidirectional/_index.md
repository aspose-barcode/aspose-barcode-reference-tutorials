---
category: general
date: 2026-11-14
description: Tutorial generator barcode C# yang menunjukkan cara membuat barcode DataBar
  Omnidirectional, mengatur dimensi X, dan menyesuaikan tinggi bar dalam piksel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: id
lastmod: 2026-11-14
og_description: Tutorial generator barcode C# menjelaskan langkah demi langkah cara
  menghasilkan barcode DataBar Omnidirectional, menentukan XDimension dalam piksel,
  dan mengubah tinggi bar untuk output PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Tutorial generator barcode C# – buat barcode DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Tutorial generator barcode C#: DataBar Omnidirectional'
url: /id/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial generator barcode C# – buat barcode DataBar Omnidirectional

Jika Anda mencari **tutorial generator barcode C#**, Anda berada di tempat yang tepat. Panduan ini memandu Anda membuat barcode DataBar Omnidirectional, mengonfigurasi XDimension dalam piksel, dan menyesuaikan tinggi bar untuk menghasilkan gambar PNG.

Anda akan melihat contoh lengkap yang dapat dijalankan yang mencakup semua hal mulai dari menginisialisasi generator hingga menyimpan beberapa gambar dengan tinggi bar yang berbeda. Tidak diperlukan dokumentasi eksternal—cukup salin kode, jalankan, dan Anda akan memiliki dua file barcode siap pakai.

## Prasyarat

* .NET 6.0 atau yang lebih baru terinstal  
* Referensi ke perpustakaan barcode yang menyediakan `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat` (misalnya, Aspose.BarCode untuk .NET)  
* Pemahaman dasar tentang sintaks C# dan Visual Studio atau IDE pilihan Anda  

> **Tip pro:** Jika Anda menggunakan Aspose.BarCode, tambahkan paket NuGet `Aspose.BarCode` ke proyek Anda.

## Tutorial generator barcode C# – langkah 1: buat generator

Langkah pertama adalah menginstansiasi `BarcodeGenerator` dengan tipe encode `DatabarOmniDirectional` dan data yang ingin Anda enkode.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Mengapa ini penting:* `EncodeTypes.DatabarOmniDirectional` memberi tahu perpustakaan untuk menghasilkan barcode yang dapat dibaca dari arah mana pun, yang ideal untuk kemasan ritel dan logistik.

## Atur piksel XDimension untuk barcode

X‑dimension menentukan lebar modul terkecil ("pixel") dalam barcode. Mengaturnya dalam piksel memberi Anda kontrol presisi atas kepadatan visual barcode.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Penjelasan:* Nilai `2` piksel menghasilkan barcode yang cukup tajam untuk kebanyakan pemindai sekaligus menjaga ukuran file gambar tetap kecil.

## Sesuaikan tinggi bar dan simpan gambar

Tinggi bar menentukan seberapa tinggi bar muncul. Anda dapat menghasilkan beberapa gambar dengan tinggi yang berbeda dengan mengubah properti `BarHeight.Pixels` dan memanggil `Save` lagi.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

`BarCodeImageFormat.Png` memastikan output berupa file PNG loss‑less, yang merupakan format yang direkomendasikan untuk grafik barcode karena mempertahankan dimensi yang tepat.

## Ubah tinggi bar untuk membuat beberapa gambar

Anda sering membutuhkan barcode yang sama dengan ukuran berbeda—misalnya, satu untuk label kecil dan satu lagi untuk poster besar. Ubah tinggi bar dan gunakan kembali instance generator yang sama:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Kasus tepi:* Jika tinggi bar diatur terlalu rendah (mis., di bawah 10 px), beberapa pemindai mungkin kesulitan membaca kode. Selalu uji gambar yang dihasilkan dengan perangkat pemindai target Anda.

## Kode sumber lengkap

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke proyek konsol baru. Program ini mencakup semua direktif `using` yang diperlukan dan menunjukkan variasi tinggi bar.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Jalankan program, ganti `YOUR_DIRECTORY` dengan jalur folder yang valid, dan Anda akan menemukan dua file PNG:

* `DatabarBarHeight30Pixels.png` – bar setinggi 30 px  
* `DatabarBarHeight60Pixels.png` – bar setinggi 60 px  

![output tutorial generator barcode C#](images/databar-example.png "Tutorial generator barcode C# menunjukkan dua gambar DataBar")

## Pertanyaan umum

| Question | Answer |
|----------|--------|
| **Apakah saya dapat mengubah format gambar?** | Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` sesuai kebutuhan. PNG lebih disukai untuk kualitas lossless. |
| **Bagaimana jika saya membutuhkan XDimension yang berbeda?** | Sesuaikan `generator.Parameters.Barcode.XDimension.Pixels` ke nilai integer apa pun. Nilai yang lebih besar meningkatkan lebar keseluruhan barcode. |
| **Apakah DataBar Omnidirectional cocok untuk pemindaian mobile?** | Ya, asalkan ukuran cetak memenuhi ukuran modul minimum pemindai (biasanya 0.33 mm). XDimension berbasis piksel membantu Anda memenuhi persyaratan tersebut. |
| **Bagaimana cara menyisipkan barcode ke dalam PDF?** | Setelah menyimpan PNG, gunakan perpustakaan PDF (mis., iTextSharp) untuk menyisipkan gambar ke halaman PDF. |

## Kesimpulan

Tutorial **generator barcode C#** ini menunjukkan cara membuat barcode DataBar Omnidirectional, mengatur XDimension dalam piksel, dan menghasilkan file PNG dengan tinggi bar yang berbeda. Anda kini memiliki potongan kode yang dapat digunakan kembali dan dapat disesuaikan untuk proyek C# apa pun yang memerlukan pembuatan barcode.

### Apa selanjutnya?

* Jelajahi `EncodeTypes` lain seperti `Code128` atau `QR` untuk memperluas repertoar barcode Anda.  
* Gabungkan PNG yang dihasilkan dengan perpustakaan pembuatan PDF untuk menghasilkan faktur yang dapat dicetak.  
* Eksperimen dengan `generator.Parameters.Barcode.Color` untuk menambahkan warna khusus sambil tetap sesuai dengan spesifikasi pemindai.

Silakan memodifikasi contoh, mencoba tinggi bar tambahan, atau mengubah format output. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara mengatur lebar dan menyesuaikan tinggi untuk barcode GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Cara mengatur tinggi barcode, menghasilkan barcode DataBar dalam C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [Cara membuat barcode Databar omnidirectional dalam C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}