---
category: general
date: 2026-11-17
description: Pelajari cara menghasilkan barcode PDF417, mengatur ukuran barcode, dan
  merender barcode ke gambar menggunakan C#. Panduan lengkap langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: id
lastmod: 2026-11-17
og_description: Hasilkan kode batang PDF417 dalam C# dan render kode batang ke gambar.
  Ikuti panduan ini untuk mengatur ukuran kode batang dan menyimpan file PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Buat kode batang PDF417 dan render sebagai PNG – Panduan C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Cara menghasilkan barcode PDF417 dan merendernya sebagai PNG
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 dan merendernya sebagai PNG

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, tutorial ini menunjukkan secara tepat caranya. Anda akan melihat cara mengatur ukuran barcode, mengonfigurasi tata letak, dan **merender barcode ke gambar** dengan hanya beberapa baris kode C#.

Menghasilkan barcode PDF417 umum dilakukan ketika Anda ingin mengkodekan sejumlah besar data untuk dipindai pada perangkat seluler atau printer. Pada akhir panduan ini Anda akan memiliki file PNG siap pakai yang dapat Anda sematkan dalam laporan, email, atau halaman web.

## Prasyarat

- .NET 6.0 SDK atau yang lebih baru terpasang  
- IDE C# seperti Visual Studio 2022 (editor apa pun dapat digunakan)  
- Paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan kompatibel lain yang menyediakan `BarcodeGenerator`)  

Anda dapat menambahkan paket dengan:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Buat proyek konsol C#

Pertama, siapkan aplikasi konsol minimal yang akan menampung kode pembuatan barcode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Tips profesional:** Jaga metode `Main` tetap singkat dan delegasikan pekerjaan berat ke metode pembantu. Ini meningkatkan keterbacaan dan memudahkan pengujian unit.

## Langkah 2: Hasilkan barcode PDF417 dengan ukuran khusus

Sekarang kita akan **menghasilkan barcode PDF417** dan menentukan ukuran modul (dimensi X). Dimensi X mengontrol seberapa lebar setiap kotak kecil barcode, secara efektif menentukan ukuran keseluruhan barcode.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### Mengapa mengatur dimensi X?

Langkah **cara mengatur ukuran barcode** penting karena dimensi X yang terlalu kecil dapat membuat barcode tidak terbaca pada pemindai beresolusi rendah, sementara nilai yang terlalu besar membuang ruang. Nilai `2` piksel bekerja dengan baik untuk kebanyakan tampilan layar dan skenario pencetakan.

## Langkah 3: Panggil metode generasi dari `Main`

Hubungkan semuanya dengan memanggil `GeneratePdf417` menggunakan teks yang diinginkan dan lokasi output.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

Menjalankan program akan membuat `LayoutPdf417.png` yang berisi barcode:

![Barcode PDF417 yang dihasilkan](/images/layout-pdf417.png "Barcode PDF417 yang dihasilkan oleh kode tutorial"){: .align-center alt="Barcode PDF417 yang dihasilkan disimpan sebagai PNG"}

> **Output yang diharapkan:** File PNG berukuran kira-kira 200 × 100 px (tergantung pada pengaturan kolom/baris) yang menampilkan pola PDF417 yang jelas siap untuk dipindai.

## Langkah 4: Verifikasi barcode berfungsi

Untuk memastikan barcode valid:

1. Buka file PNG dengan penampil gambar apa pun.  
2. Gunakan aplikasi pemindai barcode smartphone yang mendukung PDF417 (misalnya, Google Lens, QR & Barcode Scanner).  
3. Pindai gambar; aplikasi harus mengembalikan teks *Layout demo*.

Jika pemindaian gagal, periksa kembali dimensi X serta nilai kolom/baris—modul yang lebih besar meningkatkan keterbacaan pada kamera beresolusi rendah.

## Variasi umum dan kasus tepi

| Scenario | Adjustment |
|----------|------------|
| **Data lebih** (mis., URL) | Tingkatkan `Columns` atau `Rows` untuk menampung codewords tambahan. |
| **Cetak resolusi tinggi** | Naikkan `XDimension.Pixels` menjadi 3‑4 px untuk bar yang lebih tajam. |
| **Transparent background** | Gunakan `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Format gambar berbeda** | Ganti `BarCodeImageFormat.Png` dengan `Jpeg` atau `Bmp` sesuai kebutuhan. |

Variasi ini menjawab pertanyaan **cara menghasilkan PDF417** untuk berbagai kebutuhan sambil mempertahankan logika inti yang sama.

## Kesimpulan

Anda sekarang tahu cara **menghasilkan barcode PDF417**, **mengatur ukuran barcode**, dan **merender barcode ke gambar** menggunakan C#. Contoh lengkap yang dapat dijalankan ini membuat file PNG yang dapat disematkan di mana saja Anda membutuhkan barcode yang dapat dibaca mesin.

Selanjutnya, jelajahi topik terkait seperti **menyematkan PNG ke dalam PDF** (cari *render barcode to PDF*), atau **menghasilkan barcode 2‑D lainnya** seperti kode QR. Sesuaikan parameter tata letak agar cocok dengan desain UI Anda, dan bereksperimen dengan opsi warna untuk branding.

Selamat coding, dan biarkan barcode Anda melakukan pekerjaan berat!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara menghasilkan barcode PDF417 di C# – panduan lengkap langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Cara menghasilkan barcode micro pdf417 di C# – panduan langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Cara Mengatur Tingkat Kesalahan pada Barcode PDF417 – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}