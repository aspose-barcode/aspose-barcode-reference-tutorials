---
category: general
date: 2026-09-19
description: Cara menghasilkan barcode menggunakan Aspose di C# – panduan langkah
  demi langkah untuk membuat barcode dengan Aspose secara cepat dan andal.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: id
lastmod: 2026-09-19
og_description: Cara menghasilkan barcode dengan Aspose di C#. Ikuti panduan ini untuk
  membuat barcode dengan Aspose, mengonfigurasi MacroPdf417, dan menyimpannya sebagai
  PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Cara menghasilkan barcode dengan Aspose – panduan lengkap C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Cara menghasilkan barcode dengan Aspose di C#
url: /id/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode dengan Aspose di C#

Cara menghasilkan barcode di C# sangat mudah ketika Anda menggunakan pustaka Aspose.BarCode. Tutorial ini menunjukkan cara **membuat barcode dengan Aspose** langkah demi langkah, mencakup format MacroPdf417, pengaturan tampilan umum, dan cara menyimpan hasilnya sebagai gambar PNG.

Anda akan belajar cara:

* Menginstal dan mereferensikan Aspose.BarCode untuk .NET  
* Mengonfigurasi properti khusus MacroPdf417 seperti file ID, segment ID, dan checksum  
* Menyesuaikan opsi visual seperti X‑dimension dan jumlah kolom  
* Mengekspor barcode ke file gambar  

Tidak diperlukan pengalaman sebelumnya dengan Aspose—hanya pemahaman dasar tentang C# dan Visual Studio.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

