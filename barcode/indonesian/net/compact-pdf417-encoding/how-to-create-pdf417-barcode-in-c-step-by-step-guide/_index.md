---
category: general
date: 2026-09-13
description: Pelajari cara membuat barcode PDF417 di C# dan menghasilkan gambar barcode
  PDF417 dengan cepat menggunakan contoh lengkap yang dapat dijalankan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- generate pdf417 barcode
- create barcode image c#
language: id
lastmod: 2026-09-13
og_description: Buat barcode pdf417 di C# dan hasilkan gambar barcode pdf417 dengan
  tutorial singkat ini. Ikuti contoh lengkapnya dan dapatkan file PNG secara instan.
og_image_alt: Screenshot of a PDF417 barcode generated in C#
og_title: Buat kode batang pdf417 di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create pdf417 barcode in C# and generate pdf417 barcode
    images quickly with a complete, runnable example.
  headline: How to create pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cara membuat barcode pdf417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat pdf417 barcode di C# – panduan langkah demi langkah

Jika Anda perlu **membuat pdf417 barcode** dalam aplikasi .NET, tutorial ini menunjukkan secara tepat cara melakukannya. Anda akan melihat cara menghasilkan gambar pdf417 barcode di C# menggunakan pustaka Aspose.BarCode, dan Anda akan mendapatkan file PNG siap‑pakai.

Membuat barcode adalah kebutuhan umum untuk sistem inventaris, solusi tiket, atau verifikasi dokumen. Pada akhir panduan ini Anda akan dapat **membuat pdf417 barcode** secara programatis, menyesuaikan parameter kunci seperti lebar modul, kolom, dan baris, serta menyimpan hasilnya sebagai PNG tanpa alat eksternal apa pun.

## Apa yang Anda butuhkan

