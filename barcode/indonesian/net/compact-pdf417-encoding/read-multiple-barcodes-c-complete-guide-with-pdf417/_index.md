---
category: general
date: 2026-10-04
description: Pelajari cara mendekode PDF417 dan membaca beberapa barcode dalam C#
  menggunakan Aspose.BarCode. Panduan ini menunjukkan cara mendeteksi mode kompak
  dan menangani banyak barcode dalam satu gambar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Pelajari cara mendekode PDF417 dan membaca beberapa barcode dalam
  C#. Panduan langkah demi langkah ini mencakup deteksi mode kompak, penanganan multi‑barcode,
  dan praktik terbaik.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Cara mendekode PDF417 dan membaca beberapa barcode dalam C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Cara mendekode PDF417 dan membaca beberapa barcode dalam C#
url: /id/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mendekode PDF417 dan membaca beberapa barcode dalam C#

## Jawaban Cepat
- **Apakah Aspose.BarCode dapat membaca lebih dari satu barcode sekaligus?** Ya, `ReadBarCodes()` mengembalikan semua simbol yang terdeteksi dalam satu panggilan.  
- **Apa itu mode kompak untuk PDF417?** Itu adalah enkoding berukuran lebih kecil yang menghilangkan baris padding opsional untuk menghemat ruang.  
- **Apakah saya memerlukan lisensi untuk produksi?** Versi percobaan berfungsi langsung, tetapi lisensi berbayar menghapus watermark dan membuka kinerja penuh.  
- **Versi .NET mana yang didukung?** .NET 6+, .NET 5, .NET Core 3.1, dan .NET Framework 4.6+.  
- **Apakah perpustakaan ini thread‑safe?** Tidak, buat instance `BarCodeReader` terpisah per thread.

## Apa itu cara mendekode PDF417?
Frasa “cara mendekode PDF417” mengacu pada mengekstrak data yang dikodekan dalam barcode PDF417 menggunakan perangkat lunak. Aspose.BarCode menyediakan API siap pakai yang secara otomatis menangani koreksi kesalahan, deteksi simbol, dan interpretasi mode kompak, memungkinkan pengembang memperoleh teks asli tanpa harus mengelola pemrosesan gambar tingkat rendah.

## Mengapa menggunakan Aspose.BarCode untuk tugas ini?
Aspose.BarCode mendukung **50+ simbol barcode**, memproses **gambar multi‑ratus‑halaman** tanpa memuat seluruh file ke memori, dan dapat mendekode PDF417 dalam mode ukuran penuh maupun kompak dengan **akurasi 100 %** pada set pengujian standar (seperti yang diverifikasi dalam suite benchmark 2026). Ia juga menawarkan dokumentasi yang luas dan pembaruan reguler, memastikan kompatibilitas dengan rilis .NET terbaru.

## Apa yang Anda perlukan
- **.NET 6.0** SDK atau yang lebih baru (kode berfungsi dengan .NET Framework 4.6+ juga, tetapi .NET 6 adalah pilihan terbaik).  
- **Aspose.BarCode untuk .NET** paket NuGet (`Install-Package Aspose.BarCode`).  
- Gambar contoh yang berisi barcode **PDF417**—sebaiknya yang mencampur simbol kompak dan ukuran penuh. Tutorial menggunakan `CompactPdf417.png`, tetapi PNG/JPEG apa pun dapat digunakan.  
- IDE favorit Anda (Visual Studio, Rider, atau VS Code).  

Itu saja—tanpa DLL tambahan, tanpa dependensi native. Aspose.BarCode adalah kode murni yang dikelola, sehingga Anda dapat menambahkannya ke proyek .NET apa pun.

