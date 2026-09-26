---
category: general
date: 2026-09-26
description: Panduan generator barcode C# menunjukkan cara mengatur baris dan cara
  mengatur kolom saat membuat barcode Databar Expanded Stacked di C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: id
lastmod: 2026-09-26
og_description: Tutorial generator barcode C# menjelaskan cara mengatur baris dan
  kolom untuk barcode Databar Expanded Stacked, lengkap dengan kode dan tips.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: Generator barcode C# – atur baris dan kolom langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: Cara menggunakan generator barcode C# untuk baris dan kolom
url: /id/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan barcode generator C# untuk baris dan kolom

Jika Anda membutuhkan **barcode generator C#** yang memungkinkan Anda mengontrol tata letak visual barcode Databar Expanded Stacked, tutorial ini memberikan solusi lengkap yang dapat dijalankan. Anda akan belajar **cara mengatur baris** dan **cara mengatur kolom** sehingga gambar yang dihasilkan sesuai dengan desain tepat yang Anda butuhkan.

Membuat barcode secara programatik sering terasa seperti menebak properti mana yang melakukan apa. Pada akhir panduan ini Anda akan memahami permukaan API, menghindari jebakan umum, dan memiliki contoh kode siap‑jalankan yang dapat Anda salin ke proyek Anda sendiri.

## Prasyarat

* .NET 6.0 atau yang lebih baru terinstal (kode ini juga bekerja dengan .NET Core dan .NET Framework)
* Referensi ke pustaka barcode‑generation yang menyediakan `BarcodeGenerator` dan `EncodeTypes` (misalnya, Aspose.BarCode, Dynamsoft, atau SDK kompatibel lainnya)
* IDE seperti Visual Studio atau VS Code
* Izin menulis ke folder tempat file PNG akan disimpan

Tidak ada paket NuGet tambahan yang diperlukan selain SDK barcode itu sendiri.

## Barcode generator C# – mengatur baris dan kolom

Bagian berikut menjelaskan setiap langkah konfigurasi. Potongan kode lengkap dan dapat ditempel langsung ke metode `Main` aplikasi console.

### Langkah 1: Buat generator untuk barcode Databar Expanded Stacked

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*Mengapa ini penting:* Menginstansiasi `BarcodeGenerator` adalah tindakan pertama yang Anda lakukan dalam alur kerja **barcode generator C#** apa pun. Konstruktor menerima tipe enkoding dan string data yang akan dienkode.

### Langkah 2: Cara mengatur kolom – konfigurasikan barcode untuk menggunakan 4 kolom

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

Mengatur properti `Columns` mengubah jumlah modul vertikal yang digunakan DataBar. Nilai `4` menghasilkan barcode yang lebih padat dan kompak, yang berguna ketika Anda memiliki ruang horizontal terbatas.

### Langkah 3: Simpan gambar barcode dengan pengaturan kolom

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Metode `Save` menulis gambar yang dihasilkan ke disk. Verifikasi file output untuk memastikan bahwa tata letak empat‑kolom muncul seperti yang diharapkan.

