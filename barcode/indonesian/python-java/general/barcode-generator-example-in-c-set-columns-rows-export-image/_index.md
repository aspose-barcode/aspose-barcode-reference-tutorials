---
category: general
date: 2026-07-15
description: Contoh generator barcode dalam C# yang menunjukkan cara mengatur kolom,
  cara mengatur baris, dan mengekspor gambar barcode dengan cepat. Ikuti panduan langkah
  demi langkah ini.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: id
lastmod: 2026-07-15
og_description: Contoh generator barcode dalam C# menunjukkan cara mengatur kolom,
  cara mengatur baris, dan mengekspor gambar barcode. Pelajari alur kerja lengkap
  dalam hitungan menit.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Contoh Generator Barcode di C# – Kolom, Baris & Ekspor Gambar
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Contoh Generator Barcode di C# – Atur Kolom, Baris & Ekspor Gambar
url: /id/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contoh Generator Barcode dalam C# – Panduan Lengkap

Pernah bertanya-tanya bagaimana cara membuat **barcode generator example** dalam C# yang memungkinkan Anda mengatur kolom, baris, dan kemudian mengekspor hasilnya sebagai gambar? Anda tidak sendirian. Banyak pengembang mengalami kebuntuan ketika mereka membutuhkan cara cepat untuk menghasilkan barcode DataBar Expanded Stacked dengan opsi tata letak khusus. Dalam tutorial ini kami akan menyelesaikan masalah tersebut langkah demi langkah, menunjukkan **cara mengatur kolom**, **cara mengatur baris**, dan akhirnya **mengekspor file gambar barcode**—semua dengan kode yang bersih dan siap produksi.

Pada akhir panduan ini Anda akan memiliki program lengkap yang dapat dijalankan yang membuat gambar barcode, menyesuaikan tata letaknya, dan menyimpan dua file PNG ke disk. Tanpa perpustakaan misterius, tanpa konfigurasi tersembunyi—hanya C# biasa dan SDK barcode yang dapat diandalkan.

---

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

- **.NET 6.0** (atau versi .NET yang lebih baru). Kode dapat dikompilasi dengan .NET Framework juga, tetapi .NET 6+ memberikan perbaikan runtime terbaru.
- **Perpustakaan pembuatan barcode** yang mendukung DataBar Expanded Stacked. Dalam contoh kami akan menggunakan **Aspose.BarCode for .NET**, yang gratis untuk percobaan dan menawarkan API yang sederhana.
- Lingkungan pengembangan—Visual Studio 2022, Rider, atau VS Code semuanya dapat digunakan.
- Izin menulis ke folder tempat file PNG akan disimpan.

Jika Anda belum memiliki perpustakaan tersebut, dapatkan dari NuGet:

```bash
dotnet add package Aspose.BarCode
```

Baris tunggal itu mengunduh semua yang Anda perlukan, termasuk kelas `BarcodeGenerator` dan enum `BarCodeImageFormat` yang akan digunakan nanti.

---

## Langkah 1: Siapkan Kerangka Proyek

Buat aplikasi konsol baru dan tambahkan direktif `using` yang diperlukan:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Berikut adalah file `Program.cs` **lengkap** kerangka:

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Pro tip:** Jaga metode `Main` tetap rapi; kami akan menyerahkan pekerjaan berat ke metode pembantu nanti. Ini membuat kode lebih mudah diuji dan digunakan kembali.

---

## Langkah 2: Buat Contoh Barcode Generator

Sekarang kami akan membangun **barcode generator example** inti yang membuat barcode DataBar Expanded Stacked. Ini adalah inti dari tutorial.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Mengapa kami memisahkannya ke dalam metode terpisah? Hal ini mengisolasi logika **barcode generator example**, menjadikannya dapat digunakan kembali jika Anda nanti perlu menghasilkan beberapa barcode dengan data yang berbeda.

---

## Langkah 3: Cara Mengatur Kolom

Format DataBar Expanded Stacked dapat dirender dalam tata letak berorientasi kolom. Secara default SDK memilih nilai yang masuk akal, tetapi Anda sering perlu menyesuaikan ukuran label tertentu. Berikut **cara mengatur kolom** menjadi empat:

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Mengapa kolom penting:** Setiap kolom menambah ruang vertikal, yang dapat menjadi krusial saat mencetak pada label sempit. Menetapkannya ke `4` memberikan barcode yang seimbang dan mudah dibaca tanpa mengorbankan keandalan pemindaian.

Dalam alur utama kami akan memanggil metode ini:

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Langkah 4: Cara Mengatur Baris

