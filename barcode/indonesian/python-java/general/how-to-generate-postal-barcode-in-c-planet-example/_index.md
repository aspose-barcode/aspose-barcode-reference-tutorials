---
category: general
date: 2026-10-28
description: Hasilkan kode batang pos dalam C# menggunakan format Planet. Contoh kode
  batang Planet ini menunjukkan cara mengatur lebar kode batang dan menyimpan batang
  yang terisi maupun yang kosong.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: id
lastmod: 2026-10-28
og_description: Buat kode batang pos di C# dengan contoh kode batang planet lengkap.
  Pelajari cara mengatur lebar kode batang, menghasilkan bar terisi, dan membuat gambar
  bar kosong.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Buat kode batang pos di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara menghasilkan kode batang pos di C# – contoh planet
url: /id/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode pos di C# – contoh planet

Jika Anda perlu menghasilkan barcode pos di C#, panduan ini akan menuntun Anda melalui solusi lengkap. Anda akan melihat contoh barcode planet yang praktis yang mengkodekan string numerik, memungkinkan Anda mengatur lebar barcode, dan menyimpan gambar bar yang terisi maupun kosong.

Membuat barcode pos tidak memerlukan pipeline build yang kompleks. Pada akhir tutorial ini Anda dapat mengintegrasikan pembuatan barcode ke dalam aplikasi .NET apa pun, menyesuaikan dimensi‑X, dan memilih apakah bar ditampilkan terisi atau kosong.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Lingkungan pengembangan C# (Visual Studio, VS Code, atau Rider)  
* Paket NuGet **Aspose.BarCode for .NET** (versi 23.10 atau lebih baru)  

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

Potongan kode di bawah mengasumsikan Anda telah menambahkan `using Aspose.BarCode.Generation;` di bagian atas file Anda.

## Menghasilkan barcode pos dengan simbol Planet

Langkah pertama adalah membuat instance `BarcodeGenerator` yang menggunakan simbol Planet. Planet adalah format barcode pos yang dipakai oleh beberapa layanan pos nasional.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Mengapa ini penting:**  
`EncodeTypes.Planet` memberi tahu perpustakaan untuk menggunakan standar barcode Planet, yang mengkodekan data numerik dalam serangkaian bar dan spasi. Konstruktor menerima string data (`"123456"` dalam contoh ini) yang ingin Anda kodekan.

Menjalankan program menghasilkan dua file PNG di direktori kerja executable:

* **PostalPlanetFilledBars.png** – bar ditampilkan sebagai persegi panjang hitam solid.  
* **PostalPlanetEmptyBars.png** – bar ditampilkan sebagai persegi panjang putih dengan outline hitam, berguna untuk pencetakan pada latar belakang gelap.

## Mengatur lebar barcode (dimensi‑X) dalam piksel

Ukuran visual barcode dikendalikan oleh dimensi‑X, yang menentukan lebar satu bar. Menyesuaikan nilai ini memastikan barcode dapat dipindai dengan benar pada resolusi cetak yang ditargetkan.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Mengapa Anda harus mengaturnya:**  
Dimensi‑X yang lebih besar membuat barcode lebih mudah dipindai dengan pemindai beresolusi rendah, sementara nilai yang lebih kecil mengurangi ukuran gambar keseluruhan untuk pencetakan ber‑density tinggi. Lebar default adalah 2 piksel; 4 piksel merupakan kompromi umum untuk kebanyakan printer desktop.

Anda dapat bereksperimen dengan nilai yang berbeda:

| Piksel | Kasus penggunaan umum |
|--------|-----------------------|
| 2      | Label ber‑density tinggi |
| 4      | Pencetakan kantor standar |
| 6‑8    | Signage format besar |

**Tip:** Selalu uji barcode yang dihasilkan dengan pemindai target setelah mengubah dimensi‑X.

## Contoh barcode Planet – bar terisi vs kosong

Barcode Planet dapat dirender dengan bar solid (terisi) atau bar ber‑outline (kosong). Properti `FilledBars` mengatur perilaku ini.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Mengapa Anda mungkin memilih bar kosong:**  
Bar kosong meningkatkan kontras pada kemasan berwarna gelap, karena interior putih setiap bar menonjol di atas latar belakang gelap. Bar terisi adalah default dan bekerja baik pada media berwarna terang.

**Output yang diharapkan:**  

*Kedua gambar menampilkan data yang sama (`123456`).* Perbedaan visual hanya pada gaya bar. Berikut deskripsi tekstual apa yang akan Anda lihat:

* **Gambar bar terisi:** Bar vertikal hitam solid pada latar belakang putih.  
* **Gambar bar kosong:** Outline hitam membentuk pola yang sama, dengan interior putih.

Anda dapat membuka file PNG di penampil gambar apa pun untuk memverifikasi bahwa pola tersebut sesuai dengan spesifikasi Planet.

## Menyesuaikan properti barcode tambahan (opsional)

Meskipun langkah inti di atas mencakup sebagian besar skenario, Anda mungkin ingin menyempurnakan pengaturan lain:

| Properti | Deskripsi | Nilai umum |
|----------|-----------|------------|
| `Barcode.Color` | Warna latar depan bar | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Warna latar belakang | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Teks yang dapat dibaca manusia ditampilkan di bawah barcode | Sama dengan data yang dikodekan atau label khusus |
| `Barcode.ImageFormat` | Format output (PNG, JPEG, BMP, dll.) | `BarCodeImageFormat.Png` |

Contoh mengatur warna latar depan khusus:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Penyesuaian opsional ini membantu Anda menyesuaikan merek perusahaan atau memenuhi persyaratan pencetakan tertentu.

## Kesalahan umum dan cara menghindarinya

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| Barcode tidak terbaca | Dimensi‑X terlalu kecil untuk DPI printer | Tingkatkan `XDimension.Pixels` menjadi 4 atau lebih |
| File gambar rusak | Tidak ada izin menulis di folder target | Gunakan path absolut atau pastikan direktori ada |
| Simbol yang salah digunakan | Mengirim `EncodeTypes.Code128` alih‑alih `EncodeTypes.Planet` | Verifikasi argumen `EncodeTypes` sesuai format pos |

**Pro tip:** Selalu hasilkan barcode percobaan dan pindai dengan perangkat keras yang dituju sebelum diterapkan ke produksi.

## Contoh lengkap yang dapat dijalankan

Berikut adalah aplikasi konsol mandiri yang menggabungkan semua langkah yang dibahas. Salin kode ke proyek konsol .NET baru dan jalankan untuk melihat dua file PNG muncul di folder output.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Langkah verifikasi:**  

1. Build proyek (`dotnet build`).  
2. Jalankan executable (`dotnet run`).  
3. Temukan `PostalPlanetFilledBars.png` dan `PostalPlanetEmptyBars.png` di folder `bin/Debug/net6.0`.  
4. Buka masing‑masing gambar; Anda akan melihat serangkaian bar vertikal yang mewakili string numerik


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}