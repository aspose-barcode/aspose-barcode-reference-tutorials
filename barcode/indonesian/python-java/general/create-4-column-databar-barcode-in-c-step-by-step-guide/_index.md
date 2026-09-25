---
category: general
date: 2026-08-09
description: Buat barcode databar 4‑kolom di C# dengan cepat menggunakan Aspose.BarCode.
  Pelajari cara mengatur kolom, baris, dan menyimpan gambar PNG dalam panduan singkat
  ini.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: id
lastmod: 2026-08-09
og_description: Buat kode batang databar 4‑kolom di C# menggunakan Aspose.BarCode,
  lalu sesuaikan baris dan ekspor gambar PNG untuk aplikasi Anda.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: Buat barcode databar 4‑kolom di C# – tutorial singkat
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: Buat barcode databar 4‑kolom di C# – panduan langkah demi langkah
url: /id/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode databar 4‑kolom di C# – panduan langkah‑demi‑langkah

Jika Anda perlu **membuat barcode databar 4‑kolom** di C#, tutorial ini akan menunjukkan secara tepat caranya. Kami akan memandu Anda menghasilkan barcode DataBar Expanded Stacked, mengonfigurasi empat kolom, dan menyimpan hasilnya sebagai gambar PNG.

Dalam panduan ini Anda akan belajar cara:

* Menginisialisasi `BarcodeGenerator` untuk simbol **DataBar Expanded Stacked**.  
* Mengatur jumlah kolom menjadi 4 (persyaratan utama).  
* Menyesuaikan jumlah baris ketika Anda memerlukan tata letak stacked dengan tiga baris.  
* Mengekspor barcode sebagai PNG menggunakan **format gambar barcode** yang sesuai.

Anda hanya memerlukan pustaka Aspose.BarCode untuk .NET (versi 23.10 atau lebih baru) dan lingkungan pengembangan .NET 6+ seperti Visual Studio 2022. Tidak ada ketergantungan tambahan yang diperlukan.

---

## Cara membuat barcode databar 4‑kolom

Langkah pertama adalah membuat instance `BarcodeGenerator` yang menargetkan simbol **DataBar Expanded Stacked**. Kelas ini mengenkapsulasi semua opsi rendering, sehingga mudah beralih antara tata letak berbasis kolom dan berbasis baris.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Mengapa ini berhasil:**  
`EncodeTypes.DatabarExpandedStacked` memberi tahu Aspose.BarCode untuk menghasilkan versi stacked dari keluarga DataBar. Properti `DataBar.Columns` mengontrol berapa banyak modul vertikal yang ditempati barcode. Menetapkannya ke 4 memenuhi persyaratan untuk **membuat barcode databar 4‑kolom**. Akhirnya, `Save` menulis representasi visual ke disk menggunakan **format gambar barcode** `Png`.

### Konfigurasi kolom DataBar Expanded Stacked

Jika Anda memerlukan jumlah kolom yang berbeda, cukup ubah nilai integer yang diberikan ke `Columns`. Properti ini menerima nilai dari 1 hingga 4 untuk varian expanded stacked.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*Pro tip:* Selalu uji barcode yang dihasilkan dengan pemindai yang mendukung keluarga DataBar, karena penampilan visual saja tidak menjamin keterbacaan.

### Simpan gambar barcode

Enumerasi `BarCodeImageFormat` menyediakan beberapa opsi (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG bersifat loss‑less dan bekerja baik untuk kebanyakan skenario web dan desktop.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

Jika Anda memerlukan format lain, ganti `Png` dengan nilai enum yang diinginkan. File yang disimpan dapat disisipkan langsung ke HTML, PDF, atau dicetak pada label.

## Buat barcode dengan baris khusus

Kadang-kadang tata letak stacked diperlukan dengan jumlah baris tertentu alih‑alih kolom. Kelas `BarcodeGenerator` yang sama menyediakan properti `Rows` untuk tujuan ini.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Mengapa baris penting:**  
Ketika barcode stacked lebih tinggi daripada lebarnya, properti `Rows` menentukan berapa banyak irisan horizontal simbol dibagi. Menetapkan `Rows = 3` menghasilkan barcode stacked tiga baris, yang berguna untuk lebar label yang sempit.

### Atur baris barcode secara dinamis

Anda dapat menghitung jumlah baris pada runtime berdasarkan data masukan:

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

Fleksibilitas ini memungkinkan Anda **mengatur baris barcode** tanpa harus mengompilasi ulang aplikasi.

## Contoh lengkap end‑to‑end

Berikut adalah program tunggal yang menghasilkan baik barcode 4‑kolom maupun barcode 3‑baris, memperlihatkan cara kedua konfigurasi dapat berdampingan.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**Output yang diharapkan:**  
Dua file PNG muncul di direktori kerja aplikasi:

* `DatabarCols4.png` – barcode DataBar Expanded Stacked dengan empat kolom vertikal.  
* `DatabarRows3.png` – simbol yang sama diatur dalam tiga baris horizontal.

Kedua gambar dapat dibuka di penampil gambar apa pun atau disisipkan dalam kontrol UI.

---

## Pertanyaan umum dan kasus tepi

| Question | Answer |
|----------|--------|
| *Can I use a different barcode symbology?* | Ya. Ganti `EncodeTypes.DatabarExpandedStacked` dengan nilai `EncodeTypes` lain (misalnya `EncodeTypes.QR`), tetapi properti `Columns` dan `Rows` khusus untuk keluarga DataBar. |
| *What if the data string exceeds the maximum length?* | Simbologi DataBar Expanded Stacked mendukung hingga 61 karakter numerik. Melebihi batas ini akan menimbulkan `ArgumentException`. Validasi input sebelum menetapkannya ke generator. |
| *Do I need to dispose the `BarcodeGenerator`?* | `BarcodeGenerator` mengimplementasikan `IDisposable`. Pada layanan yang berjalan lama, bungkuslah dalam blok `using` atau panggil `Dispose()` secara manual untuk membebaskan sumber daya native. |
| *Can I generate SVG instead of PNG?* | Tentu saja. Gunakan `BarCodeImageFormat.Svg` pada metode `Save`. |
| *Is the library compatible with .NET Core?* | Aspose.BarCode untuk .NET mendukung .NET Core 3.1, .NET 5, .NET 6, dan versi selanjutnya. Tidak diperlukan perubahan kode. |

---

## Kesimpulan

Anda kini tahu cara **membuat barcode databar 4‑kolom** di C# menggunakan Aspose.BarCode, cara menyesuaikan tata letak dengan baris, dan cara mengekspor hasil dalam **format gambar barcode** yang praktis. Contoh lengkap menampilkan konfigurasi berbasis kolom maupun baris, memberi Anda fondasi yang kuat untuk skenario pencetakan label atau pemindaian seluler apa pun.

**Langkah selanjutnya**

* Bereksperimenlah dengan payload data yang berbeda dan verifikasi kompatibilitas pemindai.  
* Jelajahi opsi styling tambahan seperti warna latar depan/latar belakang (`generator.Parameters.Barcode.Color`).  
* Gabungkan barcode dengan grafik lain menggunakan API `Graphics` untuk desain label khusus.  

Silakan sesuaikan kode untuk proyek ASP.NET Core, Windows Forms, atau Xamarin—Aspose.BarCode berfungsi di semua platform .NET. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}