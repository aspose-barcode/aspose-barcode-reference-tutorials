---
category: general
date: 2026-10-24
description: Pelajari cara menghasilkan barcode PDF417 menggunakan Aspose.BarCode
  dalam C# dengan pengaturan kompak dan kontrol XDimension barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: id
lastmod: 2026-10-24
og_description: Hasilkan kode batang PDF417 di C# dengan Aspose.BarCode. Ikuti panduan
  lengkap ini untuk membuat gambar PDF417 yang kompak, mengontrol XDimension, dan
  mengatur kolom.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Buat kode batang PDF417 dengan Aspose.BarCode – C# langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Cara menghasilkan kode batang PDF417 dengan Aspose.BarCode di C#
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 dengan Aspose.BarCode di C#

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan solusi lengkap yang siap dijalankan. Anda akan melihat bagaimana Aspose.BarCode membuat prosesnya sederhana sekaligus memberi Anda kontrol detail atas **PDF417 kompak**, **barcode XDimension**, dan **kolom PDF417**.

Membuat barcode adalah kebutuhan umum untuk sistem inventaris, platform tiket, dan alur kerja dokumen. Pada akhir tutorial ini Anda akan memiliki program C# mandiri yang menghasilkan gambar PNG tajam dari barcode PDF417, siap disisipkan ke UI apa pun atau dicetak pada label.

## Apa yang Anda perlukan

- .NET 6.0 SDK atau lebih baru (kode juga berfungsi dengan .NET Framework 4.6+)
- Visual Studio 2022 atau editor C# pilihan Anda
- Lisensi Aspose.BarCode untuk .NET yang valid (versi percobaan gratis cukup untuk pengembangan)
- Familiaritas dasar dengan sintaks C#

> **Pro tip:** Jika Anda sedang mengevaluasi Aspose.BarCode, unduh versi percobaan dari situs resmi dan tambahkan paket NuGet `Aspose.BarCode` ke proyek Anda. Versi percobaan menambahkan watermark kecil pada gambar yang dihasilkan, yang akan hilang setelah Anda menerapkan lisensi.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka terminal di folder solusi Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini mengambil versi stabil terbaru (per Oktober 2026, versi 23.12). Menambahkan paket ini memulihkan namespace `Aspose.BarCode.Generation` yang akan Anda gunakan untuk **menghasilkan gambar barcode PDF417**.

## Langkah 2: Buat proyek konsol C# dasar

Jika belum memiliki proyek, buat satu:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Buka `Program.cs`. Kerangka sudah berisi metode `Main` tempat kita akan menempatkan kode pembuatan barcode.

## Langkah 3: Inisialisasi generator barcode

Pertama, impor namespace yang diperlukan:

```csharp
using Aspose.BarCode.Generation;
```

Kemudian, di dalam `Main`, buat instance `BarcodeGenerator` dengan simbolologi PDF417 dan data yang ingin Anda enkode:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

String tersebut mencakup karakter Unicode untuk mendemonstrasikan bahwa Aspose.BarCode menangani input non‑ASCII dengan benar. Jika Anda hanya membutuhkan ASCII, ganti teks dengan string biasa apa saja.

## Langkah 4: Sesuaikan barcode XDimension (ukuran modul)

**barcode XDimension** menentukan lebar bar terkecil (modul). Menetapkannya dalam piksel memberi Anda kontrol pixel‑perfect atas ukuran gambar akhir:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nilai `2` piksel menghasilkan gambar kompak tanpa mengorbankan keandalan pemindaian. Tingkatkan nilai untuk barcode yang lebih besar atau turunkan untuk tata letak yang sangat padat.

## Langkah 5: Konfigurasikan opsi PDF417 kompak

Dua pengaturan khusus PDF417 secara dramatis memengaruhi jejak visual:

| Pengaturan | Arti | Nilai tipikal untuk output kompak |
|------------|------|-----------------------------------|
| `Columns` | Jumlah kolom data | `3` |
| `Truncate` (mode kompak) | Menghilangkan zona tenang di sisi kanan dan mengurangi jumlah baris | `true` |

Terapkan seperti berikut:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Menggunakan **kolom PDF417** yang diset ke `3` bersama dengan `Truncate = true` menciptakan barcode *PDF417 kompak* yang muat dengan baik pada label standar sekaligus tetap dapat dibaca oleh sebagian besar scanner.

## Langkah 6: Simpan gambar barcode

Akhirnya, tulis barcode ke disk. Contoh ini menyimpan PNG, tetapi Aspose.BarCode juga mendukung BMP, JPEG, GIF, TIFF, dan SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Konstanta `BarCodeImageFormat.Png` memberi tahu perpustakaan untuk menghasilkan PNG lossless, yang ideal untuk pemrosesan lebih lanjut atau pencetakan.

## Kode sumber lengkap yang dapat dijalankan

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Menjalankan program akan menghasilkan `CompactPdf417.png` di folder root proyek. Buka file tersebut dengan penampil gambar apa saja; Anda akan melihat barcode PDF417 yang rapat yang mengenkode string *Åspóse.Barcóde©*.

![Screenshot of generated PDF417 barcode using Aspose.BarCode](placeholder-image.png "Generated PDF417 barcode")

*Teks alt gambar: Tangkapan layar barcode PDF417 yang dihasilkan menggunakan Aspose.BarCode* – teks alt ini mengandung kata kunci utama untuk aksesibilitas dan SEO.

## Memverifikasi hasilnya

1. Buka file PNG. Barcode harus terdiri dari tiga kolom data vertikal dengan tata letak kompak (tanpa zona tenang tambahan di sisi kanan).
2. Pindai gambar dengan pemindai barcode smartphone yang mendukung PDF417. Teks yang terdekripsi harus cocok dengan string input asli.
3. Jika pemindai gagal, coba tingkatkan `XDimension.Pixels` menjadi `3` atau `4`. Modul yang lebih besar meningkatkan keterbacaan pada perangkat beresolusi rendah.

## Variasi umum dan kasus tepi

### 1. Mengubah format gambar

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG berbasis vektor, yang menjaga barcode tetap tajam pada tingkat zoom apa pun—berguna untuk halaman web.

### 2. Mengenkode sejumlah besar data

PDF417 dapat menyimpan hingga ~1,1 KB teks. Ketika payload melebihi kapasitas tiga kolom, perpustakaan secara otomatis menambah baris. Untuk menjaga barcode tetap kompak, Anda dapat:

- Mengurangi panjang data (misalnya, gunakan identifier alih-alih pesan lengkap)
- Menambah jumlah **kolom PDF417** (misalnya, `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Menggunakan lisensi untuk menghapus watermark percobaan

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Letakkan file lisensi di samping executable. Setelah lisensi diterapkan, gambar yang dihasilkan tidak lagi memiliki watermark.

### 4. Menangani pengecualian

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Kegagalan umum meliputi izin menulis yang tidak cukup atau format gambar yang tidak didukung.

## Mengapa pengaturan ini penting

- **barcode XDimension** – Mengontrol berat visual tiap bar. Terlalu kecil membuat barcode tidak terbaca; terlalu besar membuang ruang.
- **kolom PDF417** – Lebih sedikit kolom menghasilkan barcode yang lebih sempit tetapi menambah jumlah baris.

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Generate PDF417 barcode with compact settings in C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}