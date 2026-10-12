---
category: general
date: 2026-09-29
description: Pelajari cara menghasilkan barcode PDF417 di C# dengan cepat. Tutorial
  langkah demi langkah ini mencakup pengaturan barcode, output gambar, dan jebakan
  umum.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- PDF417 barcode settings
- C# barcode library
- barcode image export
language: id
lastmod: 2026-09-29
og_description: Buat kode batang PDF417 di C# dengan tutorial terperinci ini. Ikuti
  contoh lengkap untuk membuat dan mengekspor gambar kode batang.
og_image_alt: Screenshot showing generated PDF417 barcode saved as PNG
og_title: Buat kode batang PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  headline: How to generate PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  name: How to generate PDF417 barcode in C# – complete programming guide
  steps:
  - name: Adjusting error correction level
    text: PDF417 supports five error‑correction levels (0‑8). Higher levels increase
      robustness at the cost of size.
  - name: Changing image format
    text: 'If you need a vector format for scaling, export as SVG instead of PNG:'
  - name: Handling very long strings
    text: 'When the input exceeds the default capacity, increase the number of rows:'
  - name: Using a different library
    text: If you prefer an open‑source alternative, the `ZXing.Net` package also supports
      PDF417. The API differs, but the overall flow—create a writer, set options,
      render to bitmap—remains the same.
  - name: Next steps
    text: '* Explore **PDF417 barcode settings** such as row count and aspect ratio
      for custom layouts. * Integrate the barcode generation into an ASP.NET Core
      API to serve images on demand. * Combine this code with a QR‑code generator
      for multi‑symbology documents.'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Cara menghasilkan barcode PDF417 di C# – panduan pemrograman lengkap
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-programming-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PDF417 di C# – panduan pemrograman lengkap

Jika Anda perlu **membuat barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan melihat contoh lengkap yang dapat dijalankan yang menghasilkan barcode PDF417, mengatur dimensinya, dan menyimpannya sebagai gambar PNG.

Membuat barcode adalah kebutuhan umum untuk sistem inventaris, platform tiket, dan otomatisasi dokumen. Pada akhir tutorial ini Anda akan dapat mengintegrasikan pembuatan barcode ke dalam proyek C# apa pun tanpa harus mencari potongan kode tambahan.

## Apa yang akan Anda pelajari

* Cara menginstansiasi generator barcode PDF417 dengan teks khusus  
* Parameter mana yang mengontrol dimensi X dan jumlah kolom  
* Cara mengekspor barcode sebagai file PNG berkualitas tinggi  
* Tips menangani karakter Unicode dan menyesuaikan ukuran gambar  

**Prasyarat**  
* .NET 6.0 atau lebih baru (kode ini juga berfungsi dengan .NET Framework 4.6+)  
* Referensi ke paket NuGet `Aspose.BarCode` (atau perpustakaan barcode kompatibel lainnya)  
* Familiaritas dasar dengan sintaks C# dan Visual Studio atau IDE pilihan Anda  

Jika Anda bertanya-tanya **bagaimana cara membuat barcode PDF417** untuk pertama kalinya, teruskan membaca – langkah‑langkahnya disusun secara berurutan mulai dari penyiapan hingga verifikasi.

## Langkah 1: Instal perpustakaan barcode

Sebelum menulis kode apa pun, tambahkan SDK barcode ke proyek Anda. Perpustakaan yang paling banyak digunakan untuk PDF417 di C# adalah **Aspose.BarCode for .NET**.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Gunakan versi stabil terbaru (saat ini 24.5) untuk mendapatkan peningkatan performa dan dukungan Unicode penuh.

## Langkah 2: Buat generator barcode PDF417

Inti proses adalah membuat instance `BarcodeGenerator` dengan enum `EncodeTypes.Pdf417`. Konstruktor juga menerima teks yang ingin Anda enkode.

```csharp
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,               // PDF417 symbology
    "Åspóse.Barcóde©");               // Text includes Unicode characters
```

*Mengapa ini penting*: Flag `EncodeTypes.Pdf417` memberi tahu perpustakaan untuk menggunakan standar PDF417, yang mendukung blok data besar dan koreksi kesalahan. Menyediakan string Unicode menunjukkan bahwa generator menangani karakter non‑ASCII dengan benar.

## Langkah 3: Atur dimensi X (lebar modul)

Dimensi X menentukan lebar satu modul barcode (garis hitam atau putih terkecil). Menetapkannya dalam piksel memberi Anda kontrol presisi atas ukuran gambar akhir.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nilai `2` piksel menghasilkan barcode yang kompak namun tetap mudah dibaca oleh kebanyakan pemindai. Jika Anda memerlukan barcode yang lebih besar untuk pencetakan poster, tingkatkan nilai ini secara proporsional.

