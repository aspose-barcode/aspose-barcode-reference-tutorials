---
category: general
date: 2026-11-23
description: Pelajari cara menggunakan BarCodeReader dalam C# untuk membaca kode batang
  dari gambar, termasuk decoding Macro PDF417, dengan contoh kode lengkap dan penjelasan
  yang jelas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: id
lastmod: 2026-11-23
og_description: Cara menggunakan BarCodeReader di C# untuk membaca barcode dari gambar.
  Ikuti panduan langkah demi langkah ini untuk mendekode Macro PDF417 dan format lainnya
  dengan kode siap pakai.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Cara menggunakan BarCodeReader di C# – baca kode batang dari gambar dengan
  cepat
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Cara menggunakan BarCodeReader di C# untuk membaca barcode dari gambar
url: /id/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan BarCodeReader di C# untuk membaca barcode dari gambar

Jika Anda perlu **cara menggunakan BarCodeReader** untuk pemindaian barcode cepat, panduan ini menunjukkan hal itu secara tepat. Baik Anda sedang membangun sistem point‑of‑sale atau mengotomatisasi pengambilan dokumen, Anda akan belajar cara membaca barcode dari gambar dalam proyek C# dengan hanya beberapa baris kode.

Dalam tutorial ini Anda akan melihat contoh lengkap yang dapat dijalankan yang mendekode barcode Macro PDF417, mengekstrak properti ekstendednya, dan mencetak informasi berguna ke konsol. Tidak diperlukan dokumentasi eksternal – semua yang Anda butuhkan ada di sini.

## Prasyarat

* .NET 6.0 (atau lebih baru) terpasang – kode menargetkan versi LTS terbaru.
* Referensi ke paket NuGet **Aspose.BarCode** (atau yang kompatibel) yang menyediakan `BarCodeReader`.
* File gambar yang berisi barcode Macro PDF417 (contoh menggunakan `ExtPDF417Meta.png`).

> **Tips pro:** Jika Anda menggunakan Visual Studio, tambahkan paket melalui `dotnet add package Aspose.BarCode` atau UI NuGet Package Manager.

## Langkah 1: Buat instance BarCodeReader

Hal pertama yang Anda lakukan saat bekerja dengan perpustakaan barcode adalah menginstansiasi pembaca yang menunjuk ke gambar sumber dan memberi tahu API jenis barcode apa yang harus dicari.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Mengapa langkah ini penting:*  
`BarCodeReader` membuka gambar, mengalokasikan memori native, dan menyiapkan algoritma decoding untuk `DecodeType` yang ditentukan. Dengan membatasi tipe ke `MacroPdf417`, Anda mengurangi beban CPU dan meningkatkan akurasi deteksi.

## Langkah 2: Baca semua barcode yang ditemukan dalam gambar

Sebuah gambar tunggal dapat berisi beberapa barcode, terutama ketika menangani data yang macro‑encoded. Metode `ReadBarCodes` mengembalikan enumerable dari objek `BarCodeResult`, masing‑masing mewakili satu kode yang terdeteksi.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Mengapa langkah ini penting:*  
Iterasi atas koleksi memastikan Anda menangkap setiap instance, yang penting untuk skenario pemrosesan batch atau ketika sebuah dokumen menyematkan beberapa kode.

## Langkah 3: Akses properti Macro PDF417 yang diperluas

Macro PDF417 menyimpan metadata tambahan seperti pengidentifikasi file, nomor segmen, dan total jumlah segmen. Nilai‑nilai ini tersedia melalui properti `Extended.Pdf417` dari `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Mengapa langkah ini penting:*  
Field yang diperluas memungkinkan Anda merekonstruksi dokumen multi‑segmen atau memvalidasi bahwa semua bagian berasal dari sumber yang sama. Melewatkan langkah ini hanya memberi Anda teks mentah, kehilangan konteks berharga.

## Langkah 4: Keluarkan informasi yang paling berguna

Akhirnya, tulis data ke konsol (atau logger apa pun) sehingga Anda dapat memverifikasi operasi pembacaan. Contoh ini mencetak tipe kode, teks terdekripsi, dan beberapa field macro.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Output konsol yang diharapkan**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Catatan:** Jika gambar tidak mengandung barcode Macro PDF417, `ReadBarCodes()` mengembalikan koleksi kosong dan badan loop tidak pernah dijalankan. Selalu periksa hasil kosong dalam kode produksi.

## Membaca barcode dari gambar di C# – menangani skenario umum

### 1. Mendekode beberapa format barcode

Jika Anda perlu mendeteksi lebih dari satu format, berikan flag `DecodeType` yang digabungkan:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Mengelola gambar besar

Gambar besar dapat menyebabkan penggunaan memori tinggi. Skala turun gambar sebelum memberikannya ke pembaca:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Penanganan kesalahan

Bungkus logika pembacaan dalam blok try‑catch untuk menampilkan kegagalan decoding:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan. Program ini mencakup semua langkah, direktif `using` yang diperlukan, dan kerangka penanganan kesalahan sederhana.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Menjalankan program** mencetak setiap barcode Macro PDF417 yang terdeteksi dan field yang diperluas, atau memberi tahu Anda bahwa tidak ada barcode yang ditemukan.

## Kesimpulan

Anda sekarang tahu **cara menggunakan BarCodeReader** untuk membaca barcode dari aplikasi C# berbasis gambar, termasuk mengekstrak metadata Macro PDF417. Solusi ini mencakup inisialisasi, iterasi, akses properti yang diperluas, dan tips praktis untuk menangani banyak format, gambar besar, dan kesalahan.

Selanjutnya, Anda mungkin ingin menjelajahi:

* **Membaca QR code** – ganti `DecodeType.MacroPdf417` dengan `DecodeType.QR`.
* **Menyimpan data terdekripsi** ke basis data atau file JSON untuk pemrosesan lanjutan.
* **Mengintegrasikan dengan ASP.NET Core** untuk menerima gambar yang diunggah melalui API web.

Silakan bereksperimen dengan berbagai tipe barcode dan sumber gambar. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang dapat dijalankan dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [tutorial pembaca barcode c# – membaca barcode Macro PDF417 langkah demi langkah menggunakan GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Cara menggunakan generator barcode C# untuk Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Membaca barcode dari gambar C# – panduan lengkap dengan Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}