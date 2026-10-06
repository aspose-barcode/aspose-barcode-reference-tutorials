---
category: general
date: 2026-08-19
description: Buat file PNG databar di C# dengan Aspose.BarCode. Pelajari cara menghasilkan
  gambar databar, mengonfigurasi parameter databar, dan menyimpan output PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: id
lastmod: 2026-08-19
og_description: Buat file PNG databar di C# menggunakan Aspose.BarCode. Tutorial ini
  memandu Anda cara menghasilkan gambar databar, mengonfigurasi parameter databar
  seperti dimensi X dan rasio aspek, serta menyimpan file PNG berkualitas tinggi untuk
  pencetakan atau penggunaan web.
og_image_alt: create databar PNG example
og_title: Buat gambar PNG databar di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Cara membuat gambar PNG databar dengan C# dan Aspose.BarCode
url: /id/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar PNG databar dengan C# dan Aspose.BarCode

Jika Anda perlu **membuat PNG databar** dalam aplikasi .NET, panduan ini menunjukkan secara tepat caranya. Anda akan melihat contoh lengkap yang dapat dijalankan yang menghasilkan kode DataBar omnidirectional bertumpuk, mengonfigurasi parameter kunci, dan menyimpan dua file PNG dengan rasio aspek yang berbeda.

Membuat gambar DataBar bukan hanya sekadar memanggil satu metode. Anda juga harus **mengonfigurasi parameter databar** seperti X‑dimension (lebar modul) dan rasio aspek agar memenuhi spesifikasi pencetakan atau pemindaian. Pada akhir tutorial ini Anda akan memahami **cara menghasilkan grafik databar** yang berfungsi andal dalam skenario dunia nyata.

## Prasyarat

- .NET 6.0 atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7+)
- Visual Studio 2022 atau IDE lain yang kompatibel dengan C#
- Lisensi yang valid untuk **Aspose.BarCode for .NET** (evaluasi gratis dapat digunakan untuk pengujian)
- Pengetahuan dasar tentang sintaks C#

> **Pro tip:** Jika Anda belum memiliki lisensi, Anda dapat meminta kunci evaluasi sementara dari portal Aspose. API berperilaku sama; hanya watermark yang berubah.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka proyek Anda di Visual Studio, klik kanan solusi, dan pilih **Manage NuGet Packages**. Cari `Aspose.BarCode` dan instal versi stabil terbaru.

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan assembly `Aspose.BarCode` ke proyek Anda dan membuat kelas `BarcodeGenerator` tersedia.

## Langkah 2: Inisialisasi generator barcode untuk DataBar omnidirectional bertumpuk

Konstruktor `BarcodeGenerator` menerima dua argumen: tipe barcode dan string data mentah. Untuk DataBar omnidirectional bertumpuk Anda menggunakan `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Mengapa ini penting:** Konstanta `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu perpustakaan untuk menghasilkan barcode yang dapat dibaca dari orientasi apa pun, yang ideal untuk label rak ritel.

## Langkah 3: Konfigurasikan X‑dimension (lebar modul) dalam piksel

X‑dimension mengontrol ukuran elemen bar terkecil. Menetapkannya dalam piksel memberi Anda kontrol presisi atas ukuran gambar akhir.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nilai **2 piksel** merupakan keseimbangan yang baik antara keterbacaan dan kepadatan untuk kebanyakan printer label. Sesuaikan nilai ini jika Anda memerlukan modul yang lebih besar atau lebih kecil.

## Langkah 4: Atur rasio aspek pertama dan simpan PNG

Rasio aspek memengaruhi tinggi DataBar bertumpuk. Rasio aspek **15** menghasilkan barcode yang relatif pendek, sementara **30** membuatnya lebih tinggi.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Metode `Save` menulis barcode yang dihasilkan ke file PNG. PNG bersifat lossless, sehingga mempertahankan tepi tajam yang dibutuhkan pemindai barcode.

## Langkah 5: Ubah rasio aspek dan simpan PNG kedua

Anda dapat menggunakan kembali instance `BarcodeGenerator` yang sama untuk menghasilkan variasi hanya dengan mengubah rasio aspek.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Sekarang Anda memiliki dua file PNG—`DatabarAspectRatio15.png` dan `DatabarAspectRatio30.png`—masing‑masing dengan kepadatan visual yang berbeda.

## Langkah 6: Verifikasi output

Buka file PNG yang dihasilkan di penampil gambar apa pun. Anda harus melihat barcode DataBar yang bersih dan kontras tinggi. Memindai gambar dengan pemindai barcode smartphone mengonfirmasi bahwa kedua rasio aspek mendekode nilai GTIN asli `12345678901231`.

![create databar PNG example](databar_example.png)

*Gambar di atas menampilkan dua file PNG berdampingan. Gambar kiri menggunakan rasio aspek 15, gambar kanan menggunakan rasio aspek 30.*

## Variasi umum dan kasus tepi

| Skenario | Apa yang diubah | Alasan |
|----------|----------------|--------|
| **Data berbeda** | Ganti string `(01)12345678901231` dengan Identifier Aplikasi GS1 yang valid dan data apa pun | Memungkinkan Anda mengkodekan ID produk, nomor seri, dll. |
| **Resolusi lebih tinggi** | Tingkatkan `XDimension.Pixels` menjadi 3 atau 4 | Diperlukan ketika barcode akan dicetak dalam ukuran besar atau dipindai dari jarak jauh. |
| **Tipe DataBar lain** | Gunakan `EncodeTypes.DatabarStacked` atau `EncodeTypes.DatabarExpanded` | Pilih tipe yang paling cocok dengan tata letak label Anda. |
| **Latar belakang transparan** | Pass `BarCodeImageFormat.Png` dengan `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Berguna untuk menempatkan barcode di atas label berwarna. |

> **Waspadai:** Menetapkan X‑dimension yang terlalu kecil (< 1 piksel) dapat menghasilkan barcode yang tampak buram setelah

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}