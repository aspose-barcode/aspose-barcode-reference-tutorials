---
category: general
date: 2026-09-19
description: contoh generator barcode dalam C# yang menunjukkan cara menghasilkan
  barcode C# menggunakan Aspose.BarCode untuk tata letak kolom dan baris
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: id
lastmod: 2026-09-19
og_description: Contoh generator barcode menunjukkan cara menghasilkan barcode C#
  dengan tata letak kolom dan baris menggunakan Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: contoh generator barcode – buat barcode DataBar Expanded Stacked dengan
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membuat contoh generator barcode di C# dengan DataBar Expanded Stacked
url: /id/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# contoh generator barcode – buat barcode DataBar Expanded Stacked dalam C#

Jika Anda memerlukan **contoh generator barcode** yang berfungsi dalam proyek .NET, panduan ini menunjukkan secara tepat cara menghasilkan barcode C# menggunakan pustaka Aspose.BarCode. Anda akan melihat cara mengonfigurasi barcode DataBar Expanded Stacked untuk tata letak berbasis kolom maupun berbasis baris, dan Anda akan mendapatkan kode siap‑jalan yang menghasilkan gambar PNG.

Tutorial ini mencakup semua hal mulai dari menginstal paket NuGet hingga menyimpan gambar akhir, sehingga Anda dapat menyalin kode ke dalam solusi Anda sendiri tanpa penelitian tambahan.

## Apa yang akan Anda pelajari

* Cara menginstal dan mereferensikan Aspose.BarCode dalam proyek C#.  
* Cara membuat **contoh generator barcode** yang mengenkode string data panjang.  
* Cara mengatur tata letak 4‑kolom dan 3‑baris pada tipe barcode yang sama.  
* Cara menyimpan gambar yang dihasilkan sebagai file PNG.  

Pada akhir artikel ini Anda akan memiliki dua file PNG siap‑pakai: `ExpandedStackedCols4.png` (empat kolom) dan `ExpandedStackedRows3.png` (tiga baris).

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code, atau IDE C# apa pun yang Anda sukai.  
* Akses internet untuk mengunduh paket NuGet **Aspose.BarCode**.  

Tidak ada layanan eksternal tambahan yang diperlukan.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan versi stabil terbaru Aspose.BarCode ke file proyek Anda. Setelah paket dipulihkan, Anda dapat mereferensikan namespace‑nya dalam file sumber C# Anda.

## Langkah 2: Tambahkan direktif using yang diperlukan

Buat aplikasi konsol C# baru (atau tambahkan kode ke proyek yang sudah ada) dan sertakan pernyataan `using` berikut di bagian atas file:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Direktif ini memberi Anda akses ke kelas `BarcodeGenerator` dan enumerasi `EncodeTypes` yang digunakan dalam **contoh generator barcode**.

## Langkah 3: Buat contoh generator barcode dengan tata letak 4‑kolom

Bagian pertama contoh membangun barcode DataBar Expanded Stacked yang menggunakan susunan empat kolom. Kode di bawah mengikuti langkah‑langkah persis seperti pada cuplikan asli, namun menambahkan komentar yang menjelaskan mengapa setiap baris diperlukan.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Mengapa ini berhasil**

* `EncodeTypes.DatabarExpandedStacked` memberi tahu Aspose.BarCode untuk menghasilkan simbol DataBar Expanded Stacked, yang cocok untuk aplikasi ritel.  
* Menetapkan `DataBar.Columns` ke `4` memaksa generator membagi simbol menjadi empat bagian vertikal, meningkatkan keterbacaan pada label sempit.  
* `Save` menulis barcode ke disk; argumen `BarCodeImageFormat.Png` memastikan kualitas gambar tanpa kehilangan.

Menjalankan blok ini membuat `ExpandedStackedCols4.png` di direktori kerja aplikasi. File tersebut berisi barcode resolusi tinggi yang dapat dipindai oleh pembaca DataBar standar.

## Langkah 4: Inisialisasi ulang generator untuk tata letak yang berbeda