![Contoh barcode generator C# yang menunjukkan pengaturan baris dan kolom](./images/barcode-rows-columns.png)

*Gambar di atas menggambarkan hasil konfigurasi kolom.*

### Langkah 4: Inisialisasi ulang generator untuk tata letak berbeda

Ketika Anda membutuhkan barcode terpisah dengan susunan visual yang berbeda, buat instance baru alih-alih menggunakan kembali yang sebelumnya. Ini menjamin bahwa pengaturan sebelumnya (seperti kolom) tidak memengaruhi konfigurasi baru.

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### Langkah 5: Cara mengatur baris – konfigurasikan barcode untuk menggunakan 3 baris

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

Properti `Rows` mengontrol penumpukan vertikal modul DataBar. Tata letak tiga‑baris adalah default untuk banyak perangkat pemindai, tetapi Anda dapat meningkatkannya untuk kepadatan data yang lebih tinggi.

### Langkah 6: Simpan gambar barcode yang mencakup pengaturan baris

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Buka `DatabarRows3.png` untuk melihat susunan tiga‑baris. Jika barcode tidak dapat dipindai, periksa kembali nilai baris/kolom sesuai dengan spesifikasi pemindai Anda.

## Kode sumber lengkap – siap disalin

Berikut adalah program lengkap yang menggabungkan semua langkah di atas. Ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang ada di mesin Anda.

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Output yang Diharapkan

Menjalankan program menghasilkan dua file PNG:

| Nama file            | Deskripsi tata letak                         |
|----------------------|--------------------------------------------|
| `DatabarCols4.png`   | Databar Expanded Stacked dengan **4 columns** |
| `DatabarRows3.png`   | Databar Expanded Stacked dengan **3 rows**    |

Kedua gambar harus dapat dipindai oleh pembaca barcode standar yang mendukung simbol Databar Expanded Stacked.

## Kesalahan umum dan tips profesional

| Jebakan                              | Mengapa terjadi                               | Perbaikan / Tips |
|--------------------------------------|----------------------------------------------|-------------------|
| Menggunakan instance `BarcodeGenerator` yang sama untuk baris dan kolom | SDK mempertahankan konfigurasi sebelumnya, sehingga mengatur baris setelah kolom dapat menghasilkan campuran yang tidak terduga | Inisialisasi ulang generator (seperti yang ditunjukkan pada Langkah 4) sebelum mengubah dimensi lainnya |
| Lupa mengatur `EncodeTypes` dengan benar | SDK menggunakan simbol default yang berbeda, menghasilkan barcode tidak valid | Selalu berikan `EncodeTypes.DatabarExpandedStacked` ketika Anda membutuhkan format spesifik ini |
| Menyimpan ke folder yang tidak ada      | `Save` melemparkan pengecualian jika jalur tidak valid | Pastikan `YOUR_DIRECTORY` ada atau gunakan `Directory.CreateDirectory` sebelum memanggil `Save` |
| Menggunakan nilai di luar rentang yang diizinkan (misalnya, 0 kolom) | SDK memvalidasi rentang dan melempar `ArgumentOutOfRangeException` | Nilai kolom yang valid adalah 1‑4; nilai baris yang valid adalah 1‑3 untuk simbol ini |

### Tips profesional

Jika Anda perlu menghasilkan banyak barcode dengan variasi baris dan kolom, bungkus logika konfigurasi dalam metode bantu:

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Pendekatan ini mengurangi duplikasi dan membuat kode lebih mudah dipelihara.

## Kesimpulan

Anda kini memiliki contoh lengkap, ujung‑ke‑ujung tentang penggunaan **barcode generator C#** untuk mengontrol baik jumlah baris maupun jumlah kolom dalam barcode Databar Expanded Stacked. Dengan mengikuti langkah‑langkah di atas, Anda dapat menghasilkan gambar barcode yang tepat sesuai dengan persyaratan tata letak perangkat pemindai Anda.

Selanjutnya Anda dapat menjelajahi:

* Menyesuaikan properti `DataBar` lainnya seperti **AspectRatio** atau **BarHeight**
* Menghasilkan simbol lain (misalnya, QR, Code128) dengan kelas `BarcodeGenerator` yang sama
* Menyematkan PNG yang dihasilkan ke dalam PDF atau mencetak langsung dari C#

Silakan bereksperimen dengan kombinasi baris/kolom yang berbeda, dan bagikan hasil Anda di komentar. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara mengatur kolom untuk barcode Databar Expanded Stacked – panduan lengkap C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [panduan barcode databar expanded stacked – cara menghasilkan dan mengukurnya di C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Contoh Barcode Generator di C# – Atur Kolom, Baris & Ekspor Gambar](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}