| Persyaratan | Detail |
|-------------|--------|
| .Runtime .NET | .NET 6.0 atau lebih baru (kode juga bekerja dengan .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider, atau editor apa pun yang mendukung C# |
| Aspose.BarCode | Paket NuGet `Aspose.BarCode` (versi percobaan gratis atau berlisensi) |
| Pengetahuan dasar C# | Familiaritas dengan pernyataan `using` dan inisialisasi objek |

Anda dapat menambahkan Aspose.BarCode ke proyek Anda melalui NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Cara menghasilkan barcode di C# – alur kerja keseluruhan

Proses terdiri dari empat langkah logis:

1. **Buat instance `BarcodeGenerator`** dengan tipe enkoding yang diinginkan (MacroPdf417) dan teks yang ingin Anda enkode.  
2. **Atur opsi tampilan umum** seperti X‑dimension dan jumlah kolom.  
3. **Konfigurasikan properti khusus MacroPdf417** seperti file ID, segment ID, dan timestamp.  
4. **Simpan barcode** ke format file pilihan Anda (PNG dalam contoh ini).  

Setiap langkah dijelaskan secara detail di bawah ini.

## Langkah 1: Buat generator barcode untuk MacroPdf417

Kelas `BarcodeGenerator` adalah titik masuk untuk semua tugas pembuatan barcode. Saat Anda menginstansiasinya, Anda memberikan dua argumen:

* `EncodeTypes.MacroPdf417` – memberi tahu Aspose untuk menggunakan simbolik MacroPdf417.  
* String data – teks yang akan dienkode di dalam barcode.  

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Mengapa ini penting:** MacroPdf417 adalah barcode dua dimensi yang dapat membawa sejumlah besar data dan mendukung fitur makro seperti segmentasi file, yang berguna untuk mentransmisikan file besar secara bertahap.

## Langkah 2: Atur opsi tampilan barcode umum

Meskipun MacroPdf417 memiliki banyak pengaturan khusus, Anda tetap ingin mengontrol kepadatan visual dan tata letak. Parameter yang paling umum adalah:

* **X‑dimension** – lebar modul terkecil (pixel). Nilai yang lebih kecil menghasilkan gambar yang lebih padat.  
* **Columns** – jumlah kolom data per baris; angka yang lebih besar mengurangi tinggi barcode.  

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Tip:** Jaga `XDimension` antara 2 hingga 4 piksel untuk kebanyakan skenario tampilan layar. Nilai yang lebih besar meningkatkan keterbacaan pada printer beresolusi rendah tetapi meningkatkan ukuran gambar secara keseluruhan.

## Langkah 3: Konfigurasikan properti khusus MacroPdf417

MacroPdf417 menambahkan sekumpulan bidang metadata yang memungkinkan Anda membagi file besar menjadi beberapa segmen barcode. Properti berikut biasanya diperlukan:

| Properti | Tujuan |
|----------|--------|
| `MacroPdf417FileID` | Pengidentifikasi unik untuk seluruh file (maks 8 digit). |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (dimulai dari 0). |
| `MacroPdf417SegmentsCount` | Jumlah total segmen dalam file. |
| `MacroPdf417FileName` | Nama yang dapat dibaca manusia dari file asli. |
| `MacroPdf417Checksum` | Checksum CCITT‑16 opsional untuk deteksi kesalahan. |
| `MacroPdf417FileSize` | Ukuran file asli dalam byte. |
| `MacroPdf417TimeStamp` | Timestamp saat file dihasilkan. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | String opsional untuk mengidentifikasi penerima/pengirim. |
| `MacroPdf417Terminator` | Menentukan apakah barcode adalah segmen terakhir (`Set`) atau segmen tengah (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Mengapa bidang ini berguna:**  
> *Ketika Anda perlu mengirim dokumen besar melalui saluran berbandwidth rendah, Anda dapat membagi dokumen menjadi beberapa barcode MacroPdf417. Penerima akan merekonstruksi file asli dengan membaca metadata setiap segmen.*

## Langkah 4: Simpan barcode yang dihasilkan sebagai gambar

Aspose mendukung banyak format output: PNG, JPEG, BMP, TIFF, SVG, dan PDF. PNG adalah format lossless yang ideal untuk tampilan web atau UI.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Saat Anda menjalankan program, Anda akan menemukan file PNG yang terlihat mirip dengan ilustrasi di bawah.

![MacroPdf417 barcode generated with Aspose in C#](placeholder-image.png){.img-fluid alt="cara menghasilkan barcode dengan Aspose di C#"}

> **Output yang diharapkan:** PNG berukuran 300 × 150 piksel yang menampilkan barcode MacroPdf417 yang mengenkode teks “Sample” bersama dengan metadata makro yang Anda berikan.

## Contoh lengkap yang dapat dijalankan

Menggabungkan semuanya, berikut program lengkap yang dapat Anda salin, tempel, dan jalankan:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Jalankan program dengan `dotnet run` (atau tekan **F5** di Visual Studio). Setelah eksekusi, pastikan file PNG ada dan dapat dibuka tanpa error.

## Pertanyaan umum dan penanganan kasus tepi

### Bagaimana jika saya membutuhkan format gambar yang berbeda?
Aspose mendukung `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, dan `Pdf`. Cukup ganti `BarCodeImageFormat.Png` dengan nilai enum yang diinginkan.

### Bagaimana cara menghasilkan beberapa segmen secara otomatis?
Anda dapat menempatkan kode di atas di dalam loop, meningkatkan `MacroPdf417SegmentID` pada setiap iterasi dan memperbarui string data. Ingat untuk menjaga `MacroPdf417SegmentsCount` tetap konstan di semua segmen.

### Bagaimana jika data melebihi kapasitas satu simbol MacroPdf417?
MacroPdf417 dirancang untuk beban data besar, tetapi setiap barcode memiliki batas maksimum teoritis (≈ 1,1 KB per segmen). Bagi file sumber menjadi potongan yang sesuai dengan batas ini, lalu enkode setiap potongan sebagai segmen terpisah.

### Apakah checksum perlu dihitung secara manual?
Aspose dapat menghasilkan checksum CCITT‑16 secara otomatis jika Anda mengatur `MacroPdf417Checksum` ke `0`. Dalam contoh kami memberikan nilai tetap untuk ilustrasi; dalam kode produksi biasanya Anda membiarkan pustaka menghitungnya.

### Bagaimana saya dapat mengubah warna latar depan/latar belakang barcode?
Gunakan properti `BarColor` dan `BackColor`:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Kesimpulan

Anda sekarang tahu **cara menghasilkan barcode** di C# menggunakan Aspose.BarCode dan, khususnya, cara **membuat barcode dengan Aspose** untuk simbolik MacroPdf417. Tutorial ini mencakup instalasi, konfigurasi tampilan, dan bidang khusus makro.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah‑per‑Langkah](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cara Menghasilkan Gambar Barcode PDF417 di C# dengan Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}