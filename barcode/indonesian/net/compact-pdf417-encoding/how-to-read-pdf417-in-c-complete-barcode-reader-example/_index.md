---
category: general
date: 2026-07-21
description: Cara membaca barcode PDF417 di C# menggunakan contoh pembaca barcode
  yang singkat. Pelajari dengan cepat cara membaca barcode dari gambar dengan kode
  langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: id
lastmod: 2026-07-21
og_description: Cara membaca barcode PDF417 di C# dengan contoh praktis. Temukan cara
  membaca barcode dari gambar dan mengintegrasikan contoh pembaca barcode C# secara
  instan.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Cara Membaca PDF417 di C# – Panduan Lengkap Pembaca Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Cara Membaca PDF417 di C# – Contoh Pembaca Barcode Lengkap
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca PDF417 di C# – Contoh Pembaca Barcode Lengkap

Pernah bertanya-tanya **bagaimana cara membaca PDF417** dalam proyek .NET tanpa harus mencari melalui dokumentasi yang tak berujung? Anda bukan satu-satunya. Baik Anda memindai SIM, boarding pass, atau tag inventaris khusus, mengekstrak data tersebut secara andal adalah kebutuhan dunia nyata.  

Dalam panduan ini kami akan membahas **contoh pembaca barcode c#** yang mengambil setiap bagian metadata Macro PDF417 dari satu file gambar. Pada akhir tutorial Anda akan memiliki aplikasi console siap‑jalankan yang **membaca barcode dari gambar** dan mencetak semua bidang ekstended yang mungkin Anda perlukan.

## Apa yang Anda Butuhkan

- .NET 6.0 SDK atau yang lebih baru (Anda juga dapat menargetkan .NET Framework 4.7+ – kode berfungsi sama)
- Visual Studio 2022, VS Code, atau editor C# apa pun yang Anda suka
- Paket NuGet **Aspose.BarCode for .NET** (kelas `BarCodeReader` berasal dari pustaka ini)
- File gambar yang berisi barcode Macro PDF417 (untuk demo kami akan menggunakan `ExtPDF417Meta.png`)

> **Tip pro:** Jika Anda tidak memiliki contoh PDF417, Aspose menyediakan beberapa gambar uji di repositori GitHub mereka – cukup unduh satu dan letakkan di folder proyek Anda.

## Langkah 1: Instal Perpustakaan Barcode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menambahkan `BarCodeReader`, `DecodeType`, dan properti `Extended` yang akan kita perlukan nanti. Tidak diperlukan konfigurasi tambahan; perpustakaan ini bekerja langsung untuk sebagian besar format gambar (PNG, JPEG, BMP, dll.).

## Langkah 2: Buat Aplikasi Console Minimal

Buat proyek console baru jika belum melakukannya:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Ganti `Program.cs` yang dihasilkan dengan kode di bawah ini. Perhatikan bagaimana setiap bagian dikomentari sehingga Anda dapat mengikuti logika meskipun baru dalam pemrosesan barcode.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Mengapa Ini Berfungsi

- **`DecodeType.MacroPdf417`** memberi tahu pembaca untuk mengharapkan format Macro PDF417 yang diperluas, yang membawa metadata tambahan (ID file, jumlah segmen, cap waktu, dll.).
- Objek **`Extended.Pdf417`** hanya diisi untuk barcode Macro PDF417, sehingga mengakses properti tersebut aman setelah pemanggilan `ReadBarCodes()`.
- Menggunakan blok **`using`** menjamin bahwa handle file dilepaskan, mencegah masalah penguncian file di Windows.

## Langkah 3: Jalankan Aplikasi

Kompilasi dan jalankan:

```bash
dotnet run
```

Jika gambar berisi barcode Macro PDF417 yang valid, Anda akan melihat output serupa dengan:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Jika tidak ada yang tercetak, periksa kembali bahwa jalur gambar sudah benar dan barcode memang merupakan varian Macro PDF417. PDF417 biasa (tanpa ekstensi macro) tetap dapat didekode, tetapi properti `Extended` akan kosong.

## Menangani Kasus Pinggir

### Beberapa Barcode dalam Satu Gambar

Kadang satu pemindaian berisi lebih dari satu segmen PDF417 (bayangkan dokumen multi‑halaman yang dienkode di beberapa simbol). Loop `foreach` sudah mengenumerasi *semua* barcode yang terdeteksi, jadi Anda tidak memerlukan logika tambahan—cukup kumpulkan segmen‑segmen tersebut dan susun kembali nanti jika diperlukan.

### Data Ekstended Hilang

Tidak setiap PDF417 membawa informasi macro. Dalam skenario tersebut `result.Extended.Pdf417` akan diinstansiasi tetapi bidang‑bidangnya akan memiliki nilai default (nol, string kosong, atau `false`). Anda dapat melindungi dari hal ini seperti berikut:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Tips Kinerja

- **Pemrosesan batch:** Jika Anda memiliki folder berisi gambar, bungkus pembuatan `BarCodeReader` di dalam loop yang menggunakan kembali instance yang sama dengan `barcodeReader.SetImage(imagePath)`. Ini mengurangi overhead alokasi.
- **Paralelisme:** Untuk beban kerja besar, pertimbangkan `Parallel.ForEach` pada daftar file, tetapi ingat bahwa pembaca Aspose hanya thread‑safe ketika setiap thread menggunakan instance `BarCodeReader` masing‑masing.

## Daftar Sumber Lengkap (Siap Salin‑Tempel)

Berikut seluruh program lagi, siap ditempatkan ke dalam `Program.cs`. Tidak diperlukan file tambahan selain gambar.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Ringkasan: Cara Membaca PDF417 di C# dengan Cepat

- Instal **Aspose.BarCode** melalui NuGet.
- Arahkan `BarCodeReader` ke gambar Anda dengan `DecodeType.MacroPdf417`.
- Loop melalui `ReadBarCodes()` dan ambil bidang dasar serta ekstended.
- Tangani data macro yang hilang dengan elegan dan pertimbangkan penyesuaian kinerja untuk pemindaian massal.

## Langkah Selanjutnya & Topik Terkait

- **Baca barcode dari gambar** menggunakan format lain (QR, DataMatrix) – cukup ganti enum `DecodeType`.
- **Enkode PDF417** dengan `BarCodeGenerator` jika Anda perlu membuat barcode secara programatik.
- Jelajahi **tingkat koreksi kesalahan** dan bagaimana mereka memengaruhi keandalan pemindaian.
- Integrasikan logika ini ke dalam API ASP.NET Core untuk menyediakan pembacaan barcode sebagai layanan web.

Silakan bereksperimen: ubah gambar, mainkan flag `DecodeType`, atau masukkan data macro ke dalam basis data. Pola inti tetap sama, dan kini Anda memiliki **contoh pembaca barcode c#** yang solid di dalam kotak peralatan Anda.

Selamat coding, semoga pemindaian Anda selalu bersih!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara membuat zona tenang barcode untuk Code 16K menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}