Terkadang Anda membutuhkan tata letak yang lebih kompak, terutama jika mencetak pada label pendek dan lebar. Di sinilah **cara mengatur baris** berperan. Beralih dari pengaturan berorientasi kolom ke berorientasi baris dapat memperkecil jejak barcode.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

Pemanggilannya seperti ini:

```csharp
SetRows(generator, 3);
```

> **Catatan kasus tepi:** Anda tidak dapat mengatur kolom *dan* baris secara bersamaan—SDK akan memprioritaskan baris jika Anda memberikan nilai non‑nol pada `Rows`. Jadi pastikan untuk mengosongkan properti lainnya jika Anda beralih tata letak:

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Langkah 5: Ekspor Gambar Barcode

Dengan tata letak yang telah dikonfigurasi, bagian akhir adalah **mengekspor file gambar barcode**. SDK mendukung PNG, JPEG, BMP, dan lainnya. PNG bersifat lossless dan bekerja baik untuk kebanyakan printer label.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Menempatkan semuanya bersama di `Main`:

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Output yang Diharapkan

Saat Anda menjalankan program, Anda akan melihat dua file PNG di `YOUR_DIRECTORY`:

- **DatabarCols4.png** – barcode yang dirender dengan empat kolom vertikal.
- **DatabarRows3.png** – data yang sama, tetapi ditata dalam tiga baris horizontal.

Kedua gambar akan berukuran 300 × 150 px (seperti yang diatur di `CreateGenerator`) dan siap untuk dicetak atau disisipkan dalam PDF.

---

## Kesalahan Umum & Tips

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Kesalahan jalur file** | Menggunakan jalur relatif tanpa direktori yang tepat dapat menyebabkan `DirectoryNotFoundException`. | Gunakan `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` atau pastikan folder ada dengan `Directory.CreateDirectory`. |
| **Konflik Baris vs. Kolom** | Menetapkan kedua properti menyebabkan SDK mengabaikan kolom. | Secara eksplisit set properti yang berlawanan ke `0` saat Anda beralih tata letak. |
| **Tipe barcode tidak didukung** | Tidak semua perpustakaan barcode mendukung DataBar Expanded Stacked. | Verifikasi bahwa versi perpustakaan Anda mencakup `EncodeTypes.DatabarExpandedStacked`. |
| **Kualitas gambar terlalu rendah** | DPI default mungkin tidak cukup untuk printer beresolusi tinggi. | Sesuaikan `generator.Parameters.Image.ResolutionX/Y` menjadi `300` atau lebih tinggi. |

---

## Memperluas Contoh Barcode Generator

Sekarang Anda memiliki **barcode generator example** yang solid, Anda mungkin bertanya-tanya apa lagi yang dapat dilakukan.

1. **Tambah warna** – Set `generator.Parameters.Barcode.ForegroundColor` ke `Color.Blue`.
2. **Enkode data berbeda** – Berikan string variabel alih-alih string tetap `"Databar Expanded Stacked long"`.
3. **Pemrosesan batch** – Loop melalui file CSV berisi kode produk, menghasilkan PNG untuk masing‑masing.
4. **Integrasi dengan API web** – Ekspos endpoint yang mengembalikan barcode sebagai string ber‑encoding base64.

Setiap ekstensi ini mengikuti pola yang sama: konfigurasikan instance `BarcodeGenerator`, lalu panggil `Save` atau `Export` sesuai kebutuhan.

---

## Kesimpulan

Kami telah menelusuri contoh **barcode generator example** lengkap dalam C# yang menunjukkan **cara mengatur kolom**, **cara mengatur baris**, dan cara **mengekspor file gambar barcode**. Kode ini berdiri sendiri, dapat dijalankan langsung dengan Aspose.BarCode, dan memperlihatkan praktik terbaik untuk keterbacaan dan pemeliharaan.

Jangan ragu untuk bereksperimen—ganti string data, ubah dimensi gambar, atau beralih ke simbol barcode yang berbeda. Konsep yang Anda pelajari di sini—menginisialisasi generator, mengkonfigurasi parameter tata letak, dan mengekspor—berlaku untuk hampir semua tipe barcode yang didukung oleh SDK.

Apakah Anda memiliki pertanyaan tentang membuat program gambar barcode c# , atau membutuhkan bantuan dengan printer label tertentu? Tinggalkan komentar di bawah, dan selamat coding!

---

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Buat gambar barcode DotCode – baris & kolom (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Buat gambar barcode c# – Konfigurasi Baris & Kolom Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Buat gambar barcode C# – Contoh GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}