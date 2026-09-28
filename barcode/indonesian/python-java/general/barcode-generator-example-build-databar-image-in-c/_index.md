---
category: general
date: 2026-07-18
description: Contoh generator barcode yang menunjukkan cara mengatur dimensi dan menghasilkan
  gambar barcode DataBar Stacked Omni‑Directional dalam C#. Pelajari tipe pengkodean
  barcode dengan cepat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: id
lastmod: 2026-07-18
og_description: Contoh generator barcode memandu Anda cara mengatur dimensi, memilih
  jenis enkode barcode, dan membuat proyek gambar barcode C# dengan kode minimal.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Contoh Generator Barcode – Pembuatan Gambar DataBar Cepat dalam C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Contoh Generator Barcode – Membuat Gambar DataBar di C#
url: /id/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contoh Generator Barcode – Membuat Gambar DataBar di C#

Pernah butuh **contoh generator barcode** yang benar‑benar mencetak barcode dunia nyata tanpa membuat Anda frustasi? Anda tidak sendirian. Kebanyakan pengembang menemui kebuntuan ketika mencoba mencari tahu **cara mengatur dimensi** untuk barcode DataBar Stacked Omni‑Directional, terutama ketika dokumentasinya tersembunyi di bawah lapisan jargon.

Dalam tutorial ini kami akan membahas program C# lengkap yang siap dijalankan yang menunjukkan **cara menghasilkan gambar databar**, memilih **tipe enkode barcode** yang tepat, dan akhirnya **membuat file gambar barcode c#** yang dapat Anda masukkan ke proyek mana pun. Tanpa basa‑basi—hanya kode yang dapat Anda salin‑tempel, plus penjelasan di balik setiap baris.

## Apa yang Anda Butuhkan

- **.NET 6** (atau versi .NET terbaru) – API yang kami gunakan menargetkan .NET Standard, sehingga juga berfungsi di .NET Framework.  
- **Aspose.BarCode for .NET** – pustaka yang menyediakan `BarcodeGenerator`. Anda dapat mengunduhnya dari NuGet dengan `Install-Package Aspose.BarCode`.  
- **IDE C#** – Visual Studio, Rider, atau VS Code sudah cukup.  
- Sebuah folder di disk tempat file PNG akan disimpan (kode membuat `DatabarAspectRatio15.png` dan `DatabarAspectRatio30.png`).

Sudah semua? Bagus—mari kita mulai.

## Contoh Generator Barcode – Menginisialisasi Generator

Hal pertama yang harus dilakukan: kita memerlukan sebuah instance `BarcodeGenerator` yang dikonfigurasi untuk simbol **DataBar Stacked Omni‑Directional**. Ini adalah **tipe enkode barcode** yang akan kita gunakan.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Mengapa ini penting:** `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu Aspose secara tepat simbol mana yang harus dirender. Jika Anda memilih tipe yang salah, pemindai tidak akan mengenali barcode, tidak peduli seindah apa gambar tersebut.

## Cara Mengatur Dimensi untuk Barcode

Keterbacaan barcode bergantung pada **X‑dimension**‑nya (lebar bar paling tipis). Dalam kebanyakan kasus nilai 2 pixel sudah cukup, tetapi Anda dapat menyesuaikannya untuk printer atau layar Anda.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tips pro:** Jika Anda pernah bertanya‑tanya **cara mengatur dimensi** untuk keluarga barcode lain, rantai properti yang sama (`Parameters.Barcode.XDimension`) berlaku—cukup ubah nilai `Pixels`.

## Cara Menghasilkan Barcode DataBar Stacked Omni‑Directional

Setelah generator siap, kita akan bermain dengan properti **aspect ratio**. Ini mengontrol hubungan tinggi‑lebar DataBar, memungkinkan Anda menghasilkan simbol pendek dan kotak atau yang tinggi dan sempit.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Apa yang terjadi?** `AspectRatio = 15` memberi tahu mesin untuk membuat bar 15 kali lebih tinggi daripada lebarnya. PNG yang dihasilkan disimpan tepat di sebelah executable Anda.

## Membuat Gambar Barcode C# – Mengubah Aspect Ratio

Mari buktikan fleksibilitas dengan mengubah rasio menjadi 30 dan menyimpan file kedua.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

Saat Anda menjalankan program, Anda akan mendapatkan dua file PNG:

| File | Rasio Aspek | Ukuran Perkiraan |
|------|--------------|-------------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Buka mereka di penampil gambar apa pun—Anda akan melihat simbol DataBar yang bersih dan dapat dipindai.

## Ikhtisar Tipe Enkode Barcode (Opsional tapi Berguna)

Jika Anda penasaran tentang **tipe enkode barcode** lain yang didukung Aspose, berikut lembar cheat cepat:

| EncodeTypes Enum | Deskripsi |
|------------------|-----------|
| `EncodeTypes.Code128` | Alfanumerik ber‑densitas tinggi |
| `EncodeTypes.QR` | Kode matriks 2‑D |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar untuk ritel |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Fokus kami** – kompak, omnidirectional |

## Kesalahan Umum & Cara Menghindarinya

- **Paket NuGet hilang** – Kode tidak akan terkompilasi tanpa `Aspose.BarCode`. Jalankan `dotnet add package Aspose.BarCode` terlebih dahulu.  
- **Path file salah** – Jika Anda menggunakan path absolut, periksa kembali backslash (`\\`) pada Windows. Path relatif (seperti yang ditunjukkan) menjaga portabilitas.  
- **Aspect ratio terlalu ekstrem** – Rasio di atas 50 dapat membuat barcode terlalu tinggi untuk pemindai umum. Tetap gunakan 15‑30 untuk kebanyakan kasus.

## Kode Sumber Lengkap (Siap Salin‑Tempel)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Jalankan program (`dotnet run` atau tekan **F5** di Visual Studio) dan Anda akan melihat pesan konsol yang mengonfirmasi file berada di disk.

![Barcode generator example output showing DataBar barcode with aspect ratio 15](placeholder/path/to/image.png){: .align-center alt="Contoh output generator barcode yang menampilkan barcode DataBar dengan aspect ratio 15"}

## Kesimpulan

Kami baru saja menyelesaikan **contoh generator barcode** yang menunjukkan **cara mengatur dimensi**, memilih **tipe enkode barcode** yang tepat, dan akhirnya **membuat file gambar barcode c#** yang dapat Anda sematkan di mana saja. Kodenya sangat kecil, konsepnya sangat jelas, dan kini Anda memiliki dasar yang kuat untuk memperluas solusi—mungkin menambahkan caption teks, memutar gambar, atau beralih ke simbol lain.

### Apa Selanjutnya?

- Bereksperimen dengan **X‑dimension berbeda** untuk melihat bagaimana toleransi pemindai berubah.  
- Coba **EncodeTypes** lain seperti `Code128` atau `QR` untuk memperluas toolkit Anda.  
- Otomatiskan pembuatan batch: loop melalui CSV ID produk dan hasilkan PNG untuk masing‑masing.

Jika Anda mengalami kendala, tinggalkan komentar di bawah atau periksa dokumentasi Aspose.BarCode—dokumentasinya penuh dengan contoh yang melengkapi apa yang kami bahas di sini.

Selamat coding, semoga barcode Anda selalu dapat dipindai pada percobaan pertama!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Barcode - Tipe Barcode Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/)
- [Membuat gambar barcode C# – Contoh GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}