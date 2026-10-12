---
category: general
date: 2026-09-29
description: Cara mengatur lebar barcode GS1 DataBar Omni‑Directional dan cara mengubah
  tinggi menggunakan C#. Ikuti panduan langkah demi langkah dengan kode lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: id
lastmod: 2026-09-29
og_description: Cara mengatur lebar barcode GS1 DataBar Omni‑Directional dan mengubah
  tinggi di C#. Pelajari panggilan API yang tepat dan lihat contoh lengkap yang dapat
  dijalankan.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Cara mengatur lebar kode batang GS1 DataBar – panduan C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Cara mengatur lebar dan menyesuaikan tinggi untuk barcode GS1 DataBar Omni‑Directional
  di C#
url: /id/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur lebar dan menyesuaikan tinggi untuk barcode GS1 DataBar Omni‑Directional di C#

Mengatur lebar barcode GS1 DataBar Omni‑Directional adalah tugas yang sering dilakukan ketika Anda memerlukan ukuran yang tepat untuk peralatan pemindaian. Dalam tutorial ini Anda juga akan belajar **cara mengubah tinggi** sehingga barcode cocok dengan tata letak Anda secara sempurna. Panduan ini membawa Anda melalui seluruh proses, mulai dari penyiapan proyek hingga contoh kode yang dapat dijalankan sepenuhnya.

Kami akan membahas:

* Paket NuGet yang diperlukan dan versi .NET.
* Mengapa X‑dimension (lebar modul) penting untuk keterbacaan barcode.
* Panggilan API yang tepat untuk **cara mengatur lebar** dan **cara mengubah tinggi**.
* Penanganan kasus tepi seperti lebar modul minimum dan rendering resolusi tinggi.
* Contoh lengkap yang dapat disalin‑tempel yang menghasilkan dua file PNG dengan tinggi bar yang berbeda.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

