---
category: general
date: 2026-11-20
description: Pelajari cara menghasilkan barcode dengan Aspose.Barcode di C#. Panduan
  ini memandu Anda membuat barcode MicroPdf417 dan menyimpannya sebagai gambar PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: id
lastmod: 2026-11-20
og_description: Cara menghasilkan barcode menggunakan Aspose.Barcode di C#. Ikuti
  tutorial lengkap ini untuk membuat barcode MicroPdf417 dan mengekspornya sebagai
  PNG.
og_image_alt: 'How to generate barcode: sample MicroPdf417 image produced by Aspose.Barcode'
og_title: Cara menghasilkan barcode dengan Aspose.Barcode – panduan langkah demi langkah
  C#
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  headline: How to generate barcode using Aspose.Barcode in C#
  type: TechArticle
- description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  name: How to generate barcode using Aspose.Barcode in C#
  steps:
  - name: Install the Aspose.Barcode NuGet package
    text: 'Open a terminal in your project folder and run:'
  - name: Create a `BarcodeGenerator` instance for MicroPdf417
    text: '```csharp using Aspose.Barcode.Generation;'
  - name: Adjust the X‑dimension (module width)
    text: '```csharp // Step 3: Set the module width in pixels – 2 px yields a clear,
      print‑ready image generator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: Choose the number of columns for the PDF417 component
    text: '```csharp // Step 4: Define how many columns the PDF417 component should
      use (1‑4 allowed) generator.Parameters.Barcode.Pdf417.Columns = 4; ```'
  - name: Save the barcode image
    text: '```csharp using System.IO;'
  - name: Full source code
    text: 'Putting all steps together yields a complete, self‑contained console application:'
  - name: Generating other symbologies
    text: 'If you want to **create barcode with Aspose** for QR codes, Code128, or
      UPC, replace `EncodeTypes.MicroPdf417` with the appropriate enum value, e.g.:'
  - name: Changing image format
    text: 'Aspose.Barcode supports multiple raster formats. To export as JPEG with
      90 % quality:'
  - name: Handling large data payloads
    text: MicroPdf417 can store up to 1 KB of data. For larger payloads switch to
      full `EncodeTypes.Pdf417` and adjust `Rows` and `Columns` accordingly.
  - name: Unicode and special characters
    text: The library automatically encodes Unicode strings. However, some legacy
      scanners only recognize ASCII. If you target such devices, limit the input to
      the ASCII range or use a different symbology that guarantees compatibility.
  type: HowTo
tags:
- barcode generation
- Aspose.Barcode
- C#
- MicroPdf417
title: Cara menghasilkan barcode menggunakan Aspose.Barcode di C#
url: /id/net/compact-pdf417-encoding/how-to-generate-barcode-using-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode menggunakan Aspose.Barcode di C#

Jika Anda perlu **cara menghasilkan barcode** untuk aplikasi desktop atau web, Aspose.Barcode menyediakan API yang sederhana. Tutorial ini menunjukkan secara tepat cara menghasilkan barcode MicroPdf417, menyesuaikan dimensinya, dan menyimpan hasilnya sebagai file PNG. Anda juga akan melihat cara **membuat barcode dengan Aspose** untuk format lain tanpa meninggalkan IDE.

Menghasilkan barcode adalah kebutuhan umum untuk sistem inventaris, platform tiket, dan alur kerja dokumen yang aman. Pada akhir panduan ini Anda akan memiliki program yang dapat dijalankan yang menghasilkan gambar barcode berkualitas tinggi siap untuk dicetak atau disematkan.

## Apa yang Anda butuhkan

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
* Visual Studio 2022 (atau editor C# apa pun)
* Lisensi yang valid untuk Aspose.Barcode untuk .NET – percobaan gratis dapat digunakan untuk pengembangan dan pengujian
* Pemahaman dasar tentang sintaks C#

Tidak ada paket NuGet tambahan yang diperlukan selain `Aspose.Barcode`.

## Cara menghasilkan barcode dengan Aspose.Barcode

Bagian-bagian berikut memecah proses menjadi langkah‑langkah terpisah. Setiap langkah menjelaskan **mengapa** kode tersebut diperlukan, bukan hanya **apa** yang dilakukannya.

### Langkah 1: Instal paket NuGet Aspose.Barcode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.Barcode
```

Perintah ini menambahkan versi stabil terbaru dari Aspose.Barcode ke file proyek Anda, memastikan kelas `BarcodeGenerator` tersedia saat kompilasi.

**Mengapa ini penting:** Paket tersebut berisi mesin rendering inti dan sekumpulan `EncodeTypes` yang telah ditentukan. Tanpa paket ini kompiler tidak dapat menemukan `BarcodeGenerator` atau `EncodeTypes`.

### Langkah 2: Buat instance `BarcodeGenerator` untuk MicroPdf417

```csharp
using Aspose.Barcode.Generation;

// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 is a compact 2‑D barcode
    "Åspóse.Barcóde©");               // Sample text – Unicode characters are supported
