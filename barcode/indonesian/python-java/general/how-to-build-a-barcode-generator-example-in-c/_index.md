---
category: general
date: 2026-09-19
description: contoh generator barcode yang menunjukkan cara mengubah tinggi, membuat
  DataBar Omni‑Directional, dan menyesuaikan dimensi barcode untuk output gambar C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: id
lastmod: 2026-09-19
og_description: contoh generator barcode yang mengajarkan cara mengubah tinggi, membuat
  DataBar Omni‑Directional, dan menyesuaikan dimensi barcode untuk gambar PNG C#
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Contoh generator barcode di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membuat contoh generator kode batang di C#
url: /id/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contoh generator barcode di C# – panduan pemrograman lengkap

Jika Anda membutuhkan **contoh generator barcode** untuk proyek .NET, panduan ini menunjukkan secara tepat cara membuat, mengonfigurasi, dan menyimpan barcode DataBar Omni‑Directional menggunakan C#. Anda akan belajar cara mengubah tinggi, menyesuaikan dimensi barcode, dan menghasilkan gambar PNG berkualitas tinggi—semua dalam satu aplikasi konsol yang dapat dijalankan.

Langkah‑langkah di bawah mencakup segala hal mulai dari menginstal SDK yang diperlukan hingga menyesuaikan dimensi‑X dan tinggi bar. Pada akhir tutorial Anda akan memiliki generator barcode siap pakai yang dapat diintegrasikan ke dalam faktur, inventaris, atau alur kerja pemindaian apa pun.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET)  
* Lisensi aktif untuk **Aspose.BarCode for .NET** (versi trial gratis dapat digunakan untuk pengujian)  

Jika Anda lebih memilih pustaka lain, konsep menyesuaikan dimensi dan menyimpan gambar tetap sama; cukup ganti pemanggilan API yang sesuai.

## Langkah 1: Siapkan proyek dan tambahkan paket Aspose.BarCode

Buat proyek konsol baru dan referensikan pustaka barcode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Perintah `dotnet add package` akan mengunduh versi stabil terbaru Aspose.BarCode, yang mencakup dukungan penuh untuk simbol DataBar Omni‑Directional.

## Langkah 2: Tulis contoh generator barcode lengkap

Buka **Program.cs** dan ganti isinya dengan kode berikut. Blok ini berisi **contoh generator barcode** secara lengkap—tanpa bagian yang hilang.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Mengapa setiap baris penting

* **Buat generator barcode** – Konstruktor `BarcodeGenerator` mengaitkan tipe enkoding (`EncodeTypes.DatabarOmniDirectional`) dengan data yang ingin Anda sematkan. Ini merupakan inti dari langkah **cara membuat databar**.  
* **Sesuaikan dimensi barcode** – Properti `XDimension.Pixels` menentukan lebar bar paling sempit. Mengubah nilai ini memengaruhi ukuran keseluruhan serta keandalan pemindaian.  
* **Cara mengubah tinggi** – Properti `BarHeight.Pixels` mengontrol ukuran vertikal. Menambah tinggi meningkatkan keterbacaan untuk pemindai genggam, sementara menguranginya menghemat ruang pada label kecil.  
* **Penyesuaian opsional** – Menetapkan warna latar depan/latar belakang atau level koreksi‑error bersifat opsional namun memperlihatkan cara memperluas konsep **sesuaikan dimensi barcode**.  
* **Buat gambar barcode C#** – Metode `Save` menulis barcode ke disk. Menggunakan `BarCodeImageFormat.Png` memastikan kompresi lossless, yang ideal untuk kebanyakan aplikasi.

## Langkah 3: Bangun dan jalankan contoh

Kompilasi dan eksekusi program:

```bash
dotnet run
```

Anda akan melihat output konsol:

```
Barcode saved to DatabarOmniDirectional.png
```

Sebuah file bernama **DatabarOmniDirectional.png** muncul di folder proyek. Membuka gambar tersebut menampilkan barcode DataBar Omni‑Directional yang tajam dan siap dipindai.

## Cara mengubah tinggi setelah pembuatan

