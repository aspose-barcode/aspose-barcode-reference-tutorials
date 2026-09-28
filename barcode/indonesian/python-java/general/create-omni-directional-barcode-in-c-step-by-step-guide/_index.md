---
category: general
date: 2026-07-15
description: Buat barcode omnidireksional dalam C# dengan cepat menggunakan Aspose.BarCode
  – pelajari cara menghasilkan barcode C# dengan tinggi bar yang dapat disesuaikan
  dan dimensi X.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: id
lastmod: 2026-07-15
og_description: Buat barcode omni-directional di C# dengan Aspose.BarCode. Kuasai
  cara menghasilkan barcode C# dengan menyesuaikan XDimension dan BarHeight untuk
  hasil yang sempurna.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Buat kode batang omnidireksional di C# – Panduan Pemrograman Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Buat barcode omnidireksional di C# – Panduan Langkah demi Langkah
url: /id/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# buat barcode omni-directional di C# – Panduan Langkah‑per‑Langkah

Pernah bertanya-tanya bagaimana cara menghasilkan barcode C# yang mematuhi simbol GS1 DataBar Omni‑Directional? Anda tidak sendirian. Dalam tutorial ini kami akan **membuat barcode omni-directional** dari awal, menyesuaikan X‑dimension, dan bermain dengan tinggi bar—semua menggunakan pustaka Aspose.BarCode.

Kami akan menelusuri skenario dunia nyata: Anda membutuhkan barcode yang kompak dan ber‑densitas tinggi untuk label ritel, dan Anda ingin mengontrol total ukuran visualnya. Pada akhir tutorial Anda akan memiliki dua file PNG—satu dengan tinggi bar 30 px dan satu lagi dengan 60 px—siap dimasukkan ke dalam alur kerja pencetakan apa pun.

## Prerequisites

- .NET 6 (atau runtime .NET terbaru lainnya) terpasang di mesin Anda.  
- Visual Studio 2022 atau VS Code—IDE favorit Anda akan cukup.  
- Paket NuGet Aspose.BarCode untuk .NET gratis (`Aspose.BarCode`).

Tidak ada dependensi lain yang diperlukan. Jika Anda belum pernah menyentuh NuGet sebelumnya, cukup buka Package Manager Console dan jalankan:

```powershell
Install-Package Aspose.BarCode
```

## buat barcode omni-directional – Memahami Dasar-dasarnya

