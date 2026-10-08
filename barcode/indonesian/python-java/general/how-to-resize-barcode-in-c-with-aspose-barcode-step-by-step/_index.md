---
category: general
date: 2026-09-23
description: Cara mengubah ukuran barcode di C# menggunakan Aspose.BarCode. Pelajari
  cara menghasilkan kode barcode C#, menyesuaikan ukuran, dan mengekspor gambar barcode
  secara efisien.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: id
lastmod: 2026-09-23
og_description: Cara mengubah ukuran barcode di C# dengan Aspose.BarCode. Ikuti panduan
  ini untuk menghasilkan kode barcode C#, menyesuaikan dimensi, dan mengekspor gambar
  barcode.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: Cara mengubah ukuran barcode di C# – tutorial lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: Cara mengubah ukuran barcode di C# dengan Aspose.BarCode – panduan langkah
  demi langkah
url: /id/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengubah ukuran barcode di C# dengan Aspose.BarCode – panduan langkah demi langkah

Jika Anda perlu **cara mengubah ukuran barcode** dalam aplikasi .NET, tutorial ini menunjukkan kode tepat yang dapat Anda salin‑tempel dan jalankan hari ini. Anda akan belajar cara **menghasilkan barcode C#**, menyesuaikan tinggi bar, dan **mengekspor gambar barcode** tanpa meninggalkan IDE Anda.

Membuat barcode umum dalam sistem inventaris, label pengiriman, dan terminal point‑of‑sale. Pada akhir panduan ini Anda akan dapat **membuat gambar Databar barcode** dengan tinggi berapa pun yang Anda perlukan, dan Anda akan memahami properti kunci yang mengontrol ukuran, resolusi, dan format file.

## Prasyarat

- .NET 6 atau lebih baru (contoh ini juga bekerja dengan .NET Framework 4.6+ )  
- Paket NuGet Aspose.BarCode untuk .NET (`Install-Package Aspose.BarCode`)  
- Familiaritas dasar dengan sintaks C# dan Visual Studio (atau IDE C# apa pun)  

Tidak diperlukan perpustakaan tambahan; Aspose.BarCode menangani rendering, scaling, dan ekspor gambar secara internal.

## Langkah 1: Siapkan proyek dan impor Aspose.BarCode

Buat proyek konsol baru (atau integrasikan ke proyek yang sudah ada) dan tambahkan namespace Aspose.BarCode:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **Pro tip:** Gunakan versi Aspose.BarCode terbaru (per September 2026) untuk mendapatkan perbaikan bug dan simbol barcode baru.

## Langkah 2: Inisialisasi generator barcode DataBar Omni‑directional

**Contoh generator barcode** dimulai dengan menentukan simbolologi (`EncodeTypes.DatabarOmniDirectional`) dan data payload. Payload mengikuti format GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Objek ini menyimpan semua parameter yang nantinya akan Anda ubah, seperti X‑dimension, tinggi bar, dan format gambar.

## Langkah 3: Tentukan parameter ukuran umum

Sebelum mengekspor, atur X‑dimension (lebar bar paling sempit) dan tinggi bar awal. X‑dimension dinyatakan dalam piksel; nilai `2` bekerja baik untuk kebanyakan resolusi layar.

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **Mengapa ini penting:** Properti `BarHeight` secara langsung memengaruhi ukuran visual barcode. Mengubahnya adalah inti dari **cara mengubah ukuran barcode** di Aspose.BarCode.

## Langkah 4: Ekspor gambar barcode pertama (tinggi 30 px)

Sekarang Anda dapat **mengekspor gambar barcode** ke file PNG. Metode `Save` secara otomatis merender barcode dengan parameter saat ini.

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

File yang dihasilkan terlihat seperti ini:

