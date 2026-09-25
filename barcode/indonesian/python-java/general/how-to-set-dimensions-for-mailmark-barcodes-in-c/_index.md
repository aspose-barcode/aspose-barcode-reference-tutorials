---
category: general
date: 2026-08-22
description: Pelajari cara mengatur dimensi untuk kode batang Mailmark di C# dan menyimpannya
  sebagai gambar PNG. Termasuk kode lengkap, penjelasan, dan tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: id
lastmod: 2026-08-22
og_description: Cara mengatur dimensi untuk kode batang Mailmark di C# dan mengekspornya
  sebagai file PNG. Ikuti contoh lengkap dan hindari jebakan umum.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Cara mengatur dimensi kode batang Mailmark di C# – panduan langkah demi
  langkah
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Cara mengatur dimensi kode batang Mailmark di C#
url: /id/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur dimensi untuk barcode Mailmark di C#

Jika Anda perlu **mengatur dimensi** untuk barcode Mailmark di C#, panduan ini menunjukkan langkah‑langkah yang tepat. Anda akan melihat cara mengonfigurasi X‑dimension dan tinggi bar, lalu menyimpan barcode sebagai gambar PNG tanpa alat tambahan.

Membuat barcode pos adalah tugas rutin saat membangun perangkat lunak label surat, tetapi ukuran default sering tidak cocok dengan printer atau kebutuhan tata letak. Pada akhir tutorial ini Anda akan dapat mengontrol ukuran barcode secara tepat dan menghasilkan dua tipe Mailmark yang valid (tipe C dan tipe L) siap untuk dicetak.

**Apa yang akan Anda pelajari**

* Cara mengatur X‑dimension (lebar modul) dan tinggi bar untuk sebuah `BarcodeGenerator`.
* Cara menyimpan barcode yang dihasilkan sebagai file PNG menggunakan `BarCodeImageFormat`.
* Kesulitan umum seperti jalur folder tidak valid atau nilai dimensi yang tidak didukung.
* Tips untuk menggunakan kembali konfigurasi yang sama pada banyak barcode.

## Prasyarat

* .NET 6.0 atau lebih baru (kode juga berfungsi dengan .NET Framework 4.6+).
* Paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan kompatibel lain yang menyediakan `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`).
* Familiaritas dasar dengan sintaks C# dan I/O file.

> **Pro tip:** Instal paket dengan perintah CLI  
> `dotnet add package Aspose.BarCode` untuk menjaga proyek Anda tetap rapi.

## Langkah 1: Tentukan folder output

Sebelum membuat barcode apa pun, Anda harus memutuskan ke mana file PNG akan ditulis. Menggunakan jalur absolut menghindari kejutan pada mesin yang berbeda.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Mengapa ini penting*: Jika folder tidak ada, `Save` akan melempar `IOException`. Pemanggilan `Directory.CreateDirectory` bersifat idempotent—tidak melakukan apa‑apa jika folder sudah ada.

## Langkah 2: Buat barcode Mailmark tipe C dan **atur dimensi**

