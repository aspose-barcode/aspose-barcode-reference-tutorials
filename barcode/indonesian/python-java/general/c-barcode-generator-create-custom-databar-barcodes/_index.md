---
category: general
date: 2026-08-19
description: Tutorial generator barcode C# menunjukkan cara menghasilkan barcode DataBar
  Expanded Stacked, menyesuaikan ukuran barcode, dan mengonfigurasi baris serta kolom.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: id
lastmod: 2026-08-19
og_description: Tutorial generator barcode C# mengajarkan Anda cara menghasilkan barcode
  DataBar, menyesuaikan ukuran, dan mengatur baris serta kolom untuk output yang tepat.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generator kode batang C# – panduan langkah demi langkah untuk kode batang
  DataBar khusus
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'Generator barcode C#: buat barcode DataBar khusus'
url: /id/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generator barcode C#: buat barcode DataBar khusus

Jika Anda membutuhkan **c# barcode generator** yang dapat menghasilkan simbol DataBar Expanded Stacked, panduan ini menunjukkan secara tepat cara menghasilkan gambar barcode dengan baris dan kolom khusus. Anda akan belajar mengonfigurasi parameter databar, menyesuaikan ukuran barcode, dan menyimpan hasilnya sebagai file PNG.

Membuat barcode secara programatik menghilangkan langkah desain manual dan menjamin output yang konsisten di semua platform. Dalam tutorial ini Anda akan:

* Instal dan referensikan pustaka Aspose.BarCode untuk .NET (atau paket kompatibel apa pun).
* Buat generator barcode untuk simbol DataBar Expanded Stacked.
* **Cara menghasilkan barcode** dengan pengaturan kolom dan baris tertentu.
* **Sesuaikan ukuran barcode** dengan mengontrol baris dan kolom DataBar.
* **Konfigurasikan parameter databar** seperti teks, format, dan kualitas gambar.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru terpasang.
* Lingkungan pengembangan C# (Visual Studio, VS Code, Rider, dll.).
* Paket NuGet `Aspose.BarCode` (atau pustaka setara yang menyediakan `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`).

Add the package with the .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

## Menggunakan generator barcode C# untuk membuat barcode DataBar

Bagian-bagian berikut akan memandu Anda melalui setiap langkah. Fokus utama adalah pada API **c# barcode generator**, namun pola yang sama berlaku untuk pustaka barcode lain yang menyediakan properti serupa.

### Langkah 1: Inisialisasi generator barcode dengan teks contoh

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Mengapa langkah ini?*  
`BarcodeGenerator` adalah titik masuk untuk semua tugas pembuatan barcode. Menyediakan enum `EncodeTypes.DatabarExpandedStacked` memberi tahu pustaka simbol apa yang akan digunakan, sementara argumen teks menjadi nilai yang dapat dibaca manusia yang dikodekan dalam simbol.

### Langkah 2: Atur jumlah kolom (baris default digunakan)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*Mengapa langkah ini?*  
Simbol DataBar Expanded Stacked terdiri dari elemen linier yang ditumpuk. Menyesuaikan properti `Columns` mengubah kepadatan horizontal, memungkinkan Anda menampung string data yang lebih panjang tanpa menambah tinggi keseluruhan. Ini secara langsung **menyesuaikan ukuran barcode**.

### Langkah 3: Simpan gambar barcode yang menggunakan empat kolom

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*Apa yang Anda lihat:*  
Gambar `DatabarCols4.png` yang disimpan menampilkan barcode DataBar yang lebih lebar daripada default karena berisi empat kolom. Anda dapat membuka file tersebut di penampil gambar apa pun untuk memverifikasi hasilnya.

### Langkah 4: Inisialisasi ulang generator untuk konfigurasi baru

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Mengapa inisialisasi ulang?*  
Mengubah properti `Rows` sambil mempertahankan pengaturan kolom sebelumnya dapat menghasilkan kombinasi yang tidak terduga. Memulai dengan instance baru memastikan hanya parameter yang dimaksud (`Rows`) yang memengaruhi gambar berikutnya.

