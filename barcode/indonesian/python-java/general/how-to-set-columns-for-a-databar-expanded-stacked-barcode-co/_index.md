---
category: general
date: 2026-08-06
description: Cara mengatur kolom untuk barcode Databar Expanded Stacked dan mempelajari
  cara menghasilkan gambar barcode, mengatur baris, serta menyimpan file barcode dalam
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set columns
- how to generate barcode
- how to set rows
- barcode save file
language: id
lastmod: 2026-08-06
og_description: Cara mengatur kolom untuk barcode Databar Expanded Stacked dan dengan
  cepat mempelajari cara menghasilkan gambar barcode, mengatur baris, serta menyimpan
  file barcode dengan Aspose.Barcode.
og_image_alt: Screenshot showing how to set columns for a Databar Expanded Stacked
  barcode in C#
og_title: Cara mengatur kolom untuk barcode Databar Expanded Stacked – panduan langkah
  demi langkah C#
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set columns for a Databar Expanded Stacked barcode and learn
    how to generate barcode images, set rows, and save the barcode file in C#.
  headline: How to set columns for a Databar Expanded Stacked barcode – complete C#
    guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Cara mengatur kolom untuk barcode Databar Expanded Stacked – panduan lengkap
  C#
url: /id/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur kolom untuk Databar Expanded Stacked barcode – panduan lengkap C#

Jika Anda perlu **how to set columns** untuk barcode Databar Expanded Stacked, tutorial ini menunjukkan langkah‑langkah tepatnya. Baik Anda membangun sistem pelabelan ritel atau aplikasi logistik, mengontrol kolom dan baris memungkinkan Anda menyesuaikan ukuran barcode dan keandalan pemindaian. Selain itu, Anda akan melihat **how to generate barcode** gambar, menyesuaikan jumlah baris, dan dengan benar **barcode save file** ke disk.

Panduan ini akan memandu Anda melalui:

* Menginstal pustaka Aspose.Barcode untuk .NET.  
* Membuat generator barcode untuk tipe Databar Expanded Stacked.  
* Menetapkan jumlah kolom, jumlah baris, dan format gambar.  
* Menyimpan file PNG yang dihasilkan ke direktori pilihan.  

Tidak diperlukan pengalaman sebelumnya dengan Aspose.Barcode—hanya lingkungan pengembangan C# dasar.

## Prasyarat

Sebelum Anda mulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terinstal.  
* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET).  
* Referensi NuGet ke **Aspose.Barcode** (`dotnet add package Aspose.Barcode`).  

Semua potongan kode dapat dikompilasi dengan templat proyek konsol default.

## Langkah 1: Buat generator barcode untuk Databar Expanded Stacked

Operasi pertama adalah menginstansiasi `BarcodeGenerator` dengan enum `EncodeTypes.DatabarExpandedStacked`. Ini menetapkan tata letak default (stacked) dan menyiapkan objek untuk konfigurasi lebih lanjut.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a generator for the Databar Expanded Stacked type.
        // The text "Databar Expanded Stacked long" is the data encoded in the barcode.
        BarcodeGenerator barcodeGeneratorCols = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

**Why this matters:** Generator menyimpan semua parameter rendering. Dengan memilih `DatabarExpandedStacked` Anda memberi tahu pustaka untuk menggunakan tata letak stacked, satu‑satunya tata letak yang mendukung penyesuaian kolom dan baris.

## Cara mengatur kolom untuk barcode Databar Expanded Stacked

Sekarang generator sudah ada, Anda dapat mengontrol jumlah kolom. Properti `DataBar.Columns` menerima bilangan bulat antara 1 dan 4. Menetapkannya ke **4** menghasilkan barcode seluas mungkin sambil tetap cocok dengan tata letak stacked.

```csharp
        // Step 2: Configure the generator to use 4 columns.
        barcodeGeneratorCols.Parameters.Barcode.DataBar.Columns = 4;
```

**Practical tip:** Gunakan jumlah kolom maksimum hanya ketika Anda memiliki cukup ruang putih pada label. Terlalu banyak kolom pada label kecil dapat menyebabkan masalah pemindaian.

## Cara menghasilkan gambar barcode dan menyimpannya

Setelah mengonfigurasi kolom, Anda perlu merender barcode dan menulis gambar ke disk. Metode `Save` menerima jalur file dan enum format gambar.

```csharp
        // Step 3: Save the barcode image as PNG.
        barcodeGeneratorCols.Save("output/DatabarCols4.png", BarCodeImageFormat.Png);
```

