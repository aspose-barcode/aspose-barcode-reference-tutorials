---
category: general
date: 2026-07-21
description: Buat kode batang PDF417 menggunakan Aspose di C#. Pelajari cara menghasilkan
  kode batang PDF417 dengan metadata dalam beberapa langkah saja.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- create barcode with aspose
language: id
lastmod: 2026-07-21
og_description: Buat kode batang PDF417 dengan cepat menggunakan Aspose. Panduan ini
  menjelaskan cara menghasilkan kode batang PDF417, mengatur metadata makro, dan menyimpan
  gambar.
og_image_alt: Screenshot showing a generated PDF417 barcode created with Aspose
og_title: Buat Kode Bar PDF417 dengan Aspose – Tutorial Langkah demi Langkah
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Create PDF417 barcode using Aspose in C#. Learn how to generate PDF417
    barcode with metadata in just a few steps.
  headline: Create PDF417 Barcode with Aspose – Complete Guide
  type: TechArticle
tags:
- barcode
- Aspose
- PDF417
title: Membuat Kode Bar PDF417 dengan Aspose – Panduan Lengkap
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Barcode PDF417 dengan Aspose – Panduan Lengkap

Pernahkah Anda perlu **membuat barcode PDF417** tetapi tidak yakin perpustakaan mana yang dapat menangani metadata makro tanpa masalah? Anda tidak sendirian. Dalam tutorial ini kami akan menunjukkan **cara menghasilkan barcode PDF417** menggunakan library Aspose.BarCode, mengatur semua bidang makro, dan menyimpan hasilnya sebagai PNG—semua dalam beberapa baris C#.

Kami akan membimbing Anda melalui seluruh proses, mulai dari menginstal Aspose.BarCode hingga menyesuaikan tampilan barcode, sehingga Anda dapat menambahkan kode ke proyek .NET apa pun dan melihatnya bekerja secara instan. Pada akhirnya, Anda akan merasa nyaman membuat barcode dengan Aspose dan menyesuaikan parameter makro untuk skenario pemindaian dunia nyata.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

- .NET 6.0 atau lebih baru (kode ini juga berfungsi pada .NET Framework 4.7+)
- Lisensi Aspose.BarCode untuk .NET yang valid (versi percobaan gratis dapat digunakan untuk evaluasi)
- Visual Studio 2022 atau IDE favorit Anda
- Pengetahuan dasar C#—tidak ada yang rumit, hanya pernyataan `using` biasa

Jika ada yang belum tersedia, dapatkan paket NuGet sekarang:

```bash
dotnet add package Aspose.BarCode
```

Itu saja—tidak ada ketergantungan tambahan yang diperlukan.

## Langkah 1: Inisialisasi Barcode Generator (Primary Keyword Appears Here)

Hal pertama yang Anda lakukan adalah membuat instance `BarcodeGenerator` yang menargetkan simbol **PDF417**. Aspose menyebutnya `EncodeTypes.Pdf417`, tetapi untuk barcode yang mendukung makro Anda menggunakan `EncodeTypes.MacroPdf417`.

```csharp
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the text you want to encode
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the steps are inside this using block
        }
    }
}
```

*Mengapa ini penting*: Pernyataan `using` menjamin generator dibuang dengan benar, melepaskan sumber daya native. Selain itu, dengan memilih `MacroPdf417` Anda membuka kemampuan untuk menyematkan metadata tingkat file—fitur berguna untuk alur kerja dokumen besar.

## Langkah 2: Definisikan Penampilan Dasar (Secondary Keyword – how to generate pdf417 barcode)

Barcode yang terlalu kecil atau sempit akan sulit dibaca. Aspose memberi Anda kontrol halus atas ukuran modul, jumlah kolom, dan lainnya.

```csharp
// Set the module (X) dimension – each bar will be 2 pixels wide
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a reasonable column count for readability
generator.Parameters.Barcode.Pdf417.Columns = 5;

// Optional: tweak error correction level if you need higher resilience
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // 0‑8 range
```

Ketiga baris ini merupakan inti **cara menghasilkan barcode PDF417** yang dapat dipindai secara andal pada kebanyakan perangkat. Sesuaikan `Columns` dan `ErrorCorrectionLevel` berdasarkan ukuran data dan lingkungan pemindaian Anda.

## Langkah 3: Tambahkan Metadata Macro PDF417 (Primary Keyword – create pdf417 barcode)

