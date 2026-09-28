---
category: general
date: 2026-08-12
description: Buat gambar barcode di C# menggunakan BarCodeGenerator. Pelajari cara
  menghasilkan DataBar, mengontrol ukuran gambar barcode, dan membuat banyak barcode
  secara efisien.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: id
lastmod: 2026-08-12
og_description: Buat gambar barcode di C# dengan BarCodeGenerator. Tutorial ini menunjukkan
  langkah demi langkah cara menghasilkan kode DataBar, menyesuaikan ukuran gambar
  barcode, dan menghasilkan beberapa barcode.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Buat gambar barcode di C# – panduan lengkap BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Buat gambar barcode di C# dengan BarCodeGenerator
url: /id/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat gambar barcode di C# dengan BarCodeGenerator

Jika Anda perlu **membuat gambar barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya dengan kelas `BarCodeGenerator`. Baik Anda sedang membangun sistem POS ritel atau alat pelacakan inventaris, Anda akan belajar menghasilkan simbol DataBar, mengontrol ukuran gambar barcode, dan menghasilkan beberapa barcode dalam satu kali proses.

Anda juga akan menemukan bagaimana API **barcode generator c#** memungkinkan Anda menyesuaikan dimensi, mengubah format output, dan menangani kasus tepi seperti string data yang tidak valid. Pada akhir tutorial Anda dapat dengan yakin **membuat banyak barcode** tanpa menulis kode yang berulang.

## Prasyarat

- .NET 6.0 atau yang lebih baru terinstal  
- Lingkungan pengembangan (Visual Studio, Rider, atau VS Code)  
- Paket NuGet Aspose.BarCode untuk .NET (atau perpustakaan kompatibel lain yang menyediakan `BarCodeGenerator`)  

Anda dapat menambahkan paket dengan:

```bash
dotnet add package Aspose.BarCode
```

## Apa yang dibahas dalam tutorial ini

1. Menyiapkan instance **barcode generator c#** untuk enkoding DataBar Omni‑directional.  
2. Menyesuaikan **ukuran gambar barcode** dengan mengubah X‑dimension dan tinggi bar.  
3. Menggunakan loop untuk **membuat banyak barcode** dengan tinggi yang berbeda.  
4. Menyimpan gambar sebagai file PNG dan memverifikasi output.  

Semua potongan kode lengkap dan siap untuk disalin‑tempel ke dalam proyek konsol baru.

![Create barcode image example](barcode-example.png){alt="Contoh gambar barcode"}

## Langkah 1: Inisialisasi generator – dasar pembuatan gambar barcode

Langkah pertama adalah menginstansiasi `BarCodeGenerator` dengan simbol yang diinginkan. Untuk simbol DataBar Omni‑directional Anda menggunakan `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Mengapa ini penting:** Menginstansiasi generator mendefinisikan aturan enkoding dan muatan data. Jika Anda melewatkan nilai `EncodeTypes` yang tepat, perpustakaan akan menghasilkan barcode yang tidak didukung atau melemparkan pengecualian.

## Langkah 2: Konfigurasikan X‑dimension dan tinggi bar – kontrol ukuran gambar barcode

Ukuran visual sebuah barcode dipengaruhi oleh dua parameter:

| Parameter | Apa yang dikontrol | Rentang tipikal |
|-----------|--------------------|-----------------|
| `x_dimension.pixels` | Lebar modul terkecil (“titik”) | 1 – 4 px |
| `bar_height.pixels`  | Tinggi bar vertikal | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Tips profesional:** X‑dimension yang lebih kecil menghasilkan gambar dengan resolusi lebih tinggi tetapi mungkin lebih sulit dipindai pada printer berkualitas rendah. Sesuaikan nilai tersebut berdasarkan peralatan pemindaian target Anda.

## Langkah 3: Simpan barcode pertama – buat gambar barcode dengan tinggi 30 px

Sekarang Anda dapat menghasilkan gambar dan menuliskannya ke disk. Metode `Save` menerima jalur file dan enum format gambar.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Hasil yang diharapkan:** File PNG bernama `Databar30.png` muncul di `C:\Barcodes`. Membuka file tersebut menampilkan simbol DataBar Omni‑directional dengan pola yang jelas dan kontras tinggi.

## Langkah 4: Ubah tinggi dan hasilkan gambar tambahan – buat banyak barcode

Untuk **membuat banyak barcode** dengan dimensi yang berbeda Anda hanya perlu mengubah properti `BarHeight` dan memanggil `Save` lagi. Ini menghindari penginstansian ulang generator, yang menghemat memori dan waktu CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Mengapa ini berhasil:** Objek `BarCodeGenerator` menyimpan semua status konfigurasi. Mengubah satu properti memperbarui mesin rendering untuk panggilan `Save` berikutnya, memungkinkan Anda **membuat banyak barcode** secara efisien.

## Langkah 5: Lanjutan – cara menghasilkan DataBar dengan data khusus

Contoh di atas menggunakan payload GS1 statis. Dalam skenario dunia nyata Anda sering perlu menyematkan pengidentifikasi produk yang variabel. Perpustakaan menerima string apa pun yang sesuai dengan spesifikasi DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Poin penting:** Menetapkan `generator.CodeText` memperbarui data yang dienkode tanpa membuat ulang objek. Ini adalah pola **cara menghasilkan databar** yang direkomendasikan saat menangani kumpulan data besar.

## Langkah 6: Verifikasi dan pemecahan masalah – memastikan ukuran gambar barcode yang tepat

Setelah menghasilkan gambar, Anda mungkin ingin secara programatik memastikan bahwa dimensi sesuai dengan harapan Anda. Kelas `Image` dari `System.Drawing` dapat membaca file dan melaporkan ukurannya.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Jika tinggi tidak mencerminkan nilai yang Anda tetapkan, periksa:

- **X‑dimension**: Nilai yang sangat kecil dapat menyebabkan renderer membulatkan tinggi.  
- **Format gambar**: Beberapa format (mis., JPEG) menerapkan kompresi yang dapat mengubah dimensi piksel saat disimpan. PNG mempertahankan dimensi yang tepat.

## Langkah 7: Praktik terbaik untuk ukuran gambar barcode dan kinerja

| Rekomendasi | Alasan |
|-------------|--------|
| Pertahankan `x_dimension.pixels` antara 2 – 3 px untuk kebanyakan pemindai. | Menyeimbangkan keterbacaan dan ukuran file. |
| Gunakan PNG untuk output lossless ketika gambar akan dicetak. | Menjamin dimensi yang tepat dan tepi yang tajam. |
| Gunakan kembali satu instance `BarCodeGenerator` saat menghasilkan banyak barcode. | Mengurangi beban alokasi objek. |
| Validasi string input terhadap standar GS1 sebelum menetapkan ke `CodeText`. | Mencegah pengecualian runtime dan pemindaian yang tidak valid. |
| Simpan gambar yang dihasilkan dalam folder khusus dengan konvensi penamaan yang jelas (mis., `Databar_{GTIN}.png`). | Menyederhanakan proses downstream dan jejak audit. |

## Contoh lengkap yang berfungsi

Berikut adalah program lengkap yang menggabungkan semua langkah mulai dari inisialisasi hingga verifikasi. Salin kode ke dalam proyek konsol baru dan jalankan.



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun pada teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Hasilkan gambar barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Buat gambar barcode DotCode – baris & kolom (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Cara Membuat Zona Tenang Barcode untuk ITF-14 Menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}