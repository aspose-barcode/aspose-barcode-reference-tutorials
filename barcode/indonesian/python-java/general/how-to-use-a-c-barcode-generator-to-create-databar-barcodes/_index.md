---
category: general
date: 2026-10-02
description: Pelajari cara mengatur kolom dan baris dalam generator barcode C# untuk
  membuat barcode DataBar. Panduan langkah demi langkah dengan kode lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: id
lastmod: 2026-10-02
og_description: Panduan generator barcode C# – pelajari cara mengatur kolom dan baris
  untuk membuat barcode DataBar dengan contoh kode lengkap.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'Generator barcode C#: atur kolom & baris untuk barcode DataBar'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: Cara menggunakan generator barcode C# untuk membuat barcode DataBar dengan
  kolom dan baris khusus
url: /id/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan generator barcode C# untuk membuat barcode DataBar dengan kolom dan baris khusus

Jika Anda membutuhkan **c# barcode generator** yang dapat menghasilkan barcode DataBar dengan konfigurasi kolom dan baris yang tepat, tutorial ini akan menunjukkan cara melakukannya secara detail. Anda akan melihat mengapa penyesuaian kolom dan baris penting, dan Anda akan mendapatkan contoh lengkap yang siap‑jalan yang membuat barcode DataBar Expanded Stacked dengan 4‑kolom dan 3‑baris.

Dalam bagian-bagian berikut kami membahas:

* Prasyarat untuk menggunakan pustaka Aspose.BarCode for .NET.
* Cara mengatur kolom (`how to set columns`) dan baris (`how to set rows`) pada barcode DataBar.
* Program konsol C# lengkap yang dapat Anda salin, kompilasi, dan jalankan.
* File output yang diharapkan serta tips untuk pemecahan masalah.

Pada akhir panduan ini Anda akan dapat **membuat barcode databar** dalam bentuk gambar yang disesuaikan dengan kebutuhan tata letak Anda.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK or later | Menyediakan runtime untuk kode C#. |
| Visual Studio 2022 (or any IDE that supports .NET) | Mempermudah pembuatan proyek dan debugging. |
| Aspose.BarCode for .NET NuGet package | Menyediakan kelas `BarcodeGenerator` yang digunakan dalam contoh. |
| Write permission to a folder for the output PNG files | Generator menulis gambar barcode ke disk. |

Install the Aspose.BarCode package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Membuat barcode DataBar Expanded Stacked dasar

Langkah pertama adalah menginstansiasi **c# barcode generator** dengan format `EncodeTypes.DatabarExpandedStacked`. Format ini adalah barcode DataBar dua‑dimensi yang dapat mengkodekan hingga 74 karakter numerik.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

Konstruktor menerima dua argumen:

* `EncodeTypes.DatabarExpandedStacked` – memberi tahu pustaka simbol apa yang akan digunakan.
* `"Databar Expanded Stacked long"` – teks yang akan dikodekan.

## Langkah 2: Cara mengatur kolom

Kolom memengaruhi kepadatan horizontal barcode DataBar. Menambah jumlah kolom membuat barcode menjadi lebih lebar, yang dapat meningkatkan keandalan pemindaian pada printer beresolusi rendah.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Mengapa 4 kolom?**  
Empat kolom memberikan keseimbangan yang baik antara ukuran dan keterbacaan untuk kebanyakan aplikasi ritel. Anda dapat bereksperimen dengan nilai 1 hingga 8; pustaka akan secara otomatis menyesuaikan lebar modul.

## Langkah 3: Simpan barcode yang dikonfigurasi dengan kolom

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

Gambar disimpan sebagai file PNG, yang mempertahankan tepi tajam yang diperlukan untuk pemindai barcode.

## Langkah 4: Membuat generator terpisah untuk konfigurasi baris

Konfigurasi baris bekerja dengan cara yang sama tetapi memengaruhi kepadatan vertikal. Untuk menghindari pencampuran pengaturan kolom dan baris, kami membuat instance generator baru.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Langkah 5: Cara mengatur baris

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**Kapan harus menggunakan lebih banyak baris?**  
Menambah baris membuat barcode menjadi lebih tinggi, yang dapat berguna ketika ruang cetak terbatas secara horizontal tetapi cukup secara vertikal (misalnya, pada label produk yang lebih tinggi daripada lebarnya).

## Langkah 6: Simpan barcode yang dikonfigurasi dengan baris

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Kedua file PNG (`DatabarCols4.png` dan `DatabarRows3.png`) akan muncul di folder `C:\Barcodes`.

