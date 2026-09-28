---
category: general
date: 2026-07-18
description: Pelajari cara menghasilkan gambar barcode dengan generator barcode .net
  dan dengan mudah mengubah tinggi barcode untuk simbol GS1‑Databar Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: id
lastmod: 2026-07-18
og_description: .net barcode generator memungkinkan Anda dengan cepat membuat gambar
  barcode. Panduan ini menunjukkan cara menghasilkan barcode, menyesuaikan tinggi
  bar, dan menyimpan file PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Ubah tinggi barcode dengan generator barcode .net
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: Generator barcode .net – ubah tinggi barcode
url: /id/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – mengubah tinggi barcode

Pernah bertanya-tanya **bagaimana cara menghasilkan barcode** gambar tanpa harus mengelola banyak alat pihak ketiga? Di dunia .NET ada cara yang cukup bersih untuk melakukannya, dan komponen kuncinya adalah **.net barcode generator**. Dengan hanya beberapa baris C# Anda dapat membuat simbol GS1‑Databar Omni‑Directional, menyesuaikan tinggi bar, dan menyimpan hasilnya ke file PNG.

Jika Anda sedang membangun sistem inventaris, printer label pengiriman, atau aplikasi apa pun yang membutuhkan kode yang dapat dipindai, tutorial ini akan membawa Anda dari nol hingga barcode yang berfungsi dalam hitungan menit. Kami akan menelusuri kode lengkap, menjelaskan mengapa setiap pengaturan penting, dan menunjukkan cara **mengubah tinggi barcode** tanpa melanggar spesifikasi.

## Apa yang Anda butuhkan

