---
category: general
date: 2026-11-14
description: Pelajari cara membaca barcode dari gambar di C# dengan tutorial pembaca
  barcode lengkap. Termasuk pengaturan, kode lengkap, dan penanganan bidang Macro
  PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: id
lastmod: 2026-11-14
og_description: Baca kode batang dari gambar di C# dengan tutorial pembaca kode batang
  ini. Dapatkan contoh lengkap yang berfungsi dan pelajari cara mengekstrak data Macro
  PDF417.
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: Baca kode batang dari gambar di C# – tutorial lengkap
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: Cara membaca barcode dari gambar menggunakan C# – panduan langkah demi langkah
url: /id/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca barcode dari gambar menggunakan C# – panduan langkah demi langkah

Jika Anda perlu **membaca barcode dari gambar** dalam aplikasi .NET, panduan ini menunjukkan secara tepat caranya. Pada akhir tutorial Anda akan memiliki program lengkap yang dapat dijalankan yang mengekstrak baik data barcode dasar maupun bidang spesifik Macro PDF417.

Dalam **barcode reader tutorial c#** ini kami akan membahas penyiapan proyek, paket NuGet yang diperlukan, dan contoh kode lengkap yang bekerja dengan .NET 8 SDK terbaru. Tidak diperlukan layanan eksternal—semua berjalan secara lokal.

## Apa yang akan Anda pelajari

- Cara menambahkan pustaka Aspose.BarCode (atau serupa) ke proyek C#.
- Cara membuat `BarCodeReader` yang menargetkan file gambar tertentu.
- Cara mengiterasi semua barcode yang terdeteksi dan menampilkan tipe, teks, serta metadata Macro PDF417.
- Tips untuk menangani gambar dengan beberapa barcode atau tipe decode yang berbeda.

### Prasyarat

- .NET 8 SDK (atau .NET 6+ jika Anda lebih suka) terpasang.  
- Familiaritas dasar dengan aplikasi konsol C#.  
- File gambar yang berisi barcode Macro PDF417 (mis., `MacroPdf417.png`).  

---

## Langkah 1: Siapkan proyek konsol baru

Buka terminal dan jalankan:

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

Ini membuat aplikasi konsol minimal bernama **BarcodeReaderDemo**. File proyek (`BarcodeReaderDemo.csproj`) akan digunakan pada langkah berikutnya.

## Langkah 2: Instal pustaka pembaca barcode

Untuk tutorial ini kami menggunakan pustaka **Aspose.BarCode for .NET** karena mendukung Macro PDF417 secara langsung. Instal melalui NuGet:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **Mengapa pustaka ini?** Ia menyediakan satu kelas `BarCodeReader`, mendukung puluhan simbol, dan mengekspos properti `Extended` yang berisi bidang Macro PDF417.

## Langkah 3: Tulis kode pembaca barcode (barcode reader tutorial c#)

Ganti isi `Program.cs` dengan contoh lengkap berikut. Contoh ini mendemonstrasikan **cara membaca barcode dari gambar** dan mencetak informasi umum serta spesifik Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Penjelasan setiap langkah

| Step | Why it matters |
|------|----------------|
| **1️⃣ Tentukan jalur gambar** | Pembaca bekerja dengan jalur file atau aliran. Menggunakan jalur relatif membuat contoh mudah untuk disalin‑tempel. |
| **2️⃣ Buat BarCodeReader** | Menyertakan `DecodeType.MacroPdf417` membatasi pemindaian ke simbol tersebut, yang meningkatkan kecepatan dan memastikan bidang `Extended` terisi. |
| **3️⃣ Iterasi hasil** | Sebuah gambar dapat berisi beberapa barcode; loop `foreach` menjamin kita menangkap semuanya. |
| **4️⃣ Output umum** | `CodeTypeName` dan `CodeText` adalah informasi paling umum yang dibutuhkan pengembang. |
| **5️⃣ Bidang Macro PDF417** | Macro PDF417 menyematkan data tambahan (ID file, ID segmen, jumlah segmen). Mengakses `result.Extended.Pdf417` memberikan nilai tersebut tanpa parsing tambahan. |
| **6️⃣ Bidang tambahan opsional** | Pustaka mengekspos bidang macro lain (mis., `MacroPdf417FileName`). Anda dapat memperluas output sesuai kebutuhan penggunaan Anda. |
| **7️⃣ Jaga konsol tetap terbuka** | Berguna saat menjalankan dari Visual Studio atau `dotnet run` untuk melihat output sebelum jendela tertutup. |

## Langkah 4: Jalankan program dan verifikasi output

Letakkan file `MacroPdf417.png` Anda di folder yang dirujuk oleh `imagePath`. Kemudian jalankan:

```bash
dotnet run
```

Output konsol tipikal terlihat seperti:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

Jika gambar berisi beberapa simbol Macro PDF417, program akan menampilkan setiap set nilai secara berurutan.

## Variasi umum dan kasus tepi

### Membaca simbol lain

Jika Anda perlu **membaca barcode dari gambar** yang bukan Macro PDF417, ganti `DecodeType.MacroPdf417` dengan daftar dipisahkan koma, mis.:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

Properti `Extended` akan `null` untuk simbol yang tidak menyediakan data tambahan, jadi selalu periksa `null` sebelum mengaksesnya.

### Menangani gambar besar

File PNG atau JPEG besar dapat meningkatkan penggunaan memori. Untuk menjaga proses tetap ringan, Anda dapat memperkecil ukuran gambar sebelum memberikannya ke `BarCodeReader`:

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### Bekerja dengan aliran alih-alih jalur file

Ketika gambar berasal dari basis data atau permintaan web, berikan sebuah `Stream`:

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## Tips pro untuk pengalaman pembaca barcode yang mulus

- **Tip pro:** Selalu atur `DecodeType` ke kumpulan simbol paling sempit yang Anda harapkan. Ini mengurangi hasil positif palsu dan mempercepat pemrosesan.  
- **Waspada:** Gambar dengan kontras rendah atau kompresi tinggi dapat menyebabkan pembacaan terlewat. Pralakukan gambar (sesuaikan kecerahan/kontras) jika Anda melihat tingkat deteksi rendah.  
- **Tip:** Kelas `BarCodeReader` mengimplementasikan `IDisposable`; menggunakan blok `using` menjamin sumber daya native dilepaskan dengan cepat.  

---

## Kesimpulan

Anda kini tahu cara **membaca barcode dari gambar** di C# dan mengekstrak baik informasi standar maupun spesifik Macro PDF417. **barcode reader tutorial c#** ini menyediakan solusi lengkap yang dapat langsung dimasukkan ke proyek .NET apa pun.

Dari sini Anda dapat:

- Menjelajahi tipe decode lain (QR, DataMatrix, Code128).  
- Mengintegrasikan pembaca ke dalam API ASP.NET Core untuk memproses unggahan secara langsung.  
- Menyimpan bidang macro yang diekstrak ke dalam basis data untuk agregasi di kemudian hari.

Selamat coding, dan silakan bereksperimen dengan berbagai sumber gambar serta format barcode!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara mendekode barcode PDF417 di C# dan membaca gambar barcode C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [Cara membaca barcode dari gambar c# menggunakan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Baca barcode dari gambar C# – panduan lengkap dengan Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}