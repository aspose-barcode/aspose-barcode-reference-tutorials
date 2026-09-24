---
category: general
date: 2026-08-06
description: Buat barcode databar bertumpuk dalam C# dengan cepat. Pelajari cara mengatur
  dimensi X, menyesuaikan rasio aspek, dan mengekspor file PNG menggunakan generator
  DataBar Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: id
lastmod: 2026-08-06
og_description: Buat kode batang databar bertumpuk di C# dengan Aspose.BarCode. Tutorial
  ini menunjukkan cara mengatur dimensi X, mengubah rasio aspek, dan menyimpan gambar
  PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Buat kode batang databar bertumpuk di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Buat kode batang databar bertumpuk di C# – panduan langkah demi langkah
url: /id/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat databar stacked barcode di C# – panduan langkah demi langkah

Jika Anda perlu **create databar stacked barcode** gambar di C#, panduan ini menunjukkan secara tepat cara melakukannya menggunakan library Aspose.BarCode. Anda akan belajar mengatur dimensi X, mengubah rasio aspek barcode, dan menyimpan hasilnya sebagai file PNG—semua dalam beberapa langkah singkat.

Membuat DataBar Stacked barcode umum ketika Anda harus mengkodekan data GS1‑128 untuk pemindaian ritel atau pelacakan logistik. Pada bagian-bagian berikut kami membahas semuanya mulai dari penyiapan proyek hingga verifikasi output, sehingga Anda dapat mengintegrasikan solusi ke dalam aplikasi .NET apa pun tanpa melewatkan detail.

## Prasyarat

* **.NET 6.0** (atau lebih baru) terpasang – kode menargetkan SDK modern.
* Salinan **licensed** dari **Aspose.BarCode for .NET**. Evaluasi gratis dapat digunakan untuk pengujian tetapi menambahkan watermark.
* IDE seperti **Visual Studio 2022** atau **VS Code** dengan ekstensi C#.
* Familiaritas dasar dengan sintaks **C#** dan konsep GS1 Application Identifiers.

> **Pro tip:** Jika Anda menggunakan NuGet package manager, perintah `dotnet add package Aspose.BarCode` menyelesaikan semua dependensi secara otomatis.

## Langkah 1: Buat proyek konsol baru

Buka terminal atau Package Manager Console dan jalankan:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

Perintah `dotnet new console` membuat file **Program.cs** minimal. Menambahkan paket **Aspose.BarCode** membuat kelas `BarcodeGenerator` tersedia.

## Langkah 2: Inisialisasi generator DataBar Stacked Omnidirectional