**GS1 DataBar Omni‑Directional** dirancang untuk pemindaian dalam orientasi apa pun, menjadikannya sempurna untuk label tepi rak. Saat Anda memanggil `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, pustaka melakukan pekerjaan berat: ia meng‑encode data, menerapkan aturan simbol, dan menyiapkan gambar raster.

> **Pro tip:** Selalu bungkus data mentah dalam format Application Identifier (AI) yang sesuai, misalnya `"(01)12345678901231"` untuk GTIN‑14. Ini memberi tahu pemindai apa yang diwakili oleh digit‑digit tersebut.

## Langkah 1 – Menyiapkan Barcode Generator (cara menghasilkan barcode c#)

Pertama kami membuat objek generator. Ini adalah fondasi **cara menghasilkan barcode c#** dengan Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Nilai enum `EncodeTypes.DatabarOmniDirectional` memberi tahu mesin simbol apa yang akan digunakan. Argumen kedua adalah string data mentah, yang sudah dibungkus dalam AI GTIN.

## Langkah 2 – Menyesuaikan X‑Dimension (barcode XDimension)

**barcode XDimension** mengontrol lebar bar terkecil. Nilai 2 px merupakan keseimbangan yang baik antara keterbacaan dan kekompakan untuk kebanyakan printer label.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Jika Anda menginginkan tampilan yang lebih halus atau lebih kasar, cukup ubah angka tersebut. Ingat: X‑dimension adalah satuan dasar; semua lebar bar lainnya adalah kelipatan nilai ini.

## Langkah 3 – Membuat Gambar Pertama dengan Tinggi Bar 30 px (barcode BarHeight)

Sekarang kami mengatur **barcode BarHeight** menjadi 30 px dan menyimpan gambar. Ini menghasilkan barcode berukuran sedang yang cocok dengan label standar.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Metode `Save` menulis file PNG ke disk. Anda dapat mengganti `BarCodeImageFormat.Jpeg` jika lebih menyukai output JPEG.

## Langkah 4 – Meningkatkan Tinggi Bar menjadi 60 px untuk Label Lebih Besar (barcode BarHeight)

Kadang‑kadang barcode yang lebih besar diperlukan—mungkin untuk label rak yang berada lebih jauh dari pemindai. Mari gandakan tinggi barnya.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Perhatikan bahwa kami **tidak** perlu membuat ulang generator; kami hanya menyesuaikan parameter dan menggunakan kembali objek yang sama. Ini menghemat memori dan menjaga kode tetap rapi.

## Langkah 5 – Menyimpan Gambar Kedua (cara menghasilkan barcode c#)

Akhirnya, kami menyimpan PNG kedua. Sekarang Anda memiliki dua file yang hanya berbeda pada tinggi bar.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Output yang Diharapkan

- `DatabarBarHeight30Pixels.png` – barcode omni‑directional setinggi 30 px.  
- `DatabarBarHeight60Pixels.png` – data yang sama, tetapi dengan barcode setinggi 60 px.

Buka file‑file tersebut di penampil gambar apa pun; Anda akan melihat bar yang tajam dan dapat dipindai yang mematuhi spesifikasi GS1 DataBar Omni‑Directional.

## Pertanyaan Umum & Kasus Tepi

### Bagaimana jika saya membutuhkan X‑dimension yang berbeda?

Cukup tetapkan nilai baru sebelum memanggil `Save`. Untuk pencetakan ultra‑high‑density Anda mungkin menurunkannya menjadi 1 px, tetapi uji dulu dengan pemindai Anda—beberapa perangkat kesulitan dengan bar di bawah 2 px.

### Bisakah saya menambahkan teks yang dapat dibaca manusia di bawah barcode?

Ya. Atur `barcodeGenerator.Parameters.Barcode.CodeText` ke string yang diinginkan dan, bila perlu, sesuaikan `barcodeGenerator.Parameters.Barcode.CodeLocation` menjadi `BarCodeTextLocation.Below`. Ini berguna di lingkungan ritel di mana GTIN numerik harus terlihat.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Apakah PNG format terbaik untuk pencetakan?

PNG bersifat lossless, sehingga mempertahankan tepi tajam yang diperlukan pemindai barcode. Jika sistem hilir Anda mengharapkan format lain (TIFF, BMP), cukup ubah enum `BarCodeImageFormat`.

## Contoh Lengkap yang Berfungsi (buat barcode omni-directional)

Berikut adalah program lengkap yang siap dijalankan. Salin‑tempel ke proyek konsol baru dan tekan **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Jalankan program, periksa folder output, dan Anda akan melihat dua file PNG persis seperti yang dijelaskan.

## Ringkasan

Kami telah menunjukkan **cara menghasilkan barcode C#** yang membuat **buat barcode omni-directional** menggunakan Aspose.BarCode. Dengan menyesuaikan **barcode XDimension** dan **barcode BarHeight**, Anda memperoleh kontrol halus atas ukuran visual tanpa mengorbankan keandalan pemindaian.

## Apa Selanjutnya?

- Bereksperimen dengan pengaturan **GS1 DataBar Omni-Directional** lainnya seperti `Color` atau `Margin`.  
- Gabungkan beberapa barcode pada satu kanvas menggunakan `Graphics` untuk desain label yang kompleks.  
- Integrasikan generator ke dalam web API sehingga platform e‑commerce Anda dapat menghasilkan barcode sesuai permintaan.

Ada ide unik yang ingin Anda bagikan? Tinggalkan komentar, dan mari teruskan diskusi. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑per‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menghasilkan Barcode – Konfigurasi Code 39 dengan Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Cara Membuat Zona Tenang Barcode untuk ITF-14 Menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cara membuat zona tenang barcode untuk Code 16K menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}