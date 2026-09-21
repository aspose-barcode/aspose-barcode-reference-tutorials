---
category: general
date: 2026-07-30
description: Baca kode batang dari gambar menggunakan Aspose.BarCode untuk .NET –
  contoh lengkap pembaca kode batang C# yang menunjukkan cara mendekode kode batang
  Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- c# barcode reader example
- macro pdf417 decoding
- aspose.barcode for .net
- barcode processing c#
language: id
lastmod: 2026-07-30
og_description: Baca kode batang dari gambar dengan Aspose.BarCode untuk .NET. Contoh
  pembaca kode batang C# langkah demi langkah ini menunjukkan cara mengekstrak semua
  metadata Macro PDF417.
og_image_alt: Screenshot of C# console output displaying decoded Macro PDF417 barcode
  information
og_title: Baca kode batang dari gambar – Contoh lengkap pembaca kode batang C#
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Read barcode from image using Aspose.BarCode for .NET – a complete
    C# barcode reader example that shows how to decode Macro PDF417 barcodes.
  headline: Read barcode from image – C# barcode reader example
  type: TechArticle
- description: Read barcode from image using Aspose.BarCode for .NET – a complete
    C# barcode reader example that shows how to decode Macro PDF417 barcodes.
  name: Read barcode from image – C# barcode reader example
  steps:
  - name: '**`using` block** – Guarantees the native resources (file handles, native
      decoder memory) are freed immediately after the operation. Skipping this can
      lead to locked files on Windows.'
    text: '**`using` block** – Guarantees the native resources (file handles, native
      decoder memory) are freed immediately after the operation. Skipping this can
      lead to locked files on Windows.'
  - name: '**`DecodeType.MacroPdf417`** – Tells Aspose to look specifically for Macro PDF417
      symbols; other barcode types are ignored, which speeds up scanning.'
    text: '**`DecodeType.MacroPdf417`** – Tells Aspose to look specifically for Macro PDF417
      symbols; other barcode types are ignored, which speeds up scanning.'
  - name: '**`ReadBarCodes()`** – Returns a collection because an image might contain
      multiple Macro PDF417 segments (think of a multi‑page document split across
      several barcodes).'
    text: '**`ReadBarCodes()`** – Returns a collection because an image might contain
      multiple Macro PDF417 segments (think of a multi‑page document split across
      several barcodes).'
  - name: '**`macroResult.Extended?.Pdf417`** – The `Extended` object is nullable;
      the safe‑navigation operator (`?.`) prevents a `NullReferenceException` if the
      barcode lacks extended data.'
    text: '**`macroResult.Extended?.Pdf417`** – The `Extended` object is nullable;
      the safe‑navigation operator (`?.`) prevents a `NullReferenceException` if the
      barcode lacks extended data.'
  - name: '**Printing each field** – Gives you visibility into the file identifier,
      segment ordering, checksum verification, and optional textual fields like sender
      or addressee.'
    text: '**Printing each field** – Gives you visibility into the file identifier,
      segment ordering, checksum verification, and optional textual fields like sender
      or addressee.'
  - name: '**Collect all segments** into a dictionary keyed by `SegmentID`.'
    text: '**Collect all segments** into a dictionary keyed by `SegmentID`.'
  - name: '**Sort** them by `SegmentID` to reassemble the original file.'
    text: '**Sort** them by `SegmentID` to reassemble the original file.'
  - name: '**Validate** the `Checksum` against the concatenated payload (Aspose does
      this internally, but you can re‑run a CRC if you need extra safety).'
    text: '**Validate** the `Checksum` against the concatenated payload (Aspose does
      this internally, but you can re‑run a CRC if you need extra safety).'
  type: HowTo
tags:
- barcode
- csharp
- aspnet
- image-processing
title: Baca kode batang dari gambar – contoh pembaca kode batang C#
url: /id/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca barcode dari gambar – contoh pembaca barcode C#  

Need to **read barcode from image** in a C# application? You’re in the right place. In this tutorial we’ll walk through a complete *c# barcode reader example* that uses the Aspose.BarCode for .NET library to decode a Macro PDF417 barcode and pull out every piece of extended information the standard provides.

