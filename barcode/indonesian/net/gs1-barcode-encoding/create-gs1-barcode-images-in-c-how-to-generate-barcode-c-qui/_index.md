---
category: general
date: 2026-07-18
description: Buat gambar barcode GS1 di C# dengan panduan langkah demi langkah ini
  tentang cara menghasilkan barcode C# menggunakan Aspose.BarCode – tanpa basa‑basi,
  hanya kode yang berfungsi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: id
lastmod: 2026-07-18
og_description: Buat gambar barcode GS1 di C# dengan tutorial singkat ini. Pelajari
  cara menghasilkan barcode C# menggunakan Aspose.BarCode dan menyimpan file PNG dalam
  hitungan detik.
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: Buat Gambar Barcode GS1 di C# – Panduan Lengkap Cara Membuat
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: Buat Gambar Barcode GS1 di C# – Cara Cepat Menghasilkan Barcode dengan C#
url: /id/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Gambar Barcode GS1 di C# – Cara Menghasilkan Barcode C#

Pernah perlu **create gs1 barcode images** untuk label kemasan tetapi tidak yakin harus mulai dari mana? Anda tidak sendirian. Dalam tutorial ini Anda akan melihat secara tepat **how to generate barcode c#** kode yang menghasilkan gambar GS1‑MicroPDF417 dalam hitungan menit.

Kami akan membahas seluruh proses—menginstal pustaka, mengonfigurasi generator, menukar data AI (Application Identifier), dan akhirnya menyimpan sekumpulan file PNG. Pada akhir tutorial Anda akan memiliki aplikasi konsol siap‑jalankan yang menghasilkan beberapa gambar barcode GS1, masing‑masing mencerminkan kombinasi AI yang berbeda.

---

## Apa yang Anda Butuhkan

- **.NET 6+** (atau .NET Framework 4.6+). Runtime terbaru bekerja paling baik dengan Aspose.BarCode.
- **Aspose.BarCode for .NET** – instal melalui NuGet (`Install-Package Aspose.BarCode`).
- Sebuah folder di disk tempat file PNG akan ditulis (kami akan menyebutnya `YOUR_DIRECTORY`).
- Pemahaman dasar tentang sintaks C#—tidak memerlukan hal yang rumit.

Jika Anda sudah memiliki semuanya, bagus. Jika belum, dapatkan paket NuGet terlebih dahulu; cukup satu baris di Package Manager Console dan akan mengurus semua dependensi.

## Langkah 1: Siapkan Proyek Konsol Minimal

Buka IDE favorit Anda (Visual Studio, Rider, atau VS Code) dan buat proyek konsol baru:

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Ganti `Program.cs` yang dihasilkan secara otomatis dengan kode yang ditunjukkan pada langkah berikut. Kerangka ini memberi kita kanvas bersih untuk **create gs1 barcode images** tanpa gangguan tambahan.

## Langkah 2: Cara **create gs1 barcode images** – Inisialisasi Generator