## Contoh lengkap yang dapat dijalankan

Berikut adalah aplikasi konsol mandiri yang menggabungkan setiap langkah yang dijelaskan di atas. Salin kode ke dalam proyek konsol .NET baru dan jalankan.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### Apa yang dilakukan kode

| Section | Purpose |
|---------|---------|
| **Namespace imports** | Mengimpor `Aspose.BarCode` dan `Aspose.BarCode.Generation`. |
| **Output directory** | Memusatkan path sehingga Anda hanya perlu mengedit satu baris jika memindahkan folder. |
| **Column generator** | Menunjukkan **cara mengatur kolom** pada `c# barcode generator`. |
| **Row generator** | Menunjukkan **cara mengatur baris** pada `c# barcode generator`. |
| **Save calls** | Menulis file PNG ke disk, menjadikannya siap dipindai atau dimasukkan ke dalam laporan. |
| **Console output** | Menyediakan umpan balik langsung, berguna selama pengembangan. |

## Output yang diharapkan

Setelah menjalankan program Anda akan melihat dua file PNG:

* **DatabarCols4.png** – barcode yang lebih lebar mencerminkan empat kolom.
* **DatabarRows3.png** – barcode yang lebih tinggi mencerminkan tiga baris.

Kedua gambar berisi teks *“Databar Expanded Stacked long”* yang dikodekan dalam simbol DataBar Expanded Stacked. Anda dapat membukanya dengan penampil gambar apa pun atau memberikannya ke pemindai barcode untuk memverifikasi keterbacaan.

## Kesalahan umum dan cara menghindarinya

| Issue | Reason | Fix |
|-------|--------|-----|
| **File‑access exception** | Folder output tidak ada atau Anda tidak memiliki izin menulis. | Buat folder secara manual atau jalankan program dengan hak istimewa yang lebih tinggi. |
| **Incorrect column/row values** | Library hanya menerima nilai 1‑8 untuk kolom dan 1‑4 untuk baris. | Validasi nilai sebelum menetapkan, misalnya `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Barcode not scanning** | Gambar yang dihasilkan terlalu kecil untuk resolusi pemindai. | Tingkatkan `ImageHeight` atau `ImageWidth` menggunakan `generator.Parameters.Image.Height` / `...Width`. |
| **Text truncation** | Teks yang dikodekan melebihi panjang maksimum untuk varian DataBar yang dipilih. | Gunakan string yang lebih pendek atau beralih ke `EncodeTypes.DatabarExpanded` jika Anda membutuhkan kapasitas lebih. |

## Tips profesional

* **Cache the generator** – Jika Anda perlu membuat banyak barcode dengan pengaturan kolom/baris yang sama, gunakan kembali instance `BarcodeGenerator` yang sama dan hanya ubah properti `CodeText`.
* **Batch processing** – Lakukan iterasi atas koleksi identifier produk, set `generator.CodeText` di dalam loop, dan panggil `Save` dengan nama file unik setiap iterasi.
* **Performance** – Untuk skenario volume tinggi, nonaktifkan anti‑aliasing (`generator.Parameters.Image.AntiAlias = false`) untuk mempercepat pembuatan gambar tanpa memengaruhi kualitas pemindaian.

## Langkah selanjutnya

Sekarang Anda sudah mengetahui **cara mengatur kolom** dan **cara mengatur baris** dengan **c# barcode generator**, Anda mungkin ingin menjelajahi:

* **Menambahkan teks yang dapat dibaca manusia** di bawah barcode (`generator.Parameters.Barcode.CodeTextLocation`).
* **Mengubah warna** (`generator.Parameters.Image.ForegroundColor` dan `BackgroundColor`).
* **Membuat varian DataBar lain** seperti `DatabarLimited` atau `DatabarExpanded`.
* **Menyematkan barcode dalam laporan PDF** menggunakan Aspose.PDF.

Setiap topik ini membangun di atas fondasi yang dibahas di sini dan membantu Anda menciptakan solusi barcode yang lebih kaya dan siap produksi.

---

*Selamat coding! Jika Anda mengalami masalah, silakan tinggalkan komentar atau periksa dokumentasi Aspose.BarCode untuk detail API yang lebih mendalam.*

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara mengatur kolom dan baris barcode dengan C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Contoh Generator Barcode di C# – Atur Kolom, Baris & Ekspor Gambar](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Cara menggunakan generator barcode C# untuk membuat barcode DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}