---
category: general
date: 2026-07-18
description: Buat barcode PDF417 dengan cepat menggunakan C#. Pelajari cara menghasilkan
  barcode, mengatur parameter, dan menyimpan file gambar – termasuk penanganan AI 10.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: id
lastmod: 2026-07-18
og_description: Buat barcode PDF417 di C# dengan panduan lengkap. Temukan cara menghasilkan
  barcode, menyesuaikan pengaturan, dan menyimpan gambar sambil menangani AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Buat Barcode PDF417 di C# – Cepat, Fleksibel, Contoh Kode Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Buat Kode Bar PDF417 di C# – Panduan Lengkap Langkah demi Langkah
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Barcode PDF417 di C# – Panduan Lengkap Langkah‑per‑Langkah

Pernah membutuhkan untuk **create pdf417 barcode** tetapi tidak yakin library atau pengaturan mana yang harus dipilih? Anda tidak sendirian—banyak pengembang mengalami kebingungan saat pertama kali mencoba GS1‑Micro‑PDF417. Kabar baiknya, dengan beberapa baris kode C# Anda dapat membuat barcode yang terformat sempurna, menyesuaikan tampilannya, dan menyimpan gambar langsung ke disk.

Dalam tutorial ini kami akan menjelaskan **how to generate barcode** menggunakan library Aspose.BarCode, menunjukkan **how to set parameters** seperti X‑dimension dan jumlah kolom, serta mendemonstrasikan **how to save image** untuk variasi AI 10 dan AI 21. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat dimasukkan ke proyek .NET mana pun.

## Prasyarat

- .NET 6+ atau .NET Framework 4.7.2 (runtime terbaru apa pun dapat digunakan)
- Visual Studio 2022 atau editor C# favorit Anda
- Paket NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Folder yang dapat ditulisi di disk tempat file PNG akan disimpan

Itu saja—tidak ada alat tambahan, tidak ada konfigurasi yang rumit. Siap? Ayo mulai.

## Langkah 1: Buat Barcode PDF417 dengan Format GS1‑Micro

Hal pertama yang kita lakukan adalah membuat objek **create pdf417 barcode** dan memasukkan data AI awal. Dalam GS1‑Micro‑PDF417, AI 10 (nomor batch/lot) biasanya menjadi titik awal, jadi kita akan mengenkodenya segera.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Mengapa ini penting:** `EncodeTypes.GS1MicroPdf417` memberi tahu library untuk mengikuti spesifikasi GS1‑Micro, yang secara otomatis menambahkan tanda kurung AI. Jika Anda melewatkannya, Anda akan mendapatkan PDF417 generik yang mungkin tidak dapat dipindai di lingkungan ritel.

## Langkah 2: Cara Mengatur Parameter untuk Barcode

Sekarang kita memiliki instance barcode, kita perlu menyempurnakan karakteristik visualnya. Di sinilah **how to set parameters** berperan. Kita akan menyesuaikan tiga pengaturan umum:

1. **X‑dimension** – mengontrol lebar bar terkecil (dalam piksel)
2. **Column count** – memengaruhi bentuk keseluruhan; lebih sedikit kolom = barcode lebih tinggi
3. **IsLinked** – mengaktifkan modul tautan opsional yang menghubungkan barcode dengan string data

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Tip pro:** Jika Anda menargetkan pemindaian seluler, tingkatkan X‑dimension menjadi 3‑4 piksel; modul yang lebih besar lebih tahan terhadap kamera beresolusi rendah.

## Langkah 3: Cara Menyimpan Gambar – Versi Pertama (AI 10)

Dengan generator yang dikonfigurasi, kita akhirnya dapat **how to save image**. Metode `Save` menulis barcode ke file dalam format yang Anda tentukan. Di sini kami menggunakan PNG karena mempertahankan tepi yang tajam tanpa artefak kompresi.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

Pada tahap ini Anda seharusnya melihat file bernama `GS1MicroPdf417_AI10.png` di `outputDir` Anda. Buka dengan penampil gambar apa pun—Anda akan melihat PDF417 yang bersih, kontras tinggi siap untuk dicetak.

## Langkah 4: Beralih ke AI yang Berbeda (AI 21) dan Simpan Lagi

Seringkali Anda perlu mengenkode identifier aplikasi yang berbeda, seperti AI 21 (nomor seri). Mengubah properti `CodeText` saja sudah cukup. Ini menunjukkan penanganan **barcode ai 10** versus **barcode ai 21** dalam satu langkah.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **Bagaimana jika Anda membutuhkan lebih banyak AI?** Cukup gabungkan mereka dalam satu string, misalnya `"(10)ABCD(21)12345(240)XYZ"`. Library secara otomatis mem-parsing tanda kurung.

## Contoh Lengkap yang Berfungsi

Menggabungkan semuanya, berikut program mandiri yang dapat Anda salin‑tempel ke aplikasi konsol:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Output yang diharapkan:** Dua file PNG muncul di `C:\Barcodes\`—`GS1MicroPdf417_AI10.png` dan `GS1MicroPdf417_AI21.png`. Keduanya berisi PDF417 yang dapat dipindai; yang pertama mengenkode AI 10, yang kedua AI 21.

## Kesalahan Umum & Cara Menghindarinya

- **Missing folder permissions:** Jika `Save` melempar `UnauthorizedAccessException`, periksa kembali bahwa path ada dan aplikasi Anda memiliki hak menulis.
- **Incorrect AI formatting:** Lupa menambahkan tanda kurung (`(10)`) akan menyebabkan barcode diperlakukan sebagai data biasa, mengganggu validasi GS1.
- **Too small X‑dimension:** Bar yang lebih tipis dari 1 piksel dapat menghilang saat gambar diubah ukurannya. Gunakan setidaknya 2 piksel untuk tampilan layar.

## Langkah Selanjutnya & Topik Terkait

Sekarang Anda tahu **how to generate barcode**, **how to set parameters**, dan **how to save image**, Anda mungkin ingin menjelajahi:

- Menambahkan **human‑readable text** di bawah barcode (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Mengekspor ke **PDF** alih-alih PNG (`BarCodeImageFormat.Pdf`)
- Mengintegrasikan pembuatan barcode ke dalam **ASP.NET Core API** untuk pembuatan gambar secara langsung

Setiap topik tersebut dibangun langsung di atas fondasi yang kami jelaskan dalam panduan ini.

---

### Ringkasan Cepat

- **Create pdf417 barcode** menggunakan `BarcodeGenerator` dengan `EncodeTypes.GS1MicroPdf417`
- **How to set parameters** seperti X‑dimension, kolom, dan linking
- **How to save image** sebagai PNG untuk varian AI 10 dan AI 21
- Menangani **barcode ai 10** dan beralih ke **barcode ai 21** dengan satu perubahan properti

Cobalah, sesuaikan pengaturannya, dan Anda akan memiliki mesin barcode yang kuat siap untuk produksi. Ada pertanyaan atau butuh penjelasan lebih mendalam? Tinggalkan komentar di bawah—selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Membuat Zona Tenang Barcode untuk ITF-14 Menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cara Membuat barcode Aztec dengan koreksi kesalahan di .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}