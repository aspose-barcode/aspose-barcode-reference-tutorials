---
category: general
date: 2026-10-15
description: Cara membaca gambar barcode di C# dengan cepat menggunakan BarCodeReader.
  Pelajari cara membaca beberapa barcode dan lihat contoh pembaca barcode C# yang
  bekerja dengan Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: id
lastmod: 2026-10-15
og_description: Cara membaca barcode di C# menggunakan BarCodeReader. Tutorial ini
  menunjukkan contoh pembaca barcode C# lengkap yang menangani beberapa barcode dan
  mengekstrak metadata Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Cara membaca barcode di C# – contoh langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membaca gambar barcode di C# – panduan contoh lengkap
url: /id/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Gambar Barcode di C# – Panduan Contoh Lengkap

Jika Anda perlu **cara membaca barcode** dari sebuah gambar dalam aplikasi .NET, panduan ini memberikan solusi siap‑jalankan. Anda akan melihat contoh **c# barcode reader** lengkap yang bekerja dengan simbol Macro‑PDF417 dan dapat **membaca beberapa barcode** dari satu gambar.

Membaca barcode adalah kebutuhan umum untuk sistem inventaris, validasi tiket, dan pemrosesan dokumen. Pada akhir tutorial ini Anda akan dapat:

* Menginisialisasi `BarCodeReader` untuk format yang didukung apa pun.  
* Mengekstrak informasi dasar seperti tipe kode dan teks terdekripsi.  
* Mengambil metadata khusus Macro‑PDF417 (ID file, segmen, checksum, …).  
* Menangani gambar yang berisi beberapa barcode tanpa kode tambahan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang.  
* Lingkungan pengembangan (Visual Studio 2022, VS Code, atau Rider).  
* Paket NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – menyediakan kelas `BarCodeReader` yang digunakan dalam contoh.  
* Sebuah file gambar yang berisi barcode Macro‑PDF417 (misalnya `MacroPdf417.png`).  

Anda dapat menginstal paket NuGet dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Cara Membaca Barcode dengan BarCodeReader di C#

Inti solusi terdiri dari empat langkah singkat. Setiap langkah dibungkus dalam blok `using` untuk memastikan sumber daya yang tidak dikelola dilepaskan dengan cepat.

### Langkah 1: Inisialisasi `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Mengapa ini penting:**  
`BarCodeReader` menerima jalur file dan sebuah `DecodeType`. Menentukan `DecodeType.MacroPdf417` memberi tahu pustaka untuk mencari simbol Macro‑PDF417 saja, yang mempercepat deteksi dan mengurangi positif palsu.

### Langkah 2: Baca semua barcode yang ada dalam gambar

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Mengapa ini penting:**  
Metode `ReadBarCodes()` mengembalikan sebuah array yang dapat berisi satu atau banyak objek `BarCodeResult`. Di sinilah kemampuan **membaca beberapa barcode** bersinar – Anda tidak memerlukan loop terpisah untuk setiap kemungkinan barcode.

### Langkah 3: Tampilkan detail barcode dasar

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Mengapa ini penting:**  
`CodeTypeName` memberi tahu Anda simbol apa yang terdeteksi (misalnya “MacroPDF417”), sementara `CodeText` berisi payload yang terdekripsi. Kedua bidang ini paling sering digunakan dalam logika selanjutnya.

### Langkah 4: Ambil dan tampilkan metadata khusus Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Mengapa ini penting:**  
Macro‑PDF417 memperluas format PDF417 reguler dengan metadata tingkat dokumen. Mengakses properti `Extended.Pdf417` memberikan semua yang Anda perlukan untuk merekonstruksi file asli, memvalidasi integritas, atau mengarahkan data ke penerima yang tepat.

### Program lengkap yang dapat dijalankan

Berikut adalah aplikasi konsol mandiri yang menggabungkan keempat langkah. Salin kode ke file `.cs` baru, sesuaikan `imagePath`, dan jalankan `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Output konsol yang diharapkan

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Jika gambar berisi lebih dari satu simbol Macro‑PDF417, program akan mencetak blok terpisah untuk setiap barcode, memperlihatkan kemampuan **membaca beberapa barcode** tanpa kode tambahan.

## Menangani kasus tepi umum

| Situasi | Apa yang harus dilakukan | Alasan |
|-----------|------------|--------|
| **File tidak ditemukan** | Bungkus konstruktor `BarCodeReader` dalam blok `try/catch (FileNotFoundException)` dan tampilkan pesan yang ramah. | Mencegah aplikasi crash dan memberi tahu pengguna tentang aset yang hilang. |
| **Tidak ada barcode terdeteksi** | Periksa `results.Length == 0` (seperti yang ditunjukkan dalam program lengkap) dan tangani dengan elegan. | Memberikan umpan balik jelas ketika gambar tidak mengandung simbol yang didukung. |
| **Tipe barcode berbeda** | Ubah `DecodeType.MacroPdf417` menjadi `DecodeType.AllSupportedTypes` atau nilai enum spesifik lainnya. | Memungkinkan basis kode yang sama bekerja dengan QR, Code128, DataMatrix, dll., sambil tetap mendukung **membaca beberapa barcode**. |
| **Gambar berukuran besar** | Setel `reader.AutoSize = true` atau lakukan down‑scale gambar sebelum memberikannya ke pembaca. | Meningkatkan kinerja dan mengurangi tekanan memori pada CLR. |
| **Penggunaan thread‑safe** | Buat instance `BarCodeReader` terpisah per thread; kelas ini tidak thread‑safe. | Menghindari kondisi balapan pada pemindai multi‑thread atau layanan web. |

## Tips profesional untuk kode produksi

* **Dispose lebih awal:** Pernyataan `using` memastikan bahwa sumber daya native (misalnya buffer gambar) dilepaskan dengan cepat. Pada layanan yang berjalan lama, lepaskan pembaca segera setelah selesai memproses tiap gambar.  
* **Pemrosesan batch**  

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Baca barcode dari gambar C# – panduan lengkap dengan Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Cara membuat barcode macro PDF417 di C# menggunakan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cara Membaca PDF417 di C# – Contoh Lengkap Pembaca Barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}