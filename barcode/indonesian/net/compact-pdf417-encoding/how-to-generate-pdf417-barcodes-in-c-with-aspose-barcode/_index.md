---
category: general
date: 2026-09-10
description: Cara menghasilkan barcode PDF417 di C# menggunakan Aspose.BarCode. Ikuti
  panduan langkah demi langkah untuk membuat Macro PDF417, menyesuaikan parameter,
  dan mengekspor sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: id
lastmod: 2026-09-10
og_description: Cara menghasilkan kode batang PDF417 di C# dengan Aspose.BarCode.
  Pelajari alur kerja lengkap mulai dari penyiapan hingga menyimpan gambar Macro PDF417
  PNG.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Cara menghasilkan kode batang PDF417 di C# – panduan lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Cara menghasilkan kode batang PDF417 di C# dengan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 di C# dengan Aspose.BarCode

Jika Anda perlu **cara menghasilkan pdf417** dalam proyek .NET, tutorial ini menunjukkan alur kerja lengkap. Anda akan melihat cara membuat barcode Macro PDF417, menyesuaikan pengaturannya, dan mengekspor hasilnya sebagai gambar PNG—semua dengan Aspose.BarCode untuk .NET.

Menghasilkan barcode PDF417 umum digunakan dalam logistik, tiket, dan alur kerja dokumen aman. Pada akhir panduan ini Anda akan memiliki generator barcode C# siap pakai yang dapat Anda sisipkan ke dalam aplikasi apa pun.

## Apa yang Anda butuhkan

