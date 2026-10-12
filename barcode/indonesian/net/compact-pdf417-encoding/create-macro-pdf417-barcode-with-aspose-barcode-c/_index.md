---
category: general
date: 2026-09-22
description: Buat barcode macro PDF417 menggunakan Aspose.BarCode di C#. Pelajari
  langkah demi langkah cara menghasilkan barcode dengan Aspose, mengonfigurasi metadata,
  dan menyimpannya sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: id
lastmod: 2026-09-22
og_description: Buat kode batang macro PDF417 menggunakan Aspose.BarCode di C#. Panduan
  ini menunjukkan cara menghasilkan kode batang dengan Aspose, mengatur metadata macro,
  dan mengekspor gambar.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Buat kode batang macro PDF417 dengan Aspose.BarCode (C#) – panduan langkah
  demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Buat barcode macro PDF417 dengan Aspose.BarCode (C#)
url: /id/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode macro PDF417 dengan Aspose.BarCode (C#)

Jika Anda perlu **membuat barcode macro PDF417** dalam aplikasi .NET, tutorial ini menunjukkan secara tepat cara melakukannya dengan Aspose.BarCode. Anda akan melihat contoh lengkap yang dapat dijalankan yang **menghasilkan barcode dengan Aspose**, mengonfigurasi semua bidang khusus macro, dan menyimpan hasilnya sebagai gambar PNG.

Barcode sering digunakan untuk inventaris, pengiriman, atau pelacakan dokumen, dan varian Macro PDF417 memungkinkan Anda menyematkan metadata tingkat file tambahan di dalam barcode itu sendiri. Pada akhir panduan ini Anda akan dapat menghasilkan barcode macro PDF417 yang lengkap dan mematuhi standar ISO/IEC 15438.

## Apa yang Anda butuhkan

* .NET 6.0 SDK atau yang lebih baru (kode ini bekerja dengan .NET Core dan .NET Framework)
* Visual Studio 2022 (atau IDE C# apa pun)
* Koneksi internet yang kompatibel dengan NuGet untuk mengunduh paket Aspose.BarCode
* Familiaritas dasar dengan sintaks C#

Prasyarat ini memastikan kode dapat dikompilasi tanpa konfigurasi tambahan.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Pustaka Aspose.BarCode menyediakan kelas `BarcodeGenerator` yang digunakan di seluruh tutorial ini.

```bash
dotnet add package Aspose.BarCode
```

Menjalankan perintah tersebut menambahkan versi stabil terbaru ke file proyek Anda (`*.csproj`). Paket ini mencakup dukungan untuk PDF417, Macro PDF417, dan banyak simbol lainnya.

## Langkah 2: Buat proyek konsol baru (opsional)

Jika Anda lebih suka memulai dari awal yang bersih, buat aplikasi konsol:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

File `Program.cs` yang dihasilkan akan menampung kode pembuatan barcode.

## Langkah 3: Inisialisasi generator barcode

Generator dibuat dengan nilai enum `EncodeTypes.MacroPdf417` dan teks yang ingin Anda enkode. Aspose.BarCode secara otomatis menangani karakter Unicode, sehingga Anda dapat menyertakan huruf beraksen atau simbol secara langsung.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Mengapa ini penting
`EncodeTypes.MacroPdf417` memberi tahu pustaka untuk menggunakan versi macro dari PDF417, yang menambahkan kemampuan menyematkan metadata tingkat file (ID file, jumlah segmen, dll.). Teks "Åspóse.Barcóde©" menunjukkan bahwa generator mengenkode karakter UTF‑8 dengan benar.

## Langkah 4: Atur dimensi dasar barcode

PDF417 memungkinkan Anda mengontrol jumlah kolom dan dimensi X (lebar satu modul). Menyesuaikan nilai-nilai ini memengaruhi ukuran fisik barcode dan keandalan pemindaian.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Nilai yang lebih kecil menghasilkan barcode yang lebih padat; nilai yang lebih besar memudahkan pemindai beresolusi rendah.
* **Columns** – Mengontrol jumlah kolom data; nilai tipikal berkisar antara 1 hingga 30.

## Langkah 5: Konfigurasikan metadata Macro PDF417

Macro PDF417 membawa bidang tambahan yang menjelaskan file yang diwakili oleh barcode. Setiap bidang bersifat opsional, tetapi mengaturnya meningkatkan interoperabilitas dengan pemindai yang memahami format macro.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Penjelasan masing‑masing bidang

| Properti | Tujuan | Rentang tipikal |
|----------|--------|-----------------|
| **MacroPdf417FileID** | Pengidentifikasi unik untuk file logis yang dapat dibagi menjadi beberapa barcode. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Indeks segmen saat ini (dimulai dari 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Jumlah total segmen yang membentuk file lengkap. | 1‑99 |
| **MacroPdf417FileName** | Nama file yang dapat dibaca manusia. | Up to 255 characters |
| **MacroPdf417Checksum** | Checksum opsional untuk deteksi kesalahan. | 0‑65535 |
| **MacroPdf417FileSize** | Ukuran file asli dalam byte. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Timestamp pembuatan atau modifikasi file. | Any `DateTime` |
| **MacroPdf417Addressee** | Identifikasi tujuan (misalnya, departemen atau mesin). | Free‑form string |
| **MacroPdf417Sender** | Identifikasi asal (misalnya, nama perusahaan). | Free‑form string |
| **MacroPdf417Terminator** | Menunjukkan apakah segmen ini adalah yang terakhir. | `Set` or `Unset` |

**Tips profesional:** Jika Anda membagi file besar menjadi beberapa barcode, pastikan `SegmentID` setiap segmen berurutan dan `SegmentsCount` tetap konstan di semua segmen. Pemindai bergantung pada nilai-nilai ini untuk merekonstruksi file asli.

## Langkah 6: Simpan gambar barcode

Aspose.BarCode mendukung banyak format output (PNG, JPEG, BMP, SVG, dll.). PNG memberikan kualitas lossless, yang ideal untuk pengujian dan dokumentasi.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Menjalankan program akan membuat file bernama `ExtPDF417Meta.png` di direktori output proyek (`bin/Debug/net6.0/`). Buka gambar dengan penampil apa pun untuk memverifikasi bahwa barcode ditampilkan dengan benar.

## Langkah 7: Verifikasi barcode yang dihasilkan (opsional)

Jika Anda memiliki aplikasi pemindai PDF417 (mobile atau desktop), pindai PNG yang disimpan. Pemindai harus mengembalikan:

* Teks yang dienkode `"Åspóse.Barcóde©"`
* Semua bidang macro yang Anda konfigurasikan (ID file, ID segmen, dll.)

Untuk verifikasi otomatis, Aspose.BarCode juga menyediakan kelas `BarCodeReader`:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Potongan kode ini menunjukkan cara membaca kembali metadata macro secara programatik, mengonfirmasi bahwa **menghasilkan barcode dengan Aspose** berfungsi end‑to‑end.

## Kasus tepi dan praktik terbaik

| Situasi | Penanganan yang disarankan |
|-----------|----------------------|
| **Unicode characters** | Pastikan string sumber dalam format UTF‑8 (default di .NET). Aspose.BarCode secara otomatis mengenkode Unicode, tetapi verifikasi set karakter pemindai. |
| **Large file size** | Macro PDF417 membagi file menjadi hingga 99 segmen. Jika file melebihi 400 KB, tingkatkan `SegmentsCount` dan buat beberapa barcode, masing‑masing dengan `SegmentID` berurutan. |
| **Timestamp precision** | Gunakan `DateTime.UtcNow` untuk waktu universal; beberapa pemindai mengharapkan UTC. |
| **Checksum validation** | Berikan checksum yang benar jika Anda berencana memvalidasi integritas di sisi penerima. |
| **Different image formats** | Gunakan `BarCodeImageFormat.Svg` untuk grafik vektor ketika Anda membutuhkan barcode yang dapat diskalakan tak terbatas. |
| **Performance** | Gunakan kembali satu instance `BarcodeGenerator` saat menghasilkan banyak barcode; hanya ubah `Parameters` di antara iterasi. |

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan tanpa modifikasi (dengan asumsi paket NuGet telah diinstal).



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Contoh barcode Aspose: menghasilkan Macro PDF417 dalam C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Buat Metadata Barcode PDF417 dalam C# – Panduan Lengkap Langkah‑per‑Langkah](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Cara Menghasilkan Gambar Barcode PDF417 dalam C# dengan Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}