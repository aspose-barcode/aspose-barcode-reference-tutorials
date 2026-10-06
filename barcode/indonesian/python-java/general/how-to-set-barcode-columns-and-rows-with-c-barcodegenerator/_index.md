---
category: general
date: 2026-09-16
description: Pelajari cara mengatur kolom barcode di C# menggunakan BarcodeGenerator
  dan juga mengatur baris barcode untuk barcode DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: id
lastmod: 2026-09-16
og_description: Atur kolom barcode di C# dengan cepat. Panduan ini menunjukkan cara
  mengonfigurasi kolom, baris, dan format gambar dengan BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Atur kolom dan baris barcode di C# – panduan lengkap BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara mengatur kolom dan baris barcode dengan C# BarcodeGenerator
url: /id/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur kolom dan baris barcode dengan C# BarcodeGenerator

Jika Anda perlu mengatur kolom barcode dalam aplikasi C#, tutorial ini menunjukkan langkah‑langkah tepat yang diperlukan. Anda akan melihat cara mengonfigurasi baik kolom maupun baris untuk barcode **DataBar Expanded Stacked**, kemudian menyimpan hasilnya sebagai gambar PNG.

Membuat barcode secara programatik menghemat Anda dari pekerjaan desain manual dan menjamin konsistensi pada laporan, faktur, dan label produk. Contoh di bawah mencakup alur kerja lengkap, mulai dari menginstal pustaka hingga menghasilkan dua gambar—satu dengan jumlah kolom khusus dan satu lagi dengan jumlah baris khusus.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 atau yang lebih baru terpasang.  
* Referensi ke paket NuGet **Aspose.BarCode for .NET**. Instal dengan:

```bash
dotnet add package Aspose.BarCode
```

* Hak menulis ke folder tempat file PNG yang dihasilkan akan disimpan.

Persyaratan ini memastikan kode dapat dikompilasi dan dijalankan tanpa konfigurasi tambahan.

## Cara mengatur kolom barcode di C#

Langkah utama pertama adalah membuat instance `BarcodeGenerator` untuk simbol **DataBar Expanded Stacked** dan menetapkan jumlah kolom yang diinginkan.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Mengapa ini berhasil:**  
`EncodeTypes.DatabarExpandedStacked` memberi tahu pustaka simbol mana yang harus dirender. Menetapkan `Parameters.Barcode.DataBar.Columns` mengubah tata letak modul internal, yang secara langsung memengaruhi lebar visual barcode. Metode `Save` menulis gambar ke disk dalam format `BarCodeImageFormat` yang diminta.

### Hasil yang diharapkan
Buka `C:\Barcodes\DatabarCols4.png` dengan penampil gambar apa pun. Anda akan melihat barcode DataBar Expanded Stacked yang lebih lebar daripada default karena menggunakan empat kolom.

## Cara mengatur baris barcode di C#

Setelah Anda menyimpan gambar berbasis kolom, Anda mungkin menginginkan barcode yang tinggiannya berubah dengan menyesuaikan baris. Prosesnya mirip dengan konfigurasi kolom tetapi menggunakan properti `Rows` sebagai gantinya.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Mengapa ini berhasil:**  
Menginisialisasi ulang generator memastikan pengaturan kolom sebelumnya tidak mengganggu konfigurasi baris. Mengubah `Parameters.Barcode.DataBar.Rows` memodifikasi tinggi barcode, menghasilkan gambar yang lebih tinggi ketika jumlah baris melebihi default.

### Hasil yang diharapkan
Buka `C:\Barcodes\DatabarRows3.png`. Barcode akan tampak lebih tinggi, mencerminkan konfigurasi tiga baris.

## Contoh lengkap end‑to‑end

Berikut adalah satu program yang membuat kedua gambar dalam satu eksekusi. Menyimpan kode dalam satu file menunjukkan cara beralih antara konfigurasi kolom dan baris tanpa harus memulai ulang aplikasi.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Menjalankan program menghasilkan dua file PNG:

* **DatabarCols4.png** – barcode dengan empat kolom.  
* **DatabarRows3.png** – barcode dengan tiga baris.

Kedua file menggunakan **format gambar barcode** PNG, yang mempertahankan tepi tajam dan mendukung kompresi lossless—ideal untuk pencetakan dan tampilan digital.

## Pertanyaan umum dan tips

| Pertanyaan | Jawaban |
|----------|--------|
| *Apakah saya dapat menggunakan JPEG alih-alih PNG?* | Ya. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`. JPEG lebih kecil tetapi memperkenalkan artefak kompresi, yang dapat memengaruhi keandalan pemindai. |
| *Berapa jumlah maksimum kolom atau baris?* | Pustaka memvalidasi nilai terhadap spesifikasi DataBar. Nilai di luar rentang yang diizinkan akan melempar `ArgumentException`. Periksa dokumentasi Aspose.BarCode untuk batas pasti. |
| *Apakah saya perlu membuang (`dispose`) `BarcodeGenerator`?* | Kelas ini mengimplementasikan `IDisposable`. Bungkus generator dalam blok `using` jika Anda membuat banyak instance dalam loop untuk membebaskan sumber daya tak terkelola dengan cepat. |
| *Bagaimana cara mengubah ukuran barcode tanpa mengubah kolom/baris?* | Gunakan `barcodeGenerator.Parameters.Image.Width` dan `Height` untuk menskalakan gambar keluaran sambil mempertahankan tata letak modul tidak berubah. |

**Tip profesional:** Saat Anda menghasilkan barcode untuk pencetakan resolusi tinggi, tingkatkan dimensi gambar keluaran (`Width`/`Height`) alih-alih menambah jumlah kolom atau baris. Pendekatan ini mempertahankan ukuran modul standar yang ditetapkan oleh simbol sambil memberikan gambar yang lebih tajam.

## Kesimpulan

Anda kini tahu cara mengatur kolom dan baris barcode di C# menggunakan kelas **BarcodeGenerator**. Panduan ini mencakup inisialisasi generator, konfigurasi jumlah kolom dan baris, penyimpanan barcode dalam format PNG, serta penanganan variasi umum seperti perubahan format gambar dan pembuangan sumber daya.

Selanjutnya, jelajahi topik terkait seperti **menyesuaikan warna barcode**, **menambahkan teks yang dapat dibaca manusia**, dan **menyematkan barcode ke dalam dokumen PDF**. Semua ekstensi ini dibangun di atas pola konfigurasi yang sama seperti yang ditunjukkan di sini, memungkinkan Anda membuat solusi barcode lengkap untuk aplikasi .NET apa pun.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}