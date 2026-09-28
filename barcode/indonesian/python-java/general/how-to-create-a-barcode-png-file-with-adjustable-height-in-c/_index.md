---
category: general
date: 2026-08-19
description: Pelajari cara menghasilkan file PNG barcode di C# dan menyesuaikan tingginya,
  mencakup cara membuat gambar barcode serta mengubah tinggi barcode dengan mudah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: id
lastmod: 2026-08-19
og_description: Buat file PNG barcode di C# dan pelajari cara menghasilkan gambar
  barcode, mengatur tinggi barcode, serta mengubah tinggi barcode untuk pemindaian
  optimal.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Buat file PNG barcode di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Cara membuat file PNG barcode dengan tinggi yang dapat disesuaikan di C#
url: /id/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat file barcode PNG dengan tinggi yang dapat disesuaikan di C#

Jika Anda perlu membuat **file barcode PNG** di C#, panduan ini menunjukkan cara melakukannya secara tepat. Anda akan melihat contoh lengkap yang dapat dijalankan yang mendemonstrasikan **cara menghasilkan gambar barcode** dan **cara menyesuaikan tinggi barcode** untuk berbagai kasus penggunaan.

Membuat file barcode PNG adalah kebutuhan umum untuk sistem inventaris, terminal point‑of‑sale, dan aplikasi apa pun yang harus mencetak atau menampilkan data yang dapat dibaca mesin. Pada akhir tutorial ini Anda akan dapat mengubah tinggi barcode, menyimpan beberapa file PNG, dan memahami dampak tinggi terhadap keandalan pemindaian.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET)  
* Paket NuGet **Aspose.BarCode for .NET** (contoh kode menggunakan pustaka ini)  

Anda dapat menambahkan paket tersebut dari baris perintah:

```bash
dotnet add package Aspose.BarCode
```

> **Tips:** Versi evaluasi gratis Aspose.BarCode dapat digunakan untuk pengembangan dan pengujian. Untuk produksi, dapatkan kunci lisensi.

## Instal pustaka barcode

Langkah pertama adalah mereferensikan pustaka dalam proyek Anda. Tambahkan direktif `using` berikut di bagian atas file C# Anda:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Namespace ini memberi Anda akses ke `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`.

## Buat file barcode PNG

Sekarang kita membuat instance `BarcodeGenerator` yang akan menghasilkan **file barcode PNG**. Contoh ini menggunakan simbol Databar OmniDirectional, tetapi Anda dapat mengganti `EncodeTypes.DatabarOmniDirectional` dengan tipe yang didukung apa pun.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

String `"(01)12345678901231"` mengikuti format GS1 Application Identifier untuk GTIN 14‑digit. Sesuaikan data tersebut dengan pengidentifikasi produk Anda sendiri.

## Atur dimensi X (opsional)

Dimensi X menentukan lebar satu modul barcode. Nilai berbasis piksel memberi Anda kontrol presisi atas ukuran gambar.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nilai `2` piksel bekerja baik untuk kebanyakan tampilan layar. Tingkatkan nilai tersebut jika Anda memerlukan barcode yang lebih besar saat dicetak.

## Sesuaikan tinggi barcode dan simpan file barcode PNG

Properti **BarHeight** mengontrol ukuran vertikal batang. Mengubah nilai ini memungkinkan Anda **menyesuaikan tinggi barcode** tanpa memengaruhi data yang dikodekan.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

File `DatabarBarHeight30Pixels.png` kini menjadi **file barcode PNG** dengan tinggi 30 piksel.  

Untuk **mengubah tinggi barcode** dan membuat gambar kedua, cukup tetapkan nilai baru dan panggil `Save` lagi:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG—satu dengan tinggi 30 px dan satu lagi dengan tinggi 60 px—menunjukkan cara **menyesuaikan tinggi barcode** secara dinamis.

### Mengapa tinggi batang penting

* **Keterbacaan:** Scanner mengharapkan tinggi minimum untuk deteksi yang dapat diandalkan. Barcode yang terlalu pendek dapat terlewat, terutama pada kamera beresolusi rendah.  
* **Estetika:** Menyesuaikan tinggi barcode dengan elemen desain di sekitarnya menciptakan UI yang lebih bersih.  
* **Keterbatasan cetak:** Beberapa printer label memiliki slot tinggi tetap; menyesuaikan tinggi barcode memastikan barcode muat.

**Praktik terbaik:** Jaga tinggi sebagai kelipatan dimensi X (misalnya, 30 px ketika dimensi X adalah 2 px) untuk mempertahankan proporsi dan menghindari distorsi.

## Contoh lengkap

Berikut adalah program lengkap yang dapat Anda tempelkan ke aplikasi konsol dan jalankan langsung.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Output yang diharapkan**

Menjalankan program akan membuat dua file di direktori kerja executable:

* `DatabarBarHeight30Pixels.png` – file barcode PNG setinggi 30 piksel  
* `DatabarBarHeight60Pixels.png` – file barcode PNG setinggi 60 piksel  

Buka salah satu PNG dengan penampil gambar apa pun; Anda akan melihat barcode Databar OmniDirectional yang jelas dan siap dipindai.

## Kasus tepi dan pemecahan masalah

| Situasi | Hal yang harus diperiksa | Perbaikan yang disarankan |
|-----------|---------------|-----------------|
| Barcode tampak buram | Dimensi X terlalu rendah untuk tinggi yang dipilih | Tingkatkan `XDimension.Pixels` (misalnya, dari 2 ke 3) |
| Scanner gagal pada barcode berukuran rendah | Tinggi di bawah minimum scanner | Atur `BarHeight.Pixels` setidaknya 30 px (atau sesuai spesifikasi scanner) |
| File PNG kosong atau rusak | Jalur output tidak valid atau izin menulis ditolak | Gunakan jalur absolut atau pastikan aplikasi memiliki akses menulis |
| Membutuhkan simbol yang berbeda | `EncodeTypes` saat ini tidak cocok | Ganti `EncodeTypes.DatabarOmniDirectional` dengan nilai enum lain (misalnya, `EncodeTypes.Code128`) |

## Pertanyaan yang sering diajukan

**T: Bisakah saya menghasilkan format gambar lain (JPEG, BMP)?**  
J: Ya. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, dll.

**T: Bagaimana cara menyematkan PNG ke dalam halaman web?**  
J: Layani PNG yang dihasilkan melalui endpoint HTTP atau konversi menjadi string Base64 dan letakkan di atribut `src` tag `<img>`.

**T: Apakah ada cara mengatur warna latar belakang?**  
J: Gunakan `generator.Parameters.Image.BackgroundColor = Color.White;` (atau `System.Drawing.Color` apa pun).

## Kesimpulan

Anda kini tahu cara **menghasilkan file barcode PNG** di C# dan secara tepat **menyesuaikan tinggi barcode** untuk memenuhi persyaratan pemindaian atau desain. Dengan mengubah properti `BarHeight.Pixels` Anda dapat **mengubah tinggi barcode** secara dinamis dan menghasilkan banyak aset PNG dari satu basis kode.

Selanjutnya, jelajahi opsi kustomisasi lain seperti warna depan, margin, dan menambahkan teks yang dapat dibaca manusia. Anda juga dapat bereksperimen dengan simbol yang berbeda (`EncodeTypes.Code128`, `EncodeTypes.QR`) untuk memperluas jenis data yang dapat Anda enkode.

Selamat coding, semoga barcode Anda selalu dapat dipindai pada percobaan pertama!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}