---
category: general
date: 2026-08-22
description: Cara menghasilkan barcode dengan cepat dan mempelajari cara mengubah
  ukuran barcode saat mengekspor gambar barcode sebagai PNG menggunakan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: id
lastmod: 2026-08-22
og_description: Cara menghasilkan barcode di C# dan dengan mudah mengubah ukuran barcode
  sebelum Anda mengekspor gambar barcode sebagai PNG. Ikuti panduan lengkap ini.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Cara menghasilkan gambar barcode dengan ukuran khusus di C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara menghasilkan gambar barcode dengan ukuran khusus di C#
url: /id/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan gambar barcode dengan ukuran khusus di C#

Jika Anda perlu **cara menghasilkan barcode** untuk otomatisasi pos, pelacakan inventaris, atau tiket acara, panduan ini menunjukkan solusi lengkap yang siap dijalankan di C#. Anda juga akan belajar **cara mengubah ukuran barcode** dan **mengekspor gambar barcode** dalam format PNG tanpa meninggalkan IDE Anda.

Kami akan menggunakan pustaka Aspose.BarCode karena mendukung simbologi OneCode, memungkinkan Anda mengontrol dimensi piksel demi piksel, dan menangani ekspor gambar dengan satu pemanggilan metode. Pada akhir tutorial Anda akan memiliki empat file PNG—masing‑masing mewakili barcode OneCode dengan jumlah digit yang berbeda.

## Prasyarat

- .NET 6.0 atau lebih baru (kode juga bekerja dengan .NET Framework 4.6+)
- Visual Studio 2022 (atau editor C# apa pun yang Anda sukai)
- Referensi NuGet ke **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Familiaritas dasar dengan sintaks C#

> **Tips pro:** Jika Anda sedang mengevaluasi pustaka ini, Aspose menawarkan percobaan gratis selama 30 hari yang mencakup semua fitur barcode.

## Langkah 1: Siapkan proyek konsol minimal

Buat aplikasi konsol baru dan tambahkan paket Aspose.BarCode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

File `Program.cs` yang dihasilkan akan berisi logika lengkap pembuatan barcode.

## Langkah 2: Cara menghasilkan barcode – buat metode yang dapat digunakan kembali

Berikut adalah metode mandiri yang menerima string data, nama file yang diinginkan, dan parameter ukuran opsional. Metode ini menunjukkan pola inti **cara menghasilkan barcode**.

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
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Mengapa metode ini penting

- **Encapsulation:** Semua pengaturan yang terkait ukuran berada di satu tempat, sehingga memanggil metode dengan dimensi berbeda menjadi sangat mudah.
- **Reusability:** Anda dapat menggunakan kembali metode yang sama untuk panjang string OneCode apa pun, yang penting karena OneCode hanya menerima 20‑31 digit.
- **Clarity:** Komentar yang diberi label emoji membimbing pembaca melalui tiga fase logis—inisialisasi, perubahan ukuran, dan ekspor.

## Langkah 3: Ubah ukuran barcode untuk kebutuhan yang berbeda

Kadang pemindai mengharapkan barcode yang lebih tinggi, atau tata letak cetak memerlukan modul yang lebih sempit. Properti `XDimension.Pixels` mengontrol lebar satu modul barcode, sementara `BarHeight.Pixels` mengatur tinggi keseluruhan.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Poin penting saat Anda mengubah ukuran:**

- **Minimum X‑dimension:** 1 pixel secara teknis diperbolehkan, tetapi kebanyakan pemindai membutuhkan setidaknya 2 pixel untuk pembacaan yang dapat diandalkan.
- **Maximum height:** Tidak ada batas keras, tetapi barcode yang sangat tinggi dapat melebihi area cetak pada label standar.
- **Aspect ratio:** Jaga rasio tinggi‑ke‑lebar‑modul tetap seimbang (≈12‑15 × lebar modul) untuk menghindari distorsi.

## Langkah 4: Ekspor gambar barcode dalam format lain (opsional)

Metode `Save` menerima beberapa nilai `BarCodeImageFormat`: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Jika Anda membutuhkan format vektor lossless, Anda dapat mengekspor ke `Svg` sebagai gantinya.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Mengekspor sebagai PNG adalah pilihan paling umum karena mempertahankan tepi yang tajam dan didukung secara luas oleh peramban web serta alur pencetakan.

## Output yang Diharapkan

Menjalankan program akan membuat empat file PNG di folder proyek:

- `PostalOneCodeBarcode20Digits.png` – barcode OneCode 20 digit
- `PostalOneCodeBarcode25Digits.png` – barcode OneCode 25 digit
- `PostalOneCodeBarcode29Digits.png` – barcode OneCode 29 digit
- `PostalOneCodeBarcode31Digits.png` – barcode OneCode 31 digit

Setiap gambar akan terlihat mirip dengan placeholder di bawah (grafik sebenarnya tergantung pada data numerik yang Anda berikan).

![Cara menghasilkan barcode contoh](https://example.com/placeholder.png "Cara menghasilkan barcode contoh")

*Teks alt gambar mencakup kata kunci utama untuk aksesibilitas dan SEO.*

## Pertanyaan umum dan kasus tepi

| Pertanyaan | Jawaban |
|------------|---------|
| **Bagaimana jika string data lebih pendek dari 20 digit?** | OneCode memerlukan minimal 20 digit. Tambahkan nol di depan string atau gunakan simbologi lain (mis., Code128). |
| **Apakah saya dapat menghasilkan barcode dalam lingkungan multi‑thread?** | Ya. `BarcodeGenerator` tidak thread‑safe, jadi buat instance generator terpisah per thread. |
| **Bagaimana cara mengatur warna latar belakang?** | Gunakan `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` sebelum memanggil `Save`. |
| **Apakah ada cara untuk menyematkan gambar langsung ke halaman HTML?** | Simpan gambar ke `MemoryStream`, konversi ke Base64, dan sematkan dengan `<img src="data:image/png;base64,..." />`. |

## Kesimpulan

Anda sekarang tahu cara **menghasilkan gambar barcode** di C# dengan Aspose.BarCode, cara **mengubah ukuran barcode** dengan menyesuaikan X‑dimension dan tinggi bar, serta cara **mengekspor gambar barcode** dalam format PNG (atau format lain). Metode `GenerateOneCode` yang dapat digunakan kembali memungkinkan Anda membuat barcode OneCode apa pun antara 20 hingga 31 digit dengan satu baris kode.

Dari sini Anda mungkin:

- Bereksperimen dengan simbologi lain (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Mengintegrasikan generator ke dalam API web yang mengembalikan gambar barcode sesuai permintaan.
- Menggabungkan output PNG dengan pustaka PDF untuk menyematkan barcode ke label pengiriman.

Selamat coding, dan silakan bagikan variasi Anda sendiri di kolom komentar!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah‑per‑Langkah](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara Menghasilkan dan Menyesuaikan Tinggi Barcode untuk One-Dimensional Databar menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}