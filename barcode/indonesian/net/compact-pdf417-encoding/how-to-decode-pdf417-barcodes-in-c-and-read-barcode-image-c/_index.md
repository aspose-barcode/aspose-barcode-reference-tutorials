---
category: general
date: 2026-10-28
description: Cara mendekode barcode PDF417 di C# dengan cepat. Pelajari cara membaca
  gambar barcode C# menggunakan Aspose.BarCode dengan contoh lengkap yang dapat dijalankan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: id
lastmod: 2026-10-28
og_description: Cara mendekode barcode PDF417 di C# dengan Aspose.BarCode. Panduan
  ini menunjukkan cara membaca gambar barcode di C# langkah demi langkah, lengkap
  dengan kode.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Cara mendekode barcode PDF417 di C# – tutorial membaca gambar barcode C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Cara mendekode barcode PDF417 di C# dan membaca gambar barcode C#
url: /id/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mendekode barcode PDF417 di C# dan membaca gambar barcode C#

Jika Anda perlu **how to decode pdf417** dalam aplikasi .NET, panduan ini memberi Anda solusi siap‑jalankan. Anda akan melihat secara tepat cara **read barcode image c#** menggunakan pustaka Aspose.BarCode, mengekstrak bidang macro‑PDF417, dan menampilkannya di konsol.

Mendekode barcode PDF417 sering muncul dalam sistem logistik, tiket, dan verifikasi identitas. Pada akhir tutorial ini Anda akan dapat memuat gambar apa pun yang berisi barcode Macro PDF417, mendekodenya, dan mengakses nilai file ID, segment ID, dan segment count yang penting untuk menyusun dokumen multi‑segment.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru terinstal  
* Visual Studio 2022 (atau IDE C# apa pun)  
* Paket NuGet Aspose.BarCode untuk .NET (`Aspose.BarCode`)  
* File gambar yang berisi barcode Macro PDF417 (contoh menggunakan `ExtPDF417Meta.png`)

Anda dapat menambahkan paket NuGet dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru dan impor namespace yang diperlukan. Direktif `using` memberi Anda akses ke `BarCodeReader`, `DecodeType`, dan objek ekstensi hasil.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Mengapa langkah ini penting** – Mengimpor namespace yang tepat mencegah kesalahan saat kompilasi dan membuat permukaan API tersedia untuk logika dekode selanjutnya.

## Langkah 2: Tentukan jalur gambar

Tentukan jalur lengkap atau relatif ke gambar barcode. Menyimpan jalur dalam variabel membuat kode dapat digunakan kembali untuk gambar yang berbeda.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Tip:** Gunakan `Path.Combine` jika Anda membangun jalur dari beberapa bagian; ia menangani pemisah direktori di berbagai sistem operasi.

## Langkah 3: Buat `BarCodeReader` yang dikonfigurasi untuk dekode Macro PDF417

Instansiasi `BarCodeReader` dengan jalur gambar dan flag `DecodeType.MacroPdf417`. Ini memberi tahu pustaka untuk mencari simbol Macro PDF417 secara khusus.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Mengapa langkah ini penting** – Memilih `DecodeType` yang tepat meningkatkan kinerja karena mesin melewatkan format barcode yang tidak terkait.

## Langkah 4: Baca semua barcode dan tampilkan informasi macro

Lakukan perulangan pada setiap `BarCodeResult` yang dikembalikan oleh `reader.ReadBarCodes()`. Objek hasil berisi baik bidang generik (`CodeTypeName`, `CodeText`) maupun ekstensi khusus Macro PDF417 (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Apa yang dilakukan setiap baris

| Line | Explanation |
|------|-------------|
| `result.CodeTypeName` | Nama yang dapat dibaca manusia dari tipe barcode yang terdeteksi (mis., “MacroPdf417”). |
| `result.CodeText` | Data mentah yang dikodekan dalam barcode. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Pengidentifikasi yang menghubungkan semua segmen dokumen macro PDF417 bersama-sama. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Indeks segmen saat ini dalam keseluruhan dokumen. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Jumlah total segmen yang diharapkan untuk dokumen. |

> **Pro tip:** Simpan bidang macro dalam basis data jika Anda perlu menyusun kembali dokumen lengkap nanti. `File ID` memungkinkan Anda mengelompokkan segmen yang berasal dari sumber yang sama.

## Langkah 5: Jalankan program dan verifikasi output

Bangun dan jalankan aplikasi konsol:

```bash
dotnet run
```

Output konsol tipikal terlihat seperti ini:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Jika gambar berisi beberapa simbol Macro PDF417, perulangan akan mencetak masing‑masing secara berurutan.

### Menangani kasus tepi umum

| Situasi | Penanganan yang disarankan |
|-----------|----------------------|
| **No barcode found** | Periksa `reader.ReadBarCodes().Any()` sebelum perulangan dan tampilkan pesan yang ramah. |
| **Corrupted image** | Bungkus pembuatan `BarCodeReader` dalam blok `try/catch` untuk `BarCodeException`. |
| **Multiple barcode formats** | Gunakan `DecodeType.AllSupported` dan saring hasil dengan `result.CodeTypeName == "MacroPdf417"`. |
| **Large images** | Turunkan resolusi gambar sebelum mendekode untuk meningkatkan kinerja; pustaka menerima objek `Bitmap`. |

## Kode sumber lengkap

Berikut adalah program lengkap yang berdiri sendiri. Salin ke `Program.cs` dari proyek konsol baru dan ganti `YOUR_DIRECTORY/ExtPDF417Meta.png` dengan jalur sebenarnya ke gambar Anda.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Kesimpulan

Anda kini tahu **how to decode pdf417** barcode di C# dan cara **read barcode image c#** menggunakan Aspose.BarCode. Tutorial ini memandu Anda melalui penyiapan proyek, pemuatan gambar, konfigurasi pembaca, ekstraksi hasil, dan penanganan kasus tepi. Dengan dasar ini Anda dapat mengintegrasikan dekode PDF417 ke dalam sistem inventaris, validator tiket, atau alur kerja apa pun yang bergantung pada data macro‑encoded.

### Langkah selanjutnya

* Jelajahi format barcode lain dengan mengubah `DecodeType` (mis., `DecodeType.QR`, `DecodeType.Code128`).  
* Gabungkan beberapa segmen yang telah didekode untuk merekonstruksi dokumen asli.  
* Gunakan kelas `BarCodeGenerator` untuk membuat barcode PDF417 percobaan secara langsung.  

Silakan bereksperimen dengan sumber gambar yang berbeda, sesuaikan output konsol, atau sematkan logika dekode ke dalam API web untuk pemrosesan waktu nyata. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara mendekode PDF417 di C# dengan contoh pembaca barcode](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Cara menghasilkan barcode PDF417 di C# dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Cara membaca barcode dari gambar c# menggunakan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}