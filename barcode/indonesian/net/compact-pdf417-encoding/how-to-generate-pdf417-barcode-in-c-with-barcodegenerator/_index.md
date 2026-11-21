---
category: general
date: 2026-11-20
description: Pelajari cara menghasilkan barcode PDF417 di C# menggunakan BarcodeGenerator.
  Panduan langkah demi langkah ini mencakup X‑Dimension, pengaturan kolom, dan ekspor
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: id
lastmod: 2026-11-20
og_description: Buat kode batang PDF417 dalam C# dengan cepat. Ikuti panduan ini untuk
  mengatur dimensi, kolom, dan mengekspor kode batang sebagai gambar PNG.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Buat barcode PDF417 di C# – panduan langkah demi langkah lengkap
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Cara menghasilkan barcode PDF417 di C# dengan BarcodeGenerator
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan PDF417 barcode di C# dengan BarcodeGenerator

Jika Anda perlu **menghasilkan PDF417 barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan melihat contoh lengkap yang dapat dijalankan yang mengatur X‑Dimension, memilih jumlah kolom, dan menyimpan hasilnya sebagai gambar PNG.

Menghasilkan barcode PDF417 umum ketika Anda harus mengkodekan banyak data—seperti SIM, boarding pass, atau catatan inventaris—ke dalam gambar yang kompak dan dapat dibaca mesin. Dalam tutorial ini kami menggunakan kelas **BarcodeGenerator** dari pustaka Aspose.BarCode, tetapi konsepnya berlaku untuk pustaka apa pun yang mendukung PDF417.

Pada akhir artikel ini Anda akan dapat:

* Menginisialisasi `BarcodeGenerator` untuk enkoding PDF417.  
* Menyesuaikan ukuran modul dengan **set XDimension pixels**.  
* Mengontrol tata letak menggunakan **configure PDF417 columns**.  
* **Menyimpan barcode sebagai PNG** untuk digunakan di halaman web, aplikasi seluler, atau materi cetak.  

> **Prerequisites**  
> * .NET 6.0 atau lebih baru (kode juga bekerja dengan .NET Framework 4.7+).  
> * Referensi ke paket NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Familiaritas dasar dengan C# dan Visual Studio (atau IDE apa pun yang Anda sukai).

---

## Cara menghasilkan PDF417 barcode di C#

Inti solusi adalah proses singkat empat langkah. Setiap langkah dibungkus dalam metode khusus sehingga Anda dapat menggunakan kembali logika ini dalam proyek yang lebih besar.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Mengapa empat langkah ini penting

1. **Inisialisasi generator** – `BarcodeGenerator` menghubungkan simbolologi yang dipilih (`EncodeTypes.Pdf417`) dengan data yang ingin Anda enkode. Tanpa objek ini Anda tidak dapat mengakses konfigurasi selanjutnya.  
2. **Set X‑Dimension** – PDF417 dibangun dari modul persegi panjang kecil. Mengubah `XDimension.Pixels` memungkinkan Anda mengontrol kepadatan visual barcode, yang penting untuk keterbacaan pada tampilan atau printer beresolusi rendah.  
3. **Configure columns** – PDF417 dapat menyusun codeword‑nya dalam jumlah kolom yang variabel. Lebih sedikit kolom menghasilkan barcode yang lebih tinggi, sementara lebih banyak kolom membuatnya lebih datar. Sesuaikan ini agar cocok dengan ruang tempat gambar akan ditempatkan.  
4. **Save as PNG** – PNG adalah format loss‑less, mempertahankan tepi tajam yang diperlukan untuk pemindaian akurat. Anda juga dapat memilih JPEG atau BMP, tetapi PNG adalah default yang paling aman.

---

## Konfigurasi dimensi barcode (X‑Dimension)

