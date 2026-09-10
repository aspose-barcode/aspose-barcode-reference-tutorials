---
category: general
date: 2026-07-24
description: Tutorial Generator Barcode C# yang menunjukkan cara menghasilkan gambar
  barcode, mengatur kolom, mengatur baris, dan membuat barcode Databar hanya dalam
  beberapa baris kode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: id
lastmod: 2026-07-24
og_description: Tutorial Barcode Generator C# memandu Anda melalui pembuatan gambar
  barcode, mengonfigurasi kolom dan baris, serta membuat barcode Databar dengan contoh
  kode yang jelas.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generator Barcode C# – Buat Barcode DataBar Bertumpuk dengan Cepat
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generator Barcode C# – Membuat Gambar DataBar Expanded Stacked
url: /id/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – Panduan Lengkap DataBar Expanded Stacked

Pernah bertanya-tanya bagaimana cara menggunakan **barcode generator c#** untuk menghasilkan gambar yang tajam dan dapat dipindai dalam hitungan detik? Mungkin Anda telah menatap proyek kosong, tidak yakin di mana kolom atau baris harus ditempatkan, atau bagaimana cara *generate barcode image* file tanpa sakit kepala. Nah, Anda berada di tempat yang tepat. Dalam tutorial ini kita akan menyiapkan aplikasi console kecil, membuat barcode DataBar Expanded Stacked, menyesuaikan tata letaknya, dan menyimpan hasilnya sebagai PNG—semua dengan library **barcode generator c#**.

Kami akan membahas semua yang perlu Anda ketahui: menginstal paket, mengonfigurasi kolom dan baris (ya, kami akan menjawab *how to set columns* dan *how to set rows*), dan akhirnya cara **create databar barcode** objek yang dapat Anda sisipkan ke dalam faktur, tiket, atau apa pun yang membutuhkan label yang dapat dibaca mesin. Tidak diperlukan dokumen eksternal; cukup salin‑tempel, jalankan, dan Anda akan melihat dua file PNG muncul di folder Anda.

## Apa yang Anda Butuhkan

