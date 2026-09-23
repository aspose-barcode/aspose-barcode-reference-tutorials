---
category: general
date: 2026-09-22
description: Pelajari cara membaca kode batang PDF417 di C# dengan contoh pembaca
  kode batang lengkap. Tutorial ini menunjukkan cara membaca gambar kode batang di
  C# secara cepat dan andal.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: id
lastmod: 2026-09-22
og_description: Cara membaca kode batang PDF417 dalam C# menggunakan contoh pembaca
  kode batang yang singkat. Ikuti panduan untuk mendekode gambar Macro PDF417 dan
  mengekstrak metadata.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Cara membaca barcode PDF417 di C# – contoh lengkap pembaca barcode
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Cara membaca kode batang PDF417 di C# – panduan lengkap langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca barcode PDF417 di C# – panduan langkah demi langkah lengkap

Jika Anda perlu **cara membaca pdf417** dalam aplikasi .NET, panduan ini menunjukkan kode tepat dan penjelasan yang Anda butuhkan. Pada akhir dua kalimat pertama Anda akan tahu cara membaca gambar barcode C# menggunakan kelas `BarCodeReader` yang populer, dan Anda akan memiliki contoh siap‑jalankan yang mengekstrak setiap bagian metadata Macro PDF417.

Membaca barcode PDF417 adalah kebutuhan umum saat memproses label pengiriman, boarding pass, atau dokumen aman. Tutorial ini mencakup semua hal mulai dari menyiapkan pembaca hingga menangani kasus pinggiran, sehingga Anda dapat mengintegrasikan pemindaian barcode dengan percaya diri.

## Apa yang akan Anda capai

- Mendekode file gambar Macro PDF417.
- Mencetak informasi barcode dasar (tipe dan teks).
- Mengakses semua bidang ekstensi Macro PDF417 seperti ID file, jumlah segmen, dan timestamp.
- Memahami jebakan umum saat bekerja dengan kode PDF417 multi‑segmen.

**Prasyarat**

- .NET 6.0 atau lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7+).
- Referensi ke SDK barcode yang menyediakan `BarCodeReader`, `DecodeType`, dan `BarCodeResult` (misalnya Aspose.BarCode, Dynamsoft, atau perpustakaan apa pun yang mengekspos API yang sama).
- File gambar (`ExtPDF417Meta.png`) yang berisi barcode Macro PDF417.

> **Pro tip:** Tempatkan gambar di folder yang relatif terhadap root proyek Anda dan atur properti **Copy to Output Directory** menjadi *Copy if newer* sehingga jalur berfungsi saat debugging.

