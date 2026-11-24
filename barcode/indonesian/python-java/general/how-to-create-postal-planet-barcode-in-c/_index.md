---
category: general
date: 2026-11-23
description: Buat kode batang postal planet di C# dengan Aspose.BarCode. Pelajari
  cara menghasilkan kode batang planet, mengatur dimensi X, dan menyimpan batang yang
  terisi atau kosong.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: id
lastmod: 2026-11-23
og_description: Buat kode batang planet pos dalam C# dan pelajari cara menghasilkan
  kode batang planet dengan Aspose.BarCode. Ikuti contoh lengkap untuk menghasilkan
  batang yang terisi dan kosong.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Cara membuat barcode Postal Planet di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cara membuat barcode Postal Planet di C#
url: /id/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode planet pos dalam C#

Jika Anda perlu **membuat barcode planet pos** dalam aplikasi .NET, panduan ini menunjukkan secara tepat **cara menghasilkan barcode planet** menggunakan pustaka Aspose.BarCode. Anda akan melihat cara mengonfigurasi dimensi X, beralih antara bar yang terisi dan kosong, serta menyimpan gambar dalam format PNG.

Membuat barcode Planet umum untuk layanan pos yang memerlukan simbol berkapasitas tinggi dan dapat dibaca mesin. Pada akhir tutorial ini Anda akan memiliki dua file PNG—satu dengan bar solid dan satu dengan bar kosong—siap untuk diintegrasikan ke dalam alur kerja pengiriman apa pun.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang.
* Visual Studio 2022 (atau editor C# apa pun) yang dikonfigurasi untuk pengembangan .NET.
* Lisensi NuGet aktif untuk **Aspose.BarCode for .NET**. Instal paket dengan:

```bash
dotnet add package Aspose.BarCode
```

Tidak ada layanan eksternal tambahan yang diperlukan; pustaka melakukan semua proses enkoding secara lokal.

## Langkah 1 – buat barcode planet pos

Operasi pertama adalah menginstansiasi `BarcodeGenerator` untuk simbol **Planet** dan menyediakan data yang akan dienkode. String data harus numerik dan maksimal 12 digit sesuai spesifikasi pos.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Membuat generator mengalokasikan semua struktur internal yang diperlukan untuk rendering. Nilai enum `EncodeTypes.Planet` memilih algoritma enkoding yang tepat untuk format pos.

## Langkah 2 – atur dimensi X untuk visibilitas yang lebih baik

Dimensi X menentukan lebar satu modul (elemen bar terkecil). Nilai 4 pixel memberikan representasi visual yang jelas tanpa memperbesar gambar secara keseluruhan.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Menyesuaikan dimensi X penting ketika barcode akan dicetak pada media beresolusi rendah. Pengaturan yang sama akan digunakan untuk versi bar kosong agar kedua gambar konsisten.

## Langkah 3 – simpan barcode dengan bar terisi

Secara default generator merender **bar terisi** (modul hitam solid). Menyimpan gambar cukup dengan satu pemanggilan metode yang menulis file PNG ke disk.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Ganti `YOUR_DIRECTORY` dengan jalur sebenarnya tempat Anda ingin menyimpan file output. Enumerasi `BarCodeImageFormat.Png` menjamin kompresi lossless, yang ideal untuk proses selanjutnya.

## Langkah 4 – buat generator Barcode Planet lain untuk bar kosong

Untuk menghasilkan versi yang menggunakan **bar kosong** (modul putih pada latar belakang hitam), Anda memerlukan instance `BarcodeGenerator` kedua. Menggunakan string data yang sama memastikan kedua gambar mewakili kode pos yang identik.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Membuat generator terpisah mengisolasi properti `FilledBars`, memungkinkan Anda mengubah gaya visual tanpa memengaruhi gambar pertama.

## Langkah 5 – konfigurasikan generator untuk merender bar kosong

Flag `FilledBars` membalik mode rendering. Menetapkannya ke `false` memberi tahu pustaka untuk menggambar bar sebagai kosong (transparan) sementara latar tetap solid.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Menjaga dimensi X tetap sama dengan versi terisi menjamin kedua file PNG memiliki dimensi yang sama, yang menyederhanakan perhitungan tata letak dalam templat pencetakan.

## Langkah 6 – simpan barcode yang merender bar kosong

Akhirnya, tulis gambar bar kosong ke disk. Format PNG yang sama tetap digunakan, namun Anda dapat beralih ke JPEG atau BMP dengan mengubah nilai `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Pada titik ini Anda memiliki dua file:

* `PostalPlanetFilledBars.png` – bar hitam solid.
* `PostalPlanetEmptyBars.png` – bar kosong pada latar belakang hitam.

Keduanya memenuhi spesifikasi pos untuk simbol Planet.

## Kode sumber lengkap

Menggabungkan semua langkah menghasilkan aplikasi konsol yang ringkas dan dapat dijalankan langsung.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Kompilasi dan jalankan program:

```bash
dotnet run
```

Konsol akan mencetak *Barcodes generated successfully.* dan dua file PNG akan muncul di folder proyek.

## Output yang diharapkan

Berikut adalah representasi visual dari gambar bar terisi. Versi bar kosong terlihat identik kecuali barnya transparan.

![Contoh barcode planet pos yang dibuat dengan bar terisi](postal-planet-filled.png)

*Teks alt gambar:* **Contoh barcode planet pos yang dibuat dengan bar terisi** (mengandung kata kunci utama).

Kedua gambar berukuran 150 × 150 pixel secara default, namun Anda dapat mengontrol ukuran keseluruhan dengan parameter `ImageWidth` dan `ImageHeight` jika diperlukan resolusi yang berbeda.

## Variasi opsional

### Mengubah format gambar

Jika sistem downstream Anda lebih menyukai JPEG, ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`. JPEG memperkenalkan artefak kompresi, jadi gunakan hanya ketika ukuran file menjadi kendala kritis.

### Menskalakan barcode

Anda dapat memperbesar barcode sambil mempertahankan lebar modul dengan menyesuaikan properti `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Nilai DPI yang lebih tinggi meningkatkan kualitas cetak pada printer laser.

### Menggunakan warna latar belakang khusus

Latar belakang dapat diatur dengan:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Ini berguna untuk pengujian visual tetapi sebaiknya dihindari pada label pos produksi, yang memerlukan latar belakang putih.

## Pertanyaan yang sering diajukan

**Apakah ini bekerja dengan .NET Core?**  
Ya. Pustaka Aspose.BarCode menargetkan .NET Standard 2.0, yang kompatibel dengan .NET 5, .NET 6, dan .NET Core 3.1.

**Bagaimana jika string data berisi karakter non‑numerik?**  
Barcode Planet hanya menerima input numerik. Memasukkan huruf atau simbol akan memicu `BarcodeException`. Validasi input sebelum membuat generator.

**Bisakah saya menghasilkan barcode di memori tanpa menulis ke disk?**  
Gunakan metode `GenerateBarCodeImage` untuk memperoleh objek `System.Drawing.Image`, lalu stream langsung ke respons atau basis data.

## Kesimpulan

Anda kini tahu cara **membuat barcode planet pos** dalam C# dan memahami **cara menghasilkan barcode planet** dengan gaya bar terisi dan kosong. Tutorial ini mencakup alur kerja lengkap—dari inisialisasi generator, konfigurasi dimensi X, mengubah flag `FilledBars`, hingga menyimpan file PNG. Bereksperimenlah dengan format gambar, pengaturan DPI, dan warna latar belakang untuk menyesuaikan barcode dengan sistem pengiriman Anda.

Untuk langkah selanjutnya, jelajahi simbol pos lainnya seperti **POSTNET** atau **Intelligent Mail** menggunakan API Aspose.BarCode yang sama. Menyesuaikan parameter seperti `EncodeTypes.Postnet` mengikuti pola yang ditunjukkan di sini, memungkinkan Anda membangun rangkaian generasi barcode yang komprehensif dalam satu basis kode.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}