- .NET 6.0 atau lebih baru (kode ini juga berfungsi pada .NET Framework 4.7+)
- Referensi ke paket NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Pengetahuan dasar tentang sintaks C# dan lingkungan pengembangan (Visual Studio, VS Code, atau Rider)

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru (atau tambahkan kode ke proyek yang sudah ada) dan impor namespace yang diperlukan. Langkah ini menyiapkan lingkungan untuk pembuatan barcode.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enumeration
```

**Mengapa ini penting:** Mengimpor `Aspose.BarCode.Generation` memberi Anda akses ke `BarcodeGenerator`, kelas yang sebenarnya membuat barcode. Namespace `Aspose.BarCode` berisi enum format gambar yang akan Anda gunakan saat **menyimpan gambar barcode**.

## Langkah 2: Inisialisasi BarcodeGenerator dengan pengaturan PDF417

Konstruktor `BarcodeGenerator` menerima dua argumen: simbol barcode (`EncodeTypes.Pdf417`) dan teks yang ingin Anda enkode. Di sini kami mengenkripsi string `"Layout demo"`.

```csharp
// Step 2: Initialise generator for PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo"))
{
    // All further configuration goes inside this block
```

**Mengapa ini penting:** Memilih `EncodeTypes.Pdf417` memberi tahu pustaka untuk menggunakan simbol PDF417 2‑D, yang ideal untuk menyimpan sejumlah besar data dan banyak didukung dalam logistik serta kartu identitas.

## Langkah 3: Konfigurasikan X‑dimension (lebar modul)

X‑dimension mengontrol lebar setiap modul individu (elemen hitam atau putih terkecil). Menetapkannya dalam piksel memberi Anda kontrol presisi atas ukuran gambar akhir.

```csharp
    // Step 3: Set module width to 2 pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa ini penting:** X‑dimension yang lebih kecil menghasilkan barcode yang lebih kompak, sementara nilai yang lebih besar membuat barcode lebih mudah dipindai dari jarak jauh. Sesuaikan nilai ini berdasarkan lingkungan pemindaian aplikasi Anda.

## Langkah 4: Tentukan tata letak – kolom dan baris

PDF417 memungkinkan Anda menentukan berapa banyak kolom dan baris yang harus digunakan barcode. Ini memengaruhi baik ukuran maupun kapasitas data.

```csharp
    // Step 4: Define layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // Number of data columns
    barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // Number of rows (height)
```

**Mengapa ini penting:** Mengontrol kolom dan baris memungkinkan Anda menyesuaikan barcode untuk dimensi label tertentu atau batasan pencetakan. Terlalu banyak baris dapat membuat barcode terlalu tinggi; terlalu sedikit kolom dapat mengurangi kapasitas data.

## Langkah 5: Simpan barcode sebagai gambar PNG

Akhirnya, tulis barcode yang dihasilkan ke disk. Metode `Save` menerima jalur output dan format gambar yang diinginkan.

```csharp
    // Step 5: Save as PNG
    barcodeGenerator.Save("LayoutPdf417.png", BarCodeImageFormat.Png);
}
```

Saat Anda menjalankan program, sebuah file bernama **LayoutPdf417.png** muncul di direktori output. Membuka file tersebut menampilkan barcode PDF417 bersih yang mengenkripsi teks `"Layout demo"`.

### Output yang diharapkan

![Tangkapan layar barcode PDF417 yang dihasilkan dalam C#](placeholder-image.png "Barcode PDF417 dibuat dengan C#")

*Teks alt gambar:* **Tangkapan layar barcode PDF417 yang dihasilkan dalam C#** (cocok dengan `og_image_alt` untuk aksesibilitas).

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua bagian, berikut adalah aplikasi konsol mandiri yang dapat Anda salin, tempel, dan jalankan.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise generator for PDF417 with the desired text
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo"))
            {
                // Set the X‑dimension (module width) in pixels
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Define layout: 4 columns and 9 rows
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
                barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

                // Save the generated barcode as a PNG image
                barcodeGenerator.Save("LayoutPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode created successfully: LayoutPdf417.png");
        }
    }
}
```

**Cara memverifikasi:** Setelah menjalankan program, buka folder yang berisi file biner yang telah dikompilasi. Anda harus melihat `LayoutPdf417.png`. Buka dengan penampil gambar apa pun; barcode harus terlihat jelas dan dapat dipindai dengan pembaca PDF417 standar.

## Variasi umum dan kasus tepi

| Situasi | Apa yang diubah | Mengapa |
|-----------|----------------|-----|
| **Kepadatan data lebih tinggi** | Tingkatkan `Columns` (misalnya, menjadi 6) dan opsional kurangi `Rows` | Lebih banyak kolom menampung lebih banyak data secara horizontal, berguna untuk label sempit. |
| **Area cetak besar** | Tingkatkan `XDimension.Pixels` (misalnya, menjadi 4) | Modul yang lebih besar membuat barcode lebih mudah dipindai dari jarak jauh. |
| **Format gambar berbeda** | Gunakan `BarCodeImageFormat.Jpeg` atau `Bmp` dalam pemanggilan `Save` | Pilih format yang sesuai dengan alur pemrosesan selanjutnya. |
| **Warna latar depan/belakang khusus** | Setel `barcodeGenerator.Parameters.Barcode.ForeColor` dan `BackColor` | Meningkatkan keterbacaan pada latar berwarna atau saat mencetak pada media gelap. |
| **Menyandikan karakter Unicode** | Berikan string Unicode (misalnya, `"Пример"`). PDF417 mendukung Unicode secara langsung. | Memungkinkan teks internasional tanpa konfigurasi tambahan. |

**Pro tip:** Selalu uji barcode yang dihasilkan dengan perangkat pemindai sebenarnya yang akan Anda gunakan. Beberapa pemindai memiliki persyaratan ukuran modul minimum; menyesuaikan `XDimension` sesuai dapat mencegah kesalahan pembacaan.

## Pertanyaan yang sering diajukan

**Q: Apakah ini bekerja dengan .NET Core?**  
Ya. Paket `Aspose.BarCode` menargetkan .NET Standard 2.0, yang kompatibel dengan .NET Core, .NET 5+, dan .NET Framework.

**Q: Bisakah saya menghasilkan beberapa barcode dalam loop?**  
Tentu saja. Letakkan blok `using` di dalam loop `foreach` dan ubah teks atau parameter tata letak untuk setiap iterasi.

**Q: Bagaimana jika saya perlu menyematkan barcode ke dalam PDF?**  
Setelah menghasilkan PNG, Anda dapat memuatnya ke dalam pustaka PDF (misalnya, iText7 atau Aspose.PDF) dan menempatkannya pada halaman. Langkah pembuatan barcode tetap sama.

## Kesimpulan

Anda kini tahu cara **membuat pdf417 barcode** dalam C# menggunakan Aspose.BarCode. Tutorial ini mencakup inisialisasi generator, konfigurasi X‑dimension, penetapan kolom dan baris, serta penyimpanan hasil sebagai file PNG. Dengan dasar ini Anda dapat **menghasilkan pdf417 barcode** untuk tag inventaris, boarding pass, atau skenario apa pun yang memerlukan barcode 2‑D berkapasitas tinggi dan kompak.

Selanjutnya, coba **create barcode image c#** untuk simbol lain seperti QR, Code‑128, atau DataMatrix dengan mengganti `EncodeTypes.Pdf417` dengan tipe yang diinginkan. Bereksperimenlah dengan warna, tingkat koreksi kesalahan, dan menyematkan gambar langsung ke PDF atau laporan untuk memperluas solusi lebih jauh.

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Buat Metadata PDF417 Barcode di C# – Panduan Lengkap Langkah‑per‑Langkah](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Cara Membaca PDF417 di C# – Contoh Barcode Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Buat PDF417 Barcode di C# – Panduan Pemrograman Lengkap](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}