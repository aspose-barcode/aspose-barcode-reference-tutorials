---
category: general
date: 2026-08-06
description: Hasilkan gambar barcode di C# menggunakan Aspose.BarCode. Pelajari cara
  menghasilkan Databar, menyesuaikan ukuran barcode khusus, dan mengubah tinggi barcode
  dengan kode sederhana.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: id
lastmod: 2026-08-06
og_description: Hasilkan gambar barcode dalam C# dengan Aspose.BarCode. Tutorial ini
  menunjukkan cara membuat barcode Databar Omnidirectional, menyesuaikan ukurannya,
  dan mengubah tinggi barcode secara efisien.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Buat gambar barcode di C# – panduan lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Buat gambar barcode di C# dengan Aspose.BarCode
url: /id/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan gambar barcode di C# dengan Aspose.BarCode

Jika Anda perlu **menghasilkan gambar barcode** secara programatik, panduan ini menunjukkan cara melakukannya secara tepat. Baik Anda sedang membangun sistem inventaris ritel maupun portal pelacakan logistik, Anda akan melihat alur kerja lengkap untuk membuat barcode Databar Omnidirectional, menyesuaikan dimensinya, dan menyimpan hasilnya sebagai file PNG.

Menghasilkan gambar barcode adalah kebutuhan umum, tetapi para pengembang sering bertanya **bagaimana cara menghasilkan Databar** dengan ukuran tepat yang mereka butuhkan. Dalam tutorial ini Anda akan belajar membuat barcode Databar, menyesuaikan lebar dan tinggi, serta mengubah tinggi barcode tanpa menulis ulang seluruh generator.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru (kode ini bekerja dengan .NET Core dan .NET Framework)
* Visual Studio 2022 (atau IDE apa pun yang mendukung C#)
* Lisensi Aspose.BarCode for .NET yang valid (versi evaluasi gratis dapat digunakan untuk pengujian)
* Familiaritas dasar dengan sintaks C#

## Langkah 1: Instal Aspose.BarCode

Tambahkan paket NuGet Aspose.BarCode ke proyek Anda:

```bash
dotnet add package Aspose.BarCode
```

Paket ini berisi kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini. Setelah instalasi, pulihkan proyek untuk mengambil dependensi.

## Langkah 2: Buat generator barcode dasar

Baris kode pertama membuat **generator barcode** yang akan menghasilkan simbol Databar Omnidirectional. Enum `EncodeTypes.DatabarOmniDirectional` memberi tahu perpustakaan simbol apa yang akan digunakan, dan string data mengikuti sintaks GS1 Application Identifier.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Mengapa ini penting:** Objek `BarcodeGenerator` adalah titik masuk untuk setiap operasi barcode. Dengan memilih `DatabarOmniDirectional` Anda memastikan output mematuhi standar GS1 untuk pemindaian ritel.

## Langkah 3: Atur X‑dimension khusus (lebar modul)

X‑dimension mengontrol lebar bar paling sempit. Menetapkannya ke nilai piksel kecil menghasilkan barcode yang kompak, sementara nilai yang lebih besar meningkatkan lebar keseluruhan.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Penjelasan:** X‑dimension 2 piksel adalah pilihan umum untuk layar beresolusi tinggi. Sesuaikan nilai ini jika Anda memerlukan kepadatan visual yang lebih rapat atau lebih longgar.

## Langkah 4: Hasilkan gambar barcode pertama dengan tinggi tertentu

Tinggi barcode bersifat independen dari X‑dimension. Di sini kita mengatur tinggi bar menjadi **30 px**, lalu menyimpan gambar sebagai PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Hasil:** Sekarang Anda memiliki file bernama `DatabarBarHeight30Pixels.png` yang menampilkan barcode Databar setinggi 30 px. Ini menunjukkan kemampuan **ukuran barcode khusus** untuk kasus penggunaan tertentu seperti label kecil.

## Langkah 5: Ubah tinggi barcode untuk versi yang lebih besar

Jika barcode yang sama harus muncul pada label yang lebih besar, Anda hanya perlu memodifikasi properti tinggi dan menggunakan kembali instance generator yang sama.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Mengapa Anda dapat menggunakan kembali generator:** Mengubah `BarHeight.Pixels` memperbarui tata letak internal tanpa membuat ulang objek, yang menghemat memori dan menjaga string data tetap utuh. Ini adalah cara yang disarankan untuk **mengubah tinggi barcode** secara dinamis.

## Langkah 6: Verifikasi output

Buka kedua file PNG di penampil gambar apa pun. Anda harus melihat dua barcode Databar Omnidirectional yang mengkodekan GTIN yang sama tetapi berbeda dalam ukuran vertikal:

* `DatabarBarHeight30Pixels.png` – setinggi 30 px, cocok untuk struk kompak.
* `DatabarBarHeight60Pixels.png` – setinggi 60 px, ideal untuk label rak yang lebih besar.

Kedua gambar mempertahankan X‑dimension yang sama, sehingga rasio bar‑to‑space tetap konsisten sementara tinggi keseluruhan berubah skala.

## Variasi umum dan kasus tepi

| Situasi | Cara menanganinya |
|-----------|------------------|
| **Simbol barcode yang berbeda** | Ganti `EncodeTypes.DatabarOmniDirectional` dengan nilai enum lain (misalnya `EncodeTypes.Code128`). Sisanya tetap tidak berubah. |
| **Dimensi bukan piksel** | Gunakan `generator.Parameters.Barcode.XDimension.Millimeters` atau `BarHeight.Millimeters` jika Anda memerlukan ukuran fisik untuk output siap cetak. |
| **Latar belakang transparan** | Set `generator.Parameters.ImageBackgroundColor = Color.Transparent;` sebelum memanggil `Save`. |
| **Output resolusi tinggi** | Tingkatkan baik `XDimension.Pixels` maupun `BarHeight.Pixels` secara proporsional, atau simpan sebagai `BarCodeImageFormat.Tiff` untuk kualitas lossless. |
| **Beberapa barcode dalam satu gambar** | Buat instance `BarcodeGenerator` terpisah, render masing‑masing ke `Bitmap`, lalu gabungkan menggunakan `Graphics.DrawImage`. |

**Tips pro:** Selalu uji barcode yang dihasilkan dengan pemindai nyata sebelum diterapkan ke produksi. Pemindai dapat menafsirkan bar yang sangat tipis secara berbeda tergantung pada pencahayaan dan kualitas sensor.

## Kode sumber lengkap untuk referensi

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
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Salin kode ke proyek konsol baru, jalankan, dan Anda akan melihat dua file PNG muncul di folder output.

## Pertanyaan yang sering diajukan

**T: Bisakah saya menghasilkan barcode tanpa memasang lisensi?**  
J: Versi evaluasi Aspose.BarCode dapat digunakan tanpa lisensi tetapi menambahkan watermark kecil. Untuk penggunaan produksi, terapkan lisensi yang dibeli dengan `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**T: Apakah mengubah X‑dimension memengaruhi keterbacaan?**  
J: Ya. X‑dimension yang sangat kecil dapat membuat barcode tidak terbaca pada printer beresolusi rendah. Minimum 1 px untuk rendering layar disarankan; untuk cetak, gunakan setidaknya 0.25 mm.

**T: Bagaimana jika saya perlu menghasilkan barcode dalam format JPEG?**  
J: Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`. Anda juga dapat mengatur `generator.Parameters.ImageQuality` untuk mengontrol kompresi.

## Kesimpulan

Anda kini tahu cara **menghasilkan gambar barcode** di C# menggunakan Aspose.BarCode, cara **membuat barcode Databar**, menyesuaikan **ukuran barcode khusus**, dan **mengubah tinggi barcode** sesuai kebutuhan. Contoh lengkap memperlihatkan alur kerja paling umum, dan tabel variasi mempersiapkan Anda menghadapi kasus tepi dunia nyata.

Selanjutnya, jelajahi topik terkait seperti **menyematkan barcode dalam dokumen PDF**, **menghasilkan batch barcode**, dan **menggunakan QR code untuk pembayaran seluler**. Setiap skenario tersebut dibangun di atas prinsip yang sama yang dibahas di sini, sehingga Anda dapat memperluas pengetahuan ini dengan percaya diri.

Selamat coding, semoga barcode Anda selalu ter-scan dengan sempurna!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}