Jika Anda perlu menghasilkan barcode dengan tinggi yang bervariasi, bungkus penetapan tinggi dalam sebuah metode:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Panggil `SetBarHeight(generator, 45);` sebelum `Save`. Pendekatan ini memungkinkan Anda **cara mengubah tinggi** secara dinamis berdasarkan masukan pengguna atau file konfigurasi.

## Cara membuat barcode DataBar Omni‑Directional dengan data berbeda

Simbol DataBar Omni‑Directional mendukung GTIN‑14, GTIN‑13, dan pengenal numerik lainnya. Untuk mengenkode nilai yang berbeda, cukup ganti string di konstruktor:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Pastikan data tetap numerik dan terformat dengan benar; jika tidak, generator akan melempar `BarcodeException`.

## Sesuaikan dimensi barcode untuk berbagai skenario pencetakan

Berbagai printer dan ukuran label memerlukan X‑dimension dan tinggi yang berbeda. Gunakan tabel berikut sebagai referensi cepat:

| Skenario                     | X‑Dimension (piksel) | Tinggi Bar (piksel) |
|------------------------------|----------------------|---------------------|
| Label kecil (25 mm × 15 mm)  | 1                    | 20                  |
| Label sedang (50 mm × 30 mm) | 2                    | 30                  |
| Label besar (100 mm × 50 mm) | 3                    | 45                  |

Terapkan nilai‑nilai ini dengan mengatur `generator.Parameters.Barcode.XDimension.Pixels` dan `BarHeight.Pixels` secara sesuai.

## Tips pro: validasi barcode yang dihasilkan

Sebelum mengirimkan label, Anda dapat memverifikasi keterbacaan secara programatis:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Potongan kode ini memperlihatkan pemeriksaan cepat **sesuaikan dimensi barcode**, memastikan barcode memenuhi persyaratan pemindaian.

## Kesalahan umum dan cara menghindarinya

| Kesalahan                              | Mengapa terjadi                              | Solusi                                                                 |
|----------------------------------------|----------------------------------------------|------------------------------------------------------------------------|
| Menggunakan data non‑numerik untuk DataBar | DataBar mengharapkan format GTIN numerik      | Pastikan string sesuai pola `(01)XXXXXXXXXXXXX`.                      |
| Menetapkan X‑dimension ke 0 atau negatif | Pustaka melempar `ArgumentOutOfRangeException`| Gunakan minimal 1 piksel; uji dulu pada printer target.               |
| Menyimpan ke folder read‑only           | `UnauthorizedAccessException` pada `Save`    | Pilih direktori yang dapat ditulisi atau jalankan aplikasi dengan hak yang tepat. |
| Lupa membuang `BarCodeReader`           | Kebocoran memori pada layanan yang berjalan lama | Bungkus pembaca dalam blok `using` atau panggil `Dispose()` secara manual. |

Menangani masalah ini sejak dini menghemat waktu debugging dan meningkatkan stabilitas produksi.

## Ringkasan kode sumber lengkap

Berikut adalah program lengkap yang siap disalin, mengimplementasikan **contoh generator barcode** dari awal hingga akhir.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Menjalankan program ini menghasilkan file PNG yang tampak seperti ini (illustrasi):

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*Teks alt gambar*: **DataBar Omni‑Directional barcode generated in C#** (sesuai `og_image_alt`).

## Kesimpulan

Anda kini memiliki **contoh generator barcode** yang memperlihatkan cara mengubah tinggi, cara membuat simbol DataBar Omni‑Directional, dan cara **menyesuaikan dimensi barcode** untuk pemindaian optimal. Kode C# lengkap menyimpan gambar PNG, memvalidasinya, dan dapat diperluas untuk generasi massal atau integrasi ke layanan web.

Selanjutnya, jelajahi topik terkait seperti **membuat QR code dengan Aspose.BarCode**, **pemrosesan batch nilai barcode**, atau **menyematkan barcode ke dalam dokumen PDF**. Semua ini dibangun di atas dasar yang sama yang dibahas dalam panduan ini.

Selamat coding, semoga barcode Anda selalu dapat dipindai!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}