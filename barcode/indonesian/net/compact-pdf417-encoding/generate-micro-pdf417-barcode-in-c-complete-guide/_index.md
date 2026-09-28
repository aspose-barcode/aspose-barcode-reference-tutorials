---
category: general
date: 2026-07-18
description: Hasilkan kode batang micro PDF417 dengan Aspose.BarCode untuk .NET –
  panduan langkah demi langkah yang mencakup kolom, baris, dan output PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: id
lastmod: 2026-07-18
og_description: Buat barcode micro pdf417 secara instan dengan Aspose.BarCode untuk
  .NET. Pelajari cara mengontrol kolom, baris, dan menyimpannya sebagai PNG dalam
  hitungan menit.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Buat Barcode Micro PDF417 – Tutorial Lengkap C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Menghasilkan Barcode Micro PDF417 di C# – Panduan Lengkap
url: /id/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan Micro PDF417 Barcode di C# – Panduan Lengkap

Pernah bertanya-tanya bagaimana **menghasilkan micro pdf417 barcode** langsung dari aplikasi C# Anda? Anda tidak sendirian. Baik Anda menandai inventaris, mengkodekan URL pendek, atau membangun solusi pemindaian khusus, menguasai kode 2‑D kecil namun kuat ini dapat menghemat banyak waktu.

Dalam tutorial ini kami akan membahas contoh dunia nyata menggunakan **Aspose.BarCode for .NET**, menunjukkan cara menyesuaikan kolom, baris, dan ukuran modul, lalu menyimpan hasilnya ke file PNG. Pada akhir tutorial Anda akan memiliki aplikasi console yang siap dijalankan dan menghasilkan tiga gambar barcode berbeda—tanpa misteri yang tersisa.

## Apa yang Anda Butuhkan

- .NET 6 atau lebih baru (kode ini juga bekerja pada .NET Framework 4.7+)
- Visual Studio 2022 (atau IDE C# lain yang Anda sukai)
- Paket NuGet **Aspose.BarCode** (`Aspose.BarCode`)
- Folder yang dapat ditulisi di disk untuk menyimpan PNG output

Jika sudah memiliki semua itu, bagus—mari kita mulai.

## Langkah 1: Siapkan Proyek dan Instal Aspose.BarCode

Pertama, buat proyek console baru:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Pro tip:** Jalankan `dotnet restore` setelah menambahkan paket untuk memastikan semua dependensi terpasang.

Sekarang buka `Program.cs`. Kita akan mulai dengan mengimpor namespace yang diperlukan:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Kedua pernyataan `using` ini memberi kita akses ke `BarcodeGenerator`, `EncodeTypes`, dan enum format gambar yang akan kita gunakan nanti.

## Langkah 2: Inisialisasi Generator MicroPdf417

Inti dari operasi ini adalah objek `BarcodeGenerator`. Kita memberi tipe enkoding **MicroPdf417** dan teks yang ingin dienkode—dalam contoh ini kata “ASPOSE”.

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Mengapa `MicroPdf417`? Dibandingkan dengan PDF417 ukuran penuh, versi micro memuat lebih banyak data dalam jejak yang lebih kecil, cocok untuk label dengan ruang terbatas.

## Langkah 3: Sesuaikan Ukuran Modul (X‑Dimension)

Ukuran modul menentukan berapa banyak piksel yang ditempati setiap kotak kecil barcode. Nilai **2 piksel** menghasilkan gambar yang tajam dan dapat dibaca tanpa memperbesar ukuran file.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Catatan:** Jika Anda memerlukan barcode yang lebih besar untuk pemindaian jarak jauh, naikkan angka ini menjadi 3 atau 4.

## Langkah 4: Hasilkan Barcode dengan Konfigurasi Kolom/Baris Berbeda

### 4.1 Dua Kolom, Baris Dihitung Otomatis

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Enam Baris, Kolom Dihitung Otomatis

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Empat Kolom × Delapan Baris (Spesifikasi Penuh)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Setiap pemanggilan `Save` menulis file PNG ke direktori kerja proyek. Anda dapat mengubah path (`"YOUR_DIRECTORY/..."`) menjadi sesuatu seperti `Path.Combine(Environment.CurrentDirectory, "output")` jika ingin menyimpan ke folder khusus.

## Langkah 5: Contoh Kerja Lengkap

Menggabungkan semuanya, berikut program lengkap yang siap disalin‑tempel:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Output yang Diharapkan

Menjalankan program menghasilkan tiga file PNG:

| Nama file | Dimensi perkiraan (px) | Keterangan visual |
|-----------|------------------------|--------------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Barcode sempit, lebih tinggi |
| `MicroPdf417Rows6.png` | 120 × 180 | Barcode lebar, lebih pendek |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Bentuk hampir kotak, tata letak seimbang |

Buka salah satu di penampil gambar—Anda akan melihat barcode **Micro PDF417** yang tajam dan siap dipindai.

## Pertanyaan Umum & Kasus Khusus

- **Bagaimana jika folder output tidak ada?**  
  Panggil `Directory.CreateDirectory(path)` sebelum `Save` pertama untuk menghindari `DirectoryNotFoundException`.

- **Bisakah saya mengubah format gambar?**  
  Tentu. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` sesuai kebutuhan.

- **Apakah ada batas panjang teks?**  
  MicroPdf417 dapat mengkode hingga 1 KB data, tetapi batas praktis tergantung pada baris/kolom yang dipilih. Jika muncul error, tingkatkan baris atau kolom.

- **Bagaimana cara menyisipkan barcode ke dalam PDF?**  
  Gunakan Aspose.Pdf untuk memasukkan PNG yang dihasilkan, atau ubah menjadi `BarCodeImageFormat.Pdf` untuk output PDF langsung.

## Tips Pro untuk Generasi Barcode di C#

1. **Cache generator** ketika Anda membutuhkan banyak barcode dengan pengaturan yang sama—hanya teks yang perlu diubah, menghemat siklus CPU.  
2. **Sesuaikan tingkat koreksi kesalahan** lewat `generator.Parameters.Barcode.Pdf417.ErrorLevel` jika lingkungan pemindaian Anda berisik.  
3. **Uji dengan pemindai nyata** sejak awal. Beberapa perangkat genggam kesulitan dengan micro barcode yang sangat padat; menyesuaikan `XDimension` dapat membuat perbedaan besar.

## Kesimpulan

Sekarang Anda tahu cara **menghasilkan micro pdf417 barcode** menggunakan **Aspose.BarCode for .NET**, mengatur **kolom MicroPdf417** dan **baris MicroPdf417**, serta menyimpan hasilnya sebagai file PNG—semua dari satu aplikasi console C# yang rapi. Bereksperimenlah dengan ukuran modul berbeda, tingkat kesalahan, atau bahkan output berwarna untuk menyesuaikan kebutuhan proyek Anda.

Selanjutnya, Anda dapat menjelajahi **generasi barcode C#** untuk simbol lain seperti QR, Code128, atau DataMatrix, atau menyisipkan gambar langsung ke PDF dengan Aspose.Pdf. Langit adalah batasnya ketika Anda telah menguasai dasar-dasarnya.

Selamat coding, semoga pemindaian Anda selalu bebas error!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Buat gambar barcode DotCode – baris & kolom (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Generate DataMatrix Barcode – Panduan Pro dengan Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}