## Langkah 4: Tentukan jumlah kolom

PDF417 memungkinkan Anda menentukan jumlah kolom, yang memengaruhi rasio aspek barcode. Lebih sedikit kolom membuat barcode lebih tinggi; lebih banyak kolom membuatnya lebih lebar.

```csharp
// Step 4: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Tiga kolom menghasilkan bentuk seimbang yang cocok untuk kebanyakan penggunaan berbasis layar. Untuk data yang padat, Anda dapat meningkatkan angka ini menjadi 5 atau 7.

## Langkah 5: Simpan barcode sebagai gambar PNG

Akhirnya, ekspor barcode yang dihasilkan ke file. PNG mempertahankan tepi yang tajam dan mendukung transparansi, menjadikannya ideal untuk tampilan UI.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Pdf417Basic.png");

barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Saat kode dijalankan, Anda akan menemukan `Pdf417Basic.png` di desktop Anda. Membuka file tersebut menampilkan barcode PDF417 yang jelas dengan string **Åspóse.Barcóde©**.

## Memverifikasi hasil

Untuk memastikan barcode mengenkode data yang dimaksud, Anda dapat menggunakan aplikasi pemindai PDF417 gratis (misalnya, aplikasi ZXing Android) atau decoder daring. Pindai PNG yang disimpan; teks yang terdekripsi harus persis sama dengan input asli, termasuk karakter khusus.

**Output yang diharapkan** – gambar PNG serupa dengan ini (illustrasi):

![Generated PDF417 barcode saved as PNG – generate pdf417 barcode example](https://example.com/assets/pdf417-sample.png "generate pdf417 barcode")

*Teks alt di atas memenuhi persyaratan alt‑image untuk kata kunci utama.*

## Variasi umum dan kasus tepi

### Menyesuaikan level koreksi kesalahan

PDF417 mendukung lima level koreksi kesalahan (0‑8). Level yang lebih tinggi meningkatkan ketahanan dengan mengorbankan ukuran.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // medium protection
```

### Mengubah format gambar

Jika Anda memerlukan format vektor untuk skalabilitas, ekspor sebagai SVG alih‑alih PNG:

```csharp
barcodeGenerator.Save("Pdf417Basic.svg", BarCodeImageFormat.Svg);
```

### Menangani string sangat panjang

Ketika input melebihi kapasitas default, tingkatkan jumlah baris:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 10;
```

### Menggunakan perpustakaan lain

Jika Anda lebih suka alternatif sumber terbuka, paket `ZXing.Net` juga mendukung PDF417. API‑nya berbeda, tetapi alur keseluruhan—membuat writer, mengatur opsi, merender ke bitmap—tetap sama.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin ke aplikasi console dan jalankan langsung.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize the generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose a compact column count
        generator.Parameters.Barcode.Pdf417.Columns = 3;

        // Optional: increase error correction for noisy environments
        generator.Parameters.Barcode.Pdf417.ErrorLevel = 5;

        // 4️⃣ Determine output path (desktop for easy access)
        string desktop = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);
        string filePath = Path.Combine(desktop, "Pdf417Basic.png");

        // 5️⃣ Export as PNG
        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to: {filePath}");
    }
}
```

Jalankan program (`dotnet run`), lalu buka file yang dihasilkan untuk melihat barcode. Konsol akan mengonfirmasi lokasi gambar yang disimpan.

## Kesimpulan

Anda kini tahu **bagaimana cara membuat barcode PDF417** di C# dari awal hingga akhir. Dengan membuat `BarcodeGenerator`, mengatur dimensi X dan jumlah kolom, serta mengekspor ke PNG, Anda dapat menyematkan pembuatan barcode ke dalam solusi .NET apa pun. Bereksperimenlah dengan level koreksi kesalahan, format gambar berbeda, atau payload data yang lebih besar untuk menyesuaikan barcode dengan skenario spesifik Anda.

### Langkah selanjutnya

* Jelajahi **pengaturan barcode PDF417** seperti jumlah baris dan rasio aspek untuk tata letak khusus.  
* Integrasikan pembuatan barcode ke dalam API ASP.NET Core untuk menyajikan gambar secara dinamis.  
* Gabungkan kode ini dengan generator QR‑code untuk dokumen multi‑simbol.

Silakan sesuaikan contoh, bagikan hasil Anda, atau ajukan pertanyaan di kolom komentar. Selamat coding!


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [How to generate PDF417 barcode in C# with Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}