Untuk mendemonstrasikan tata letak berbasis baris, Anda memerlukan instance `BarcodeGenerator` yang baru. Inisialisasi ulang memastikan pengaturan kolom sebelumnya tidak memengaruhi konfigurasi baru.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Langkah 5: Konfigurasikan barcode untuk menggunakan tata letak 3‑baris

API DataBar juga mendukung susunan baris. Menetapkan properti `Rows` menentukan berapa banyak irisan horizontal yang akan dimiliki simbol.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Mengapa Anda mungkin memilih baris daripada kolom**

Baris berguna ketika tinggi label terbatas tetapi lebar cukup luas. Tata letak tiga baris memampatkan barcode secara vertikal sambil mempertahankan jumlah data yang diperlukan.

## File sumber lengkap

Berikut adalah `Program.cs` lengkap yang dapat Anda kompilasi dan jalankan langsung. File ini mencakup contoh kolom dan baris, sehingga Anda mendapatkan dua file PNG dengan satu eksekusi.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Output yang diharapkan

Setelah menjalankan program Anda akan melihat dua pesan konsol yang mengonfirmasi pembuatan file:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Kedua file PNG akan menampilkan barcode DataBar Expanded Stacked yang mengenkode string `"Long data string"`. Memindai salah satu gambar dengan pemindai barcode standar akan mengembalikan data asli.

## Pertanyaan umum dan kasus tepi

| Pertanyaan | Jawaban |
|------------|---------|
| **Apakah saya dapat mengubah format gambar?** | Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Tiff` sesuai kebutuhan Anda. |
| **Bagaimana jika string data lebih pendek?** | Format DataBar secara otomatis menyesuaikan ukuran simbol; Anda tidak perlu mengubah pengaturan tata letak. |
| **Bagaimana cara mengatur ukuran barcode (lebar/tinggi)?** | Gunakan `generator.Parameters.Image.Width` dan `generator.Parameters.Image.Height` sebelum memanggil `Save`. |
| **Apakah memungkinkan menambahkan keterangan yang dapat dibaca manusia?** | Atur `generator.Parameters.Barcode.CodeText` dan aktifkan `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **Versi .NET apa yang didukung?** | Aspose.BarCode mendukung .NET Standard 2.0, .NET 5/6, dan .NET Framework 4.6.1+. |

Menangani variasi ini membuat **contoh generator barcode** cukup kuat untuk penggunaan produksi.

## Tips Pro

* **Gunakan kembali objek generator hanya ketika tata letak tetap sama.** Membuat instance baru untuk setiap tata letak, seperti pada Langkah 4‑5, mencegah properti yang tidak sengaja terbawa.  
* **Validasi barcode yang dihasilkan** dengan `generator.Validate()` jika Anda perlu memastikan kepatuhan terhadap standar ISO/GS1.  
* **Pemrosesan batch:** Bungkus logika kolom dan baris dalam loop yang mengiterasi daftar konfigurasi tata letak. Ini mengurangi duplikasi kode ketika Anda memerlukan banyak variasi.

## Kesimpulan

**Contoh generator barcode** ini menunjukkan cara **menghasilkan barcode C#** yang menghasilkan baik barcode DataBar Expanded Stacked 4‑kolom maupun 3‑baris. Anda kini memiliki program lengkap yang dapat dijalankan, pemahaman tentang properti kunci (`Columns`, `Rows`), serta tips praktis untuk memperluas solusi.

Selanjutnya, jelajahi topik terkait seperti **menyesuaikan warna barcode**, **menyisipkan barcode dalam dokumen PDF**, atau **menghasilkan kode QR dengan Aspose.BarCode**. Setiap subjek tersebut dibangun di atas prinsip API yang sama seperti yang dibahas di sini.

Jangan ragu bereksperimen dengan string data yang berbeda, format gambar, dan kombinasi tata letak. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Contoh Generator Barcode di C# – Atur Kolom, Baris & Ekspor Gambar](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Hasilkan barcode Databar Aspose.BarCode menggunakan .NET API – Konfigurasi Baris & Kolom](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Contoh generator barcode di C# – atur lebar dan tinggi](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}