```

**Mengapa ini penting:** Konstruktor mengaitkan simbolologi (`EncodeTypes.MicroPdf417`) dengan data mentah yang ingin Anda enkode. MicroPdf417 ideal ketika Anda membutuhkan jejak yang lebih kecil dibandingkan PDF417 penuh sambil tetap mendukung data alfanumerik.

### Langkah 3: Sesuaikan dimensi X (lebar modul)

```csharp
// Step 3: Set the module width in pixels – 2 px yields a clear, print‑ready image
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa ini penting:** Dimensi X menentukan ukuran setiap sel barcode. Nilai yang terlalu rendah menghasilkan gambar buram; nilai yang terlalu tinggi membuat barcode terlalu besar. Dua piksel adalah nilai default yang seimbang untuk kebanyakan skenario layar dan cetak.

### Langkah 4: Pilih jumlah kolom untuk komponen PDF417

```csharp
// Step 4: Define how many columns the PDF417 component should use (1‑4 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Mengapa ini penting:** MicroPdf417 secara internal menggunakan komponen PDF417. Menyesuaikan jumlah kolom memengaruhi rasio aspek dan kapasitas data barcode. Empat kolom memberikan bentuk yang kompak sambil mempertahankan keterbacaan.

### Langkah 5: Simpan gambar barcode

```csharp
using System.IO;

// Step 5: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
```

**Mengapa ini penting:** `Save` menulis barcode yang telah dirender ke disk. PNG bersifat loss‑less, sehingga menjaga tepi tajam yang penting bagi pemindai. Anda dapat mengganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` jika alur kerja Anda memerlukan format lain.

### Kode sumber lengkap

Menggabungkan semua langkah menghasilkan aplikasi konsol yang lengkap dan mandiri:

```csharp
using System;
using System.IO;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with MicroPdf417 symbology and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©");

            // Configure visual appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Determine output location (Desktop for easy access)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");

            // Save the barcode image as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
    }
}
```

Jalankan program (`dotnet run`) dan Anda akan menemukan `MicroPdf417.png` di desktop Anda. Membuka file tersebut menampilkan barcode MicroPdf417 yang tajam dan mengenkode teks `"Åspóse.Barcóde©"`.

## Memverifikasi barcode

Untuk memastikan barcode telah dihasilkan dengan benar:

1. Buka PNG di penampil gambar apa pun.
2. Gunakan aplikasi pemindai barcode seluler yang mendukung PDF417 atau MicroPdf417.
3. Pindai gambar; aplikasi harus menampilkan teks asli, termasuk karakter khusus.

Jika pemindai gagal, periksa hal berikut:

* **Dimensi X:** Nilai di bawah 1 px dapat menyebabkan artefak rendering.
* **Jumlah kolom:** Nilai di luar 1‑4 akan memicu pengecualian.
* **Set karakter:** Aspose.Barcode mendukung UTF‑8; pastikan file sumber disimpan dengan encoding UTF‑8.

## Variasi umum dan kasus khusus

### Menghasilkan simbol lain

Jika Anda ingin **membuat barcode dengan Aspose** untuk QR code, Code128, atau UPC, ganti `EncodeTypes.MicroPdf417` dengan nilai enum yang sesuai, misalnya:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Semua langkah konfigurasi lainnya (dimensi X, penyimpanan) tetap sama.

### Mengubah format gambar

Aspose.Barcode mendukung berbagai format raster. Untuk mengekspor sebagai JPEG dengan kualitas 90 %:

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg, 90);
```

### Menangani payload data besar

MicroPdf417 dapat menyimpan hingga 1 KB data. Untuk payload yang lebih besar, beralihlah ke `EncodeTypes.Pdf417` penuh dan sesuaikan `Rows` serta `Columns` sesuai kebutuhan.

### Unicode dan karakter khusus

Pustaka secara otomatis mengenkode string Unicode. Namun, beberapa pemindai lama hanya mengenali ASCII. Jika Anda menargetkan perangkat tersebut, batasi input ke rentang ASCII atau gunakan simbolologi lain yang menjamin kompatibilitas.

## Tips profesional untuk penggunaan produksi

* **Cache generator** saat menghasilkan banyak barcode dengan pengaturan yang sama – ini mengurangi overhead pembuatan objek.
* **Setel `Resolution`** (`generator.Parameters.ImageResolution`) ke 300 dpi untuk output cetak berkualitas tinggi.
* **Aktifkan koreksi kesalahan** untuk barcode 2‑D (`generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel`) guna meningkatkan keandalan pemindaian pada media yang rusak.
* **Bungkus logika penyimpanan** dalam blok `try / catch` untuk menangani pengecualian I/O, terutama saat menulis ke share jaringan.

## Kesimpulan

Anda kini tahu **cara menghasilkan barcode** menggunakan Aspose.Barcode di C#. Tutorial ini mencakup instalasi paket NuGet, pembuatan `BarcodeGenerator`, konfigurasi dimensi dan kolom, serta penyimpanan hasil sebagai gambar PNG. Dengan dasar ini Anda dapat **membuat barcode dengan Aspose** untuk simbolologi apa pun yang didukung, menyesuaikan parameter visual, dan mengintegrasikan pembuatan barcode ke dalam solusi .NET yang lebih besar.

Siap menjelajah lebih jauh? Cobalah menghasilkan QR code untuk pemendekan URL, sematkan barcode dalam laporan PDF menggunakan Aspose.PDF, atau otomatisasi pembuatan batch barcode untuk manajemen inventaris. Setiap skenario baru dibangun di atas konsep inti yang ditunjukkan di sini. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}