Mailmark tipe C mengkodekan string alfanumerik sepanjang 20 karakter. Setelah menginisialisasi generator, Anda dapat **mengatur dimensi** melalui objek `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Mengapa memilih nilai ini?

* **X‑dimension** mengontrol lebar bar terkecil (sebuah “modul”). Nilai `4` piksel menghasilkan barcode yang mudah dibaca oleh kebanyakan printer laser sekaligus menjaga ukuran file tetap kecil.
* **BarHeight** menentukan ukuran vertikal bar. `50` piksel adalah tinggi umum untuk label pos standar, tetapi Anda dapat meningkatkannya untuk format yang lebih besar.

> **Kasus tepi:** Beberapa printer memerlukan tinggi bar minimum 30 px. Menetapkan tinggi lebih rendah dari kemampuan printer dapat menyebabkan barcode yang tidak dapat dibaca.

## Langkah 3: Buat barcode Mailmark tipe L dan **atur dimensi**

Tipe L menggunakan string data yang lebih panjang (hingga 30 karakter). Pendekatan pengaturan dimensi yang sama berlaku.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Menggunakan kembali konfigurasi

Jika Anda menghasilkan banyak barcode dengan dimensi yang identik, pertimbangkan untuk mengekstrak konfigurasi ke dalam metode pembantu:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Memanggil `ApplyStandardDimensions(mailmarkC)` dan `ApplyStandardDimensions(mailmarkL)` mengurangi duplikasi dan membuat perubahan di masa depan (misalnya, beralih ke modul 5 piksel) menjadi satu baris edit.

## Langkah 4: Verifikasi file PNG yang dihasilkan

Setelah menjalankan program, buka dua file PNG di penampil gambar apa pun. Anda harus melihat dua barcode Mailmark yang berbeda, masing‑masing 4 px per modul dan 50 px tinggi.

*Output yang diharapkan*

| Nama file                     | Dimensi perkiraan (px) |
|-------------------------------|------------------------|
| `PostalMailmarkCType.png`     | 4 px × modul × N modul |
| `PostalMailmarkLType.png`     | 4 px × modul × N modul |

Lebar tepat tergantung pada panjang data yang dikodekan, tetapi tinggi akan selalu **50 px** karena kami menetapkan `BarHeight.Pixels`.

## Kesulitan umum dan cara menghindarinya

| Masalah                               | Gejala                                         | Solusi |
|---------------------------------------|-----------------------------------------------|--------|
| Jalur folder tidak valid              | `IOException: Could not find a part of the path` | Gunakan `Path.Combine` dengan `Environment.SpecialFolder` atau verifikasi string jalur. |
| X‑dimension diatur ke 0 atau negatif | Barcode muncul sebagai blok padat            | Pastikan `XDimension.Pixels` adalah bilangan bulat positif (minimum 1). |
| `EncodeTypes.Mailmark` tidak didukung | `ArgumentException` saat konstruktor generator | Pastikan Anda menggunakan versi terbaru perpustakaan Aspose.BarCode yang mencakup dukungan Mailmark. |
| Menyimpan dengan format gambar yang salah | File PNG rusak                               | Gunakan `BarCodeImageFormat.Png` (atau `Jpeg` jika memerlukan format lain). |

## Memperluas contoh

* **Ukuran berbeda** – Ubah `XDimension.Pixels` menjadi 3 untuk barcode yang lebih kompak, atau tingkatkan `BarHeight.Pixels` menjadi 70 untuk label yang lebih besar.
* **Generasi batch** – Lakukan loop melalui koleksi string data, menerapkan pengaturan dimensi yang sama pada setiap iterasi.
* **Format gambar lain** – Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp` jika alur kerja Anda memerlukannya.

## Kesimpulan

Anda kini tahu **cara mengatur dimensi** untuk barcode Mailmark di C# dan mengekspornya sebagai file PNG. Dengan mengonfigurasi `XDimension.Pixels` dan `BarHeight.Pixels` Anda mengendalikan ukuran visual baik barcode tipe C maupun tipe L, memastikan mereka memenuhi spesifikasi printer dan batasan tata letak.  

Dari sini Anda dapat bereksperimen dengan nilai dimensi yang berbeda, mengintegrasikan kode ke dalam sistem label pos yang lebih besar, atau menghasilkan batch barcode untuk operasi pengiriman massal.

---

*Langkah selanjutnya*: jelajahi **dimensi BarcodeGenerator** untuk QR code, atau baca dokumentasi Aspose.BarCode tentang **menetapkan DPI** untuk cetakan resolusi tinggi. Jika Anda perlu menyematkan barcode dalam PDF, gabungkan pendekatan ini dengan perpustakaan **Aspose.PDF** untuk solusi end‑to‑end yang lengkap.

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Set Border for ITF-14 Barcode Customization](/barcode/english/net/itf-14-barcode-customization/)
- [How to Configure Patch Code Barcodes with Aspose.BarCode for .NET](/barcode/english/net/patch-code-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}