### Langkah 5: Atur jumlah baris (kolom default digunakan)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*Mengapa langkah ini?*  
Properti `Rows` mengontrol penumpukan vertikal. Menambah baris membuat barcode lebih tinggi, yang dapat berguna ketika ruang terbatas secara horizontal namun melimpah secara vertikal. Ini adalah cara lain untuk **menyesuaikan ukuran barcode**.

### Langkah 6: Simpan gambar barcode yang menggunakan tiga baris

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*Hasil:*  
`DatabarRows3.png` menampilkan barcode yang lebih tinggi dengan tiga baris yang ditumpuk, menunjukkan bagaimana **konfigurasikan parameter databar** memengaruhi tampilan visual.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan. Program ini mencakup semua impor, penanganan error, dan komentar untuk kejelasan.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**Output yang diharapkan**

Menjalankan program menghasilkan dua file PNG:

* `DatabarCols4.png` – barcode DataBar lebar dengan empat kolom.
* `DatabarRows3.png` – barcode DataBar tinggi dengan tiga baris.

Buka gambar-gambar tersebut untuk memastikan dimensi barcode sesuai dengan parameter yang dikonfigurasi.

## Pertanyaan umum dan penanganan kasus tepi

| Question | Answer |
|----------|--------|
| *Bagaimana jika saya membutuhkan baris khusus **dan** kolom?* | Setel `Rows` **and** `Columns` pada instance `BarcodeGenerator` yang sama sebelum memanggil `Save`. Pustaka akan menggabungkan kedua nilai tersebut untuk menghasilkan grid dengan ukuran yang diminta. |
| *Apakah saya dapat mengubah format gambar?* | Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` sesuai alur kerja Anda. |
| *Apa yang terjadi ketika teks lebih panjang daripada yang dapat ditampung simbol?* | Generator akan melempar `ArgumentException`. Pendekkan teks atau tingkatkan `Columns`/`Rows` untuk menyediakan kapasitas lebih. |
| *Apakah ada cara untuk mengatur DPI atau resolusi gambar?* | Gunakan `generator.Parameters.ImageResolution` untuk menentukan DPI yang diinginkan sebelum menyimpan. Ini lebih lanjut **menyesuaikan ukuran barcode** untuk pencetakan resolusi tinggi. |
| *Apakah pustaka mendukung varian DataBar lainnya?* | Ya. Ganti `EncodeTypes.DatabarExpandedStacked` dengan `DatabarExpanded`, `DatabarLimited`, dll., sambil mempertahankan struktur parameter yang sama. |

## Tips untuk menghasilkan barcode yang andal

* **Pro tip:** Selalu verifikasi gambar yang dihasilkan dengan pemindai atau aplikasi seluler sebelum menerapkannya ke produksi.  
* **Watch out for:** Direktori output yang null atau kosong—`Save` akan melempar pengecualian jika path tidak ada. Buat folder secara programatik jika diperlukan.  
* **Performance note:** Menggunakan kembali satu instance `BarcodeGenerator` dan hanya mengubah `Rows` atau `Columns` dapat mengurangi overhead pembuatan objek saat menghasilkan banyak barcode dalam loop.

## Kesimpulan

Anda kini tahu cara menggunakan **c# barcode generator** untuk **membuat gambar barcode databar**, **menyesuaikan ukuran barcode**, dan **mengonfigurasi parameter databar** seperti baris dan kolom. Dengan menyesuaikan pengaturan ini, Anda dapat menempatkan barcode ke dalam kebutuhan tata letak apa pun sambil mempertahankan keandalan pemindaian.

Selanjutnya, jelajahi topik terkait seperti **cara menghasilkan barcode** PDF, menyematkan barcode dalam laporan, atau beralih ke simbol lain (QR, Code‑128, dll.). Bereksperimenlah dengan `Rows`, `Columns`, dan resolusi gambar yang berbeda untuk menemukan konfigurasi optimal bagi kasus penggunaan spesifik Anda.

---

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan dan Menyesuaikan Tinggi Barcode untuk One-Dimensional Databar menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hasilkan Barcode 2D One-Dimensional Databar Menggunakan Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Hasilkan barcode Databar Aspose.BarCode menggunakan .NET API – Konfigurasi Baris & Kolom](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}