---
category: general
date: 2026-08-19
description: Hasilkan barcode C# menggunakan Aspose.BarCode untuk membuat Macro PDF417
  dengan teks khusus dan simpan sebagai file gambar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: id
lastmod: 2026-08-19
og_description: Buat barcode C# dengan Aspose.BarCode, pelajari cara menghasilkan
  PDF417, tambahkan teks khusus, dan simpan file gambar barcode.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Buat barcode C# – Panduan Macro PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Buat barcode C# dengan Macro PDF417 – contoh lengkap
url: /id/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan barcode C# dengan Macro PDF417 – contoh lengkap

Jika Anda perlu **menghasilkan barcode C#** untuk format Macro PDF417, panduan ini menunjukkan solusi siap‑jalankan. Anda akan melihat cara **menghasilkan pdf417**, menyematkan teks khusus, dan **menghasilkan file gambar barcode** dalam satu program yang berdiri sendiri.

Tutorial ini mencakup semua hal mulai dari menginstal pustaka Aspose.BarCode hingga mengonfigurasi metadata Macro PDF417, sehingga Anda dapat menyalin kode langsung ke dalam proyek Anda dan melihat hasilnya segera.

## Prasyarat

- .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
- Visual Studio 2022 (atau IDE apa pun yang mendukung C#)
- Lisensi Aspose.BarCode untuk .NET (versi percobaan gratis dapat digunakan untuk evaluasi)
- Familiaritas dasar dengan sintaks C#

> **Pro tip:** Instal paket NuGet melalui CLI untuk menghindari ketidaksesuaian versi:  
> `dotnet add package Aspose.BarCode`

## Langkah 1: Siapkan proyek dan impor pustaka

Buat aplikasi konsol baru dan tambahkan direktif `using` yang diperlukan.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Mengapa langkah ini penting:**  
Namespace `Aspose.BarCode.Generation` menyediakan kelas `BarcodeGenerator`, yang merupakan titik masuk untuk membuat jenis barcode apa pun, termasuk Macro PDF417. Mengimpor `System` memberi Anda akses ke `DateTime` untuk metadata timestamp.

## Langkah 2: Buat generator Macro PDF417 dengan teks khusus

Ganti komentar placeholder dengan inisialisasi generator. Ini menunjukkan **membuat teks khusus barcode** sambil juga memilih tipe enkoding yang tepat.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Penjelasan:**  
- `EncodeTypes.MacroPdf417` memberi tahu Aspose untuk menghasilkan barcode PDF417 yang mendukung fitur macro (segmentasi file, checksum, dll.).  
- Teks `"Åspóse.Barcóde©"` menunjukkan bahwa karakter Unicode didukung sepenuhnya, yang sering diperlukan untuk aplikasi internasional.

## Langkah 3: Konfigurasikan tampilan dan metadata Macro PDF417

Sesuaikan dimensi barcode dan atur bidang khusus macro yang diperlukan untuk penanganan file tersegmentasi.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Mengapa pengaturan ini penting:**

| Pengaturan | Tujuan |
|------------|--------|
| `XDimension.Pixels` | Mengontrol kepadatan visual; 2 px menghasilkan gambar yang jelas dan dapat dipindai. |
| `Columns` | Menentukan berapa banyak kolom data yang muncul per baris, memengaruhi ukuran barcode. |
| `MacroPdf417FileID` | Mengidentifikasi secara unik file logis di seluruh segmen. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Memungkinkan rekonstruksi file asli dari beberapa barcode. |
| `MacroPdf417FileName` | Nama yang dapat dibaca manusia disimpan di dalam barcode untuk pemrosesan selanjutnya. |
| `MacroPdf417Checksum` | Menyediakan deteksi kesalahan menggunakan algoritma CRC CCITT‑16. |
| `MacroPdf417FileSize` | Membantu decoder mengetahui kapan seluruh file telah diterima. |
| `MacroPdf417TimeStamp` | Mencatat kapan barcode dihasilkan, berguna untuk jejak audit. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Bidang opsional yang dapat digunakan dalam alur kerja bisnis. |
| `MacroPdf417Terminator` | Menunjukkan bahwa segmen ini adalah yang terakhir (`Set`). |

## Langkah 4: Simpan barcode sebagai file gambar

Akhirnya, tulis barcode ke file PNG sehingga Anda dapat melihat atau menyematkannya di tempat lain.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Apa yang akan Anda lihat:**  
Sebuah gambar PNG bernama `ExtPDF417Meta.png` yang berisi barcode Macro PDF417 yang mengenkode teks khusus dan semua bidang metadata yang Anda atur di atas. Gambar ini dapat dibuka dengan penampil standar apa pun atau disisipkan ke dalam PDF, laporan, atau halaman web.

## Kode sumber lengkap (siap salin‑tempel)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Output yang diharapkan

Running the program prints:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Membuka `ExtPDF417Meta.png` menampilkan barcode Macro PDF417 yang bersih dan dapat dipindai dengan benar oleh pembaca PDF417 apa pun, mempertahankan teks khusus `"Åspóse.Barcóde©"` dan metadata macro yang Anda definisikan.

## Pertanyaan umum dan kasus tepi

- **Apakah saya dapat menghasilkan format gambar lain?**  
  Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` sesuai kebutuhan.

- **Bagaimana jika data saya melebihi satu barcode?**  
  Macro PDF417 dirancang untuk segmentasi. Sesuaikan `MacroPdf417SegmentsCount` dan `MacroPdf417SegmentID` untuk setiap bagian, lalu gabungkan hasil pemindaian.

- **Apakah dukungan Unicode dijamin?**  
  Aspose.BarCode sepenuhnya mendukung Unicode. Pastikan file sumber Anda disimpan dengan encoding UTF‑8 untuk menghindari korupsi karakter.

- **Apakah saya memerlukan lisensi untuk produksi?**  
  Versi berlisensi menghapus watermark evaluasi dan menyediakan fungsionalitas penuh. Versi percobaan dapat digunakan untuk pengujian dan pembelajaran.

## Kesimpulan

Anda kini tahu cara **menghasilkan barcode C#** untuk Macro PDF417, **cara menghasilkan pdf417** dengan metadata kaya, **membuat teks khusus barcode**, dan **menghasilkan file gambar barcode** menggunakan Aspose.BarCode. Contoh lengkap yang dapat dijalankan ini memperlihatkan setiap langkah yang diperlukan—dari penyiapan proyek hingga menyimpan gambar PNG akhir.

### Langkah selanjutnya

- Bereksperimen dengan pengaturan PDF417 lainnya seperti `ErrorCorrectionLevel` dan `CompactPdf417` untuk simbol yang lebih kecil.  
- Integrasikan barcode yang dihasilkan ke dalam laporan PDF menggunakan Aspose.PDF.  
- Jelajahi pembuatan batch: lakukan loop pada koleksi file dan hasilkan serangkaian barcode Macro PDF417 yang tersegmentasi.

Silakan sesuaikan kode untuk alur kerja Anda sendiri, dan biarkan pembuatan barcode menjadi bagian yang mulus dari aplikasi C# Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hasilkan gambar barcode – Code 93 dengan Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Cara Menghasilkan dan Menyesuaikan Tinggi Barcode untuk One-Dimensional Databar menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}