- .NET 6.0 atau lebih baru (API berfungsi sama pada .NET Framework 4.7+)
- Referensi ke perpustakaan barcode (misalnya, Aspose.BarCode for .NET – kelas yang sama digunakan oleh banyak paket komersial)
- Lingkungan pengembangan (Visual Studio, Rider, atau VS Code dengan ekstensi C#)
- Folder di mana Anda memiliki izin menulis – tutorial akan menyimpan file PNG di sana

Itu saja. Tidak ada paket NuGet tambahan selain perpustakaan barcode itu sendiri.

## Menggunakan .net barcode generator untuk mengubah tinggi barcode

Berikut ini adalah **program konsol lengkap yang dapat dijalankan**. Tempelkan ke dalam proyek C# baru, sesuaikan folder output, dan tekan F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Mengapa setiap baris penting

| Baris | Alasan |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Membuat instance **.net barcode generator** dengan simbol dan data payload yang diinginkan. Enum `EncodeTypes.DatabarOmniDirectional` memberi tahu perpustakaan untuk menggunakan format GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | X‑dimension adalah lebar bar paling tipis. Menetapkannya ke *2 pixel* menghasilkan gambar tajam pada kebanyakan monitor sambil menjaga ukuran file tetap kecil. |
| `BarHeight.Pixels = 30;` | Ini adalah langkah **mengubah tinggi barcode** yang menentukan seberapa tinggi setiap bar. Tinggi 30 pixel adalah nilai default yang baik untuk label kecil. |
| `generator.Save(...);` | Menyimpan barcode ke file PNG. PNG bersifat loss‑less, yang berarti pemindai melihat pola persis yang Anda hasilkan. |
| `BarHeight.Pixels = 60;` | Di sini kami **mengubah tinggi barcode** lagi—kali ini menjadi 60 pixel. Perpustakaan secara otomatis merender ulang simbol dengan dimensi baru ketika Anda memanggil `Save` untuk kedua kalinya. |
| `Console.WriteLine(...);` | Memberikan umpan balik cepat bahwa proses selesai tanpa melempar pengecualian. |

> **Tips pro:** Jika Anda membutuhkan output resolusi lebih tinggi untuk pencetakan, ubah `BarCodeImageFormat.Png` menjadi `BarCodeImageFormat.Tiff` dan tingkatkan properti `Resolution` (mis., `generator.Parameters.ImageResolution = 300;`). Tinggi bar tetap dipertahankan, hanya dirender pada DPI yang lebih halus.

## Cara menghasilkan gambar barcode dengan pengaturan berbeda

Potongan kode di atas mencakup dasar-dasarnya, tetapi skenario dunia nyata sering memerlukan penyesuaian tambahan:

### Menyesuaikan X‑dimension untuk cetakan lebih besar
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Meningkatkan X‑dimension membuat seluruh barcode menjadi lebih besar tanpa mengubah data yang dikodekan. Ini berguna saat Anda mencetak pada label besar.

### Mengganti format output
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG dapat diskalakan tak terbatas, yang sempurna untuk pemindai berbasis web yang membutuhkan vektor tajam.

### Menambahkan teks yang dapat dibaca manusia
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Mengaktifkan `CodeTextVisible` menambahkan data mentah di bawah barcode, berguna untuk verifikasi selama pengujian.

## Kesalahan umum saat Anda **mengubah tinggi barcode**

1. **Tinggi terlalu kecil** – Beberapa pemindai memerlukan tinggi bar minimum (seringkali 10 mm dalam satuan fisik). Jika Anda menetapkan `BarHeight.Pixels` terlalu rendah, gambar yang dihasilkan mungkin tidak dapat dibaca pada pemindai sebenarnya. Selalu uji dengan perangkat keras target Anda.
2. **X‑dimension dan tinggi tidak cocok** – Tinggi bar yang sangat besar dipasangkan dengan X‑dimension yang kecil dapat terlihat terdistorsi dan dapat menyebabkan kesalahan decoding. Usahakan rasio seimbang (sekitar 3:1 hingga 5:1) kecuali spesifikasi menyatakan lain.
3. **Lupa mereset parameter** – Generator menyimpan keadaan antar penyimpanan. Jika Anda mengubah `BarHeight` untuk satu gambar dan kemudian menggunakan kembali instance yang sama untuk barcode lain, tinggi sebelumnya akan tetap ada. Reset properti tersebut atau buat instance baru `BarcodeGenerator` untuk setiap barcode yang berbeda.

## Contoh lengkap end‑to‑end (termasuk instalasi NuGet)

Jika Anda memulai dari awal, ikuti langkah-langkah berikut untuk menjalankan proyek:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Ganti `Program.cs` yang dihasilkan otomatis dengan blok kode yang ditampilkan sebelumnya, **ingat untuk mengganti `YOUR_DIRECTORY`** dengan sesuatu seperti `Path.Combine(Environment.CurrentDirectory, "output")`. Kemudian:

```bash
dotnet run
```

Anda seharusnya melihat dua file PNG di folder `output`:

- `DatabarBarHeight30Pixels.png` – barcode tinggi 30 pixel yang kompak.
- `DatabarBarHeight60Pixels.png` – versi tinggi 60 pixel yang lebih tinggi.

Kedua gambar akan terlihat serupa, tetapi yang kedua akan memiliki bar yang secara jelas lebih panjang, memudahkan pemindai beresolusi rendah untuk membaca.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator output menunjukkan tinggi bar yang berbeda"}

## Ringkasan & langkah selanjutnya

Kami telah membahas cara **menghasilkan barcode** gambar menggunakan **.net barcode generator**, menyesuaikan properti **mengubah tinggi barcode**, dan menyimpan hasilnya dalam format PNG. Poin pentingnya adalah:

- Membuat instance generator dengan `EncodeTypes` yang tepat.
- Mengontrol ukuran visual melalui `XDimension` dan `BarHeight`.
- Memanggil `Save` setelah setiap perubahan untuk menyimpan gambar baru.
- Menyesuaikan resolusi, format,

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara membuat dotcode dengan teks kode ekstended menggunakan Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}