| Persyaratan | Alasan |
|------------|--------|
| .NET 6.0 SDK atau yang lebih baru | Contoh ini menggunakan fitur C# modern dan dapat dijalankan di Windows, Linux, atau macOS. |
| Visual Studio 2022 (atau IDE C# apa saja) | Menyediakan IntelliSense untuk API Aspose.Barcode. |
| **Aspose.Barcode for .NET** paket NuGet | Berisi `BarcodeGenerator`, `EncodeTypes`, dan dukungan format gambar. Instal dengan `dotnet add package Aspose.Barcode`. |
| Izin menulis ke folder tempat file PNG akan disimpan | Generator menulis gambar output ke disk. |

## Cara mengatur lebar barcode

Langkah **cara mengatur lebar** dilakukan dengan mengonfigurasi properti `XDimension` pada parameter barcode. `XDimension` mewakili lebar modul (garis atau ruang terkecil) dalam piksel, poin, atau milimeter. Menetapkannya dengan benar memastikan barcode memenuhi spesifikasi pemindai.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Mengapa X‑dimension penting

* **Toleransi pemindai** – Kebanyakan pemindai mengharapkan lebar modul minimum; nilai yang terlalu kecil dapat menyebabkan kesalahan pembacaan.
* **Resolusi cetak** – Saat mencetak pada 300 dpi, modul 2 px setara dengan ~0,17 mm, yang berada dalam rentang yang direkomendasikan untuk GS1 DataBar.
* **Ukuran gambar** – Nilai X‑dimension yang lebih besar meningkatkan lebar keseluruhan barcode, yang dapat memengaruhi batasan tata letak.

### Tips untuk pengaturan lebar yang andal

* **Jangan pernah menetapkan XDimension di bawah 1 px** – pustaka akan memaksa nilai minimum, tetapi barcode yang dihasilkan mungkin tidak dapat dibaca.
* **Sesuaikan dengan DPI target** – jika Anda merender ke format resolusi tinggi (misalnya TIFF pada 600 dpi), tingkatkan XDimension secara proporsional.
* **Uji dengan pemindai nyata** – setelah mengubah lebar, validasi barcode pada perangkat yang akan membacanya.

## Cara mengubah tinggi barcode

Setelah lebar ditentukan, Anda dapat mengontrol ukuran vertikal dengan properti `BarHeight`. Kode berikut menunjukkan **cara mengubah tinggi** dari 30 px menjadi 60 px dan menyimpan dua gambar terpisah.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Memahami tinggi bar

* **Keseimbangan visual** – Bar yang lebih tinggi meningkatkan keterbacaan pada latar belakang kontras rendah tetapi menambah jejak vertikal gambar.
* **Batas regulasi** – Beberapa standar (misalnya pelabelan ritel) menentukan tinggi bar maksimum; sesuaikan sesuai kebutuhan.
* **Rasio aspek** – Mengubah tinggi tidak memengaruhi lebar modul; Anda dapat menyetel keduanya secara independen.

### Penanganan kasus tepi untuk penyesuaian tinggi

| Situasi | Pendekatan yang disarankan |
|-----------|----------------------|
| Tinggi < 10 px | Tingkatkan menjadi setidaknya 10 px; bar yang sangat pendek dapat diabaikan oleh pemindai. |
| Bar sangat tinggi (≥ 100 px) | Pastikan media output (kertas, label) dapat menampung ruang tambahan tersebut. |
| Membutuhkan skala proporsional | Hitung `BarHeight = XDimension * desiredRatio` untuk menjaga konsistensi visual. |

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang menggabungkan langkah **cara mengatur lebar** dan **cara mengubah tinggi**. Salin kode ke proyek konsol baru, pulihkan paket NuGet Aspose.Barcode, dan jalankan. Dua file PNG akan muncul di folder `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Output yang diharapkan**

Menjalankan program menghasilkan dua file PNG:

* `DatabarBarHeight30Pixels.png` – barcode dengan tinggi 30 px, modul lebar 2 px.
* `DatabarBarHeight60Pixels.png` – barcode yang sama dengan tinggi vertikal dua kali lipat.

Buka salah satu gambar di penampil apa pun; Anda akan melihat simbol GS1 DataBar Omni‑Directional yang bersih dan siap dipindai.

## Pertanyaan umum terjawab

| Pertanyaan | Jawaban |
|----------|--------|
| *Bisakah saya menggunakan milimeter alih-alih piksel?* | Ya. Atur `generator.Parameters.Barcode.XDimension.Millimeters` dan `BarHeight.Millimeters`. Pustaka akan mengonversi ke piksel perangkat berdasarkan DPI gambar. |
| *Bagaimana jika saya membutuhkan tipe barcode yang berbeda?* | Ganti `EncodeTypes.DatabarOmniDirectional` dengan nilai `EncodeTypes` lain (misalnya `EncodeTypes.QR`). Properti lebar dan tinggi berfungsi dengan cara yang sama. |
| *Apakah ada cara menghasilkan SVG alih-alih PNG?* | Gunakan `BarCodeImageFormat.Svg` pada pemanggilan `Save`. Pengaturan lebar/tinggi tetap berlaku. |
| *Apakah saya perlu memanggil `generator.Dispose()`?* | `BarcodeGenerator` mengimplementasikan `IDisposable`. Pada aplikasi konsol Anda dapat membungkusnya dalam blok `using`, tetapi untuk contoh singkat ini opsional. |

## Kesimpulan

Anda kini mengetahui **cara mengatur lebar** barcode GS1 DataBar Omni‑Directional dan **cara mengubah tinggi** menggunakan API Aspose.Barcode di C#. Contoh lengkap menunjukkan cara membuat generator, mengonfigurasi `XDimension` dan `BarHeight`, serta menyimpan file PNG dengan ukuran vertikal yang berbeda.

Dari sini Anda dapat:

* Bereksperimen dengan `EncodeTypes` lain (mis., QR, Code128).
* Merender ke format resolusi tinggi seperti TIFF untuk pencetakan.
* Mengintegrasikan generator ke dalam API web yang mengembalikan barcode secara dinamis.

Selamat coding, semoga barcode Anda selalu terbaca dengan bersih!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Mengubah Tinggi Barcode di C# – Panduan Lengkap](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Contoh generator barcode di C# – mengatur lebar dan tinggi](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Cara menggunakan generator barcode C# untuk membuat barcode DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}