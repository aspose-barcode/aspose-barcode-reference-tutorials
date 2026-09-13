---
category: general
date: 2026-09-13
description: Buat barcode databar stacked di C# dengan cepat menggunakan Aspose.Barcode
  – pelajari cara mengatur kolom, baris, dan menyimpan gambar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: id
lastmod: 2026-09-13
og_description: Buat kode batang databar bertumpuk di C# menggunakan Aspose.Barcode.
  Panduan ini menunjukkan cara mengatur kolom, baris, dan mengekspor gambar PNG.
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: Buat Barcode Databar Stacked di C# – Panduan Langkah-demi-Langkah Lengkap
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: Cara membuat barcode databar bertumpuk di C# dengan Aspose.Barcode
url: /id/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode databar stacked di C# dengan Aspose.Barcode

Jika Anda perlu **membuat barcode databar stacked** dalam aplikasi .NET, panduan ini memberikan solusi lengkap yang siap dijalankan. Anda akan melihat secara tepat cara mengonfigurasi jumlah kolom, menyesuaikan baris, dan menyimpan hasilnya sebagai file PNG—semua dengan pustaka Aspose.Barcode untuk .NET.

Membuat barcode **Databar Expanded Stacked** bukanlah misteri setelah Anda memahami alur kerja tiga langkah: membuat instance generator, mengatur dimensi yang diinginkan, dan menulis gambar ke disk. Bagian-bagian berikut akan memandu Anda melalui setiap langkah, menjelaskan mengapa pengaturan penting, dan menampilkan output akhir yang dapat Anda verifikasi secara langsung.

## Prasyarat