Inti dari operasi ini adalah `BarcodeGenerator`. Kami akan memulainya dengan nilai GS1‑MicroPDF417 awal, misalnya `(17)991231(10)ABCD`. String tersebut mengkodekan dua AI: tanggal kedaluwarsa (17) dan batch/lot (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**Mengapa ini penting:** `EncodeTypes.GS1MicroPdf417` memberi tahu Aspose bahwa kita menggunakan format GS1 yang kompak dan berkapasitas tinggi. Memulai dengan string AI yang valid memastikan PNG pertama yang kami simpan sudah sesuai dengan standar GS1.

## Langkah 3: Sesuaikan Parameter Visual – Penyetelan Ukuran dan Tata Letak

Barcode yang terlalu kecil atau berbentuk aneh tidak akan terbaca. Di sini kami mengatur X‑dimension (lebar modul) menjadi 2 pixel, membatasi jumlah kolom agar gambar tetap sempit, dan mengaktifkan linking sehingga beberapa barcode dapat digabungkan nanti bila diperlukan.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**Tip:** Jika Anda membutuhkan barcode yang lebih tinggi, tingkatkan `Rows` bukan kolom. Bereksperimenlah dengan `XDimension` untuk memenuhi ukuran modul minimum 0.33 mm yang diperlukan oleh kebanyakan scanner.

## Langkah 4: Simpan Barcode Pertama – AI 17 + AI 10

Sekarang kami benar‑benar menulis gambar ke disk. Nama file mencerminkan AI yang digunakan, sehingga mudah ditemukan nanti.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

Setelah menjalankan program, Anda akan melihat PNG yang jelas di `YOUR_DIRECTORY`. Buka file tersebut—Anda akan melihat bar kecil dan teks yang dapat dibaca manusia di bawahnya. Itu adalah yang pertama dari banyak **gs1 barcode images** yang akan kami hasilkan.

## Langkah 5: Ubah Data yang Dikodekan – Gunakan Kembali Generator yang Sama

Alih‑alih membuat `BarcodeGenerator` baru untuk setiap pasangan AI, kami cukup menukar properti `CodeText` dan memanggil `Save` lagi. Pendekatan ini adalah cara paling efisien untuk **create gs1 barcode images** secara massal.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**Mengapa menggunakan kembali?** Mengubah `CodeText` menghindari beban membuat ulang generator dan menjamin pengaturan visual yang konsisten di semua gambar.

## Langkah 6: Jalankan, Verifikasi, dan Sesuaikan

Kompilasi dan jalankan:

```bash
dotnet run
```

Sekarang Anda seharusnya memiliki lima file PNG, masing‑masing dinamai sesuai pasangan AI yang terkandung. Buka salah satu dengan penampil gambar; Anda akan melihat barcode dan teks yang dikodekan di bawahnya. Untuk memeriksa kembali bahwa data benar, gunakan aplikasi pemindai GS1 gratis di ponsel Anda—arahkan ke PNG di layar dan lihat nilai AI muncul.

**Masalah umum & cara menghindarinya**

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| Barcode tidak terbaca | `XDimension` terlalu rendah (mis., 1 pixel) | Tingkatkan menjadi 2 atau 3 pixel |
| Kurung AI hilang | Format `CodeText` tidak tepat | Selalu bungkus setiap AI dalam tanda kurung |
| Gambar terlalu besar | Terlalu banyak kolom/baris | Kurangi `Columns` atau biarkan Aspose mengatur ukuran otomatis |
| Runtime error `EncodeTypes` tidak ditemukan | `using Aspose.BarCode.Generation` tidak ada | Tambahkan pernyataan `using` yang hilang |

## Langkah 7: Memperluas Contoh – Menghasilkan Lebih Banyak Kombinasi AI

Jika Anda perlu **create gs1 barcode images** untuk puluhan varian produk, pertimbangkan memuat pasangan AI dari file CSV:

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

## Kesimpulan

Anda kini memiliki program C# lengkap yang siap dijalankan yang **creates gs1 barcode images** untuk berbagai skenario AI, menunjukkan cara paling sederhana untuk **how to generate barcode c#** menggunakan Aspose.BarCode. Dengan menggunakan kembali satu instance `BarcodeGenerator`, menyetel parameter visual, dan menukar `CodeText`, Anda dapat menghasilkan sebanyak mungkin PNG GS1‑MicroPDF417 yang sesuai dengan kebutuhan proyek Anda.

Apa selanjutnya? Coba tambahkan warna (`barcodeGen.Parameters.Barcode.ForeColor`), sematkan barcode ke dalam PDF, atau beralih ke simbol GS1 lain seperti DataMatrix. Pola yang sama tetap berlaku—inisialisasi, konfigurasi, set `CodeText`, dan simpan.

Jangan ragu meninggalkan komentar jika Anda mengalami kendala, atau bagikan variasi Anda sendiri. Selamat coding, semoga pemindaian Anda selalu bersih!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat zona tenang barcode untuk Code 16K menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cara Membuat Zona Tenang Barcode untuk ITF-14 Menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cara Menghasilkan Barcode – Konfigurasi Code 39 dengan Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}