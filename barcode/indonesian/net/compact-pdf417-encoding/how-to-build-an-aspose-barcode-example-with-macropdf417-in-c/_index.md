---
category: general
date: 2026-10-12
description: Pelajari cara membuat contoh barcode Aspose dalam C# yang menghasilkan
  barcode MacroPdf417 dengan metadata lengkap dan membacanya kembali menggunakan BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: id
lastmod: 2026-10-12
og_description: Contoh barcode Aspose dalam C# yang menunjukkan cara menghasilkan
  barcode MacroPdf417 dengan metadata tersemat dan membacanya kembali menggunakan
  BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Buat contoh barcode Aspose dengan MacroPdf417 dalam C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Cara membuat contoh barcode Aspose dengan MacroPdf417 di C#
url: /id/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat contoh barcode Aspose dengan MacroPdf417 di C#

Jika Anda membutuhkan **contoh barcode Aspose** yang membuat barcode MacroPdf417 dan membaca metadata yang tertanam, panduan ini menunjukkan alur kerja lengkapnya. Anda akan melihat cara mengonfigurasi generator, menyematkan informasi tingkat‑file, menyimpan gambar, dan kemudian mendekode data yang sama dengan `BarCodeReader`.

Tutorial ini mencakup semua yang perlu Anda ketahui untuk **generasi barcode C#** dengan Aspose.BarCode, termasuk jebakan umum dan tips untuk menangani ID file besar atau timestamp khusus.

## Apa yang Anda butuhkan

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru (kode ini bekerja dengan .NET Core dan .NET Framework)
* Visual Studio 2022 atau IDE apa pun yang mendukung C#
* Lisensi Aspose.BarCode yang aktif (versi percobaan gratis cukup untuk pengembangan)
* Paket NuGet `Aspose.BarCode` terpasang di proyek Anda

Prasyarat ini menjamin contoh dapat dijalankan tanpa konfigurasi tambahan.

## Langkah 1: Siapkan proyek contoh barcode Aspose

Buat aplikasi konsol baru dan tambahkan pustaka Aspose.BarCode:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Paket `Aspose.BarCode` menyediakan `BarcodeGenerator`, `BarCodeReader`, dan semua tipe yang diperlukan untuk penanganan MacroPdf417.

### Mengapa langkah ini penting
Menambahkan paket NuGet menyelesaikan referensi ke enum `EncodeTypes`, `DecodeType`, dan `BarCodeImageFormat` yang akan digunakan nanti. Tanpa paket tersebut, kompiler tidak akan mengenali simbol‑simbol ini, dan contoh akan gagal pada saat build.

## Langkah 2: Buat generator barcode MacroPdf417

Buka **Program.cs** dan ganti kode templat dengan blok berikut. Blok ini membuat `BarcodeGenerator` yang dikonfigurasi untuk simbolologi MacroPdf417 dan mengatur parameter tampilan dasar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Penjelasan properti kunci

| Properti | Tujuan | Rentang tipikal / catatan |
|----------|--------|---------------------------|
| `MacroPdf417FileID` | Pengidentifikasi unik untuk seluruh file | Harus ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Indeks segmen saat ini | Mulai dari 0 |
| `MacroPdf417SegmentsCount` | Jumlah total segmen dalam file | Harus ≥ SegmentID |
| `MacroPdf417FileName` | Nama file yang dapat dibaca manusia | Hingga 255 karakter |
| `MacroPdf417Checksum` | Checksum CCITT‑16 dari file asli | Dihitung oleh alat eksternal bila diperlukan |
| `MacroPdf417FileSize` | Ukuran file asli dalam byte | Berguna untuk validasi |
| `MacroPdf417TimeStamp` | Tanggal/waktu pembuatan file | Gunakan UTC untuk konsistensi |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Informasi routing opsional | String apa saja hingga 255 karakter |
| `MacroPdf417Terminator` | Menandai segmen terakhir | Gunakan `Set` untuk segmen akhir |

