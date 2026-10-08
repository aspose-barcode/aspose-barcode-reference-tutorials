---
category: general
date: 2026-09-19
description: Cara mendekode PDF417 di C# – pelajari cara membaca barcode dari gambar
  menggunakan contoh pembaca barcode yang singkat yang mengekstrak data Macro PDF417
  lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: id
lastmod: 2026-09-19
og_description: Cara mendekode PDF417 di C# dengan contoh pembaca kode batang langkah
  demi langkah. Ekstrak setiap bidang Macro PDF417 dari gambar dalam hitungan detik.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Cara mendekode PDF417 di C# – panduan lengkap pembaca kode batang
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Cara mendekode PDF417 di C# dengan contoh pembaca kode batang
url: /id/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mendekode PDF417 di C# dengan contoh pembaca barcode

Jika Anda perlu mendekode PDF417 di C#, panduan ini menunjukkan secara tepat cara mendekode PDF417 dari file gambar. Anda akan belajar membaca barcode dari gambar, mengakses bidang Macro PDF417 yang diperluas, dan mengintegrasikan solusi ke dalam proyek .NET apa pun.

Mendekode barcode PDF417 umum digunakan dalam logistik, tiket, dan verifikasi identitas. Tutorial ini mencakup semua yang diperlukan untuk implementasi siap produksi, termasuk pustaka prasyarat, kode sumber lengkap, dan tips untuk menangani kasus tepi.

## Prasyarat

- .NET 6.0 atau lebih baru terinstal  
- Visual Studio 2022 (atau IDE apa pun yang mendukung C#)  
- Paket NuGet **Aspose.BarCode for .NET** (versi 23.11 atau lebih baru)  

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

Kelas `BarCodeReader` dari pustaka ini mendukung tipe decode `MacroPdf417` yang diperlukan untuk ekstraksi PDF417 lengkap.

## Langkah 1: Cara mendekode PDF417 di C# – inisialisasi pembaca

Langkah pertama membuat instance `BarCodeReader` yang menargetkan gambar Macro PDF417. Flag `DecodeType.MacroPdf417` memberi tahu pustaka untuk mengurai bidang Macro yang diperluas.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Mengapa ini penting:** Inisialisasi dengan `MacroPdf417` mengaktifkan properti `Extended.Pdf417` pada setiap `BarCodeResult`, memberi Anda akses ke metadata tingkat file seperti ID segmen dan cap waktu.

## Langkah 2: Membaca barcode dari gambar

Sebuah gambar PDF417 dapat berisi beberapa segmen macro. Metode `ReadBarCodes()` mengembalikan enumerable dari semua barcode yang terdeteksi, sehingga Anda dapat melakukan loop dengan aman.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Tip:** Jika Anda hanya mengharapkan satu barcode, Anda dapat menghentikan loop setelah iterasi pertama, tetapi iterasi semua hasil menjamin Anda menangkap setiap segmen dalam dokumen multi‑halaman.

## Langkah 3: Mendekode barcode PDF417 – mengekstrak data dasar dan diperluas

Di dalam loop, keluarkan baik informasi barcode umum maupun bidang khusus Macro. Objek `Extended.Pdf417` menyimpan setiap potongan metadata yang didefinisikan oleh standar PDF417.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

**Penjelasan bidang kunci**

| Field | Meaning |
|-------|---------|
| `MacroPdf417FileID` | Pengidentifikasi yang mengelompokkan semua segmen yang termasuk dalam file logis yang sama |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (dimulai dari 0) |
| `MacroPdf417SegmentsCount` | Jumlah total segmen yang diharapkan untuk file |
| `MacroPdf417FileName` | Nama file opsional yang disematkan dalam macro |
| `MacroPdf417Checksum` | Checksum CRC‑16 untuk integritas data |
| `MacroPdf417FileSize` | Ukuran file asli dalam byte |
| `MacroPdf417TimeStamp` | Cap waktu ketika macro dihasilkan |
| `MacroPdf417Addressee` | Penerima yang dimaksud dari data macro |
| `MacroPdf417Sender` | Pengirim data macro |
| `MacroPdf417Terminator` | Flag boolean yang menunjukkan segmen akhir |

Mengakses bidang-bidang ini memungkinkan Anda merekonstruksi dokumen asli, memverifikasi integritas, atau mengarahkan data berdasarkan informasi pengirim/penerima.

## Langkah 4: Contoh pembaca barcode C# lengkap – menggabungkan semuanya

Berikut adalah program lengkap yang dapat dijalankan. Ganti `YOUR_DIRECTORY` dengan folder yang berisi file `MacroPdf417.png` Anda.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Output konsol yang diharapkan (contoh)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

Nilai sebenarnya akan berbeda tergantung pada konten barcode Macro PDF417 Anda.

## Menangani kasus tepi umum

| Situasi | Pendekatan yang direkomendasikan |
|-----------|----------------------|
| **Tidak ada barcode terdeteksi** | Verifikasi jalur gambar, pastikan file tidak rusak, dan konfirmasi bahwa barcode terlihat (kontras yang memadai). |
| **Segmen macro parsial** | Gunakan `MacroPdf417SegmentsCount` untuk mendeteksi bagian yang hilang. Anda dapat meminta segmen yang tersisa dari sistem sumber dan menjalankan kembali decoder. |
| **Gambar besar menyebabkan tekanan memori** | Muat gambar ke dalam `System.Drawing.Bitmap` dengan resolusi yang dikurangi sebelum mengirimkannya ke `BarCodeReader`. |
| **PDF417 non‑Macro** | Ubah `DecodeType.MacroPdf417` menjadi `DecodeType.Pdf417` jika Anda hanya membutuhkan teks barcode biasa. |

## Tips profesional

- **Pemrosesan batch:** Bungkus logika pembaca dalam metode yang menerima daftar jalur file. Gunakan kembali satu instance `BarCodeReader` per thread untuk mengurangi overhead alokasi.  
- **Kinerja:** Untuk skenario throughput tinggi, aktifkan properti `ReaderOptions` `ReadQuality` untuk menyeimbangkan kecepatan versus akurasi.  
- **Keamanan:** Validasi `CodeText` sebelum menggunakannya dalam operasi sistem file untuk mencegah serangan traversal jalur.

## Kesimpulan

Dalam tutorial ini Anda belajar cara mendekode PDF417 di C# dengan membaca barcode dari gambar, mengekstrak setiap bidang Macro PDF417, dan membangun contoh pembaca barcode C# lengkap. Solusi ini bekerja dengan pustaka Aspose.BarCode terbaru, menangani macro multi‑segmen, dan memberikan panduan praktis untuk proyek dunia nyata.

Selanjutnya, jelajahi topik terkait seperti **membaca QR code**, **pemrosesan batch barcode**, dan **menghasilkan barcode PDF417** untuk memperluas toolkit otomatisasi dokumen Anda. Jangan ragu untuk bereksperimen dengan berbagai sumber gambar, mengintegrasikan kode ke dalam layanan ASP.NET, atau memperluasnya untuk menyimpan metadata yang diekstrak ke dalam basis data. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membaca PDF417 di C# – Contoh Pembaca Barcode Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Cara Menghasilkan Gambar Barcode PDF417 di C# dengan Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Membaca barcode dari gambar – contoh pembaca barcode C#](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}