Bayangkan Anda baru saja memindai label pengiriman, boarding pass, atau KTP pemerintah yang menyisipkan segmen Macro PDF417. Anda ingin mengambil ID file, jumlah segmen, cap waktu, dan bahkan nama pengirim—semua tanpa meninggalkan kode Anda. Itulah yang akan kita capai, dan kita akan melakukannya dengan cara yang mudah disalin‑tempel ke proyek Anda sendiri.

---

## Apa yang akan Anda pelajari

- Cara menambahkan paket NuGet Aspose.BarCode ke proyek .NET.  
- Cara membuka file gambar yang berisi barcode Macro PDF417.  
- Cara mengiterasi hasil **read barcode from image** dan mengakses setiap bidang tambahan.  
- Tips untuk menangani beberapa segmen, memvalidasi checksum, dan memecahkan masalah umum.

Pada akhir panduan ini Anda akan memiliki aplikasi konsol yang mencetak semua metadata Macro PDF417, siap diintegrasikan ke sistem yang lebih besar seperti pelacak inventaris atau alur kerja manajemen dokumen.

---

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

| Persyaratan | Mengapa penting |
|-------------|-----------------|
| .NET 6.0 SDK atau yang lebih baru (versi terbaru apa pun) | Menyediakan runtime untuk aplikasi konsol. |
| Visual Studio 2022 (atau VS Code dengan ekstensi C#) | Mempermudah pengeditan dan debugging. |
| Aspose.BarCode for .NET (free trial or licensed) | Pustaka yang sebenarnya mendekode barcode. |
| File gambar (`MacroPdf417Meta.png`) yang berisi barcode Macro PDF417 | Sumber yang akan kami baca. |

Jika Anda belum memiliki Aspose.BarCode, Anda dapat mengunduhnya dari NuGet:

```bash
dotnet add package Aspose.BarCode
```

Baris tunggal itu menginstal semua yang Anda butuhkan, termasuk `BarCodeReader`, `DecodeType`, dan set properti `Extended` yang kaya yang akan kami jelajahi.

---

## Langkah 1 – Siapkan proyek dan impor pustaka

Buat proyek konsol baru (atau masukkan kode ke proyek yang sudah ada). Direktif `using` sangat penting; mereka membawa kelas barcode ke dalam ruang lingkup.

```csharp
// Program.cs – entry point for the demo
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;   // contains BarCodeReader and DecodeType
```

> **Pro tip:** Jika Anda menggunakan Visual Studio, IDE akan menawarkan menambahkan pernyataan `using` yang hilang secara otomatis—cukup tekan *Ctrl+.`*.

---

## Langkah 2 – Siapkan jalur gambar

Hard‑coding jalur absolut bekerja untuk demo cepat, tetapi di produksi Anda mungkin menerima argumen baris perintah atau pengaturan konfigurasi. Untuk kejelasan kami akan tetap sederhana:

```csharp
// Adjust the path to point at your image file
string imagePath = @"C:\Barcodes\MacroPdf417Meta.png";
```

> **Mengapa penting:** `BarCodeReader` mengharapkan lokasi file yang valid; jalur yang salah akan melempar `FileNotFoundException` sebelum proses dekode dimulai.

---

## Langkah 3 – **Baca barcode dari gambar** dan ekstrak detail Macro PDF417

Sekarang masuk ke inti **c# barcode reader example**. Kami akan menginstansiasi `BarCodeReader` dengan flag `DecodeType.MacroPdf417`, melintasi semua hasil (bisa lebih dari satu barcode dalam satu gambar), dan mencetak setiap properti tambahan.

```csharp
// Step 3: Open the image and decode Macro PDF417 barcodes
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Iterate over every barcode found in the image
    foreach (BarCodeResult macroResult in reader.ReadBarCodes())
    {
        // The Extended property contains the Macro PDF417 specific fields
        var pdf417 = macroResult.Extended?.Pdf417;

        if (pdf417 == null)
        {
            Console.WriteLine("No Macro PDF417 extension data found for this barcode.");
            continue;
        }

        // Output each piece of metadata – this is what makes the example useful
        Console.WriteLine($"FileID: {pdf417.MacroPdf417FileID}");
        Console.WriteLine($"SegmentID: {pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"SegmentsCount: {pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName: {pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum: {pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize: {pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"TimeStamp: {pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender: {pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator: {pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40)); // separator for readability
    }
}
```

### Apa yang dilakukan kode (mengapa, bukan hanya bagaimana)

1. **`using` block** – Menjamin sumber daya native (handle file, memori decoder native) dibebaskan segera setelah operasi. Melewatkannya dapat menyebabkan file terkunci di Windows.  
2. **`DecodeType.MacroPdf417`** – Memerintahkan Aspose untuk mencari simbol Macro PDF417 secara khusus; tipe barcode lain diabaikan, yang mempercepat pemindaian.  
3. **`ReadBarCodes()`** – Mengembalikan koleksi karena sebuah gambar mungkin berisi beberapa segmen Macro PDF417 (bayangkan dokumen multi‑halaman yang dibagi menjadi beberapa barcode).  
4. **`macroResult.Extended?.Pdf417`** – Objek `Extended` dapat bernilai null; operator navigasi aman (`?.`) mencegah `NullReferenceException` jika barcode tidak memiliki data tambahan.  
5. **Mencetak setiap field** – Memberikan visibilitas ke identifier file, urutan segmen, verifikasi checksum, dan field teks opsional seperti pengirim atau penerima.

---

## Langkah 4 – Jalankan aplikasi dan verifikasi output

Kompilasi dan jalankan program:

```bash
dotnet run
```

Jika semuanya terhubung dengan benar, Anda akan melihat sesuatu yang mirip dengan berikut di konsol Anda:

```
FileID: 12
SegmentID: 3
SegmentsCount: 5
FileName: invoice_2023.pdf
Checksum: 0x1A2B
FileSize: 45231
TimeStamp: 2023-08-15T14:32:00Z
Addressee: Acme Corp.
Sender: Warehouse 7
Terminator: 0xFF
----------------------------------------
```

> **Catatan:** Nilai tepat tergantung pada barcode yang Anda dekode. Jika Anda mendapatkan “No Macro PDF417 extension data found,” periksa kembali bahwa gambar benar‑benar berisi kode Macro PDF417 dan bahwa Anda menggunakan `DecodeType` yang tepat.

---

## Menangani beberapa segmen dan validasi (lanjutan)

Macro PDF417 dirancang untuk muatan data besar yang dibagi menjadi beberapa simbol. Ketika Anda menemukan lebih dari satu segmen, biasanya Anda perlu:

1. Kumpulkan semua segmen ke dalam kamus yang diindeks oleh `SegmentID`.  
2. Urutkan mereka berdasarkan `SegmentID` untuk menyusun kembali file asli.  
3. Validasi `Checksum` terhadap payload yang digabungkan (Aspose melakukannya secara internal, tetapi Anda dapat menjalankan kembali CRC jika memerlukan keamanan tambahan).  

Berikut sketsa cepat:

```csharp
var segments = new SortedDictionary<int, BarCodeResult>();

using (var reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    foreach (var result in reader.ReadBarCodes())
    {
        var pdf = result.Extended?.Pdf417;
        if (pdf != null)
            segments[pdf.MacroPdf417SegmentID] = result;
    }
}

// Reassemble data (pseudo‑code)
byte[] fullPayload = AssembleSegments(segments);
bool isValid = VerifyChecksum(fullPayload, segments[0].Extended.Pdf417.MacroPdf417Checksum);
Console.WriteLine(isValid ? "Checksum OK" : "Checksum mismatch");
```

Anda perlu mengimplementasikan `AssembleSegments` dan `VerifyChecksum` berdasarkan format payload Anda—seringkali hanya penggabungan array byte diikuti dengan pemeriksaan CRC‑16.

---

## Kesalahan umum dan cara menghindarinya

| Gejala | Penyebab kemungkinan | Perbaikan |
|--------|----------------------|-----------|
| `null` dikembalikan dari `macroResult.Extended` | Gambar berisi PDF417 biasa, bukan versi Macro. | Gunakan `DecodeType.Pdf417` sebagai gantinya, atau verifikasi barcode sumber. |
| Tidak ada output sama sekali | `imagePath` salah atau file tidak dapat diakses. | Periksa kembali jalur file; pastikan aplikasi memiliki izin membaca. |
| Exception “Object disposed” | Mencoba menggunakan `reader` setelah blok `using`. | Simpan semua pemrosesan di dalam ` |

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Pemrograman Pembaca DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Inisialisasi Pembaca DotCode dengan Aspose.BarCode untuk .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-reader-initialization/)
- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}