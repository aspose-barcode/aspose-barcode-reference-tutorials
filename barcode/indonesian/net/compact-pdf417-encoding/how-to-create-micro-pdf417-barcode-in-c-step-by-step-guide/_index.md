---
category: general
date: 2026-08-22
description: Pelajari cara membuat kode batang micro PDF417 di C# dan menghasilkan
  gambar PNG kode batang. Termasuk mengatur dimensi kode batang dan menyimpan file.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: id
lastmod: 2026-08-22
og_description: Buat kode batang micro PDF417 dalam C# dan ekspor sebagai PNG. Ikuti
  panduan ini untuk mengatur dimensi kode batang dan menghasilkan gambar kode batang
  dengan cepat.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Buat barcode micro PDF417 di C# – tutorial pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Cara membuat barcode micro PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat micro PDF417 barcode di C# – panduan langkah demi langkah

Jika Anda perlu **membuat micro PDF417 barcode** untuk sistem tiket, label inventaris, atau pemindaian seluler, tutorial ini menunjukkan secara tepat cara melakukannya. Anda akan melihat program C# lengkap yang menghasilkan barcode PNG, mempelajari cara mengatur dimensi barcode, dan memahami setiap opsi konfigurasi.

Pada akhir panduan ini Anda akan dapat menghasilkan gambar barcode resolusi tinggi, menyesuaikan X‑dimension, memilih jumlah kolom, dan menyimpan hasilnya sebagai file PNG—semua dengan beberapa baris kode.

## Apa yang Anda perlukan

- .NET 6.0 SDK atau yang lebih baru (kode ini bekerja dengan .NET Core dan .NET Framework)
- Visual Studio 2022 atau IDE apa pun yang kompatibel dengan C#
- Paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan apa pun yang mendukung `EncodeTypes.MicroPdf417`)
- Pemahaman dasar tentang sintaks C#

> **Pro tip:** Edisi komunitas gratis Aspose.BarCode sudah cukup untuk pengembangan dan pengujian. Untuk produksi, dapatkan lisensi untuk menghapus watermark evaluasi.

## Langkah 1: Instal perpustakaan barcode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Ini menambahkan assembly `Aspose.BarCode`, yang menyediakan kelas `BarcodeGenerator` yang digunakan untuk **membuat aplikasi gambar barcode C#**.

## Langkah 2: Inisialisasi generator – buat barcode micro PDF417

Baris pertama yang dapat dijalankan membuat instance `BarcodeGenerator` yang dikonfigurasi untuk simbolik Micro PDF417 dan menyediakan data yang ingin Anda enkode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Mengapa ini penting*: Enum `EncodeTypes.MicroPdf417` memberi tahu perpustakaan untuk menggunakan versi kompak PDF417, yang ideal untuk label kecil dan layar seluler.

## Langkah 3: Cara mengatur dimensi barcode di C#

Penyetelan halus lebar modul (X‑dimension) mengontrol kepadatan visual barcode. Nilai yang lebih kecil menghasilkan gambar yang lebih tajam, sementara nilai yang lebih besar membuat barcode lebih mudah dipindai dari jarak jauh.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Mengapa Anda harus mengatur dimensi**: Tanpa menyesuaikan X‑dimension, nilai default dapat menghasilkan barcode yang tampak buram saat dirender pada DPI tinggi. Mengaturnya ke 2 piksel adalah keseimbangan yang baik untuk kebanyakan pemindaian berbasis layar.

## Langkah 4: Pilih jumlah kolom – mengontrol lebar barcode

Micro PDF417 memungkinkan antara 1 hingga 4 kolom. Lebih banyak kolom mengompres data secara horizontal, mengurangi lebar gambar secara keseluruhan.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Kasus tepi*: Jika Anda meminta 5 kolom, perpustakaan akan melempar `ArgumentOutOfRangeException`. Selalu tetap dalam rentang yang didokumentasikan.

## Langkah 5: Cara menghasilkan barcode PNG – menyimpan gambar

Sekarang Anda dapat mengekspor barcode yang dihasilkan ke file PNG. PNG mempertahankan kualitas lossless, yang penting untuk pemindaian yang dapat diandalkan.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Saat Anda menjalankan program, Anda akan melihat pesan konsol yang mengonfirmasi lokasi file. `MicroPdf417.png` yang dihasilkan terlihat seperti ini:

![Tangkapan layar yang menunjukkan barcode micro PDF417 yang dihasilkan dengan C#](micro-pdf417-example.png "Barcode micro PDF417 yang dihasilkan")

*Teks alt gambar*: **barcode micro PDF417 yang dihasilkan dalam C#** – menunjukkan output akhir setelah menerapkan dimensi dan pengaturan kolom.

## Langkah 6: Jalankan dan verifikasi output

1. Bangun proyek: `dotnet build`.
2. Jalankan: `dotnet run`.
3. Buka `MicroPdf417.png` di desktop Anda dan pindai dengan aplikasi pemindai barcode seluler.

Anda harus melihat teks **“Sample text”** terdekripsi. Jika pemindai melaporkan kesalahan, periksa kembali X‑dimension dan jumlah kolom – nilai ekstrem dapat membuat barcode terlalu padat untuk beberapa perangkat.

## Variasi umum dan pemecahan masalah

| Situation | Adjustment |
|-----------|------------|
| **Butuh barcode lebih besar untuk printer beresolusi rendah** | Increase `XDimension.Pixels` to 3 or 4. |
| **Ingin barcode lebih tinggi tanpa mengubah lebar** | Set `generator.Parameters.Barcode.Pdf417.Rows` (rows range 3‑90). |
| **Membuat beberapa barcode dalam loop** | Re‑use the same `BarcodeGenerator` instance and only change `CodeText` before each `Save`. |
| **Menyimpan sebagai JPEG bukan PNG** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. |
| **Menjalankan pada .NET Framework 4.7** | The same code works; just reference the appropriate `Aspose.BarCode.dll`. |

## Daftar sumber lengkap (dapat dijalankan)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Output yang diharapkan** – file PNG 200 × 100 piksel yang berisi barcode Micro PDF417 yang tajam dan mendekode menjadi “Sample text”.

## Kesimpulan

Anda sekarang tahu cara **membuat barcode micro PDF417** di C#, **mengatur dimensi barcode**, dan **menghasilkan gambar barcode PNG**. Contoh lengkap ini menunjukkan setiap langkah yang diperlukan—dari instalasi perpustakaan hingga menyimpan file akhir—sehingga Anda dapat menyematkan pembuatan barcode langsung ke dalam aplikasi Anda.

Selanjutnya, jelajahi topik terkait seperti **membuat kode QR dengan Aspose.BarCode**, **menyesuaikan warna**, atau **menyematkan barcode dalam dokumen PDF**. Masing‑masingnya dibangun di atas dasar `BarcodeGenerator` yang sama yang dibahas di sini.

Silakan bereksperimen dengan string data yang berbeda, jumlah kolom, dan nilai X‑dimension untuk menyesuaikan lingkungan pemindaian Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Menghasilkan Barcode PDF417 – Enkoding PDF417 Kompak](/barcode/english/net/compact-pdf417-encoding/)
- [Cara membuat barcode Aztec dengan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}