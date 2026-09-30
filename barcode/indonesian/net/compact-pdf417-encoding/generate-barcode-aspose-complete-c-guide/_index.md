---
category: general
date: 2026-08-12
description: Buat barcode Aspose dengan Aspose.BarCode dan pelajari cara menghasilkan
  PDF417 dengan teks khusus dalam beberapa langkah mudah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: id
lastmod: 2026-08-12
og_description: Hasilkan barcode Aspose menggunakan Aspose.BarCode. Tutorial ini menunjukkan
  cara menghasilkan PDF417 dengan teks khusus, metadata makro, dan menyimpan hasilnya
  sebagai PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Buat barcode aspose – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Menghasilkan Barcode Aspose – Panduan Lengkap C#
url: /id/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan barcode aspose – panduan lengkap C#

Jika Anda perlu **generate barcode aspose** untuk simbol MacroPdf417, tutorial ini akan memandu Anda melalui seluruh proses. Anda akan melihat cara mengonfigurasi opsi khusus macro, menyematkan teks khusus, dan menyimpan barcode sebagai gambar PNG.

Membuat barcode dengan Aspose.BarCode menghilangkan perhitungan manual dan menjamin kepatuhan terhadap spesifikasi PDF417. Pada langkah‑langkah di bawah ini Anda juga akan belajar **how to generate pdf417** dengan metadata khusus seperti ID file, jumlah segmen, dan timestamp. Pada akhir panduan Anda akan memiliki contoh kode siap pakai yang dapat Anda masukkan ke proyek .NET mana pun.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 atau lebih baru (kode juga bekerja dengan .NET Framework 4.7+)
* Lisensi Aspose.BarCode untuk .NET yang valid (evaluasi gratis dapat digunakan untuk pengujian)
* Visual Studio 2022 atau IDE C# apa pun yang Anda sukai
* Familiaritas dasar dengan sintaks C# dan konsep berorientasi objek

Tidak ada paket NuGet tambahan yang diperlukan selain **Aspose.BarCode**.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka proyek Anda di Visual Studio, lalu jalankan perintah berikut di Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode`, yang berisi kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini.

## Langkah 2: Buat generator barcode untuk MacroPdf417

Baris pertama membuat instance `BarcodeGenerator` yang menargetkan simbol **MacroPdf417** dan menyematkan teks khusus yang ingin Anda enkode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Mengapa ini penting*: Enum `EncodeTypes.MacroPdf417` memberi tahu Aspose untuk memperlakukan barcode sebagai simbol PDF417 yang mendukung macro, yang memungkinkan pemecahan data besar menjadi beberapa segmen. String `"Åspóse.Barcóde©"` menunjukkan bahwa generator menangani karakter Unicode dengan benar.

## Langkah 3: Tentukan ukuran modul dasar

Ukuran modul mengontrol kepadatan visual barcode. Nilai piksel `2` menghasilkan gambar tajam yang mencetak dengan baik pada printer label standar.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Meningkatkan nilai membuat barcode lebih besar, sementara menurunkannya dapat menyebabkan masalah pemindaian pada perangkat beresolusi rendah.

## Langkah 4: Konfigurasikan opsi tata letak khusus PDF417 macro

MacroPdf417 memerlukan beberapa parameter tambahan. Pengaturan ini memungkinkan Anda memecah data menjadi beberapa file, mengidentifikasi setiap segmen, dan memverifikasi integritas.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Mengapa ini penting*: Properti `Columns` memengaruhi lebar barcode, sementara bidang macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) memungkinkan sistem hilir untuk menyusun kembali data asli dengan benar.

## Langkah 5: Tambahkan metadata macro tambahan

Aspose.BarCode memungkinkan Anda menyematkan bidang macro opsional seperti checksum, ukuran file, timestamp, dan informasi pengirim/penerima. Bidang‑bidang ini berguna untuk jejak audit dan deteksi kesalahan.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Mengapa ini penting*: Checksum melindungi dari kesalahan transmisi, sementara timestamp dan bidang pengirim memberikan konteks untuk pemrosesan hilir. Menetapkan `MacroPdf417Terminator` ke `Set` menandakan bahwa ini adalah segmen terakhir dalam rangkaian macro.

## Langkah 6: Simpan barcode sebagai gambar PNG

Akhirnya, tulis barcode yang dihasilkan ke disk. PNG mempertahankan kualitas lossless, yang ideal untuk pemindaian.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Ketika kode selesai, file `ExtPDF417Meta.png` berisi barcode MacroPdf417 resolusi tinggi yang mengenkode teks khusus dan semua metadata macro.

### Output yang diharapkan

Membuka `ExtPDF417Meta.png` menampilkan barcode berorientasi vertikal dengan baris dan kolom yang jelas terdefinisi. Memindai gambar dengan pembaca PDF417 apa pun mengembalikan string asli **Åspóse.Barcóde©** serta bidang macro yang Anda konfigurasikan (ID file, ID segmen, checksum, dll.).

## Cara menghasilkan pdf417 tanpa opsi macro (skenario alternatif)

Jika Anda hanya membutuhkan barcode PDF417 standar, hapus properti macro dan pertahankan konfigurasi dasar:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Potongan kode ini memperlihatkan **how to generate pdf417** dengan cepat ketika fungsi macro tidak diperlukan.

## Kesalahan umum dan tips profesional

| Masalah | Mengapa terjadi | Solusi |
|-------|----------------|-----|
| Barcode terlalu kecil untuk dipindai | X‑dimension disetel ke 1 piksel atau kolom terlalu tinggi | Gunakan setidaknya `2` piksel untuk `XDimension` dan pertahankan kolom antara `3` dan `9` untuk ukuran label tipikal |
| Karakter Unicode muncul sebagai � | Ketidaksesuaian encoding pada file proyek | Pastikan file proyek disimpan sebagai UTF‑8 dan file sumber berisi BOM yang benar |
| Bidang macro diabaikan oleh pemindai | `MacroPdf417Terminator` tidak disetel untuk segmen terakhir | Set `MacroPdf417Terminator = Pdf417MacroTerminator.Set` pada segmen akhir |
| File gambar rusak | Aliran output tidak ditutup dengan benar | Gunakan pernyataan `using` (seperti yang ditunjukkan) untuk menjamin disposisi generator |

## Contoh lengkap yang dapat dijalankan

Salin kode berikut ke aplikasi konsol baru dan jalankan. Program akan membuat barcode, menyimpannya, dan mencetak jalur output ke konsol.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Menjalankan program mencetak baris serupa dengan:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Buka file tersebut untuk memverifikasi output visual.

## Kesimpulan

Anda kini tahu cara **generate barcode aspose** untuk simbol MacroPdf417, menyematkan teks Unicode khusus, mengonfigurasi metadata macro, dan mengekspor hasilnya sebagai gambar PNG. Pola yang sama memungkinkan Anda **how to generate pdf417** tanpa opsi macro, dan Anda dapat menyesuaikan kode untuk format barcode lain yang didukung oleh Aspose.BarCode.

Selanjutnya, jelajahi topik terkait seperti **create barcode custom text** untuk kode QR, menambahkan filter warna dengan parameter `Color`, atau menyematkan barcode langsung ke dokumen PDF menggunakan Aspose.PDF. Bereksperimenlah dengan nilai `XDimension` dan jumlah kolom yang berbeda untuk menyempurnakan barcode sesuai printer atau pemindai spesifik Anda.

Selamat coding, dan nikmati keandalan yang dibawa Aspose.BarCode ke solusi barcode .NET Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara menghasilkan barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generate Barcode Java - Set Teks Kode menggunakan Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}