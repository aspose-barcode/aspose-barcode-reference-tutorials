---
category: general
date: 2026-09-29
description: Bagaimana cara mendekode barcode PDF417 di C# menggunakan Aspose.BarCode.
  Pelajari contoh pembaca barcode yang menunjukkan cara membaca gambar barcode dan
  mengekstrak data makro.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: id
lastmod: 2026-09-29
og_description: Cara mendekode barcode PDF417 di C# dengan Aspose.BarCode. Panduan
  ini menampilkan contoh pembaca barcode siap pakai untuk membaca gambar barcode.
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: Cara mendekode barcode PDF417 di C# – contoh lengkap pembaca barcode
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  headline: How to decode PDF417 barcodes in C# – step‑by‑step guide
  type: TechArticle
- description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  name: How to decode PDF417 barcodes in C# – step‑by‑step guide
  steps:
  - name: Expected console output
    text: '``` Pdf417MacroFileID: 12345 Pdf417MacroSegmentID: 1 Pdf417MacroFileName:
      Invoice_2026_09_29.pdf ```'
  - name: No barcode detected
    text: '```csharp var results = reader.ReadBarCodes().ToList(); if (!results.Any())
      { Console.WriteLine("No PDF417 barcode found in the image."); return; } ```'
  - name: Unsupported image format
    text: Aspose.BarCode supports PNG, JPEG, BMP, TIFF, and GIF. Attempting to read
      a RAW or WebP file throws `ArgumentException`. Convert the image to a supported
      format before feeding it to the reader.
  - name: Large macro files
    text: Macro‑PDF417 can span many segments. To reconstruct the original file you
      must collect all segments (ordered by `MacroPdf417SegmentID`) and concatenate
      their payloads. The example above only prints individual segment metadata; a
      production implementation would store each segment in a dictionary, the
  - name: Performance tip
    text: If you process thousands of images, reuse a single `BarCodeReader` instance
      with the `SetImage` method instead of creating a new object for each file. This
      reduces memory allocations and speeds up decoding.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- Aspose.BarCode
title: Cara mendekode barcode PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mendekode barcode PDF417 di C# – panduan langkah‑demi‑langkah

Jika Anda perlu **how to decode PDF417** barcode di C#, tutorial ini memberi Anda solusi lengkap yang dapat dijalankan. Anda akan melihat **barcode reader example** yang menunjukkan **how to read barcode** gambar, mengekstrak informasi makro, dan mencetak hasilnya ke konsol.

Mendekode PDF417 umum dilakukan saat memproses label pengiriman, tiket, atau ID pemerintah. Pada akhir panduan ini Anda akan dapat membaca gambar barcode PDF417, mengakses field makronya, dan menangani kasus tepi yang umum. Tidak diperlukan dokumentasi eksternal – semua yang Anda butuhkan sudah disertakan.

## Apa yang akan Anda pelajari

- Install library Aspose.BarCode untuk .NET  
- Buat sebuah `BarCodeReader` yang **read PDF417 barcode** data dari file PNG atau JPEG  
- Iterasi objek `BarCodeResult` dan ambil properti macro‑PDF417  
- Memecahkan masalah umum seperti format gambar yang tidak didukung atau data makro yang hilang  

## Prasyarat

| Persyaratan | Alasan |
|-------------|--------|
| .NET 6.0 SDK atau lebih baru | Menyediakan runtime untuk proyek C# |
| Visual Studio 2022 (atau IDE apa pun yang mendukung .NET) | Memungkinkan pembuatan proyek dan debugging yang mudah |
| Paket NuGet **Aspose.BarCode** | Menyediakan kelas `BarCodeReader` yang digunakan dalam contoh |
| Gambar macro PDF417 (mis., `ExtPDF417Meta.png`) | File sumber yang akan didekode oleh pembaca |

> **Pro tip:** Jika Anda tidak memiliki gambar PDF417, Anda dapat membuatnya dengan demo online Aspose.BarCode gratis atau memindai label nyata.

## Langkah 1: Instal Aspose.BarCode via NuGet

Buka terminal di folder solusi Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah tersebut menambahkan versi stabil terbaru dari Aspose.BarCode ke proyek Anda dan memperbarui file `.csproj`. Library ini mengimplementasikan fungsionalitas **read barcode image C#** untuk puluhan simbol, termasuk PDF417.

## Langkah 2: Buat BarCodeReader untuk **how to decode PDF417**

Inti dari proses **how to read barcode** adalah `BarCodeReader`. Anda harus memberi tahu pembaca baik jalur file maupun simbol yang diharapkan (`DecodeType.MacroPdf417`). Menyediakan `DecodeType` yang tepat meningkatkan kecepatan deteksi dan akurasi.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Adjust the path to point at your PDF417 macro image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// The reader is disposable; wrap it in a using block to release resources automatically.
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 3 is inside this block.
}
```

**Mengapa ini penting:**  
- `DecodeType.MacroPdf417` memberi tahu mesin untuk mencari field macro‑PDF417 (ID file, ID segmen, dll.).  
- Menggunakan `using` memastikan aliran gambar yang mendasari ditutup, mencegah masalah penguncian file di Windows.