![Baca beberapa barcode C# output konsol](image.png "Baca beberapa barcode C# output konsol")
[Read multiple barcodes C# console output](image.png "Baca beberapa barcode C# output konsol")

*Image alt text: Baca beberapa barcode C# – tangkapan layar konsol yang menampilkan status mode kompak untuk barcode PDF417.*

## Bagaimana cara membaca beberapa barcode dalam C#?
Muat gambar dengan `BarCodeReader`, panggil `ReadBarCodes()`, dan iterasi koleksi yang dikembalikan. Metode ini secara otomatis menemukan setiap barcode, terlepas dari posisi atau orientasinya, dan mengembalikan array `BarCodeResult[]` yang dapat Anda proses dalam loop `foreach` sederhana. Pendekatan ini menghilangkan kebutuhan pemindaian berulang atau pemilihan wilayah manual.

## Definisi BarCodeReader
Kelas `BarCodeReader` adalah komponen inti Aspose.BarCode yang memindai gambar dan mengekstrak data barcode untuk semua simbol yang didukung.

## Definisi ReadBarCodes()
`ReadBarCodes()` adalah metode `BarCodeReader` yang mengembalikan array objek `BarCodeResult`, masing‑masing mewakili barcode yang terdeteksi dalam gambar sumber.

## Langkah 1 – instal dan referensikan pustaka BarCodeReader C# library
First things first, you need the **BarCodeReader C#** class that powers the decoding. Open your terminal (or Package Manager Console) and run:

```powershell
dotnet add package Aspose.BarCode
```

Or, if you’re inside Visual Studio’s NuGet manager, just search for *Aspose.BarCode* and hit **Install**. This pulls in the latest stable version (as of July 2026 it’s 23.9), which supports PDF417, QR, DataMatrix, and dozens of other symbologies.

Why this matters: the library abstracts away the heavy lifting of image processing, error correction, and symbol recognition. You could write your own scanner, but you’d spend weeks chasing edge‑cases. Aspose gives you a battle‑tested, **C# barcode library** that’s been updated for modern .NET runtimes.

## Langkah 2 – siapkan proyek konsol minimal
Create a fresh console app so we can focus on the barcode logic without any UI noise:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Replace the generated `Program.cs` with the full example below. Feel free to keep the default namespace or rename it—nothing special is required.

## Langkah 3 – tulis implementasi lengkap “read multiple barcodes C#” implementation
Below is a **complete, runnable** code sample. It covers all four steps from the original snippet, adds error handling, and prints useful diagnostics.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Mengapa kode ini berhasil
The `BarCodeReader` is the workhorse from the **BarCodeReader C#** API. It opens the image, applies pre‑processing, and searches for symbols of the type you specify. `ReadBarCodes()` returns an array, not just a single result. That’s the key to **reading multiple barcodes C#**—the method automatically collects every match it finds. The `result.Extended.Pdf417.IsTruncated` flag tells us whether the PDF417 is in *compact* (a.k.a. truncated) mode. This flag only exists for PDF417, so we guard with the null‑conditional operator (`?.`) to avoid exceptions if another symbology sneaks in. The `foreach` loop prints both the decoded text and the compact status, giving you a quick sanity check.

## Langkah 4 – menangani tipe barcode berbeda (opsional)
If your image might contain more than just PDF417, simply change the second argument of `BarCodeReader` to `DecodeType.AllSupported`. The loop stays the same, but you’ll need to guard against `result.Extended` being null for non‑PDF417 symbols:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Langkah 5 – kasus tepi dan tip praktik terbaik
### 1️⃣ Tidak ada barcode terdeteksi  
Jika `ReadBarCodes()` mengembalikan array kosong, penyebab paling umum adalah:

- Jalur file salah atau izin baca tidak ada.  
- Kualitas gambar terlalu rendah (blur, kontras rendah). Pertimbangkan pra‑pemrosesan dengan `reader.ImagePreprocessingOptions` (mis., `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Gambar sangat besar  
Memproses foto 10 MP dapat menghabiskan memori. Anda dapat membatasi area pemindaian:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Keamanan Thread  
`BarCodeReader` mengimplementasikan `IDisposable` dan **tidak** thread‑safe. Buat instance terpisah per thread jika Anda memerlukan pemrosesan paralel.

### 4️⃣ Lisensi  
Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark on the output image. For production, set the license early:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Logging  
When you integrate this into a larger service, replace `Console.WriteLine` with a structured logger (Serilog, NLog). That way you can capture `CodeText`, `CodeType`, and `IsTruncated` as fields for downstream analytics.

## Pertanyaan yang Sering Diajukan
**T: Bisakah saya mendekode PDF417 yang menggunakan mode kompak?**  
**J:** Ya. Properti `IsTruncated` pada hasil PDF417 yang diperluas memberi tahu Anda secara langsung apakah barcode tersebut kompak.

**T: Bagaimana jika gambar berisi kode QR dan PDF417?**  
**J:** Gunakan `DecodeType.AllSupported` saat membuat `BarCodeReader`. Reader akan mengembalikan hasil untuk setiap simbol yang terdeteksi dalam array yang sama.

**T: Apakah saya perlu membuang (dispose) reader secara manual?**  
**J:** Tentu saja. Bungkus `BarCodeReader` dalam blok `using` atau panggil `Dispose()` untuk membebaskan sumber daya native dengan cepat.

**T: Seberapa besar file yang dapat ditangani Aspose.BarCode?**  
**J:** Perpustakaan dapat memproses gambar hingga **200 MP** (sekitar 20 000 × 20 000 piksel) tanpa memuat seluruh bitmap ke memori, berkat mesin pemindaian berlapisnya.

**T: Apakah lisensi terpisah diperlukan untuk setiap penyebaran?**  
**J:** Satu file lisensi dapat digunakan pada beberapa server selama total jumlah instance bersamaan tidak melebihi jumlah seat yang dibeli.

## Artikel Terkait
- [Cara Membuat Barcode PDF417 – Enkoding PDF417 Kompak](/barcode/english/net/compact-pdf417-encoding/)
- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/)

---

**Terakhir Diperbarui:** 2026-10-04  
**Diuji Dengan:** Aspose.BarCode 23.9 for .NET  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}