---
category: general
date: 2026-09-26
description: Pelajari cara membuat barcode di C# menggunakan Aspose.BarCode. Panduan
  langkah demi langkah ini mencakup contoh generator barcode dan menunjukkan cara
  menyesuaikan tinggi bar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: id
lastmod: 2026-09-26
og_description: Buat barcode di C# dengan Aspose.BarCode. Ikuti panduan ini untuk
  menghasilkan barcode, menyesuaikan tinggi bar, dan menyimpan gambar PNG.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Buat kode batang di C# dengan Aspose.BarCode – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cara membuat barcode di C# dengan Aspose.BarCode
url: /id/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode di C# dengan Aspose.BarCode  

Jika Anda perlu **create barcode c#** proyek dengan cepat, Aspose.BarCode menyediakan API yang mudah digunakan yang menangani pekerjaan berat. Dalam tutorial ini Anda akan melihat contoh **barcode generator example** lengkap, mempelajari **how to adjust bar height**, dan mengekspor hasilnya sebagai file PNG.  

Apakah Anda sedang membangun sistem checkout ritel, menghasilkan tag inventaris, atau mengotomatiskan label pengiriman, kemampuan untuk secara programatis mengubah ukuran visual barcode sangat penting. Panduan ini mengasumsikan Anda memiliki pemahaman dasar tentang C# dan lingkungan pengembangan seperti Visual Studio 2022.  

## Prasyarat  

* .NET 6.0 SDK atau yang lebih baru terpasang.  
* Visual Studio 2022 (atau IDE C# apa pun).  
* Lisensi Aspose.BarCode yang aktif (versi percobaan gratis dapat digunakan untuk belajar).  

Anda juga perlu menambahkan paket NuGet Aspose.BarCode ke proyek Anda:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Jika Anda berencana menghasilkan banyak barcode dalam loop, gunakan kembali satu instance `BarcodeGenerator` dan hanya ubah parameter yang berubah. Ini mengurangi alokasi memori dan meningkatkan kinerja.

## Cara membuat barcode di C# dengan Aspose.BarCode  

Bagian berikut menjelaskan setiap langkah dari **barcode generator example**. Kode ini berdiri sendiri; salin ke aplikasi konsol baru dan jalankan.

### Langkah 1: Impor namespace yang diperlukan  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Namespace ini memberi Anda akses ke kelas `BarcodeGenerator` dan enumerasi `EncodeTypes`.

### Langkah 2: Inisialisasi generator barcode  

Kami akan menghasilkan simbol **Databar Omni‑Directional** yang mengkodekan nilai GTIN‑14. Konstruktor menerima symbology dan string data mentah.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Nilai `EncodeTypes.DatabarOmniDirectional` memberi tahu Aspose.BarCode standar barcode mana yang akan digunakan. String data mengikuti format GS1 Application Identifier, yang umum untuk barcode ritel.

### Langkah 3: Atur parameter barcode umum  

Dua parameter visual yang paling sering disesuaikan: X‑dimension (lebar bar sempit) dan tinggi bar keseluruhan.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**X‑dimension** mengontrol kepadatan barcode, sementara **BarHeight** menentukan ukuran vertikal setiap bar. Menyesuaikan **BarHeight** adalah hal yang tepat ketika Anda ingin **change barcode height** untuk media cetak yang berbeda.

### Langkah 4: Simpan gambar pertama (tinggi 30 piksel)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Metode `Save` menulis gambar yang dirender ke disk. Nama file dengan jelas menunjukkan tinggi yang digunakan, yang membantu saat Anda membandingkan output yang berbeda.

### Langkah 5: Ubah tinggi bar menjadi 60 piksel  

Sekarang kami mendemonstrasikan **how to adjust bar height** pada runtime. Instance `generator` yang sama digunakan kembali; hanya properti `BarHeight` yang diubah.

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Karena generator mempertahankan semua pengaturan lain (symbology, data, X‑dimension), satu-satunya perbedaan visual antara dua file PNG adalah ukuran vertikal bar.

### Kode sumber lengkap  

Menggabungkan semuanya menghasilkan program yang ringkas dan dapat dijalankan:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Output yang diharapkan**  

Menjalankan program membuat dua file PNG di direktori kerja executable:

* `DatabarBarHeight30Pixels.png` – barcode dengan tinggi bar 30 px.  
* `DatabarBarHeight60Pixels.png` – barcode yang sama, tetapi setiap bar dua kali lebih tinggi.

Buka gambar di penampil apa pun; Anda akan melihat pola keseluruhan tetap identik sementara dimensi vertikal berubah, mengonfirmasi bahwa operasi **change barcode height** berhasil.

## Variasi lanjutan  

### Beralih ke symbology yang berbeda  

Jika Anda membutuhkan QR code alih-alih Databar, ganti nilai `EncodeTypes`:

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Semua pengaturan parameter lain (X‑dimension, BarHeight) tetap berlaku di mana relevan.

### Menggunakan `BarHeight` dalam milimeter  

Aspose.BarCode juga mendukung satuan fisik. Untuk mengatur tinggi 10 mm:

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Ini berguna ketika Anda menghasilkan barcode untuk tata letak cetak yang memerlukan ukuran tepat.

### Menangani kesalahan  

Jika string data tidak sesuai dengan symbology yang dipilih, `BarcodeGenerator` akan melempar `ArgumentException`. Bungkus logika pembuatan dalam blok try‑catch untuk memberikan pesan yang ramah:

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Pertanyaan umum terjawab  

* **Apakah mengubah BarHeight memengaruhi kemampuan pemindaian?**  
  Barcode tetap dapat dipindai selama X‑dimension dan zona tenang keseluruhan memenuhi spesifikasi symbology. Meningkatkan tinggi hanya membuat bar menjadi lebih panjang; tidak pernah mengurangi kontras.

* **Bisakah saya mengatur tinggi yang berbeda untuk bar individual?**  
  Tidak. Properti `BarHeight` diterapkan secara seragam ke seluruh simbol. Untuk desain dengan tinggi variabel, Anda memerlukan rutin rendering khusus di luar cakupan Aspose.BarCode.

* **Apakah PNG format terbaik untuk pencetakan?**  
  PNG mempertahankan data piksel lossless, menjadikannya ideal untuk tampilan layar. Untuk pekerjaan cetak resolusi tinggi, pertimbangkan `BarCodeImageFormat.Tiff` atau `Pdf` untuk mempertahankan informasi vektor.

## Kesimpulan  

Anda sekarang tahu cara **create barcode c#** aplikasi dengan Aspose.BarCode, melihat contoh **barcode generator example** lengkap, dan memahami **how to adjust bar height** untuk memenuhi persyaratan tata letak yang berbeda. Dengan menggunakan kembali instance generator yang sama dan hanya memodifikasi `BarHeight`, Anda dapat secara efisien **change barcode height** tanpa membangun ulang seluruh objek.

Dari sini Anda dapat menjelajahi:

* Menghasilkan symbology lain (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Mengekspor ke SVG atau PDF untuk grafik yang dapat diskalakan.  
* Menyematkan barcode langsung ke dokumen Word atau Excel menggunakan Aspose.Words atau Aspose.Cells.

Selamat coding, dan nikmati fleksibilitas yang dibawa Aspose.BarCode ke proyek barcode C# Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan dan Menyesuaikan Tinggi Barcode untuk Databar Satu Dimensi menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Cara membuat file PNG barcode dengan tinggi yang dapat disesuaikan di C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [Cara Menghasilkan Barcode di C# – Panduan Lengkap Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}