## Langkah 3: Iterasi barcode yang terdeteksi

Sebuah gambar tunggal dapat berisi beberapa barcode. Metode `ReadBarCodes()` mengembalikan `IEnumerable<BarCodeResult>` yang dapat Anda iterasi.

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

Jika gambar tidak mengandung simbol PDF417 apa pun, tubuh loop tidak pernah dijalankan, dan Anda dapat menangani kasus tersebut setelah loop (lihat bagian “Error handling”).

## Langkah 4: Akses field macro PDF417

Setiap `BarCodeResult` mengekspos properti `Extended` dengan sub‑objek `Pdf417`. Field macro yang paling sering Anda butuhkan adalah:

| Properti | Makna |
|----------|-------|
| `MacroPdf417FileID` | Pengidentifikasi seluruh file macro PDF417 |
| `MacroPdf417SegmentID` | Nomor urut segmen saat ini |
| `MacroPdf417FileName` | Nama file opsional yang disimpan dalam macro |

Berikut adalah kode lengkap yang mencetak nilai-nilai tersebut:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Macro fields are nullable; use the null‑conditional operator to avoid exceptions.
    Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
    Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
    Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");

    // You can also read other macro properties, such as:
    // result.Extended.Pdf417.MacroPdf417Addressee
    // result.Extended.Pdf417.MacroPdf417Sender
}
```

### Output konsol yang diharapkan

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

Jika field macro tidak ada, output akan menampilkan baris kosong karena properti tersebut `null`. Itu normal untuk barcode PDF417 non‑macro.

## Langkah 5: Tangani jebakan umum (penanganan error & kasus tepi)

### Tidak ada barcode terdeteksi

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### Format gambar tidak didukung

Aspose.BarCode mendukung PNG, JPEG, BMP, TIFF, dan GIF. Mencoba membaca file RAW atau WebP akan melempar `ArgumentException`. Konversi gambar ke format yang didukung sebelum memberikannya ke pembaca.

### File macro besar

Macro‑PDF417 dapat mencakup banyak segmen. Untuk merekonstruksi file asli Anda harus mengumpulkan semua segmen (diurutkan berdasarkan `MacroPdf417SegmentID`) dan menggabungkan payloadnya. Contoh di atas hanya mencetak metadata segmen individu; implementasi produksi akan menyimpan setiap segmen dalam kamus, lalu menyusunnya setelah semua segmen dibaca.

### Tips kinerja

Jika Anda memproses ribuan gambar, gunakan kembali satu instance `BarCodeReader` dengan metode `SetImage` alih‑alih membuat objek baru untuk setiap file. Ini mengurangi alokasi memori dan mempercepat proses dekode.

```csharp
using (BarCodeReader reader = new BarCodeReader(null, DecodeType.MacroPdf417))
{
    foreach (string file in Directory.GetFiles(@"YOUR_DIRECTORY", "*.png"))
    {
        reader.SetImage(file);
        // read barcodes as shown earlier
    }
}
```

## Contoh lengkap yang berfungsi

Salin program berikut ke dalam proyek Console App baru (`dotnet new console`). Program ini mencakup semua langkah, penanganan error, dan komentar.

```csharp
// Program.cs
using System;
using System.IO;
using System.Linq;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the PDF417 macro image – update to your actual location.
        string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Verify the file exists before attempting to read.
        if (!File.Exists(imagePath))
        {
            Console.WriteLine($"File not found: {imagePath}");
            return;
        }

        // Initialize the reader for Macro PDF417.
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            var results = reader.ReadBarCodes().ToList();

            if (!results.Any())
            {
                Console.WriteLine("No PDF417 barcode detected in the image.");
                return;
            }

            foreach (BarCodeResult result in results)
            {
                // Print macro information safely.
                Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");
                Console.WriteLine(); // blank line for readability
            }
        }
    }
}
```

**Menjalankan program**

```bash
dotnet run
```

Anda akan melihat field macro dicetak ke konsol, sesuai dengan output yang diharapkan yang ditunjukkan sebelumnya.

## Kesimpulan

Dalam tutorial ini Anda belajar **how to decode PDF417** barcode di C# dengan contoh **barcode reader example** yang ringkas. Dengan menginstal Aspose.BarCode, membuat `BarCodeReader` untuk `MacroPdf417`, mengiterasi hasil, dan mengakses properti macro `Extended.Pdf417`, Anda dapat secara andal **read PDF417 barcode** data dari gambar apa pun yang didukung.  

Dari sini Anda dapat:

- Menerapkan agregasi segmen untuk membangun kembali file macro multi‑segmen.  
- Menjelajahi simbol lain (QR, Code128) menggunakan pola `BarCodeReader` yang sama.  
- Mengintegrasikan decoder ke dalam web API yang memproses gambar yang diunggah (`read barcode image C#` dalam konteks layanan).  

Silakan bereksperimen dengan sumber gambar yang berbeda, strategi penanganan error, dan optimasi kinerja. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membaca PDF417 di C# – panduan lengkap barcode reader](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Cara Menghasilkan Barcode PDF417 dengan Aspose – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cara Membuat Barcode PDF417 dengan Aspose – Panduan Langkah‑demi‑Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}