![How to resize barcode example](https://example.com/images/databar-30px.png){: .align-center alt="Contoh cara mengubah ukuran barcode – tinggi 30 piksel"}

## Langkah 5: Ubah tinggi bar untuk membuat barcode yang lebih besar

Untuk mendemonstrasikan **cara mengubah ukuran barcode** secara dinamis, sesuaikan properti `BarHeight` dan simpan kembali. Ini **tidak** memerlukan pembuatan instance `BarcodeGenerator` baru; Anda cukup memodifikasi objek yang sudah ada.

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Langkah 6: Ekspor gambar barcode yang diubah ukurannya (tinggi 60 px)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG—satu dengan tinggi 30 px dan satu lagi dengan tinggi 60 px—menunjukkan bagaimana data yang sama dapat dirender dengan ukuran berbeda.

### Output yang diharapkan

| Nama file                     | Tinggi bar (px) | Hasil visual |
|-------------------------------|----------------|---------------|
| `DatabarBarHeight30Pixels.png`| 30             | ![30 px barcode](https://example.com/images/databar-30px.png){: alt="barcode 30 px"} |
| `DatabarBarHeight60Pixels.png`| 60             | ![60 px barcode](https://example.com/images/databar-60px.png){: alt="barcode 60 px"} |

Kedua gambar merupakan barcode GS1‑128 DataBar yang valid dan siap dipindai.

## Langkah 7: Opsional – Sesuaikan pengaturan visual tambahan

Meskipun tujuan utama adalah **cara mengubah ukuran barcode**, Anda mungkin juga ingin menyesuaikan:

| Properti | Deskripsi | Nilai tipikal |
|----------|-----------|---------------|
| `XDimension.Pixels` | Lebar bar paling sempit | 1–4 |
| `BarHeight.Pixels`  | Tinggi seluruh barcode | 20–200 |
| `Resolution` | DPI untuk output raster | 72, 150, 300 |
| `ForeColor` / `BackColor` | Warna latar depan dan latar belakang | `Color.Black`, `Color.White` |

Contoh:

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

Penyesuaian ini tidak memengaruhi logika **resize**, tetapi memberi Anda kontrol penuh atas kualitas gambar akhir.

## Kesalahan umum dan cara menghindarinya

| Masalah | Gejala | Solusi |
|---------|--------|--------|
| Tinggi bar tidak berubah | Gambar yang disimpan terlihat identik | Pastikan Anda memodifikasi `barcode.Parameters.Barcode.BarHeight.Pixels` *sebelum* setiap pemanggilan `Save`. |
| Barcode menjadi tidak terbaca | Scanner melaporkan “cannot read” | Pertahankan `XDimension` ≥ 2 px untuk DataBar Omni‑directional; bar yang terlalu tipis dapat mengganggu pemindaian. |
| File PNG blur | Diekspor dengan DPI rendah | Atur `barcode.Parameters.ImageResolution.DpiX/Y` minimal 150 untuk gambar kualitas cetak. |
| File tertimpa secara tidak sengaja | Gambar baru menggantikan yang lama | Gunakan nama file unik atau sertakan nilai tinggi dalam nama file, seperti contoh di atas. |

## Contoh lengkap yang dapat dijalankan

Salin seluruh blok di bawah ini ke aplikasi konsol baru (`Program.cs`). Kode ini dapat dikompilasi dan dijalankan apa adanya, menghasilkan dua file PNG di folder output proyek.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

Menjalankan program menghasilkan:

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

Periksa folder output untuk dua file PNG. Kedua file siap untuk pencetakan, disisipkan ke PDF, atau dikirim ke perangkat remote.

## Kesimpulan

Dalam panduan ini kami membahas **cara mengubah ukuran barcode** di C# menggunakan Aspose.BarCode, memperlihatkan contoh lengkap **generator barcode**, dan menunjukkan cara **mengekspor gambar barcode** dengan tinggi berbeda. Sekarang Anda tahu cara:

1. **Membuat objek Databar barcode** dengan data khusus.  
2. Menyesuaikan `BarHeight` (inti dari proses resize).  
3. Mengekspor file PNG untuk ukuran apa pun yang dibutuhkan.  

Selanjutnya Anda dapat mengeksplorasi kustomisasi lebih lanjut—simbolologi lain, skema warna, atau format vektor seperti SVG. Pola yang sama (`barcode.Parameters.Barcode.BarHeight.Pixels = <nilai>`) berlaku untuk semua tipe barcode yang didukung Aspose.BarCode, sehingga Anda dapat menerapkan pengetahuan **cara mengubah ukuran barcode** dengan percaya diri di seluruh aplikasi Anda.

---

**Langkah selanjutnya**

- Coba ubah ukuran simbolologi lain (QR, Code128) untuk melihat bagaimana tinggi dan lebar berinteraksi.  
- Gunakan `BarCodeImageFormat.Svg` untuk menghasilkan grafik vektor skalabel bagi halaman web.  
- Integrasikan gambar yang dihasilkan ke dalam laporan PDF dengan Aspose.PDF atau iTextSharp.  

Selamat coding, dan nikmati fleksibilitas yang ditawarkan oleh pembuatan barcode secara programatik!

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}