Macro PDF417 memungkinkan Anda menyematkan informasi tingkat dokumen langsung ke dalam barcode. Di sinilah Anda benar‑benar *membuat barcode PDF417* yang membawa lebih dari sekadar string sederhana.

```csharp
// File identifier – must be unique across all segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

// Segment identifier – this is segment 12 of the whole file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

// Total number of segments in the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

// Human‑readable file name (optional but nice for debugging)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

// Optional CCITT‑16 checksum for extra integrity checking
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

// Approximate file size in bytes – helpful for large PDFs
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

// Timestamp when the file was generated
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

// Add address fields – these are free‑form strings
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

// Define the macro terminator (whether this is the last segment)
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Mengapa Anda membutuhkannya*: Pemindai yang memahami Macro PDF417 dapat merekonstruksi file asli dari beberapa segmen barcode, memverifikasi integritas melalui checksum, dan bahkan menampilkan informasi pengirim/penerima. Ini sangat cocok untuk logistik, pengarsipan dokumen, atau skenario apa pun di mana satu barcode tidak dapat menampung seluruh muatan.

## Langkah 4: Simpan Barcode sebagai Gambar (Secondary Keyword – create barcode with aspose)

Terakhir, tulis barcode ke file PNG (atau format apa pun yang didukung Aspose). Enum `BarCodeImageFormat` membuat ini sangat mudah.

```csharp
// Choose a folder you have write access to
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";

// Save the barcode – PNG keeps the crisp edges
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Itulah seluruh alur **membuat barcode dengan Aspose**. Setelah menjalankan program, buka file PNG—Anda akan melihat simbol PDF417 yang bersih dengan bidang makro yang disematkan.

![Create PDF417 barcode example](image.png "Create PDF417 barcode example")

*Tip*: Jika Anda memerlukan format gambar lain (JPEG, BMP, SVG), cukup ganti `BarCodeImageFormat.Png` dengan nilai enum yang diinginkan.

## Contoh Lengkap yang Berfungsi

Menggabungkan semua bagian, berikut adalah aplikasi konsol siap‑jalankan:

```csharp
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Initialise generator for Macro PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Basic appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

            // Macro metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save as PNG
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Jalankan program, buka gambar yang dihasilkan, dan Anda akan melihat barcode PDF417 yang terbentuk sempurna siap dipindai.

## Pertanyaan Umum & Kasus Tepi

**Bagaimana jika data saya melebihi kapasitas satu simbol PDF417?**  
Aspose secara otomatis akan membagi data ke beberapa segmen makro jika Anda mengaktifkan `MacroPdf417`. Pastikan `SegmentsCount` mencerminkan total jumlah bagian.

**Bisakah saya mengubah warna barcode?**  
Tentu saja. Gunakan `generator.Parameters.Barcode.BarColor` dan `BackgroundColor` untuk mewarnainya sesuai keinginan Anda.

**Apakah Unicode didukung?**  
Ya—contoh menggunakan karakter seperti `Å` dan `©`. Aspose menangani enkoding UTF‑8 secara internal, sehingga Anda dapat menyematkan hampir semua bahasa.

**Bagaimana dengan kinerja untuk ribuan barcode?**  
Membuat generator per barcode cukup untuk beban kerja ringan. Untuk pemrosesan massal, gunakan kembali satu instance `BarcodeGenerator` dan cukup ubah properti `CodeText` di antara penyimpanan.

## Kesimpulan

Sekarang Anda tahu **cara membuat barcode PDF417** dengan Aspose, mengatur metadata tingkat makro, dan mengekspor hasilnya sebagai PNG berkualitas tinggi. Pendekatan ini—*membuat barcode PDF417* dengan tampilan yang disesuaikan dan informasi file yang disematkan—sangat kuat dan mudah diintegrasikan ke dalam layanan .NET yang ada.

Siap untuk langkah berikutnya? Cobalah menghasilkan serangkaian barcode tersegmentasi untuk mewakili PDF berukuran multi‑megabyte, atau bereksperimen dengan tingkat koreksi kesalahan yang berbeda untuk melihat bagaimana keandalan pemindaian berubah. Dan jika Anda penasaran dengan simbol lain, lihat panduan Aspose tentang pembuatan kode QR atau DataMatrix.

Selamat coding, semoga pemindaian Anda selalu bebas error!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang berhubungan erat dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo crear un código de barras – PDF417 compacto con Aspose.BarCode](/barcode/spanish/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode 创建紧凑型 PDF417 条码](/barcode/chinese/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}