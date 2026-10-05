---
category: general
date: 2026-09-10
description: Pelajari cara mendekode barcode dari gambar menggunakan contoh pembaca
  barcode C# yang ringkas yang dapat membaca kode Macro PDF417 dalam hanya beberapa
  baris.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: id
lastmod: 2026-09-10
og_description: Dekode barcode dari gambar menggunakan contoh pembaca barcode C# singkat.
  Ikuti panduan langkah demi langkah untuk membaca data Macro PDF417 secara instan.
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: Mendekode barcode dari gambar dengan contoh pembaca barcode C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Mendekode barcode dari gambar dengan contoh pembaca barcode C#
url: /id/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mendekode barcode dari gambar dengan contoh pembaca barcode C#

Jika Anda perlu **decode barcode from image**, panduan ini menunjukkan secara tepat cara melakukannya di C#. Menggunakan contoh **C# barcode reader example** yang ringkas, Anda akan membaca data Macro PDF417 hanya dengan beberapa baris kode.

Anda akan melihat program lengkap yang dapat dijalankan, memahami mengapa setiap bagian penting, dan mempelajari tip yang mencegah jebakan umum. Tidak diperlukan dokumentasi eksternal—semua yang Anda butuhkan ada di sini.

## Apa yang akan Anda pelajari

- Siapkan paket NuGet yang diperlukan untuk dekode barcode.  
- Tuliskan **C# barcode reader example** yang membuka file gambar dan mengekstrak setiap barcode.  
- Akses bidang Macro PDF417 yang diperluas seperti file ID.  
- Verifikasi output dan sesuaikan kode untuk tipe barcode lain.

### Prasyarat

- .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Core 3.1 dan .NET Framework 4.7+).  
- Pemahaman dasar tentang aplikasi konsol C#.  
- File gambar yang berisi barcode Macro PDF417 (misalnya `MacroPdf417.png`).  

## Langkah 1: Instal perpustakaan barcode

Contoh ini menggunakan **Aspose.BarCode for .NET**, sebuah perpustakaan yang banyak digunakan yang mendukung dekode Macro PDF417.

```bash
dotnet add package Aspose.BarCode
```

> **Mengapa perpustakaan ini?**  
> Ia menyediakan satu kelas `BarCodeReader` yang menangani banyak format, menawarkan akurasi tinggi, dan mengembalikan informasi tambahan untuk kode Macro PDF417—semua tanpa konfigurasi tambahan.

## Langkah 2: Buat contoh pembaca barcode C#

Buat proyek konsol baru dan ganti `Program.cs` yang dihasilkan dengan kode di bawah ini. Contoh ini mengikuti tiga tindakan jelas:

1. **Initialize** sebuah `BarCodeReader` untuk gambar target.  
2. **Iterate** atas setiap barcode yang terdeteksi.  
3. **Print** data standar dan Macro PDF417 yang diperluas.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### Penjelasan setiap bagian

- **`BarCodeReader` constructor** – Argumen pertama adalah path gambar; argumen kedua memberi tahu perpustakaan untuk mencari secara khusus kode Macro PDF417. Dekode terfokus ini meningkatkan kinerja dibandingkan memindai setiap format yang mungkin.  
- **`ReadBarCodes()`** – Mengembalikan enumerable dari semua barcode yang terdeteksi dalam gambar, memungkinkan Anda menangani beberapa kode dalam satu file.  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – Macro PDF417 menyimpan metadata tambahan (file ID, jumlah segmen, dll.). Contoh ini memeriksa null untuk menghindari `NullReferenceException` ketika gambar berisi barcode non‑Macro.  

## Langkah 3: Jalankan program dan verifikasi output

Bangun dan jalankan aplikasi konsol:

```bash
dotnet run
```

Anda akan melihat output serupa dengan:

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

Jika gambar tidak berisi barcode Macro PDF417, program tetap akan menampilkan format lain yang terdeteksi, namun bidang tambahan akan dihilangkan.

## Tips pro: Dekode tipe barcode lain tanpa mengubah banyak kode

Untuk **decode barcode from image** dengan format berbeda, ubah nilai enum `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

Anda juga dapat memberikan `DecodeType.AllSupportedTypes` agar perpustakaan mendeteksi semua barcode yang dikenalnya.

## Kesalahan umum dan cara menghindarinya

| Gejala | Penyebab | Solusi |
|---------|----------|--------|
| Tidak ada output sama sekali | Path gambar salah atau format file tidak didukung | Verifikasi path, pastikan file adalah gambar yang didukung (PNG, JPEG, BMP) |
| `result.Extended` is null for Macro PDF417 | Barcode bukan varian Macro PDF417 | Pastikan gambar sumber memang berisi kode Macro PDF417 |
| Exception `System.IO.FileNotFoundException` | Paket NuGet tidak ada saat runtime | Jalankan `dotnet restore` dan pastikan `Aspose.BarCode.dll` disalin ke folder output |

## Daftar sumber lengkap untuk salin‑tempel cepat

Berikut adalah seluruh program, siap disalin ke `Program.cs`. Tidak diperlukan file tambahan.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## Langkah selanjutnya

- **Explore other extended fields** seperti `MacroPdf417SegmentID` atau `MacroPdf417FileSize` untuk membangun alur kerja rekonstruksi dokumen penuh.  
- **Integrate the reader into a web API** sehingga klien dapat mengunggah gambar dan menerima data terdekripsi secara instan.  
- **Benchmark performance** dengan mendekode batch besar gambar; `BarCodeReader` mendukung pemrosesan asynchronous pada versi Aspose yang lebih baru.

---

Dengan mengikuti **C# barcode reader example** ini, Anda kini memiliki cara yang andal untuk **decode barcode from image** dan mengekstrak informasi Macro PDF417 yang kaya. Bereksperimenlah dengan nilai `DecodeType` yang berbeda, gabungkan logika ini dengan file‑watcher, atau sematkan dalam backend mobile—kapabilitas pemrosesan barcode Anda siap untuk skala.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membaca PDF417 di C# – Contoh Pembaca Barcode Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Hasilkan barcode dengan teks – Panduan Macro PDF417 Lengkap](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Cara Membuat Barcode PDF417 dengan Aspose – Panduan Langkah‑per‑Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}