- **Visual Studio 2022** (atau IDE C# apa pun) dengan .NET 6+ terinstal.
- Paket NuGet **Aspose.Barcode for .NET** (`Install-Package Aspose.Barcode`).
- Izin menulis ke folder tempat file PNG akan disimpan.

Tidak ada dependensi tambahan yang diperlukan.

## Langkah 1: Siapkan proyek dan tambahkan Aspose.Barcode

1. Buat proyek Console App baru:

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. Tambahkan paket Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Buka **Program.cs** dan tambahkan pernyataan `using` yang diperlukan:

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

Langkah-langkah ini memastikan kelas **C# barcode generator** tersedia untuk kode Anda.

## Langkah 2: Buat generator untuk barcode Databar stacked

Objek pertama yang Anda butuhkan adalah `BarcodeGenerator` yang dikonfigurasi untuk simbol **Databar Expanded Stacked**. Objek ini merupakan titik masuk untuk semua operasi terkait barcode.

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**Mengapa ini penting:**  
`EncodeTypes.DatabarExpandedStacked` memberi tahu Aspose.Barcode untuk menggunakan versi stacked dari keluarga DataBar, yang ideal untuk ruang dengan tinggi terbatas seperti struk. Argumen kedua menyediakan data yang dienkode dalam barcode; Anda dapat menggantinya dengan string numerik atau alfanumerik apa pun yang sesuai dengan standar DataBar.

## Langkah 3: Konfigurasikan kolom barcode dan simpan gambar

DataBar stacked dapat ditampilkan menggunakan jumlah **kolom** yang dapat dikonfigurasi. Defaultnya tiga, tetapi Anda mungkin memerlukan empat kolom untuk string data yang lebih panjang. Sesuaikan properti `Columns` sebelum menyimpan.

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**Penjelasan:**  
- `Parameters.Barcode.DataBar.Columns` secara langsung memengaruhi segmentasi horizontal barcode. Lebih banyak kolom menghasilkan gambar yang lebih lebar tetapi tinggi tetap sama.  
- `Save` menulis barcode ke file PNG. Format lain (JPEG, BMP, SVG) juga didukung dengan memberikan nilai `BarCodeImageFormat` yang berbeda.

## Langkah 4: Buat generator lain dan konfigurasikan baris barcode

Kadang lingkungan pemindaian memerlukan barcode yang lebih tinggi, yang dapat Anda capai dengan meningkatkan jumlah **baris**. Potongan kode berikut membuat instance generator kedua, mengatur tiga baris, dan menyimpan hasilnya.

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**Mengapa instance terpisah?**  
Mengubah `Rows` pada `BarcodeGenerator` yang sama setelah pemanggilan `save` juga dapat berfungsi, tetapi membuat instance baru menjaga setiap konfigurasi terisolasi dan membuat kode lebih mudah dibaca—terutama ketika Anda nanti memperluas tutorial untuk mencakup variasi lain (misalnya, string data yang berbeda atau level koreksi kesalahan).

## Langkah 5: Verifikasi barcode yang dihasilkan

Buka dua file PNG yang baru saja Anda buat. Anda akan melihat:

- **DatabarCols4.png** – barcode yang lebih lebar terdiri dari empat kolom vertikal.  
- **DatabarRows3.png** – barcode yang lebih tinggi terdiri dari tiga baris horizontal.

Kedua gambar mengkodekan teks yang sama (`"Databar Expanded Stacked long"`), tetapi struktur visualnya berbeda. Pindai keduanya dengan pemindai DataBar standar atau aplikasi seluler yang mendukung DataBar untuk memastikan mereka terdekripsi dengan benar.

## Kesalahan umum dan tips profesional

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Path folder tidak benar** | `Save` melempar `DirectoryNotFoundException` jika direktori tidak ada. | Gunakan `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))` sebelum memanggil `Save`. |
| **Terlalu banyak kolom/baris** | Spesifikasi DataBar membatasi kolom hingga 4 dan baris hingga 3. | Tetap pada rentang yang diizinkan; Aspose.Barcode akan melempar `ArgumentOutOfRangeException` jika tidak. |
| **Barcode tidak terbaca** | Resolusi gambar yang rendah dapat membuat barcode menjadi buram. | Tingkatkan DPI melalui `barcodeGenerator.Parameters.ImageResolution` jika Anda membutuhkan kualitas lebih tinggi (mis., 300 dpi). |
| **Format data salah** | DataBar hanya menerima string numerik hingga 13 digit untuk mode tertentu. | Validasi string input Anda sebelum mengirimkannya ke generator. |

## Memperluas contoh

Setelah Anda dapat **membuat barcode databar stacked** dengan kolom dan baris yang disesuaikan, Anda mungkin ingin menjelajahi:

- **Mengubah warna latar depan/latar belakang** (`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`).  
- **Menambahkan quiet zone** (`barcodeGenerator.Parameters.Barcode.Qz = 2;`).  
- **Mengekspor ke SVG** untuk rendering yang tidak bergantung pada resolusi (`BarCodeImageFormat.Svg`).

Semua opsi ini didokumentasikan dalam [Aspose.Barcode for .NET API reference](https://docs.aspose.com/barcode/net/).

## Kode sumber lengkap

Berikut adalah program lengkap yang dapat dijalankan yang menggabungkan setiap langkah yang dijelaskan di atas. Salin ke `Program.cs` Anda, ganti `YOUR_DIRECTORY` dengan path yang sebenarnya, dan jalankan `dotnet run`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

Menjalankan program menghasilkan dua file PNG yang menunjukkan bagaimana **kolom barcode** dan **baris barcode** memengaruhi tata letak visual simbol **Databar Expanded Stacked**.

## Kesimpulan

Anda kini tahu cara **membuat barcode databar stacked** di C# menggunakan Aspose.Barcode untuk .NET. Dengan menyesuaikan properti `Columns` dan `Rows` Anda dapat menghasilkan barcode yang cocok untuk berbagai batasan ruang sambil menjaga integritas data. Contoh ini mencakup semua hal mulai dari penyiapan proyek hingga pemecahan masalah, memberikan fondasi yang kuat untuk skenario barcode yang lebih maju.

**Langkah selanjutnya:**  
- Bereksperimen dengan string data yang berbeda dan lihat bagaimana batas kolom/baris memengaruhi keterbacaan.  
- Gabungkan kode ini dengan API web untuk menghasilkan barcode sesuai permintaan.  
- Jelajahi simbol lain (mis., QR, Code128) menggunakan pola `BarcodeGenerator` yang sama.

Selamat coding, semoga pemindaian Anda selalu berhasil!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Barcode Generator C# – Membuat Gambar DataBar Expanded Stacked](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [Panduan barcode databar expanded stacked – cara menghasilkan dan mengatur ukurannya di C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Menghasilkan barcode Aspose.BarCode Databar menggunakan .NET API – Konfigurasi Baris & Kolom](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}