Langkah **set XDimension pixels** secara langsung memengaruhi cara pemindai menginterpretasikan barcode. Jika modul terlalu kecil, kamera beresolusi rendah dapat melewatkan bar individu; jika terlalu besar, barcode dapat menjadi terlalu besar.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Uji gambar yang dihasilkan pada ukuran cetak yang dimaksudkan. Untuk pencetakan ber‑density tinggi (300 dpi atau lebih), nilai `1` atau `2` bekerja dengan baik. Untuk tampilan di layar pada 96 dpi, `2`–`3` memberikan visual yang jelas.

---

## Atur kolom PDF417

Langkah **configure PDF417 columns** memungkinkan Anda menentukan bentuk barcode.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Kapan mengubah jumlah kolom

| Kolom | Bentuk yang dihasilkan | Kasus penggunaan umum |
|------|------------------------|-----------------------|
| 1–3  | Tinggi, sempit         | Label dengan lebar terbatas |
| 4–9  | Seimbang               | Pemindaian umum |
| 10+  | Lebar, pendek          | Tanda besar atau grafik web |

Jika payload data Anda melebihi kapasitas default, pustaka secara otomatis menambahkan baris ekstra, tetapi Anda masih dapat memengaruhi rasio aspek dengan menyesuaikan jumlah kolom.

---

## Ekspor barcode ke PNG

Menyimpan barcode sebagai gambar PNG sangat sederhana:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Why PNG?**  
* Kompresi lossless mempertahankan tepi tajam yang dibutuhkan pembaca barcode.  
* PNG mendukung transparansi, yang dapat berguna jika Anda menumpangkan barcode di latar belakang berwarna nanti.

Jika Anda memerlukan format lain, ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Svg`—API akan menangani konversi secara otomatis.

---

## Kesulitan umum dan pemecahan masalah

| Masalah | Penyebab kemungkinan | Solusi |
|---------|----------------------|--------|
| Barcode terlihat buram | X‑Dimension terlalu kecil untuk resolusi output | Tingkatkan `XDimension.Pixels` menjadi 3 atau 4. |
| Pemindai tidak dapat membaca kode | Karakter Unicode tidak didukung oleh font yang dipilih | Pastikan font pustaka mendukung karakter tersebut, atau ganti dengan padanan ASCII. |
| File output tidak dibuat | Path tidak valid atau izin menulis tidak ada | Gunakan path absolut dan verifikasi akses menulis folder. |
| Terlalu banyak baris, barcode menjadi tinggi | Jumlah kolom terlalu sedikit untuk panjang data | Tingkatkan `Pdf417.Columns` ke angka yang lebih tinggi (mis., 6). |

---

## Ringkasan contoh kerja lengkap

Berikut adalah **program lengkap** yang dapat Anda salin‑tempel ke proyek konsol baru. Tidak ada kode tambahan yang diperlukan selain pernyataan `using` dan paket Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Expected output:** Sebuah file bernama `Pdf417Basic.png` yang berisi barcode PDF417 yang jelas dan mengenkode string `Åspóse.Barcóde©`. Saat dibuka, gambar akan menampilkan serangkaian bar persegi panjang yang ditumpuk dengan sisi kiri ber‑density lebih tinggi (karena tata letak tiga kolom).

---

## Kesimpulan

Anda kini tahu cara **menghasilkan PDF417 barcode** di C# menggunakan kelas `BarcodeGenerator`. Tutorial ini mencakup inisialisasi generator, **set XDimension pixels**, **configure PDF417 columns**, dan **save barcode as PNG**—langkah penting untuk alur kerja barcode siap produksi apa pun.

Dari sini Anda dapat:

* Bereksperimen dengan `EncodeTypes` yang berbeda (mis., QR, Code128).  
* Menambahkan tingkat koreksi kesalahan melalui `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Merender barcode langsung ke `MemoryStream` untuk API web.  

Silakan sesuaikan kode dengan proyek Anda, dan bagikan hasilnya di komentar atau di Stack Overflow menggunakan tag `#pdf417`. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Generate PDF417 barcode as PNG in C# – panduan langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# – panduan langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}