---
category: general
date: 2026-10-21
description: Buat kode batang databar stacked dengan cepat menggunakan C#. Pelajari
  cara mengatur dimensi X, menyesuaikan rasio aspek, dan menyimpan gambar PNG dalam
  tutorial lengkap ini.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: id
lastmod: 2026-10-21
og_description: Buat kode batang databar bertumpuk di C# dengan Aspose.BarCode. Ikuti
  panduan ini untuk mengonfigurasi dimensi X, mengubah rasio aspek, dan mengekspor
  file PNG.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Buat barcode databar bertumpuk di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: Cara membuat barcode databar stacked di C# – panduan langkah demi langkah
url: /id/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat databar stacked barcode di C# – panduan langkah demi langkah

Jika Anda perlu **membuat databar stacked barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan melihat cara mengonfigurasi X‑dimension, mengubah aspect ratio, dan menyimpan barcode sebagai file PNG.

Membuat barcode DataBar stacked tidak memerlukan pipeline build yang kompleks. Tutorial ini mencakup semua yang Anda perlukan: paket yang dibutuhkan, penjelasan kode per kode, dan tips untuk jebakan umum. Pada akhir tutorial Anda dapat menghasilkan beberapa gambar barcode dengan aspect ratio berbeda dalam satu metode.

## Apa yang Anda butuhkan

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE apa pun yang mendukung C#)  
* **Aspose.BarCode for .NET** paket NuGet – perpustakaan yang menyediakan `BarcodeGenerator` dan `EncodeTypes`  

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru atau tambahkan kode ke proyek yang sudah ada. Impor namespace yang diperlukan agar compiler mengenali kelas barcode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Pernyataan `using` ini mengekspor `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat` yang akan digunakan nanti dalam contoh.

## Langkah 2: Tentukan folder output

Pilih folder tempat file PNG yang dihasilkan akan disimpan. Menggunakan path absolut atau relatif berfungsi sama; contoh ini menggunakan folder relatif bernama `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Membuat folder secara programatik mencegah error runtime ketika direktori tidak ada.

## Langkah 3: Inisialisasi generator **create databar stacked barcode**

Buat instance `BarcodeGenerator` dengan `EncodeTypes.DatabarStackedOmniDirectional`. Data contoh `(01)12345678901231` mengikuti format GS1‑128 yang diperlukan oleh DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

Objek generator menyimpan semua parameter yang memengaruhi tampilan visual barcode.

## Langkah 4: Atur X‑dimension (lebar piksel bar terkecil)

X‑dimension mengontrol ukuran keseluruhan barcode tanpa mengubah data yang dikodekan. Nilai `2` piksel memberikan gambar yang jelas dan dapat dipindai untuk kebanyakan resolusi layar.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Sesuaikan nilai ini jika Anda membutuhkan barcode yang lebih besar atau lebih kecil; pertahankan rasio antara lebar dan tinggi secara konsisten.

## Langkah 5: Konfigurasikan aspect ratio dan simpan gambar pertama

Aspect ratio menentukan hubungan tinggi‑terhadap‑lebar dari barcode DataBar stacked. Aspect ratio `15` adalah nilai default umum yang menghasilkan tampilan kompak.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Metode `Save` menulis file PNG ke folder yang telah ditentukan sebelumnya. Nama file dengan jelas menunjukkan aspect ratio yang digunakan.

### Output yang diharapkan untuk aspect ratio 15

File `DatabarAspectRatio15.png` yang dihasilkan terlihat mirip dengan ilustrasi di bawah.

![Barcode image generated with aspect ratio 15](https://example.com/images/databar-aspect15.png "Barcode image generated with aspect ratio 15")

*Teks alternatif:* `create databar stacked barcode image saved with aspect ratio 15`

## Langkah 6: Ubah aspect ratio dan simpan gambar kedua

Anda dapat menggunakan kembali instance `BarcodeGenerator` yang sama untuk menghasilkan variasi. Mengubah `AspectRatio` menjadi `30` menggandakan tinggi setiap tumpukan bar, yang mungkin diperlukan untuk pencetakan resolusi tinggi.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Output yang diharapkan untuk aspect ratio 30

Gambar `DatabarAspectRatio30.png` lebih tinggi, mempertahankan lebar yang sama sambil meningkatkan keterbacaan untuk pemindai yang berada jauh.

![Barcode image generated with aspect ratio 30](https://example.com/images/databar-aspect30.png "Barcode image generated with aspect ratio 30")

*Teks alternatif:* `create databar stacked barcode image saved with aspect ratio 30`

## Kode sumber lengkap

Menggabungkan semua langkah menghasilkan program mandiri yang dapat Anda jalankan langsung.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Kompilasi dan jalankan program. Setelah eksekusi, direktori `Barcodes` berisi dua file PNG, masing‑masing mewakili **create databar stacked barcode** dengan aspect ratio yang berbeda.

## Tips profesional dan jebakan umum

* **Pro tip:** Jaga X‑dimension antara 1 px dan 4 px untuk kebanyakan kasus penggunaan berbasis layar. Nilai yang lebih besar meningkatkan ukuran file tanpa meningkatkan keandalan pemindaian.  
* **Pitfall:** Mengubah nilai `EncodeTypes` setelah generator dibuat tidak memperbarui encoding internal. Selalu tentukan `EncodeTypes` yang tepat di konstruktor.  
* **Pro tip:** Ketika Anda membutuhkan lebih dari dua aspect ratio, lakukan loop pada array nilai integer dan panggil `Save` di dalam loop. Ini mengurangi duplikasi kode.  
* **Pitfall:** Menyimpan ke path tanpa izin menulis akan melempar `UnauthorizedAccessException`. Pastikan aplikasi dijalankan dengan hak akses sistem file yang sesuai.

## Kesimpulan

Anda kini tahu cara **membuat databar stacked barcode** di C# menggunakan Aspose.BarCode. Panduan ini mencakup penyiapan lingkungan, konfigurasi X‑dimension, penyesuaian aspect ratio, dan penyimpanan file PNG. Dengan dasar ini Anda dapat menghasilkan variasi tambahan, mengintegrasikan pembuatan barcode ke dalam API web, atau menyematkan gambar ke dalam laporan PDF.

Selanjutnya, jelajahi topik terkait seperti praktik terbaik pemindaian **DataBar Stacked Omnidirectional**, menyematkan barcode dalam respons **ASP.NET Core**, atau menghasilkan **QR code** dengan perpustakaan yang sama. Bereksperimenlah dengan berbagai `EncodeTypes` dan format gambar untuk memenuhi kebutuhan aplikasi Anda.

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat gambar PNG databar dengan C# dan Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Cara mengatur kolom untuk barcode Databar Expanded Stacked – panduan lengkap C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar stacked omnidirectional barcode di C# – Panduan Lengkap](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}