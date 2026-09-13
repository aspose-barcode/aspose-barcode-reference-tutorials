---
category: general
date: 2026-09-13
description: Pelajari cara menghasilkan barcode di C#, menyesuaikan ukuran barcode,
  dan menyimpan gambar barcode sebagai PNG menggunakan Aspose.BarCode. Panduan lengkap
  langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: id
lastmod: 2026-09-13
og_description: Cara menghasilkan barcode di C# dengan ukuran barcode khusus dan menyimpan
  gambar barcode sebagai PNG. Ikuti panduan lengkap ini untuk Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Cara menghasilkan barcode, mengatur ukuran khusus, dan menyimpan gambar
  di C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Cara membuat barcode dengan ukuran khusus dan menyimpan gambar di C#
url: /id/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan set barcode ukuran khusus dan menyimpan gambar di C#

Jika Anda perlu **cara menghasilkan barcode** dalam aplikasi .NET, tutorial ini menunjukkan solusi lengkap. Anda akan melihat cara menyesuaikan **ukuran barcode khusus** dan **menyimpan gambar barcode** dengan hanya beberapa baris kode C#.

Membuat barcode adalah kebutuhan umum untuk sistem inventaris, label pengiriman, dan aplikasi point‑of‑sale. Pada akhir panduan ini Anda akan memiliki program yang dapat dijalankan yang membuat dua barcode DataBar‑Stacked‑Omnidirectional, masing‑masing dengan rasio aspek yang berbeda, dan menuliskannya ke file PNG di disk.

**Prerequisites**

- .NET 6.0 atau lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
- Visual Studio 2022 atau IDE C# apa pun
- Aspose.BarCode untuk .NET (versi percobaan gratis atau paket NuGet berlisensi)

---

## Cara menghasilkan barcode dengan Aspose.BarCode

Pustaka Aspose.BarCode mengabstraksi detail tingkat rendah dari standar barcode, memungkinkan Anda fokus pada data yang ingin Anda enkode dan tampilan visual yang Anda butuhkan.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Mengapa setiap baris penting

| Step | Explanation |
|------|-------------|
| **1️⃣ Create a generator** | Enum `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu Aspose simbol barcode mana yang akan digunakan. String `"(01)12345678901231"` mengikuti format data GS1‑128, di mana `(01)` adalah Application Identifier untuk GTIN. |
| **2️⃣ Set X‑dimension** | `XDimension.Pixels` menentukan lebar satu modul barcode (garis terkecil). Mengubah nilai ini adalah cara utama untuk mencapai **ukuran barcode khusus** tanpa mengubah data yang dienkode. |
| **3️⃣ Set aspect ratio & save** | `DataBar.AspectRatio` mengontrol rasio tinggi‑lebar simbol DataBar. Rasio aspek 15 menghasilkan barcode yang relatif pendek dan lebar, sementara 30 membuatnya lebih tinggi. `Save` menulis representasi visual ke file PNG, memenuhi kebutuhan **menyimpan gambar barcode**. |
| **4️⃣ Change aspect ratio & save again** | Menggunakan kembali instance generator yang sama memungkinkan Anda menghasilkan beberapa gambar dengan karakteristik visual berbeda sambil mempertahankan data tetap. |

---

## Menyesuaikan ukuran barcode khusus di luar X‑dimension

Meskipun `XDimension.Pixels` mengatur lebar modul, Anda juga dapat menyesuaikan dimensi keseluruhan barcode dengan menggabungkan dua properti:

1. **`BarHeight`** – tinggi eksplisit dalam piksel.  
2. **`BarWidth`** – lebar eksplisit dalam piksel (menimpa X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** Saat mencetak barcode, selalu uji gambar yang dihasilkan pada ukuran cetak akhir. Lebar modul 2 px cocok untuk tampilan di layar, tetapi label yang dicetak sering memerlukan setidaknya 4 px agar tetap dapat dipindai.

---

## Memilih format gambar yang tepat untuk menyimpan gambar barcode

Aspose.BarCode mendukung PNG, JPEG, BMP, GIF, dan TIFF. PNG bersifat lossless dan mempertahankan tepi yang tajam, menjadikannya pilihan paling aman untuk kebanyakan aplikasi. Jika Anda membutuhkan file yang lebih kecil untuk penggunaan web, JPEG dengan pengaturan kualitas 90 bekerja dengan baik, namun perhatikan bahwa artefak kompresi dapat memengaruhi keandalan pemindaian.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Contoh lengkap yang dapat dijalankan

Berikut adalah aplikasi konsol mandiri yang dapat Anda salin, tempel, dan jalankan. Ini mendemonstrasikan **cara menghasilkan barcode**, memodifikasi **ukuran barcode khusus**, dan **menyimpan gambar barcode** dalam dua format berbeda.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Output yang diharapkan di konsol**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Empat file gambar akan muncul di program


## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah‑per‑Langkah](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cara Menghasilkan Barcode PDF417 dengan Aspose – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}