Bidang‑bidang ini membentuk **metadata barcode** yang dapat diekstrak pembaca nanti.

## Langkah 3: Dekode barcode dan tampilkan metadata

Setelah menyimpan gambar, program yang sama melanjutkan dengan membuka file menggunakan `BarCodeReader`. Tambahkan kode berikut di dalam metode `Main`, setelah blok `using` sebelumnya:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Mengapa membaca kembali penting
`BarCodeReader` memvalidasi bahwa metadata yang Anda sematkan telah terkode dengan benar. Jika ada properti yang hilang atau berada di luar rentang, pembaca akan mengembalikan `null` untuk bidang tersebut, memungkinkan Anda menangani kesalahan secara elegan.

## Langkah 4: Jalankan dan verifikasi output

Jalankan program:

```bash
dotnet run
```

Anda seharusnya melihat output konsol yang mirip dengan:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Jika nilai‑nilai tersebut cocok dengan yang Anda tetapkan pada Langkah 2, **contoh barcode Aspose** berfungsi sebagaimana mestinya.

## Kasus tepi dan tips praktik terbaik

| Situasi | Hal yang perlu diwaspadai | Penanganan yang disarankan |
|---------|---------------------------|----------------------------|
| **FileID melebihi rentang 32‑bit** | Aspose melempar `ArgumentOutOfRangeException`. | Jaga ID ≤ 2 147 483 647 atau bagi file menjadi beberapa blok MacroPdf417. |
| **Timestamp dalam waktu lokal** | Pembaca di zona waktu lain dapat salah menafsirkan nilai. | Simpan timestamp dalam UTC (`DateTime.UtcNow`) dan konversi saat ditampilkan bila diperlukan. |
| **Ukuran file besar** | `MacroPdf417FileSize` bertipe `int`; nilai > 2 GB akan overflow. | Gunakan bidang khusus atau bagi file menjadi segmen yang lebih kecil. |
| **Segmen hilang** | Jika `SegmentID` tidak berurutan, rekonstruksi gagal. | Validasi urutan segmen sebelum enkoding atau gunakan pengaturan koreksi kesalahan. |
| **Format gambar tidak didukung** | Menyimpan sebagai BMP dapat meningkatkan ukuran secara dramatis. | PNG adalah pilihan default yang baik; JPEG dapat dipakai jika Anda menerima kompresi lossy. |

**Pro tip:** Saat Anda menghasilkan banyak barcode secara batch, gunakan satu instance `BarcodeGenerator` dan hanya ubah `EncodeTypes` serta teks sumber. Ini mengurangi alokasi memori dan mempercepat proses.

## Topik terkait yang dapat Anda jelajahi selanjutnya

* **Simbolologi makro lainnya** – Aspose juga mendukung MacroPdf417 dengan level koreksi kesalahan.
* **Menyematkan barcode dalam PDF** – Gabungkan `Aspose.PDF` dengan generator barcode untuk menghasilkan dokumen yang dapat dicetak.
* **Integrasi ASP.NET Core** – Layani barcode yang dihasilkan langsung dari API web.
* **Pemindaian via perangkat seluler** – Gunakan SDK `Aspose.BarCode.Cloud` untuk dekoding lintas platform.

Subjek‑subjek lanjutan ini secara alami memperluas **contoh barcode Aspose** dan memperdalam keahlian Anda dalam **generasi barcode C#**.

## Kesimpulan

Anda kini memiliki **contoh barcode Aspose** yang berfungsi penuh: membuat barcode MacroPdf417, menyematkan **metadata barcode** yang kaya, menyimpan gambar, dan membaca kembali data dengan `BarCodeReader`. Dengan mengikuti langkah‑langkah di atas, Anda dapat menyesuaikan kode untuk ID file, timestamp, atau bahkan tipe barcode lain yang didukung Aspose.

Silakan bereksperimen dengan bidang metadata tambahan, ubah format gambar, atau integrasikan generator ke dalam aplikasi yang lebih besar. Selamat coding!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}