- .NET 6.0 SDK atau yang lebih baru (kode ini bekerja pada .NET Core, .NET Framework, dan .NET 5+)
- Proyek console baru (`dotnet new console`) – Anda juga dapat menggunakan Visual Studio jika lebih suka UI.
- Paket NuGet Aspose.BarCode untuk .NET (perpustakaan yang mendukung **barcode generator c#**). Instal dengan:

```bash
dotnet add package Aspose.BarCode
```

Itu saja. Setelah paket dipulihkan, Anda siap memulai.

## Barcode Generator C# – Menyiapkan Proyek

Pertama, mari import namespace yang diperlukan dan buat metode pembantu yang akan menjaga rutinitas utama tetap rapi.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Mengapa Struktur Ini Berfungsi

- **Separation of concerns** – setiap pembantu fokus pada satu konfigurasi (kolom vs. baris). Hal ini membuat kode lebih mudah dibaca dan digunakan kembali.
- **Explicit parameters** – kami mengirim `columns` atau `rows` sebagai argumen, sehingga Anda dapat memanggil metode yang sama dengan nilai apa pun tanpa mengedit isi metode.
- **Immediate feedback** – `Console.WriteLine` memberi tahu Anda tepat di mana file disimpan, yang berguna saat Anda menjalankan program dari terminal.

## Cara Mengatur Kolom untuk DataBar Expanded Stacked

Properti `DataBar.Columns` adalah pengatur yang menentukan berapa banyak irisan vertikal yang akan dimiliki barcode. Nilai defaultnya adalah `4`, tetapi Anda mungkin memerlukan `2` atau `6` tergantung pada jumlah data yang Anda enkode atau persyaratan pemindai. Berikut cuplikan singkat yang memisahkan logika pengaturan kolom:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Pro tip:** Saat Anda menambah kolom, lebar keseluruhan barcode akan bertambah secara proporsional. Jika Anda berencana menanamkan gambar dalam PDF atau halaman web, pastikan kontainer dapat menampung lebar tambahan, jika tidak pemindai dapat membacanya salah.

## Cara Mengatur Baris untuk DataBar Expanded Stacked

Baris bekerja dengan cara yang sama, tetapi memengaruhi tinggi barcode. Jumlah baris default adalah `3`. Jika label Anda memiliki ruang vertikal terbatas, Anda dapat menurunkannya menjadi `2`. Sebaliknya, lebih banyak baris dapat meningkatkan keterbacaan pada printer beresolusi rendah.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Watch out:** Mengatur baris ke nilai yang lebih rendah dari minimum yang diperlukan untuk data yang dienkode akan menyebabkan pengecualian pada waktu berjalan. Perpustakaan melempar `ArgumentException` dengan pesan yang jelas, sehingga Anda langsung tahu jika konfigurasi tidak valid.

## Menghasilkan Gambar Barcode – Menyimpan sebagai PNG

Kedua pembantu di atas diakhiri dengan pemanggilan `Save`. Enum `BarCodeImageFormat.Png` memberi tahu Aspose.BarCode untuk menghasilkan file PNG loss‑less, yang ideal untuk kebanyakan skenario pemindaian karena mempertahankan tepi yang tajam. Jika Anda lebih suka format lain (JPEG untuk web, BMP untuk sistem lama), cukup ganti nilai enum—tidak perlu mengubah kode lain.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

PNG yang dihasilkan terlihat seperti ini (bayangkan gambarnya; teks alt di bawah menjelaskannya):

> **Alt text for the generated images:** *Barcode DataBar Expanded Stacked dengan 4 kolom (kiri) dan 3 baris (kanan), ditampilkan dalam warna hitam kontras tinggi pada latar belakang transparan.*

## Membuat DataBar Barcode – Contoh Kerja Lengkap

Menggabungkan semua, berikut versi ringkas yang dapat Anda masukkan langsung ke dalam `Program.cs`. Ini mendemonstrasikan konfigurasi kolom dan baris, serta pemeriksaan cepat bahwa file ada setelah disimpan.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Output yang Diharapkan

Saat Anda menjalankan program (`dotnet run`), Anda akan melihat baris konsol serupa dengan:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Buka kedua file PNG dalam penampil gambar apa pun; Anda akan melihat file kiri memiliki empat modul vertikal (kolom) sementara file kanan memiliki tiga modul tinggi (baris). Kedua file dapat dipindai dengan sempurna menggunakan pembaca DataBar standar apa pun.

## Kesalahan Umum & Cara Menghindarinya

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| `ArgumentException: Columns value is out of range` | Kolom diatur ke 0 atau > 8 (perpustakaan membatasi hingga 8). | Gunakan nilai antara **1** dan **8**. |
| Barcode muncul buram di PDF | PNG disimpan dengan DPI default (96) lalu diubah skala. | Gunakan `generator.Parameters.ImageResolution = 300;` sebelum menyimpan. |
| Pemindai gagal pada konfigurasi hanya baris | Baris diubah tetapi kolom tetap pada default yang tidak cocok dengan panjang data. | Sesuaikan baik baris **dan** kolom bersama-sama, atau biarkan perpustakaan mengatur ukuran otomatis dengan menghilangkan pengaturan manual. |

## Langkah Selanjutnya

Sekarang Anda tahu cara **generate barcode image**, **set columns**, **set rows**, dan **create databar barcode** dengan **barcode generator c#**, Anda dapat:

- Menyematkan PNG ke dalam PDF menggunakan `Aspose.PDF` atau `iTextSharp`.
- Beralih ke `EncodeTypes.DatabarLimited` jika Anda membutuhkan jejak yang lebih kecil.
- Bereksperimen dengan warna (`generator.Parameters.Barcode.ForeColor = Color.Blue`).
- Tambahkan kode QR atau simbol lainnya dalam proyek yang sama—Aspose.BarCode mendukung lebih dari 150 tipe.

Jika Anda mengalami kendala, tinggalkan komentar di bawah atau periksa dokumentasi resmi Aspose.BarCode (referensi API sangat lengkap dan mencakup puluhan contoh kode langsung). Selamat coding, semoga pemindai Anda tidak pernah melewatkan satu pun tanda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}