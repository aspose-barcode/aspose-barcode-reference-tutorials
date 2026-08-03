---
category: general
date: 2026-08-03
description: Buat barcode PDF417 di C# dengan cepat. Pelajari cara menghasilkan barcode
  PDF417 dan cara menyimpan gambar barcode sebagai PNG dengan Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: id
lastmod: 2026-08-03
og_description: Buat kode batang PDF417 dalam C# dengan Aspose.Barcode. Ikuti panduan
  ini untuk menghasilkan kode batang PDF417 dan cara menyimpan gambar kode batang
  secara efisien.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Buat barcode PDF417 di C# – tutorial pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Buat kode batang PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat barcode PDF417 di C# – panduan langkah‑demi‑langkah

Jika Anda perlu **membuat barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara menghasilkan barcode PDF417 dan cara menyimpan gambar barcode. Anda akan mendapatkan file PNG yang dapat digunakan dalam laporan, tiket, atau aplikasi pemindaian seluler.

Tutorial ini mencakup semua hal mulai dari penyiapan proyek hingga file PNG akhir. Tidak diperlukan dokumentasi eksternal; cukup ikuti langkah‑langkahnya dan jalankan kode.

## Apa yang Anda perlukan

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7+)
* Visual Studio 2022 atau IDE apa pun yang mendukung C#
* Akses internet untuk menginstal paket NuGet **Aspose.Barcode for .NET**

Prasyarat ini memastikan kode dapat dikompilasi tanpa konfigurasi tambahan.

## Membuat barcode PDF417 – penyiapan proyek

1. Buka command prompt dan buat proyek konsol baru:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Tambahkan pustaka Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Buka file `Program.cs` yang dihasilkan. Pernyataan `using` di bagian atas memberi Anda akses ke kelas barcode:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

Proyek kini siap untuk **membuat barcode PDF417**.

## Cara menghasilkan barcode PDF417 dengan Aspose.Barcode

Inti pembuatan barcode berada di kelas `BarcodeGenerator`. Anda menentukan simbolologi (`EncodeTypes.Pdf417`) dan data yang ingin dienkode.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Mengapa ini penting

* **EncodeTypes.Pdf417** memberi tahu pustaka untuk menggunakan standar PDF417, yang mendukung muatan data besar dan koreksi kesalahan.
* Menyertakan karakter Unicode membuktikan generator dapat menangani masukan non‑ASCII tanpa konfigurasi tambahan.

## Cara mengonfigurasi tampilan barcode

Anda dapat mengontrol ukuran setiap modul, jumlah kolom, dan apakah barcode menggunakan mode kompak (terpotong). Pengaturan ini memengaruhi keterbacaan serta ukuran file.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Tips praktis

Jika Anda membutuhkan barcode yang lebih tinggi karena ruang horizontal terbatas, tingkatkan `Columns`. Menetapkan `Truncate` ke `true` mengurangi tinggi keseluruhan dengan menghilangkan zona tenang, yang ideal untuk layar seluler.

## Cara menyimpan gambar barcode sebagai PNG

Setelah mengonfigurasi generator, panggil `Save` dengan jalur file dan format gambar yang diinginkan. Metode ini menulis gambar langsung ke disk.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Hasil yang diharapkan

Menjalankan program akan membuat `CompactPdf417.png` di folder proyek. Membuka file tersebut menampilkan barcode PDF417 kompak yang mengenkripsi string *Åspóse.Barcóde©*. Gambar ini dapat disematkan dalam HTML, laporan PDF, atau dicetak pada label.

## Kode sumber lengkap

Berikut adalah program lengkap yang dapat dijalankan. Salin ke `Program.cs` dan jalankan `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Memverifikasi output

Setelah program selesai, Anda dapat memverifikasi keberadaan file dengan perintah singkat:

```bash
dotnet run && ls -l CompactPdf417.png
```

Jika file muncul, proses **membuat barcode PDF417** berhasil.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian |
|-----------|------------|
| **String data lebih panjang** | Tingkatkan `Columns` atau atur `Rows` untuk menampung lebih banyak codeword. |
| **Format gambar berbeda** | Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif`. |
| **Resolusi lebih tinggi** | Atur `generator.Parameters.ImageResolution` sebelum `Save`. |
| **Warna latar belakang** | Gunakan `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Penanganan pengecualian** | Bungkus `generator.Save` dalam blok `try/catch` untuk menangkap kesalahan I/O. |

Variasi ini memungkinkan Anda menyesuaikan barcode untuk perangkat atau kebutuhan branding tertentu.

## Kesimpulan

Anda kini tahu cara **membuat barcode PDF417** di C# menggunakan Aspose.Barcode, mengonfigurasi tampilannya, dan **menyimpan gambar barcode** sebagai file PNG. Contoh lengkap ini menunjukkan setiap langkah yang diperlukan, mulai dari penyiapan proyek hingga verifikasi, sehingga Anda dapat mengintegrasikan pembuatan barcode ke dalam solusi .NET apa pun.

Selanjutnya, pertimbangkan untuk menjelajahi topik terkait seperti **cara menghasilkan QR code**, **menyematkan barcode dalam dokumen PDF**, atau **menyesuaikan warna barcode**. Semua ini dibangun di atas API generator yang sama, memungkinkan Anda memperluas kemampuan pemindaian aplikasi dengan usaha minimal. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}