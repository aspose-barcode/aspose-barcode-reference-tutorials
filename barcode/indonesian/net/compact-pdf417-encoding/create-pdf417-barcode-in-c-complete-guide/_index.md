---
category: general
date: 2026-09-22
description: Buat kode batang PDF417 di C# dengan Aspose.BarCode. Pelajari cara menghasilkan
  gambar kode batang PDF417, mengatur kolom/baris, dan menyimpannya sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
language: id
lastmod: 2026-09-22
og_description: Buat kode batang PDF417 di C# dengan Aspose.BarCode. Pelajari cara
  menghasilkan gambar kode batang PDF417, menyesuaikan tata letak, dan mengekspor
  ke PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Buat kode batang PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create PDF417 barcode in C# with Aspose.BarCode. Learn how to generate
    PDF417 barcode images, set columns/rows, and save as PNG.
  headline: Create PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
- image generation
title: Buat barcode PDF417 di C# – panduan lengkap
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat barcode PDF417 di C# – panduan lengkap

Jika Anda perlu **membuat barcode PDF417** dalam aplikasi .NET, tutorial ini menunjukkan secara tepat cara melakukannya. Anda akan melihat contoh lengkap yang dapat dijalankan yang menghasilkan barcode PDF417, menyesuaikan tata letak kolom dan barisnya, serta menyimpan hasilnya sebagai gambar PNG.

Membuat barcode merupakan kebutuhan umum untuk sistem inventaris, platform tiket, dan otomatisasi dokumen. Pada akhir panduan ini Anda akan dapat menjawab pertanyaan *bagaimana cara menghasilkan barcode PDF417* secara programatik, tanpa meninggalkan IDE Anda.

## Prasyarat

- .NET 6.0 atau yang lebih baru terpasang (kode ini juga berfungsi dengan .NET Framework 4.8)
- Versi terbaru **Aspose.BarCode for .NET** (versi percobaan gratis dapat digunakan untuk pengembangan)
- IDE seperti Visual Studio 2022 atau Visual Studio Code
- Pemahaman dasar tentang sintaks C#

> **Pro tip:** Jika Anda menggunakan pipeline CI/CD, tambahkan paket NuGet `Aspose.BarCode` ke file proyek Anda sehingga proses build akan memulihkannya secara otomatis.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan versi stabil terbaru dari pustaka ke proyek Anda dan memperbarui file `.csproj` sesuai.

## Langkah 2: Buat generator barcode PDF417

Objek generator adalah titik masuk untuk semua operasi barcode. Anda menentukan simbol (`EncodeTypes.Pdf417`) dan teks yang ingin dienkode.

```csharp
using Aspose.BarCode.Generation;

// ...

// Step 2: Instantiate the generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

Kelas `BarcodeGenerator` mengabstraksi algoritma enkoding, sehingga Anda tidak perlu berurusan dengan manipulasi bit tingkat rendah.

## Langkah 3: Sesuaikan tata letak PDF417 – kolom dan baris

PDF417 memungkinkan Anda mengontrol jumlah kolom (modul horizontal) dan baris (modul vertikal). Menyesuaikan nilai-nilai ini mengubah kepadatan dan ukuran fisik barcode.

```csharp
// Step 3: Configure layout
generator.Parameters.Barcode.Pdf417.Columns = 4; // supported range: 2‑10
generator.Parameters.Barcode.Pdf417.Rows = 9;    // optional; if omitted, rows are auto‑calculated
```

- **Columns**: Menentukan berapa banyak kolom data yang akan dimiliki barcode. Lebih sedikit kolom menghasilkan barcode yang lebih tinggi.
- **Rows**: Memungkinkan Anda memaksa tinggi tertentu. Membiarkannya pada `0` membuat mesin memilih jumlah optimal.

## Langkah 4: Simpan gambar barcode sebagai PNG

Akhirnya, ekspor barcode ke format gambar yang cocok untuk sebagian besar kerangka UI.

```csharp
using Aspose.BarCode;

// ...

// Step 4: Save as PNG
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Enum `BarCodeImageFormat.Png` memastikan kompresi lossless, yang ideal untuk pemrosesan lanjutan atau pencetakan.

## Contoh lengkap yang dapat dijalankan