Folder `output` harus ada atau pemanggilan akan melempar pengecualian. Anda dapat membuatnya secara programatis dengan `Directory.CreateDirectory("output");` jika diinginkan.

## Cara mengatur baris untuk barcode Databar Expanded Stacked

Baris bekerja mirip dengan kolom, tetapi memengaruhi penumpukan vertikal modul barcode. Properti `DataBar.Rows` menerima nilai dari 1 hingga 5. Dalam contoh ini kami menggunakan **3** baris.

```csharp
        // Step 4: Create a second generator for the same barcode type.
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the generator to use 3 rows.
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        // Step 6: Save the row‑adjusted barcode.
        barcodeGeneratorRows.Save("output/DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Why rows matter:** Menambahkan baris meningkatkan tinggi barcode, yang dapat berguna untuk label ber‑densitas tinggi di mana Anda memerlukan lebih banyak modul data tanpa memperlebar barcode.

## Opsi penyimpanan file barcode dan praktik terbaik

Metode `Save` mendukung beberapa format gambar (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG bersifat lossless dan bekerja baik untuk kebanyakan perangkat pemindai. Jika Anda memerlukan ukuran file lebih kecil dan dapat mentolerir artefak kompresi ringan, pilih JPEG:

```csharp
barcodeGeneratorCols.Save("output/DatabarCols4.jpg", BarCodeImageFormat.Jpeg);
```

**Edge case:** Saat menyimpan ke JPEG, pastikan parameter kualitas diatur dengan tepat (default 90). Kualitas rendah dapat membuat modul kecil menjadi blur, sehingga barcode tidak terbaca.

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua langkah, berikut satu file yang dapat Anda salin ke proyek konsol baru dan jalankan segera:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists.
        Directory.CreateDirectory("output");

        // ------------------------------
        // How to set columns (4 columns)
        // ------------------------------
        BarcodeGenerator colsGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
        colsGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colsGenerator.Save("output/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to output/DatabarCols4.png");

        // ------------------------------
        // How to set rows (3 rows)
        // ------------------------------
        BarcodeGenerator rowsGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
        rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowsGenerator.Save("output/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to output/DatabarRows3.png");

        // ------------------------------
        // How to generate barcode (additional format)
        // ------------------------------
        rowsGenerator.Save("output/DatabarRows3.jpg", BarCodeImageFormat.Jpeg);
        Console.WriteLine("Saved JPEG version to output/DatabarRows3.jpg");
    }
}
```

**Expected output:** Setelah menjalankan program, folder `output` berisi tiga file:

* `DatabarCols4.png` – barcode dengan 4 kolom (lebar).  
* `DatabarRows3.png` – barcode dengan 3 baris (tinggi).  
* `DatabarRows3.jpg` – versi JPEG dari barcode 3‑baris.

Buka salah satu file PNG di penampil gambar; Anda akan melihat barcode Databar Expanded Stacked yang jelas dan siap dipindai.

## Pertanyaan umum dan pemecahan masalah

| Question | Answer |
|----------|--------|
| *Bagaimana jika gambar menjadi buram?* | Pastikan Anda menggunakan PNG untuk output lossless. Jika Anda memerlukan JPEG, tingkatkan pengaturan kualitas (`new JpegOptions { Quality = 95 }`). |
| *Apakah saya dapat mengubah teks barcode?* | Ya—ganti argumen kedua dalam `new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Your Text")`. |
| *Apakah kolom dan baris dapat bekerja bersama?* | Mereka dapat digabungkan; cukup atur kedua `DataBar.Columns` dan `DataBar.Rows` sebelum memanggil `Save`. |
| *Apakah ada batasan kedalaman direktori?* | Path harus valid untuk sistem operasi. Gunakan `Path.Combine` untuk keamanan lintas‑platform. |

## Kesimpulan

Anda kini tahu **how to set columns** untuk barcode Databar Expanded Stacked, **how to set rows**, dan **how to generate barcode** gambar yang dapat Anda **barcode save file** dalam format PNG atau JPEG. Contoh lengkap menunjukkan setiap langkah yang diperlukan, mulai dari instalasi pustaka hingga verifikasi file akhir.

Selanjutnya, pertimbangkan untuk menjelajahi:

* **how to generate barcode** dengan level koreksi kesalahan untuk QR code.  
* **barcode save file** opsi untuk format vektor seperti SVG atau PDF.  
* Mengintegrasikan barcode yang dihasilkan ke dalam tampilan ASP.NET Core MVC untuk pencetakan label dinamis.

Silakan bereksperimen dengan kombinasi kolom/baris yang berbeda, format gambar, dan konten barcode untuk menyesuaikan spesifikasi proyek Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}