- **Visual Studio 2022** (atau IDE C# apa pun)  
- **.NET 6.0** atau lebih baru  
- **Aspose.BarCode for .NET** paket NuGet (`Install-Package Aspose.BarCode`)  
- Familiaritas dasar dengan sintaks C#  

> **Pro tip:** Gunakan versi Aspose.BarCode terbaru untuk mendapatkan fitur Macro PDF417 terbaru dan perbaikan bug.

---

## Cara menghasilkan barcode PDF417 di C#

Berikut adalah contoh yang dapat dijalankan sepenuhnya yang membuat barcode **Macro PDF417**, mengonfigurasi bidang khusus macro, dan menyimpan gambar.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Mengapa setiap langkah penting

1. **Buat generator Macro PDF417** – `EncodeTypes.MacroPdf417` memberi tahu Aspose.BarCode untuk menggunakan versi macro dari PDF417, yang mendukung pemecahan muatan besar ke beberapa simbol.  
2. **Sesuaikan tampilan dasar** – `XDimension` mengontrol lebar modul (titik); `Columns` menentukan berapa banyak kolom yang akan dimiliki setiap simbol, memengaruhi ukuran dan keterbacaan.  
3. **Setel bidang khusus macro** – Properti ini (`MacroPdf417FileID`, `MacroPdf417SegmentID`, dll.) diperlukan oleh spesifikasi macro PDF417 untuk menyusun kembali data asli di sisi pemindai.  
4. **Ekspor gambar** – `BarCodeImageFormat.Png` menyediakan gambar lossless yang bekerja baik untuk web, cetak, dan skenario seluler.

---

## Menyiapkan Aspose.BarCode untuk .NET (generator barcode C#)

Sebelum Anda dapat menjalankan kode di atas, Anda harus menambahkan pustaka Aspose.BarCode ke proyek Anda:

```bash
dotnet add package Aspose.BarCode
```

*Paket NuGet mencakup semua dependensi, jadi tidak diperlukan DLL tambahan.*  
Jika Anda menargetkan .NET Framework, perintah `Install-Package Aspose.BarCode` yang sama berfungsi dari Package Manager Console.

### Kesalahan umum

- **Lisensi hilang** – Secara default Aspose berjalan dalam mode evaluasi, yang menambahkan watermark pada barcode. Daftarkan file lisensi (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) untuk menghilangkannya.  
- **`EncodeTypes` tidak tepat** – Menggunakan `EncodeTypes.Pdf417` alih-alih `EncodeTypes.MacroPdf417` akan mengabaikan semua bidang macro, memutuskan rekonstruksi multi‑segmen.

---

## Mengonfigurasi parameter barcode Macro PDF417

Bidang macro memungkinkan Anda memecah dokumen besar menjadi beberapa simbol PDF417. Berikut referensi cepat:

| Properti | Tujuan | Rentang tipikal |
|----------|--------|-----------------|
| `MacroPdf417FileID` | Pengidentifikasi unik untuk file lengkap | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (dimulai dari 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Jumlah total segmen dalam file | 1‑255 |
| `MacroPdf417FileName` | Nama yang dapat dibaca manusia (opsional) | 0‑255 karakter |
| `MacroPdf417Checksum` | Checksum CCITT‑16 untuk deteksi kesalahan | 0‑65535 |
| `MacroPdf417FileSize` | Ukuran file asli dalam byte | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Stempel waktu pembuatan (opsional) | nilai `DateTime` |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadata opsional untuk pengiriman | String apa saja |
| `MacroPdf417Terminator` | Menunjukkan segmen akhir (`Set` atau `Unset`) | enum `Pdf417MacroTerminator` |

Sesuaikan nilai-nilai ini agar cocok dengan data yang Anda enkode. Misalnya, jika Anda memecah file 2 MB menjadi 20 segmen, setel `MacroPdf417FileSize` ke `2_000_000` dan `MacroPdf417SegmentsCount` ke `20`.

---

## Mengekspor barcode sebagai gambar PNG (ekspor gambar barcode)

Menyimpan barcode sebagai PNG adalah format ekspor paling umum karena mempertahankan tepi tajam dan mendukung transparansi. Aspose.BarCode juga mendukung JPEG, BMP, GIF, dan TIFF—pilih yang sesuai dengan proses hilir Anda.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Tips untuk output berkualitas tinggi**

- Tingkatkan `XDimension.Pixels` untuk modul yang lebih besar saat mencetak pada media resolusi tinggi.  
- Gunakan `BarCodeImageFormat.Tiff` dengan kompresi CCITT Group 4 untuk PDF yang kompatibel dengan faks.  
- Setel `generator.Parameters.ImageOptions.Resolution` jika Anda memerlukan DPI tertentu (mis., 300 dpi untuk cetak).

---

## Menguji dan memecahkan masalah barcode PDF417 Anda

1. **Verifikasi visual** – Buka `MacroPdf417.png` di penampil gambar apa pun. Anda harus melihat sekumpulan batang vertikal yang ditumpuk dengan keterangan teks kecil (data yang dienkode).  
2. **Uji pemindai** – Gunakan aplikasi pemindai barcode seluler yang mendukung PDF417. Pindai gambar; aplikasi harus mengembalikan “Sample text” asli plus metadata macro (file ID, segment ID, dll.).  
3. **Penanganan kesalahan** – Jika pemindai melaporkan “checksum error,” periksa kembali `MacroPdf417Checksum` dan pastikan `MacroPdf417Terminator` diset dengan benar pada segmen terakhir.  
4. **Kinerja** – Menghasilkan banyak segmen dalam loop dapat memakan banyak CPU. Gunakan kembali satu instance `BarcodeGenerator` dan hanya perbarui bidang macro antara penyimpanan untuk meningkatkan throughput.

---

## Kesimpulan

Anda kini tahu **cara menghasilkan PDF417** barcode di C# menggunakan Aspose.BarCode, mulai dari menginstal pustaka hingga mengonfigurasi bidang Macro PDF417 dan mengekspor gambar PNG bersih. Solusi lengkap ini menunjukkan:

- Menyiapkan **generator barcode C#** dengan tipe Macro PDF417  
- Menyesuaikan **parameter barcode PDF417** untuk data multi‑segmen  
- Melakukan **ekspor gambar barcode** untuk penggunaan hilir  

Dari sini Anda dapat menjelajahi topik lanjutan seperti menyematkan barcode dalam dokumen PDF, menghasilkan pasangan QR‑code, atau mengotomatiskan pemrosesan batch file besar.

**Langkah selanjutnya**

- Coba nilai `BarCodeImageFormat` yang berbeda (mis., `Tiff` untuk cetakan resolusi tinggi).  
- Gabungkan Macro PDF417 dengan simbol lain dalam dokumen yang sama menggunakan `generator.Parameters.Barcode.Symbology`.  
- Tinjau [Aspose.BarCode documentation](https://docs.aspose.com/barcode/net/) untuk opsi kustomisasi lebih dalam seperti tingkat koreksi kesalahan dan mode enkoding.

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Generate barcode with text – Panduan Lengkap Macro PDF417](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [adjust barcode size – Panduan C# untuk menghasilkan barcode PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Panduan Pemrograman Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}