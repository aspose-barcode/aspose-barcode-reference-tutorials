---
category: general
date: 2026-09-10
description: Cara mengatur barcode di C# menggunakan Generator Barcode. Sesuaikan
  lebar modul barcode, hasilkan gambar barcode, dan pelajari cara menyimpan file barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: id
lastmod: 2026-09-10
og_description: Cara mengatur barcode di C# dengan Generator Barcode. Pelajari cara
  menyesuaikan lebar modul, menghasilkan barcode, dan menyimpan gambar barcode secara
  efisien.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Cara mengatur properti barcode menggunakan Generator Barcode C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Cara mengatur properti barcode dengan Generator Barcode C#
url: /id/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur properti barcode dengan C# Barcode Generator

Mengatur properti barcode sangat penting ketika Anda memerlukan kontrol yang tepat atas gaya visual barcode. Panduan ini menunjukkan cara menghasilkan barcode Planet, menyesuaikan lebar modul barcode, dan menyimpan gambar barcode menggunakan C# Barcode Generator.

Anda akan melihat contoh lengkap yang dapat dijalankan yang mencakup setiap langkah mulai dari membuat objek barcode hingga menulis file PNG ke disk. Tidak diperlukan dokumentasi eksternal—hanya kode di bawah ini dan pustaka Aspose.BarCode (atau SDK barcode kompatibel lainnya). Pada akhir tutorial Anda dapat menjawab pertanyaan seperti “bagaimana cara menghasilkan barcode dengan dimensi khusus?” dan “bagaimana cara menyimpan barcode dalam format berbeda?”.

## Prasyarat

* .NET 6.0 atau yang lebih baru terinstal  
* Visual Studio 2022 (atau IDE C# apa pun)  
* Paket NuGet **Aspose.BarCode** (atau perpustakaan lain yang menyediakan `BarcodeGenerator`)  

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Cara mengatur lebar modul barcode

*Lebar modul* (juga disebut X‑dimension) menentukan ukuran piksel setiap bar tipis dalam barcode. Menetapkan nilai ini memungkinkan Anda mengontrol ukuran keseluruhan dan keterbacaan gambar.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Mengapa ini penting*: X‑dimension yang lebih besar menghasilkan barcode yang lebih besar sehingga lebih mudah dibaca pemindai dari jarak jauh, sementara nilai yang lebih kecil mengurangi ukuran file untuk rendering di layar.

## Menghasilkan barcode dengan bar terisi

Gaya default untuk barcode Planet menggunakan **filled bars** (bar hitam padat). Kode berikut membuat gambar dan menyimpannya sebagai PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Hasil**: `PostalPlanetFilledBars.png` berisi barcode Planet standar di mana setiap bar terisi.

## Membuat barcode bar kosong

Terkadang Anda memerlukan barcode yang hanya menampilkan garis luar bar (bar kosong). Untuk mencapainya, Anda menduplikasi generator, mempertahankan lebar modul yang sama, dan mematikan flag `FilledBars`.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Hasil**: `PostalPlanetEmptyBars.png` menampilkan data yang sama tetapi dengan bar tidak terisi, berguna untuk dokumen yang banyak desain di mana Anda ingin barcode menyatu dengan latar belakang.

## Cara menyimpan barcode dalam format berbeda

Metode `Save` menerima format apa pun yang didukung oleh SDK, seperti **Jpeg**, **Bmp**, **Gif**, atau **Svg**. Mengubah format hanya memerlukan pertukaran nilai enum `BarCodeImageFormat`.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Tip*: Gunakan SVG ketika Anda memerlukan grafik vektor yang dapat diskalakan tanpa pikselasi, terutama untuk PDF siap cetak.

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua bagian memberikan Anda program mandiri yang dapat Anda tempel ke dalam aplikasi konsol.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Output yang diharapkan**

| Nama file                     | Deskripsi                              |
|-------------------------------|------------------------------------------|
| `PostalPlanetFilledBars.png`  | Barcode Planet dengan bar hitam padat     |
| `PostalPlanetEmptyBars.png`   | Data yang sama, bar ditampilkan sebagai garis luar     |
| `PostalPlanet.svg`            | Versi vektor untuk skala tanpa kehilangan kualitas  |

Jalankan program, buka file yang dihasilkan, dan verifikasi bahwa barcode cocok dengan string numerik “123456”.

## Variasi umum dan kasus tepi

| Situasi                               | Penyesuaian                                                                 |
|----------------------------------------|-----------------------------------------------------------------------------|
| Membutuhkan barcode yang lebih tebal   | Tingkatkan `XDimension.Pixels` (mis., `8`)                                   |
| Menginginkan ukuran file lebih kecil   | Gunakan `BarCodeImageFormat.Jpeg` atau turunkan X‑dimension                    |
| Menghasilkan simbolologi lain          | Ganti `EncodeTypes.Planet` dengan `EncodeTypes.Code128`, `QR`, dll.       |
| Mencetak pada printer resolusi tinggi  | Simpan sebagai `BarCodeImageFormat.Tiff` untuk output raster tanpa kehilangan |
| Menjalankan pada server tanpa antarmuka| Tidak diperlukan kode UI; generator berfungsi di konteks konsol atau layanan  |

**Pro tip**: Selalu validasi barcode yang dihasilkan dengan pemindai atau alat verifikasi sebelum menerapkannya ke produksi. Lebar modul atau format yang tidak tepat dapat menyebabkan kegagalan pemindaian.

## Kesimpulan

Anda sekarang tahu cara mengatur properti barcode menggunakan C# Barcode Generator, cara mengontrol lebar modul barcode, cara menghasilkan gaya bar terisi dan kosong, serta cara menyimpan barcode dalam format PNG atau SVG. Langkah-langkah ini memberi Anda dasar yang kuat untuk menambahkan pembuatan barcode ke aplikasi .NET apa pun.

Selanjutnya, jelajahi topik terkait seperti **c# barcode generator performance tuning**, **embedding barcodes in PDF documents**, dan **creating QR codes with custom colors**. Bereksperimenlah dengan `EncodeTypes` dan format gambar yang berbeda untuk menemukan yang paling cocok untuk proyek Anda.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menyimpan Barcode di C# – Menghasilkan Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Tutorial Barcode Generator: Cara Menghasilkan Barcode PDF417 di C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Cara Mengatur Tingkat Kesalahan pada Barcode PDF417 – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}