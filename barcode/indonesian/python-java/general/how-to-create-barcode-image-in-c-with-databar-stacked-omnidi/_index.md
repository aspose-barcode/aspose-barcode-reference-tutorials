---
category: general
date: 2026-11-17
description: Buat gambar barcode di C# menggunakan perpustakaan Barcode Generator.
  Ikuti panduan ini untuk mempelajari cara menghasilkan kode DataBar stacked omnidirectional
  langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: id
lastmod: 2026-11-17
og_description: Buat gambar barcode di C# dengan contoh singkat. Pelajari cara menghasilkan
  barcode DataBar stacked omnidirectional menggunakan perpustakaan Barcode Generator.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Buat gambar barcode di C# – panduan lengkap untuk kode DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membuat gambar barcode di C# dengan DataBar stacked omnidirectional
url: /id/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode di C# dengan DataBar stacked omnidirectional

Jika Anda perlu **create barcode image** dalam aplikasi .NET, tutorial ini menunjukkan solusi lengkap yang siap dijalankan. Anda akan melihat secara tepat cara menggunakan API **Barcode Generator C#** untuk menghasilkan DataBar stacked omnidirectional, yang merupakan format yang dibahas oleh kueri *how to generate databar*.

Panduan ini melangkah melalui setiap langkah yang diperlukan—dari menginstal pustaka hingga menyesuaikan rasio aspek—sehingga Anda dapat menyalin kode, menjalankannya, dan langsung memperoleh file PNG. Tidak perlu mencari dokumentasi eksternal.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru terinstal (contoh juga berfungsi dengan .NET Framework 4.7+)
* Lingkungan pengembangan seperti Visual Studio 2022 atau VS Code
* Paket NuGet **Aspose.BarCode for .NET** (pustaka yang menyediakan `BarcodeGenerator`)

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Gunakan flag `--version` untuk mengunci paket ke rilis stabil terbaru, misalnya, `dotnet add package Aspose.BarCode --version 23.9`.

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru dan referensikan namespace yang diperlukan. Langkah ini menyiapkan lingkungan untuk kode **barcode generator c#** yang akan datang.

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
            // All barcode generation logic lives here
```

Namespace `Aspose.BarCode.Generation` berisi kelas `BarcodeGenerator`, yang merupakan inti dari alur kerja **create barcode image**.

## Langkah 2: Inisialisasi BarcodeGenerator untuk DataBar stacked omnidirectional

Generator memerlukan dua informasi: tipe barcode dan data yang akan dienkode. Nilai enum `EncodeTypes.DatabarStackedOmniDirectional` memilih varian DataBar yang tepat yang diperlukan oleh skenario *how to generate databar*.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Mengapa ini penting:* Memilih nilai `EncodeTypes` yang tepat memastikan gambar yang dihasilkan mematuhi spesifikasi industri untuk pemindaian ritel.

## Langkah 3: Tentukan ukuran modul (dimensi X) dalam piksel

Kepadatan visual barcode dikendalikan oleh dimensi X. Menetapkannya ke nilai piksel yang wajar menjamin gambar dapat dibaca baik di layar maupun cetakan.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Jika Anda memerlukan barcode yang lebih besar untuk pencetakan beresolusi rendah, tingkatkan nilai piksel sesuai kebutuhan.

## Langkah 4: Sesuaikan rasio aspek DataBar untuk membuat baris lebih tinggi

DataBar stacked omnidirectional terdiri dari dua baris. Memodifikasi `AspectRatio` memungkinkan Anda mengontrol tinggi masing‑masing baris, yang dapat berguna ketika ukuran default terasa sempit.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Rasio aspek `15` adalah pilihan umum untuk label ritel; Anda dapat bereksperimen dengan nilai antara `10` dan `20` untuk memenuhi kebutuhan tata letak tertentu.

## Langkah 5: Simpan barcode yang dihasilkan sebagai gambar PNG

Akhirnya, tulis gambar ke disk. PNG bersifat lossless, menjadikannya ideal untuk pemrosesan selanjutnya atau penyematan dalam PDF.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Menjalankan program menghasilkan file bernama **DatabarAspectRatio15.png** di direktori output proyek. Membuka file tersebut menampilkan barcode yang bersih dan kontras tinggi, siap untuk dipindai.

### Output yang Diharapkan

Gambar yang disimpan terlihat mirip dengan ilustrasi di bawah (visual sebenarnya dihilangkan untuk singkat).

*Alt text for the example image:* **create barcode image** – file PNG yang menampilkan DataBar stacked omnidirectional dengan rasio aspek 15.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian |
|-----------|------------|
| **Panjang payload berbeda** | Ganti string GTIN dengan konten DataBar yang valid (mis., `(01)01234567890123`). |
| **Resolusi lebih tinggi untuk cetakan besar** | Tingkatkan `XDimension.Pixels` menjadi 4 atau 5 dan opsional atur `Resolution` di `Parameters.Image`. |
| **Format DataBar lainnya** | Gunakan `EncodeTypes.DatabarStacked` untuk varian stacked dua‑baris tanpa kemampuan omnidirectional. |
| **Menyimpan sebagai JPEG** | Ubah `BarCodeImageFormat.Png` menjadi `BarCodeImageFormat.Jpeg` dan opsional atur `Quality`. |

Variasi ini menjawab pertanyaan lebih luas *how to generate databar* dengan menunjukkan bahwa generator yang sama dapat dikonfigurasi ulang untuk berbagai keluarga DataBar.

## Ringkasan kode sumber lengkap

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
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Salin kode ke `Program.cs`, pulihkan paket NuGet, dan jalankan `dotnet run`. Konsol akan mengonfirmasi lokasi gambar, dan Anda dapat membuka PNG untuk memverifikasi hasil **create barcode image**.

## Kesimpulan

Anda sekarang tahu cara **create barcode image** di C# menggunakan pustaka Barcode Generator dan cara **generate DataBar** dengan kontrol presisi atas ukuran dan rasio aspek. Contoh lengkap ini menunjukkan setiap pengaturan yang diperlukan—dari menginisialisasi `BarcodeGenerator` hingga mengekspor file PNG—sehingga Anda dapat mengintegrasikan pembuatan barcode ke dalam aplikasi .NET apa pun tanpa penelitian lebih lanjut.

### Apa selanjutnya?

* Jelajahi simbol barcode lain dengan `EncodeTypes` (mis., QR, Code128) – ekstensi alami dari alur kerja **barcode generator c#**.
* Gabungkan gambar yang dihasilkan dengan laporan PDF atau Excel menggunakan Aspose.PDF atau Aspose.Cells.
* Sesuaikan warna, tambahkan margin, atau sematkan barcode dalam API web untuk generasi on‑demand.

Silakan bereksperimen dengan parameter, dan biarkan kode menjadi fondasi andal untuk semua proyek terkait barcode Anda di masa depan. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menggunakan barcode generator C# untuk membuat barcode DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [Cara menggunakan barcode generator C# untuk membuat barcode DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Cara membuat barcode databar stacked di C# – panduan langkah‑demi‑langkah](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}