Buka **Program.cs** dan ganti konten default dengan kode berikut. Baris pertama membuat **BarcodeGenerator** yang dikonfigurasi untuk simbol **DataBar Stacked Omnidirectional** dan menyediakan payload GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Mengapa ini penting:** Nilai enum `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu library untuk menghasilkan **databar stacked barcode**, yang merupakan varian stacked dari keluarga DataBar omnidirectional. Simbol ini dapat menampung hingga 14 karakter numerik, menjadikannya ideal untuk kode GTIN‑14.

## Langkah 3: Atur dimensi X (lebar modul)

Dimensi X mengontrol lebar bar terkecil (modul). Nilai yang terlalu kecil dapat menghasilkan gambar yang buruk pada printer beresolusi rendah, sementara nilai yang terlalu besar dapat melebihi ruang label.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tip:** Properti `Pixels` nyaman untuk pengujian berbasis layar. Untuk skenario fokus cetak, gunakan `generator.Parameters.Barcode.XDimension.Millimeters` sebagai gantinya.

## Langkah 4: Sesuaikan rasio aspek dan simpan gambar pertama

Rasio **aspect ratio** memengaruhi hubungan tinggi‑lebar dari barcode stacked. Tipe DataBar Stacked Omnidirectional mendukung rasio dari 10 hingga 30. Kami akan menghasilkan dua gambar untuk menggambarkan dampak visual.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Pemanggilan `generator.Save` menulis file **PNG** ke direktori kerja saat ini. Enum `BarCodeImageFormat.Png` memastikan kompresi lossless, yang ideal untuk pemrosesan lanjutan atau penyematan dalam PDF.

## Langkah 5: Ubah rasio aspek menjadi 30 dan simpan gambar kedua

Sekarang kami meningkatkan tinggi bar stacked dengan mengubah rasio aspek menjadi **30**. Ini membuat barcode lebih tinggi tanpa mengubah dimensi X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Menjalankan program sekarang menghasilkan dua file PNG:

* **DatabarAspectRatio15.png** – barcode kompak yang cocok untuk label kecil.
* **DatabarAspectRatio30.png** – barcode lebih tinggi yang meningkatkan keandalan pemindaian pada permukaan berkontras rendah.

Anda dapat membuka gambar di penampil apa pun untuk memverifikasi bahwa bar terstack dengan benar dan data yang dikodekan cocok dengan string GS1 asli.

## Langkah 6: Verifikasi nilai yang dikodekan (opsional)

Jika Anda perlu memastikan bahwa barcode benar-benar mewakili string input, Anda dapat mendekodenya dengan library yang sama:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Dekoder harus menghasilkan `(01)12345678901231`, membuktikan bahwa proses **create databar stacked barcode** mempertahankan data.

## Kesalahan umum dan cara menghindarinya

| Masalah | Mengapa terjadi | Solusi |
|-------|----------------|-----|
| Barcode tampak buram | Dimensi X diatur terlalu rendah untuk resolusi output | Tingkatkan `XDimension.Pixels` atau gunakan `Millimeters` untuk pencetakan |
| Pemindai melaporkan “symbol tidak ditemukan” | Rasio aspek di luar rentang 10‑30 yang didukung | Pertahankan rasio antara 10 dan 30; 15 dan 30 adalah nilai default yang aman |
| PNG berisi watermark | Menggunakan lisensi evaluasi gratis Aspose.BarCode | Beli lisensi penuh atau gunakan trial hanya untuk pengujian |
| Dekode gagal pada gambar kedua | Dekoder dikonfigurasi untuk simbol yang salah | Gunakan `DecodeType.DatabarStackedOmniDirectional` saat membaca barcode stacked |

## Langkah selanjutnya

Setelah Anda dapat **create databar stacked barcode** gambar, Anda mungkin ingin:

* **Menyematkan PNG ke dalam faktur PDF** menggunakan library PDF seperti **Aspose.PDF**.
* **Menghasilkan barcode secara langsung dalam web API** – mengembalikan byte PNG langsung dari controller ASP.NET Core.
* **Mencoba varian DataBar lainnya** (mis., `DatabarExpanded`, `DatabarLimited`) dengan mengubah enum `EncodeTypes`.
* **Menyesuaikan warna** dengan mengatur `generator.Parameters.Barcode.ForeColor` dan `BackColor` untuk desain sesuai merek.

Setiap topik ini dibangun di atas konsep inti yang sama yang dibahas di sini: inisialisasi `BarcodeGenerator`, konfigurasi parameter visual, dan menyimpan hasil dengan `BarCodeImageFormat`.

---

### Kesimpulan

Tutorial ini menunjukkan cara **create databar stacked barcode** gambar di C# menggunakan Aspose.BarCode. Anda belajar mengatur **dimensi X**, memodifikasi **rasio aspek barcode**, dan mengekspor hasil sebagai file **PNG** dengan `BarcodeGenerator`. Dengan langkah dekode opsional, Anda juga dapat memverifikasi bahwa data GS1 yang dikodekan akurat. Terapkan pola ini ke inventaris, pengiriman, atau aplikasi point‑of‑sale Anda, dan jelajahi banyak opsi kustomisasi yang disediakan library. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Penyesuaian Tinggi Barcode Databar Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hasilkan gambar barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}