---
category: general
date: 2026-10-08
description: Pelajari cara mengubah ukuran gambar barcode dengan contoh generator
  barcode C#, menyesuaikan tinggi bar dari 30 px menjadi 60 px hanya dalam beberapa
  baris kode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: id
lastmod: 2026-10-08
og_description: Cara mengubah ukuran barcode dengan cepat menggunakan contoh generator
  barcode C#. Sesuaikan tinggi bar, simpan file PNG, dan hindari jebakan umum.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Cara mengubah ukuran barcode di C# – contoh generator langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Cara mengubah ukuran barcode menggunakan contoh generator barcode di C#
url: /id/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengubah ukuran barcode menggunakan contoh generator barcode di C#

Jika Anda perlu **mengubah ukuran barcode** dalam proyek .NET, panduan ini menunjukkan solusi lengkapnya. Anda akan melihat contoh **barcode generator C#** yang singkat yang mengubah tinggi bar dari 30 px menjadi 60 px dan menyimpan setiap versi sebagai file PNG.

Mengubah ukuran barcode sering diperlukan ketika data yang sama harus muncul pada struk, label, atau halaman produk dengan skala visual yang berbeda. Daripada mengedit gambar raster dengan editor eksternal, Anda dapat menyesuaikan dimensi barcode secara programatis, menjaga integritas data tetap utuh.

Dalam tutorial ini Anda akan:

* Menyiapkan generator barcode DataBar Omni‑Directional.
* Memodifikasi parameter X‑dimension dan bar height.
* Menyimpan dua gambar dengan tinggi yang berbeda.
* Memahami mengapa mengubah tinggi bar berhasil dan kasus tepi apa yang perlu diwaspadai.

> **Prasyarat** – Anda memiliki lingkungan pengembangan .NET (Visual Studio 2022 atau lebih baru) dan perpustakaan barcode yang menyediakan `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`. Kode ini bekerja dengan versi terbaru perpustakaan per Oktober 2026.

## Prasyarat untuk contoh barcode generator C#

Sebelum memulai, pastikan Anda memiliki:

| Item | Alasan |
|------|--------|
| .NET 6.0 SDK atau yang lebih baru | Menyediakan runtime dan fitur bahasa yang digunakan dalam contoh. |
| Perpustakaan barcode (mis. Aspose.BarCode, Dynamsoft, atau perpustakaan lain yang menyediakan `BarcodeGenerator`) | Menyediakan enum `EncodeTypes.DatabarOmniDirectional` dan metode ekspor gambar. |
| Folder yang dapat ditulisi (mis. `C:\Temp\Barcodes\`) | Contoh menyimpan file PNG ke lokasi ini. |
| Pengetahuan dasar C# | Tutorial mengasumsikan familiaritas dengan kelas, properti, dan interpolasi string. |

Instal perpustakaan melalui NuGet jika belum:

```bash
dotnet add package Aspose.BarCode
```

Ganti nama paket dengan yang sebenarnya Anda gunakan; antarmuka API yang ditampilkan di bawah ini umum pada sebagian besar SDK barcode.

## Cara mengubah ukuran barcode – langkah 1: buat generatornya

Langkah pertama adalah menginstansiasi `BarcodeGenerator` dengan simbolologi dan data yang diinginkan. Pada contoh ini kami menghasilkan barcode **DataBar Omni‑Directional** yang mengenkode nilai GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Mengapa ini penting:** Enum `EncodeTypes.DatabarOmniDirectional` memberi tahu perpustakaan standar barcode mana yang akan dipakai. String data mengikuti Application Identifier GS1 `(01)` untuk GTIN 14 digit, memastikan barcode mematuhi standar perdagangan global.

## Cara mengubah ukuran barcode – langkah 2: definisikan lebar modul dan tinggi bar awal

Ukuran visual barcode bergantung pada dua parameter:

* **X‑dimension** – lebar bar terkecil (modul). Diukur dalam piksel atau milimeter.
* **Bar height** – panjang vertikal bar.

Menetapkan nilai ini sebelum menyimpan menjamin gambar yang dihasilkan sesuai dengan dimensi yang Anda butuhkan.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Penjelasan:** X‑dimension sebesar 2 px menghasilkan barcode yang kompak namun tetap dapat dipindai dengan andal. Tinggi 30 px adalah nilai default umum untuk label kecil. Anda dapat menyesuaikan X‑dimension secara terpisah dari tinggi bila memerlukan pola yang lebih padat atau lebih tersebar.

## Cara mengubah ukuran barcode – langkah 3: simpan gambar pertama (tinggi 30 px)

Sekarang ekspor barcode ke file PNG. Metode `Save` menerima jalur file dan enum format gambar.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Hasil:** `DatabarBarHeight30Pixels.png` berisi barcode setinggi 30 px. Anda dapat membuka file tersebut dengan penampil gambar apa pun untuk memverifikasi dimensinya.

## Cara mengubah ukuran barcode – langkah 4: ubah tinggi bar menjadi 60 px

Untuk membuat versi yang lebih besar, cukup ubah properti `BarHeight`. Generator menggunakan data dan X‑dimension yang sama, sehingga pola barcode tetap identik—hanya ukuran visual yang berubah.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Mengapa ini berhasil:** Mesin rendering barcode menghitung geometri tiap bar secara dinamis. Memperbarui properti tinggi sebelum pemanggilan `Save` berikutnya memicu rasterisasi ulang dengan dimensi baru.

## Cara mengubah ukuran barcode – langkah 5: simpan gambar kedua (tinggi 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG, satu kecil (30 px) dan satu lebih besar (60 px), siap digunakan pada label dengan ukuran berbeda.

## Kode sumber lengkap untuk contoh barcode generator C#

Berikut adalah program lengkap yang dapat dijalankan. Salin ke proyek konsol baru untuk langsung diuji.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Output yang diharapkan di konsol:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Setelah dijalankan, buka kedua file PNG untuk melihat perbedaan visual. Kedua barcode mengenkode nilai GTIN‑14 yang sama dan akan dipindai secara identik, terlepas dari tinggi.

## Mengapa mengubah tinggi bar aman untuk pemindaian

Pemindai barcode membaca pola modul terang dan gelap, bukan jumlah piksel absolut. Selama **X‑dimension** tetap berada dalam toleransi pemindai (biasanya 0,5 mm hingga 2 mm dalam satuan fisik), mengubah tinggi tidak memengaruhi keterbacaan. Perpustakaan secara otomatis menskalakan modul, mempertahankan zona tenang dan pola alignment yang diperlukan.

## Kesalahan umum dan cara menghindarinya

| Kesalahan | Cara memperbaiki |
|-----------|------------------|
| **Folder output tidak ada** | Panggil `Directory.CreateDirectory(outputPath)` sebelum menyimpan. |
| **X‑dimension tidak tepat menyebabkan pemindaian blur** | Jaga `XDimension.Pixels` antara 1 px dan 4 px untuk kebanyakan printer; uji dengan pemindai fisik. |
| **Menggunakan format raster untuk barcode sangat besar** | Beralih ke `BarCodeImageFormat.Svg` untuk skalabilitas tak terbatas tanpa pikselasi. |
| **Lupa mereset `BarHeight` sebelum penyimpanan kedua** | Pastikan Anda menetapkan tinggi baru **sebelum** memanggil `Save` lagi. |

## Tips pro: menghasilkan banyak ukuran dalam loop

Jika Anda memerlukan rentang tinggi (mis. 30 px, 45 px, 60 px), loop `foreach` sederhana mengurangi duplikasi kode:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Pola ini skalabel untuk pemrosesan batch katalog produk.

## Kasus tepi: format gambar berbeda dan pengaturan DPI

* **Output SVG** – Gunakan `BarCodeImageFormat.Svg` untuk menghasilkan file vektor yang dapat diubah ukuran tanpa kehilangan kualitas.
* **PNG ber‑DPI tinggi** – Atur `generator.Parameters.Image.DpiX` dan `DpiY` ke 300 atau 600 untuk gambar siap cetak; tinggi bar tetap diukur dalam piksel, jadi tingkatkan secara proporsional.
* **Simbolologi non‑standar** – Beberapa tipe barcode (mis. QR Code) memiliki properti `Size` terpisah alih‑alih `BarHeight`. Lihat dokumentasi perpustakaan untuk kasus tersebut.

## Menguji barcode yang telah diubah ukurannya

1. Buka setiap PNG di penampil gambar dan verifikasi dimensi piksel (mis. 150 × 30 px vs. 150 × 60 px).  
2. Cetak gambar pada skala 100 %.  
3. Pindai dengan pemindai barcode genggam atau aplikasi seluler. Data yang terdekripsi harus sama.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang memperluas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [How to save barcode images with Barcode Generator C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}