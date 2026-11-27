---
category: general
date: 2026-11-27
description: cara membaca barcode pdf417 di C# dari gambar menggunakan Aspose.BarCode
  – panduan langkah demi langkah dengan contoh kode lengkap dan tips pemecahan masalah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- C# barcode decoding
- BarCodeReader class
- DecodeType.MacroPdf417
- BarCodeResult properties
language: id
lastmod: 2026-11-27
og_description: cara membaca kode batang PDF417 di C# dengan cepat. Pelajari cara
  mendekode kode batang PDF417 dari gambar dengan Aspose.BarCode, kode lengkap, dan
  praktik terbaik.
og_image_alt: Console output showing how to read PDF417 barcode in C#
og_title: Cara membaca kode batang PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  headline: How to read PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  name: How to read PDF417 barcode in C# – complete programming guide
  steps:
  - name: Create a new console project
    text: 'Open a terminal (or PowerShell) and run:'
  - name: Install the Aspose.BarCode NuGet package
    text: 'Aspose.BarCode provides the `BarCodeReader` class used in the example.
      Install it with:'
  - name: Add the code shown above
    text: Replace the content of `Program.cs` with the full snippet from the previous
      section. The code demonstrates **C# barcode decoding** and shows how to access
      **BarCodeResult properties** such as `CodeTypeName`, `CodeText`, and the macro‑specific
      `MacroPdf417FileID`.
  - name: Run the application
    text: '```bash dotnet run ```'
  - name: Handle multiple barcodes and error cases
    text: 'Real‑world images may hold more than one barcode or none at all. Wrap the
      reading logic in a `try`/`catch` block to surface parsing errors, and check
      `reader.HasBarcodes` before iterating:'
  - name: Optional – Decode other barcode types from the same image
    text: 'If you later need to **read barcode from image c#** for other symbologies,
      simply change the `DecodeType` argument:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membaca kode batang PDF417 di C# – panduan pemrograman lengkap
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca PDF417 barcode di C# – panduan pemrograman lengkap

Jika Anda perlu **cara membaca pdf417 barcode** dari sebuah gambar, panduan ini menunjukkan langkah‑langkah tepatnya. Menggunakan Aspose.BarCode untuk .NET Anda dapat mendekode PDF417 barcode dalam satu pemanggilan metode, dan panduan ini menuntun Anda melalui setiap baris kode yang diperlukan.

Membaca barcode dari sebuah gambar adalah tugas umum saat membangun pemindai inventaris, sistem validasi tiket, atau pipeline pemrosesan dokumen. Dalam tutorial ini Anda akan belajar cara menyiapkan lingkungan, menginstal paket yang diperlukan, dan menulis program C# yang kuat untuk membaca PDF417 barcode dan mengekstrak bidang data ekstendednya. Tidak ada layanan eksternal yang diperlukan; semuanya berjalan secara lokal.

> **Prasyarat**  
> • .NET 6.0 SDK atau yang lebih baru terpasang  
> • Pengetahuan dasar tentang C# dan aplikasi konsol  
> • Akses ke file gambar yang berisi PDF417 (atau Macro PDF417) barcode  

Kami juga akan membahas alternatif **read barcode from image c#**, menjelaskan properti paling berguna dari objek `BarCodeResult`, dan memberi Anda tip untuk menangani beberapa barcode dalam satu gambar.

---

## Cara membaca PDF417 barcode dari gambar di C#

