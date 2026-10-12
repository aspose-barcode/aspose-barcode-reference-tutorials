---
category: general
date: 2026-09-26
description: Pelajari cara membuat gambar barcode pos di C#. Panduan ini menunjukkan
  cara menghasilkan barcode planet dan mengatur tinggi barcode untuk output khusus.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: id
lastmod: 2026-09-26
og_description: Buat gambar barcode pos dalam C# dengan cepat. Ikuti tutorial ini
  untuk menghasilkan barcode planet, mengatur tinggi barcode, dan menghasilkan file
  PNG berkualitas tinggi.
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: Buat gambar kode pos dengan tinggi khusus di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Cara membuat gambar barcode pos dengan tinggi khusus di C#
url: /id/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode pos dengan tinggi khusus di C#

Jika Anda perlu **membuat gambar barcode pos** untuk label pengiriman, tutorial ini menunjukkan langkah‑langkah yang tepat. Anda akan belajar cara menghasilkan barcode Planet, menyesuaikan tinggi bar, dan menyimpan hasilnya sebagai file PNG—semua dengan library Aspose.BarCode untuk .NET.

Membuat gambar barcode tidak memerlukan alat desain eksternal. Pada akhir panduan ini Anda dapat menghasilkan barcode dengan tinggi default maupun tinggi khusus untuk standar Planet dan RM4SCC, siap untuk diintegrasikan ke dalam alur kerja pengiriman apa pun.

## Prasyarat

* .NET 6.0 atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE C# apa pun)  
* Aspose.BarCode untuk .NET ditambahkan melalui NuGet (`Install-Package Aspose.BarCode`)  

Tidak diperlukan konfigurasi tambahan; library menangani rendering gambar secara internal.

## Langkah 1: Siapkan proyek dan impor namespace

Buat aplikasi konsol baru dan tambahkan pernyataan `using` yang diperlukan.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Namespace ini menyediakan kelas `BarcodeGenerator` dan enumerasi `EncodeTypes` yang akan Anda gunakan untuk **menghasilkan barcode planet** dan format pos lainnya.

## Langkah 2: Buat barcode Planet dengan tinggi bar default

Contoh pertama membuat barcode Planet menggunakan tinggi bar default library. Ini memperlihatkan output dasar sebelum Anda menerapkan ukuran khusus apa pun.

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**Mengapa ini penting:** Tinggi default cocok untuk kebanyakan printer label, tetapi beberapa alur kerja memerlukan bar yang lebih tinggi untuk meningkatkan keandalan pemindaian. Kode di atas memberi Anda gambar referensi untuk dibandingkan dengan versi tinggi khusus.

## Langkah 3: Terapkan tinggi bar khusus pada barcode Planet

Untuk **mengatur tinggi barcode** secara manual, tetapkan nilai piksel ke `BarHeight.Pixels`. Potongan kode berikut membuat barcode Planet dengan tinggi 100 piksel.

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Tips profesional:** Pilih tinggi bar yang sesuai dengan DPI printer Anda. Untuk printer 300 dpi, bar 100 piksel setara dengan kira‑kira 0,33 inci, yang sering direkomendasikan untuk pemindai pos.

## Langkah 4: Hasilkan barcode RM4SCC dengan tinggi default

RM4SCC adalah simbol pos umum lainnya. Prosesnya mirip dengan contoh Planet tetapi menggunakan `EncodeTypes.RM4SCC`.

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

Langkah ini mengonfirmasi bahwa logika **tinggi khusus generator barcode** yang sama berfungsi pada berbagai format pos.

## Langkah 5: Terapkan tinggi khusus pada barcode RM4SCC

Akhirnya, sesuaikan tinggi bar untuk barcode RM4SCC dengan cara yang sama seperti yang Anda lakukan pada barcode Planet.

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## Output yang Diharapkan

Menjalankan program lengkap menghasilkan empat file PNG di direktori output proyek:

| Nama file                               | Tinggi bar | Simbol |
|----------------------------------------|------------|--------|
| `PostalPlanetBarHeightDefault.png`     | default    | Planet |
| `PostalPlanetBarHeight100Pixels.png`   | 100 px     | Planet |
| `PostalRM4SCCBarHeightDefault.png`     | default    | RM4SCC |
| `PostalRM4SCCBarHeight100Pixels.png`   | 100 px     | RM4SCC |

Setiap gambar menampilkan barcode yang jelas dan kontras tinggi, siap untuk dicetak pada label pengiriman. Anda dapat membuka file PNG di penampil gambar apa pun untuk memverifikasi dimensi bar.

## Pertanyaan umum dan kasus tepi

**Bagaimana jika saya membutuhkan tinggi bar dalam milimeter bukan piksel?**  
Library bekerja dalam piksel karena langsung memetakan ke resolusi bitmap. Konversi milimeter ke piksel menggunakan DPI printer:  
`pixels = (mm / 25.4) * DPI`. Tetapkan `BarHeight.Pixels` dengan nilai yang dihitung.

**Apakah saya dapat mengubah tinggi bar setelah memanggil `Save`?**  
Tidak. Gambar barcode dirender pada saat `Save` dipanggil. Sesuaikan semua parameter sebelum memanggil `Save`.

**Apakah dimensi X yang lebih besar diperlukan untuk bar yang lebih tinggi?**  
Meningkatkan `XDimension` membuat setiap modul lebih lebar, yang dapat meningkatkan keterbacaan pada printer resolusi rendah. Namun, hal ini juga memperlebar lebar keseluruhan barcode. Uji kedua nilai untuk menemukan keseimbangan optimal bagi ukuran label Anda.

**Apakah kode yang sama akan bekerja pada .NET Framework 4.8?**  
Ya. Aspose.BarCode mendukung .NET Framework 4.6.2 dan yang lebih baru, sehingga Anda dapat menargetkan runtime lama tanpa perubahan.

## Kode sumber lengkap untuk salin‑tempel cepat

Berikut adalah program lengkap yang dapat dijalankan yang menggabungkan semua langkah yang dijelaskan di atas.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

Jalankan program, dan konsol akan mengonfirmasi bahwa setiap gambar telah disimpan. Anda kini dapat menyematkan file PNG ini ke dalam templat label pengiriman Anda, mencetaknya, atau mengirimkannya ke API logistik pihak ketiga.

## Kesimpulan

Anda kini tahu cara **membuat file gambar barcode pos** di C# menggunakan Aspose.BarCode. Panduan ini mencakup pembuatan barcode Planet, penyesuaian tinggi bar, dan penerapan teknik yang sama pada barcode RM4SCC. Dengan mengendalikan `XDimension` dan `BarHeight.Pixels`, Anda memperoleh hasil visual yang tepat sesuai dengan persyaratan layanan pos.

Selanjutnya, jelajahi topik terkait seperti **menghasilkan QR code untuk pelacakan**, **menyematkan barcode dalam faktur PDF**, atau **memproses batch banyak gambar barcode**. Menyesuaikan tinggi bar hanyalah satu cara; Anda juga dapat menyesuaikan warna, menambahkan teks yang dapat dibaca manusia, atau mengekspor ke SVG untuk penggunaan web.

Selamat coding, semoga kiriman Anda ter‑scan dengan sempurna!

## Apa yang Harus Anda Pelajari Selanjutnya?

- [Buat gambar barcode pos di C# – panduan langkah demi langkah](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [Buat Gambar Barcode Pos – Ubah Tinggi Barcode dengan Mudah](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [Cara menghasilkan barcode pos di C# dengan dimensi khusus](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}