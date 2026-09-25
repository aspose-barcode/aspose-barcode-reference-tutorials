---
category: general
date: 2026-08-03
description: Tutorial generator barcode C# menunjukkan cara menghasilkan gambar barcode
  dengan Aspose.BarCode, mengatur kolom dan baris, serta menyimpan file PNG untuk
  DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: id
lastmod: 2026-08-03
og_description: Tutorial generator barcode C# menjelaskan cara menghasilkan gambar
  barcode menggunakan Aspose.BarCode, mengkonfigurasi kolom dan baris DataBar Expanded
  Stacked, serta menyimpan file PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generator Barcode C# – panduan langkah demi langkah untuk membuat gambar
  barcode
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generator Barcode C# – menghasilkan gambar barcode
url: /id/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generator barcode C# – menghasilkan gambar barcode

Jika Anda membutuhkan barcode generator C# yang dapat menghasilkan gambar barcode untuk DataBar Expanded Stacked, panduan ini akan memandu Anda melalui proses lengkap. Anda akan belajar cara mengonfigurasi pengaturan kolom dan baris, menyimpan hasil sebagai PNG, dan menyesuaikan kode untuk simbol lainnya.

Menghasilkan gambar barcode secara programatik menghilangkan langkah manual dan memastikan konsistensi di seluruh faktur, label pengiriman, dan sistem inventaris. Tutorial ini mencakup semua yang Anda perlukan, mulai dari penyiapan proyek hingga kode sumber lengkap, sehingga Anda dapat menjalankan contoh segera.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 atau yang lebih baru terpasang  
* IDE seperti Visual Studio 2022 (editor apa pun yang mendukung C# dapat digunakan)  
* Lisensi untuk **Aspose.BarCode for .NET** – evaluasi gratis dapat digunakan untuk pengujian  
* Familiaritas dasar dengan sintaks C#  

Jika salah satu hal di atas belum ada, instal .NET SDK dari dotnet.microsoft.com dan dapatkan paket NuGet Aspose.BarCode dengan:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Buat proyek barcode generator C# 

Buat aplikasi console baru dan tambahkan direktif `using` yang diperlukan:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

Kelas `BarcodeGenerator` adalah inti dari API barcode generator C#. Ia menerima tipe simbol dan teks yang akan dienkode.

## Langkah 2: Hasilkan barcode DataBar Expanded Stacked dan atur kolom

Contoh pertama membuat barcode dengan empat kolom. Menyesuaikan properti `Columns` mengubah kepadatan visual simbol DataBar Expanded Stacked.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Mengapa ini penting:** Jumlah kolom memengaruhi jumlah data yang dapat disimpan dalam ruang yang kompak. Menetapkannya ke 4 menghasilkan barcode yang lebih lebar namun tetap dapat dibaca oleh sebagian besar pemindai.

## Langkah 3: Hasilkan barcode dengan jumlah baris khusus

Contoh kedua menunjukkan cara mengontrol tata letak vertikal dengan mengatur properti `Rows`. Konfigurasi tiga baris berguna ketika Anda memerlukan barcode yang lebih tinggi karena ruang horizontal terbatas.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Mengapa ini penting:** Menyesuaikan baris memungkinkan Anda menempatkan barcode dalam kolom sempit sambil mempertahankan keterbacaan. Barcode generator C# secara otomatis menghitung ulang ukuran modul untuk memenuhi spesifikasi.

## Langkah 4: Contoh lengkap yang dapat dijalankan

Berikut adalah program mandiri yang menggabungkan langkah‑langkah sebelumnya. Salin kode ke dalam `Program.cs`, ganti `YOUR_DIRECTORY` dengan jalur folder yang ada, dan jalankan aplikasi.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Output yang diharapkan

Saat Anda menjalankan program, dua file PNG muncul di direktori target:

* **DatabarCols4.png** – barcode DataBar Expanded Stacked dengan empat kolom  
* **DatabarRows3.png** – data yang sama dienkode dalam tiga baris  

Buka gambar dengan penampil gambar apa pun; mereka menampilkan barcode tajam dan dapat dipindai, siap untuk dicetak atau disematkan dalam PDF.

## Cara menghasilkan gambar barcode dengan dimensi khusus

Jika Anda memerlukan ukuran gambar tertentu, sesuaikan properti `ImageHeight` dan `ImageWidth` sebelum memanggil `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Mengubah dimensi tidak memengaruhi data yang dienkode; hanya memperbesar representasi visual. Teknik ini berguna saat mengintegrasikan barcode ke dalam komponen UI dengan batasan tata letak tetap.

## Kesalahan umum dan tips profesional

* **Pememisah jalur:** Gunakan string verbatim (`@"C:\Path\file.png"`) atau `Path.Combine` untuk menghindari masalah karakter escape pada Windows.  
* **Penegakan lisensi:** Tanpa lisensi yang valid, gambar yang dihasilkan berisi watermark. Terapkan lisensi Anda di awal aplikasi:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Batas enkoding:** DataBar Expanded Stacked mendukung hingga 74 karakter numerik. Melebihi batas ini akan menimbulkan pengecualian. Validasi panjang input sebelum membuat generator.  
* **Kinerja:** Menggunakan satu instance `BarcodeGenerator` untuk beberapa penyimpanan mengurangi alokasi memori. Hanya ubah properti `Rows` atau `Columns` di antara penyimpanan jika teks yang dienkode tetap sama.

## Langkah selanjutnya

Sekarang Anda dapat menghasilkan gambar barcode dengan barcode generator C#, pertimbangkan untuk menjelajahi:

* **Simbol berbeda** – coba `EncodeTypes.QR`, `EncodeTypes.Code128`, atau `EncodeTypes.Pdf417`.  
* **Kustomisasi warna** – atur `Parameters.Barcode.ForeColor` dan `BackColor` agar sesuai dengan merek.  
* **Penyematan dalam PDF** – gabungkan PNG yang dihasilkan dengan Aspose.PDF untuk membuat dokumen yang dapat dicetak.  

Ekstensi ini memungkinkan Anda membangun solusi barcode lengkap untuk aplikasi inventaris, logistik, atau ritel.

---


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}