Langkah utama pertama adalah membuat `BarCodeReader` yang menunjuk ke file gambar dan memberi tahu perpustakaan jenis barcode apa yang harus dicari. Dengan menentukan `DecodeType.MacroPdf417` Anda membatasi pemindaian pada varian PDF417, yang meningkatkan kecepatan dan akurasi.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains the PDF417 barcode
            string imagePath = @"C:\Barcodes\Pdf417Sample.png";

            // Initialize the reader for Macro PDF417 barcodes
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific extended information
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID : {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    // Show confidence and symbology details
                    Console.WriteLine($"Code Confidence : {result.CodeTextConfidence}");
                    Console.WriteLine($"Is Mirror Image : {result.IsMirrored}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

**Mengapa ini berhasil** – Konstruktor `BarCodeReader` menerima jalur gambar dan sebuah `DecodeType`. `MacroPdf417` memberi tahu mesin untuk mencari keluarga PDF417, termasuk ekstensi macro yang membawa metadata tambahan seperti file ID. Metode `ReadBarCodes()` mengembalikan enumerable berisi objek `BarCodeResult`, masing‑masing mewakili barcode yang terdeteksi.

### Langkah 1: Buat proyek konsol baru

Buka terminal (atau PowerShell) dan jalankan:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Membuat proyek baru yang bersih mengisolasi demo dan memastikan file `csproj` hanya berisi dependensi yang Anda tambahkan selanjutnya.

### Langkah 2: Instal paket NuGet Aspose.BarCode

Aspose.BarCode menyediakan kelas `BarCodeReader` yang digunakan dalam contoh. Instal dengan:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

Paket ini mencakup dukungan untuk semua simbolologi 1D dan 2D, termasuk PDF417 dan varian macro‑nya.

### Langkah 3: Tambahkan kode yang ditampilkan di atas

Ganti isi `Program.cs` dengan cuplikan lengkap dari bagian sebelumnya. Kode ini mendemonstrasikan **C# barcode decoding** dan menunjukkan cara mengakses **BarCodeResult properties** seperti `CodeTypeName`, `CodeText`, dan `MacroPdf417FileID` yang spesifik untuk macro.

### Langkah 4: Jalankan aplikasi

```bash
dotnet run
```

Jika gambar berisi PDF417 barcode yang dapat dibaca, konsol akan menampilkan sesuatu yang mirip dengan:

```
Code Type : PDF417
Code Text : https://example.com/invoice/12345
Macro PDF417 File ID : 7
Code Confidence : 98.7
Is Mirror Image : False
----------------------------------------
```

Jika gambar tidak mengandung PDF417 barcode, loop akan selesai tanpa mencetak apa‑apa.

### Langkah 5: Tangani beberapa barcode dan kasus error

Gambar dunia nyata mungkin berisi lebih dari satu barcode atau tidak ada sama sekali. Bungkus logika pembacaan dalam blok `try`/`catch` untuk menampilkan error parsing, dan periksa `reader.HasBarcodes` sebelum iterasi:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    if (!reader.HasBarcodes)
    {
        Console.WriteLine("No PDF417 barcodes detected.");
        return;
    }

    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // existing processing code...
    }
}
```

**Pro tip:** Sesuaikan properti `Resolution` pada `BarCodeReader` (misalnya, `reader.Resolution = 300;`) saat menangani pemindaian beresolusi rendah. Resolusi yang lebih tinggi meningkatkan deteksi tetapi dapat meningkatkan penggunaan CPU.

### Langkah 6: Opsional – Dekode tipe barcode lain dari gambar yang sama

Jika nanti Anda perlu **read barcode from image c#** untuk simbolologi lain, cukup ubah argumen `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupportedTypes))
{
    // This will detect QR, Code128, DataMatrix, etc.
}
```

Kelas `BarCodeResult` yang sama bekerja untuk setiap tipe, sehingga Anda dapat menggunakan kembali loop pemrosesan tanpa modifikasi.

---

## Memahami kelas kunci

| Kelas | Tujuan | Anggota paling berguna |
|-------|--------|------------------------|
| `BarCodeReader` | Membuka gambar dan memindai barcode | `ReadBarCodes()`, `HasBarcodes`, `Resolution` |
| `BarCodeResult` | Menyimpan informasi tentang satu barcode yang terdeteksi | `CodeTypeName`, `CodeText`, `CodeTextConfidence`, `Extended` |
| `Extended.Pdf417` | Menyediakan data khusus macro untuk PDF417 | `MacroPdf417FileID`, `MacroPdf417SegmentCount`, `MacroPdf417SegmentIndex` |

Mengetahui anggota‑anggota ini memungkinkan Anda mengekstrak tidak hanya teks yang dapat dibaca manusia tetapi juga metadata terstruktur yang disematkan oleh Macro PDF417, yang sering diperlukan untuk pemrosesan batch dokumen multi‑halaman.

---

## Kesulitan umum dan cara menghindarinya

* **`DecodeType` yang salah** – Menggunakan `DecodeType.Pdf417` alih‑alih `MacroPdf417` akan melewatkan ekstensi macro. Pilih tipe yang tepat sesuai barcode Anda.  
* **Format gambar tidak didukung** – Aspose.BarCode membaca PNG, JPEG, BMP, TIFF, dan GIF. Jika Anda memiliki gambar RAW, konversi terlebih dahulu.  
* **Kontras gambar rendah** – Pra‑proses gambar (tingkatkan kontras atau binarisasi) sebelum memberi ke `BarCodeReader`. Perpustakaan juga menyediakan `reader.ImageProcessingOptions`.  
* **File besar** – Untuk pemindaian beresolusi sangat tinggi, atur `reader.MaxBarcodesPerPage` untuk membatasi konsumsi memori.

---

## Kesimpulan

Anda kini tahu **cara membaca pdf417 barcode** di C# menggunakan Aspose.BarCode, mulai dari penyiapan proyek hingga penanganan bidang spesifik macro. Contoh lengkap yang dapat dijalankan mendemonstrasikan **C# barcode decoding**, menunjukkan cara mengakses **BarCodeResult properties**, dan memberi tip praktis untuk pemindaian yang andal.  

Selanjutnya, jelajahi topik terkait seperti **read barcode from image c#** untuk QR code, integrasikan pembacaan barcode ke dalam API ASP.NET Core, atau bereksperimen dengan pemrosesan batch banyak gambar. Kelas `BarCodeReader` yang sama bekerja pada semua simbolologi yang didukung, sehingga Anda dapat memperluas solusi ini ke barcode apa pun yang ditemui aplikasi Anda.

Selamat coding, dan silakan sesuaikan contoh ini agar cocok dengan alur kerja Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membaca barcode macro PDF417 di C# dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/)
- [Cara membaca PDF417 barcode di C# – panduan lengkap pembaca barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/)
- [Cara Membuat PDF417 Barcode dengan Aspose – Panduan Langkah‑per‑Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}