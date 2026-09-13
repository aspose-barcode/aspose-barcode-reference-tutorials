---
category: general
date: 2026-09-13
description: Pelajari cara membuat gambar barcode PDF417 di C# menggunakan BarcodeGenerator
  dan opsi Macro PDF417. Kode langkah demi langkah, tips, dan contoh lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: id
lastmod: 2026-09-13
og_description: Buat gambar barcode PDF417 di C# dengan BarcodeGenerator. Ikuti tutorial
  terperinci ini untuk mengonfigurasi opsi Macro PDF417 dan menyimpan barcode PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Buat gambar barcode PDF417 di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Cara membuat gambar barcode PDF417 di C# dengan opsi Macro PDF417
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode PDF417 di C# dengan opsi Macro PDF417

Jika Anda perlu **membuat gambar barcode PDF417** di C#, panduan ini menunjukkan secara tepat cara melakukannya menggunakan **kelas BarcodeGenerator**. Baik Anda sedang membangun sistem pelacakan dokumen maupun mengkodekan file berukuran besar, instruksi langkah‑demi‑langkah di bawah ini mencakup semua hal mulai dari menyiapkan opsi Macro PDF417 hingga menyimpan PNG akhir.

Membuat barcode menjadi mudah setelah Anda memahami parameter kunci. Dalam tutorial ini Anda akan belajar cara:

* Menginisialisasi `BarcodeGenerator` untuk **Macro PDF417**.  
* Menyesuaikan ukuran modul barcode (`XDimension`).  
* Mengonfigurasi pengaturan khusus segmen seperti file ID, segment ID, dan checksum.  
* Menyimpan hasil sebagai **format gambar barcode** (PNG) yang dapat ditampilkan di UI apa pun.

Satu‑satunya prasyarat adalah lingkungan pengembangan .NET (Visual Studio 2022 atau lebih baru) dan paket NuGet Aspose.BarCode untuk .NET, yang menyediakan API `BarcodeGenerator` yang digunakan dalam contoh.

---

## Cara membuat gambar barcode PDF417 di C# – ikhtisar

Membuat gambar barcode PDF417 terdiri dari empat langkah logis:

1. **Buat generator** – instantiate `BarcodeGenerator` dengan `EncodeTypes.MacroPdf417` dan data mentah yang ingin Anda enkode.  
2. **Tentukan ukuran modul** – set `XDimension.Pixels` untuk mengontrol lebar fisik tiap elemen barcode.  
3. **Konfigurasikan opsi Macro PDF417** – tentukan kolom, identifier file, nomor segmen, dan checksum opsional.  
4. **Simpan barcode** – tulis gambar yang dihasilkan ke disk menggunakan **format gambar barcode** yang didukung seperti PNG.

Setiap langkah dijelaskan secara detail di bawah, lengkap dengan kode C# yang dapat dijalankan.

---

## Langkah 1: Inisialisasi BarcodeGenerator untuk Macro PDF417

Baris pertama membuat objek `BarcodeGenerator` yang mengetahui bahwa ia harus menghasilkan barcode **Macro PDF417**. Konstruktor mengambil dua argumen: tipe enkoding dan string data mentah.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Mengapa ini penting:**  
`EncodeTypes.MacroPdf417` memberi tahu pustaka untuk memperlakukan barcode sebagai kontainer multi‑segmen, yang penting ketika Anda harus membagi file besar menjadi beberapa simbol. Instance `BarcodeGenerator` bersifat disposable, sehingga blok `using` menjamin semua sumber daya tak terkelola dibebaskan setelah gambar disimpan.

---

## Langkah 2: Atur ukuran modul barcode (XDimension)

`XDimension` mengontrol lebar piksel satu modul barcode (garis hitam atau putih terkecil). Nilai **2 piksel** menghasilkan gambar yang kompak namun tetap dapat dibaca.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tips praktis:**  
Jika printer target Anda memiliki DPI rendah, tingkatkan jumlah piksel (misalnya `3` atau `4`) untuk menghindari smearing. Sebaliknya, untuk tampilan di layar Anda dapat mempertahankan nilai rendah guna mengurangi ukuran file.

---

## Langkah 3: Konfigurasikan opsi khusus Macro PDF417

Macro PDF417 menambahkan metadata yang memungkinkan pemindai merekonstruksi file asli dari beberapa segmen barcode. Opsi yang paling umum adalah:

| Properti | Arti |
|----------|------|
| `Columns` | Jumlah kolom di setiap simbol (mempengaruhi lebar). |
| `MacroPdf417FileID` | Identifier unik untuk seluruh file. |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (dimulai dari 1). |
| `MacroPdf417SegmentsCount` | Total jumlah segmen yang membentuk file. |
| `MacroPdf417FileName` | Nama file asli (opsional, untuk tampilan). |
| `MacroPdf417Checksum` | Checksum 16‑bit opsional untuk verifikasi integritas. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Mengapa pengaturan ini penting:**  
- **Columns** memengaruhi keterbacaan dan dimensi gambar secara keseluruhan.  
- **FileID** harus sama di semua segmen agar decoder mengetahui bahwa mereka termasuk dalam satu file.  
- **SegmentID** dan **SegmentsCount** memungkinkan pemindai mengurutkan potongan dengan benar.  
- **FileName** dan **Checksum** bersifat opsional namun meningkatkan pengalaman pengguna dan integritas data.

**Kasus tepi:** Jika Anda menghasilkan lebih dari 999 segmen, bidang `SegmentID` akan overflow; bagi data menjadi beberapa file sebagai gantinya.

---

## Langkah 4: Simpan barcode yang dihasilkan sebagai gambar PNG

Langkah akhir menulis barcode ke disk. `BarCodeImageFormat.Png` menghasilkan gambar loss‑less yang bekerja pada platform web, desktop, dan mobile.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Format alternatif:**  
Anda dapat mengganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` jika sistem downstream Anda memerlukan format tertentu. Perlu diingat bahwa JPEG menambahkan artefak kompresi yang dapat mengurangi keandalan pemindaian.

**Output yang diharapkan:**  
File `MacroPdf417.png` akan berisi barcode PDF417 multi‑segmen dengan kontras tinggi. Saat dibuka, gambar tersebut akan terlihat serupa dengan ilustrasi di bawah.

![Create PDF417 barcode image example](image.png){: .align-center alt="Contoh gambar barcode PDF417 yang dibuat oleh kode C#"}

---

## Kode sumber lengkap – siap disalin dan dijalankan

Berikut adalah program lengkap yang berdiri sendiri. Ia mencakup direktif `using` yang diperlukan, metode `Main`, dan komentar yang menjelaskan setiap baris yang tidak langsung.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Menjalankan program:**  

1. Buat proyek konsol .NET 6 (atau lebih baru).  
2. Tambahkan paket NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Ganti `Program.cs` yang dihasilkan dengan kode di atas.  
4. Sesuaikan `outputPath` ke folder yang Anda miliki hak tulis.  
5. Build dan jalankan – konsol akan mengonfirmasi lokasi gambar.

---

## Pertanyaan umum & pemecahan masalah

| Pertanyaan | Jawaban |
|------------|---------|
| *Bagaimana jika barcode terlalu lebar untuk label saya?* | Kurangi `Columns` atau tingkatkan `XDimension.Pixels` untuk menyeimbangkan lebar dan keterbacaan. |
| *Apakah saya harus mengatur checksum?* | Checksum bersifat opsional |

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat Barcode PDF417 di C# – Panduan Langkah demi Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Buat Metadata Barcode PDF417 di C# – Panduan Langkah demi Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Hasilkan barcode dengan teks – Panduan Lengkap PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}