---
category: general
date: 2026-11-14
description: Buat barcode micro PDF417 di C# dengan Aspose.BarCode – panduan langkah
  demi langkah yang mencakup pengaturan generator, dimensi X, kolom, dan ekspor PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: id
lastmod: 2026-11-14
og_description: Buat barcode micro PDF417 dalam C# menggunakan Aspose.BarCode. Pelajari
  cara mengonfigurasi generator, mengatur XDimension, memilih kolom, dan mengekspor
  sebagai PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Buat kode batang micro PDF417 di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Cara membuat barcode micro PDF417 di C#
url: /id/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode micro PDF417 di C#  

Jika Anda perlu **membuat barcode micro PDF417** dengan cepat, panduan ini menunjukkan solusi lengkap yang siap dijalankan. Anda akan melihat cara menginstansiasi generator barcode, mengonfigurasi X‑dimension, memilih jumlah kolom, dan akhirnya menyimpan hasilnya sebagai gambar PNG—semua menggunakan pustaka Aspose.BarCode untuk .NET.

Membuat barcode micro PDF417 tidak memerlukan pipeline build yang kompleks. Pada akhir tutorial ini Anda akan memiliki satu file C# yang menghasilkan gambar barcode berkualitas tinggi yang dapat Anda sematkan dalam laporan, label, atau aplikasi seluler.

## Prasyarat  

* .NET 6.0 SDK atau yang lebih baru (kode juga dapat berjalan dengan .NET Framework 4.7+).  
* Lingkungan pengembangan seperti Visual Studio 2022, VS Code, atau Rider.  
* Lisensi Aspose.BarCode untuk .NET (atau kunci evaluasi gratis). Anda dapat memperolehnya dari [situs Aspose](https://purchase.aspose.com/barcode/net).  

> **Pro tip:** Jika Anda menggunakan versi evaluasi, PNG yang dihasilkan akan berisi watermark “Evaluation” kecil. Versi berlisensi akan menghapusnya secara otomatis.

## Langkah 1: Siapkan proyek  

Buat proyek konsol baru dan tambahkan paket NuGet Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

Perintah `dotnet add package` mengambil dependensi **contoh Aspose.BarCode C#**, sehingga Anda tidak perlu mengelola DLL secara manual.

## Langkah 2: Tulis kode lengkap  

Ganti `Program.cs` yang dihasilkan secara otomatis dengan kode berikut. Kode ini menunjukkan cara **membuat barcode micro pdf417** dari awal hingga akhir.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Mengapa setiap baris penting  

* **BarcodeGenerator constructor** – Menginstansiasi **generator barcode micro pdf417** dengan teks yang ingin Anda enkode.  
* **XDimension.Pixels** – Mengontrol lebar modul; mengatur ke `2` piksel menghasilkan barcode padat, beresolusi tinggi yang cocok untuk kebanyakan pemindai.  
* **Pdf417.Columns** – MicroPDF417 hanya mendukung 1‑4 kolom. Memilih `4` mengurangi tinggi barcode, yang berguna ketika Anda memiliki ruang vertikal terbatas.  
* **Save method** – Menulis barcode ke file PNG. PNG bersifat lossless, memastikan pemindai membaca pola persis yang Anda hasilkan.  

## Langkah 3: Build dan jalankan  

Kompilasi dan jalankan program:

```bash
dotnet run
```

Anda akan melihat output konsol:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Sebuah file bernama **MicroPdf417.png** muncul di folder proyek. Buka dengan penampil gambar apa saja; Anda akan melihat barcode micro PDF417 yang tajam yang mengenkode string `"Åspóse.Barcóde©"`.

![Contoh barcode micro PDF417 yang dihasilkan](MicroPdf417.png "Contoh barcode micro PDF417 yang dihasilkan"){.center-image width=400 alt="Contoh gambar barcode micro PDF417 yang dihasilkan"}

*Gambar di atas adalah hasil dari kode yang ditunjukkan pada Langkah 2.*

## Langkah 4: Variasi umum dan kasus tepi  

| Situation | How to adapt the code |
|-----------|----------------------|
| **Panjang data berbeda** | MicroPDF417 dapat mengenkode hingga 1 200 karakter. Cukup ubah argumen kedua dari `BarcodeGenerator`. |
| **Resolusi lebih tinggi** | Tingkatkan `XDimension.Pixels` menjadi `3` atau `4`. Modul yang lebih besar meningkatkan keterbacaan pada pemindai beresolusi rendah tetapi memperbesar ukuran gambar. |
| **Warna khusus** | Setelah membuat generator, atur `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` dan `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Menyimpan dalam format lain** | Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` tergantung pada kebutuhan selanjutnya. |
| **Menyematkan dalam PDF** | Gunakan `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` lalu gabungkan PDF dengan dokumen lain menggunakan Aspose.PDF. |

> **Watch out for:** Menetapkan `XDimension.Pixels` di bawah `1` akan menimbulkan `ArgumentOutOfRangeException`. Selalu pertahankan nilai `1` atau lebih.

## Langkah 5: Verifikasi barcode  

Untuk memastikan barcode dipindai dengan benar:

1. Buka PNG dengan penampil gambar.  
2. Gunakan aplikasi pemindai barcode smartphone apa saja yang mendukung PDF417 (kebanyakan aplikasi “pemindai QR‑code” menyertakannya).  
3. Pindai gambar; aplikasi harus menampilkan teks asli `"Åspóse.Barcóde©"`.

Jika pemindaian gagal, periksa kembali pengaturan **X‑dimension** dan **column** – lebar modul yang terlalu kecil atau jumlah kolom yang tidak didukung dapat membuat pola tidak terbaca.

## Kesimpulan  

Anda sekarang tahu cara **membuat barcode micro pdf417** di C# menggunakan Aspose.BarCode. Tutorial ini mencakup:

* Menginstansiasi **generator barcode micro pdf417**.  
* **Mengatur XDimension pixels** untuk mengontrol lebar modul.  
* **Mendefinisikan kolom barcode** untuk menyesuaikan bentuk.  
* **Menyimpan barcode sebagai PNG** untuk output gambar lossless.  

Dari sini Anda dapat menjelajahi fitur tambahan seperti kustomisasi warna, menyematkan barcode dalam PDF, atau menghasilkan barcode secara langsung dalam API web ASP.NET Core. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat barcode PNG di C# – panduan lengkap untuk GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Cara membuat barcode macro PDF417 di C# menggunakan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Buat barcode PDF417 di C# menggunakan Aspose.BarCode – panduan langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}