![Cara membaca barcode PDF417 menggunakan C#](https://example.com/placeholder-image.png)

## Cara membaca barcode PDF417 di C# – kode lengkap

Di bawah ini adalah program mandiri yang dapat Anda tempelkan ke aplikasi konsol. Program ini membuat pembaca barcode, mengiterasi setiap hasil dekode, dan mencetak baik bidang standar maupun bidang ekstensi Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
}
```

### Mengapa setiap langkah penting

1. **Membuat pembaca dengan `DecodeType.MacroPdf417`** – Macro PDF417 adalah varian khusus yang dapat membawa metadata tingkat file. Menentukan tipe dekode memastikan SDK mem-parsing bidang ekstra tersebut alih‑alih memperlakukan kode sebagai PDF417 biasa.
2. **Mengiterasi `ReadBarCodes()`** – Sebuah gambar dapat berisi lebih dari satu barcode (misalnya QR code di samping PDF417). Loop ini menjamin Anda menangkap setiap hasil.
3. **Mencetak `CodeTypeName` dan `CodeText`** – Ini adalah properti yang paling sering digunakan; mereka memberi Anda nama simbolologi dan payload yang dapat dibaca manusia.
4. **Mengakses `Extended.Pdf417`** – Objek `Extended` hanya muncul untuk tipe dekode terkait PDF417. Setiap properti memetakan langsung ke spesifikasi Macro PDF417, memungkinkan Anda membangun kembali file asli atau memvalidasi urutan segmen.

## Variasi umum dan kasus pinggiran

### Membaca barcode PDF417 non‑macro

Jika gambar sumber Anda berisi kode PDF417 reguler (tanpa metadata macro), ganti `DecodeType.MacroPdf417` dengan `DecodeType.Pdf417`. Sisanya tetap sama, tetapi blok `Extended.Pdf417` akan kosong karena bidang tersebut memang tidak ada.

### Menangani PDF multi‑segmen

Macro PDF417 dapat membagi dokumen besar menjadi beberapa segmen barcode. Untuk menyusun kembali file asli Anda harus:

1. Mengumpulkan `Pdf417MacroSegmentID` setiap segmen.
2. Mengurutkan segmen berdasarkan ID‑nya.
3. Memverifikasi `Pdf417MacroSegmentsCount` cocok dengan jumlah segmen yang diterima.
4. Menggabungkan `CodeText` setiap segmen secara berurutan.
5. Opsional: memvalidasi `Pdf417MacroChecksum`.

Berikut adalah cuplikan singkat yang menunjukkan logika penyusunan kembali:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Menangani gambar yang rusak

- **Kontras rendah** – Tingkatkan pra‑pemrosesan gambar (misalnya equalisasi histogram) sebelum mengirimkannya ke `BarCodeReader`.
- **Rotasi** – Gunakan `barcodeReader.SetRotateAngle(90)` atau aktifkan auto‑rotate jika SDK mendukungnya.
- **Pemindaian parsial** – Pastikan resolusi gambar setidaknya 300 dpi; jika tidak SDK mungkin melewatkan segmen kecil.

## contoh pembaca barcode c# – praktik terbaik

| Praktik | Alasan |
|----------|--------|
| **Dispose the reader with `using`** | Menjamin sumber daya native dilepaskan segera, mencegah kebocoran memori. |
| **Validate `result.Extended` is not null** | Beberapa SDK mengembalikan `null` untuk kode non‑macro; pengecekan menghindari `NullReferenceException`. |
| **Log the `Pdf417MacroFileID`** | Identifier ini unik per file dan berguna untuk jejak audit. |
| **Wrap decoding in a try/catch** | Kesalahan I/O (file tidak ditemukan) atau format tidak didukung akan menimbulkan pengecualian yang harus ditangani secara elegan. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Output yang diharapkan

Menjalankan program lengkap terhadap `ExtPDF417Meta.png` yang diformat dengan benar menghasilkan output serupa dengan:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Jika gambar berisi beberapa segmen, loop akan mencetak metadata setiap segmen secara berurutan.

## Kesimpulan

Anda kini tahu **cara membaca pdf417** barcode di C# dan memiliki **contoh pembaca barcode c#** yang mengekstrak setiap bidang Macro PDF417. Solusi ini mencakup dekode dasar, ekstraksi metadata, penyusunan kembali multi‑segmen, dan penanganan error, memberikan fondasi siap produksi untuk alur kerja pemrosesan dokumen apa pun.

### Langkah selanjutnya

- Jelajahi teknik **read barcode image C#** untuk simbolologi lain (QR, DataMatrix) menggunakan API `BarCodeReader` yang sama.
- Integrasikan decoder barcode ke layanan ASP.NET Core untuk memproses unggahan secara real‑time.
- Bereksperimen dengan perpustakaan pra‑pemrosesan gambar (misalnya `OpenCvSharp`) untuk meningkatkan tingkat keberhasilan pada pemindaian berkualitas rendah.

Selamat coding, dan silakan sesuaikan contoh ini agar cocok dengan kasus penggunaan spesifik Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menyimpan Barcode di C# – Membuat Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Cara Membaca PDF417 di C# – Panduan Langkah demi Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Cara Mengatur Tingkat Kesalahan pada Barcode PDF417 – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}