Gabungkan semuanya dalam aplikasi console bernama `Pdf417Demo`.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Install Aspose.BarCode via NuGet before running this code

            // 2️⃣ Create the generator
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

            // 3️⃣ Set layout – 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;

            // 4️⃣ Define output path
            string outputPath = Path.Combine(
                Environment.CurrentDirectory, "Pdf417_4x9.png");

            // 5️⃣ Save the barcode
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode created at: {outputPath}");
        }
    }
}
```

### Output yang diharapkan

Menjalankan program mencetak baris konfirmasi dan membuat file yang mirip dengan tangkapan layar di bawah ini:

![Generated PDF417 barcode](/images/pdf417-example.png "Create PDF417 barcode – PNG output")

File `Pdf417_4x9.png` yang disimpan berisi simbol PDF417 yang jelas dan dapat dipindai yang mengenkripsi teks **“Sample”**.

## Cara menghasilkan barcode PDF417 dengan data khusus

Jika Anda perlu mengenkripsi lebih dari satu kata, cukup ganti argumen kedua `BarcodeGenerator` dengan string apa pun (termasuk baris baru). Pustaka secara otomatis membagi data ke dalam baris dan kolom sesuai tata letak yang Anda tentukan.

```csharp
var generator = new BarcodeGenerator(
    EncodeTypes.Pdf417,
    "OrderID: 12345\nDate: 2026-09-22\nCustomer: John Doe");
```

Pengaturan tata letak yang sama (columns = 4, rows = 9) tetap berlaku, tetapi barcode akan tumbuh secara vertikal jika data melebihi ruang yang tersedia.

## Kasus tepi dan pemecahan masalah

| Situation | What to check | Recommended fix |
|-----------|---------------|-----------------|
| Barcode terlihat terlalu kecil di layar | DPI PNG yang disimpan | Pass a `Resolution` object: `generator.Save(path, BarCodeImageFormat.Png, new Resolution(300))` |
| Baris diabaikan | `Rows` diatur ke `0` atau tidak diset | Explicitly assign a positive integer (e.g., `Rows = 9`) |
| Teks terpotong | Jumlah kolom terlalu sedikit untuk panjang data | Increase `Columns` (max 10) or let the engine auto‑size by setting `Columns = 0` |
| Pemindaian gagal pada perangkat seluler | Kontras tidak cukup | Use `generator.Parameters.Barcode.ForegroundColor = Color.Black` and `BackgroundColor = Color.White` |

## Mengapa Anda harus menggunakan Aspose.BarCode untuk PDF417

- **Kontrol penuh** atas tata letak (kolom, baris, koreksi kesalahan)
- **Tanpa ketergantungan** pada generasi gambar – tidak memerlukan pustaka grafis eksternal
- **Dukungan lintas platform** (Windows, Linux, macOS) karena menargetkan .NET Standard
- **Dokumentasi lengkap** dan contoh kode langsung dari vendor

Memilih pustaka ini memastikan bahwa tugas **membuat barcode PDF417** tetap dapat dipelihara dan tahan masa depan.

## Kesimpulan

Anda sekarang tahu cara **membuat barcode PDF417** di C# menggunakan Aspose.BarCode, menyesuaikan kolom dan barisnya, serta mengekspor hasilnya sebagai file PNG. Solusi lengkap ini menjawab *bagaimana cara menghasilkan barcode PDF417* untuk proyek .NET apa pun, dan Anda dapat memperluasnya dengan mengubah teks yang dienkode, format gambar, atau resolusi.

**Langkah selanjutnya**

- Bereksperimen dengan format gambar lain seperti `Jpeg` atau `Bmp`.
- Gabungkan barcode dengan dokumen PDF menggunakan `Aspose.PDF` untuk pembuatan laporan end‑to‑end.
- Jelajahi tingkat koreksi kesalahan (`generator.Parameters.Barcode.Pdf417.ErrorLevel`) untuk meningkatkan keandalan pemindaian di lingkungan yang berisik.

Selamat coding, dan nikmati menyematkan simbol PDF417 yang kuat dalam aplikasi Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang dapat dijalankan dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menyimpan Barcode di C# – Menghasilkan Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Contoh barcode Aspose: menghasilkan Macro PDF417 di C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Menghasilkan barcode PDF417 C# – panduan lengkap dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}