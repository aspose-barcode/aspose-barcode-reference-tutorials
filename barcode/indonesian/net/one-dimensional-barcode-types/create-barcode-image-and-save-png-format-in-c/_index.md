---
category: general
date: 2026-11-27
description: Membuat gambar barcode di C# dan menyimpan gambar dalam format PNG dengan
  Aspose.BarCode – panduan langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: id
lastmod: 2026-11-27
og_description: Buat gambar kode batang di C# dan simpan dalam format PNG menggunakan
  Aspose.BarCode. Ikuti tutorial ini untuk menghasilkan kode batang Macro PDF417 langkah
  demi langkah.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Buat gambar barcode dan simpan dalam format PNG di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Buat gambar barcode dan simpan dalam format PNG di C#
url: /id/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat gambar barcode dan simpan dalam format PNG di C#

Jika Anda perlu **membuat gambar barcode** dalam aplikasi .NET, panduan ini menunjukkan cara menghasilkan barcode Macro PDF417 dan **menyimpan gambar dalam format PNG** menggunakan Aspose.BarCode. Anda akan mendapatkan contoh lengkap yang dapat dijalankan serta penjelasan setiap pengaturan sehingga Anda dapat menyesuaikan kode dengan kebutuhan Anda.

Membuat barcode lebih dari sekadar memanggil satu metode; Anda harus mengonfigurasi ukuran modul, parameter macro, dan format output. Pada akhir tutorial ini Anda akan memahami mengapa setiap properti penting, cara menangani kasus tepi umum, dan cara memverifikasi bahwa file PNG telah ditulis dengan benar.

## Apa yang Anda perlukan

- .NET 6.0 atau yang lebih baru (kode ini juga bekerja dengan .NET Framework 4.6+)
- Aspose.BarCode untuk .NET (tersedia via NuGet: `Install-Package Aspose.BarCode`)
- IDE seperti Visual Studio 2022 atau Visual Studio Code
- Izin menulis ke folder tempat file PNG akan disimpan

## Langkah 1: Inisialisasi generator barcode

Langkah pertama adalah membuat instance `BarcodeGenerator` dengan menentukan simbol `EncodeTypes.MacroPdf417` dan teks yang ingin Anda enkode.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Mengapa ini penting:**  
`EncodeTypes.MacroPdf417` memberi tahu pustaka untuk menggunakan varian macro PDF417, yang mendukung segmentasi file dan metadata tambahan. Konstruktor juga menerima teks yang dapat dibaca manusia yang akan dienkode dalam barcode.

## Langkah 2: Tentukan ukuran modul (X‑dimension)

X‑dimension mengontrol lebar satu modul barcode (elemen hitam/putih terkecil). Nilai `2` piksel bekerja dengan baik untuk PNG yang ditampilkan di layar.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tips praktis:**  
Jika Anda berencana mencetak barcode, tingkatkan nilai piksel (misalnya, `4` atau `5`) untuk menghindari hasil yang buram pada printer beresolusi rendah.

## Langkah 3: Konfigurasikan parameter macro PDF417

Macro PDF417 menambahkan beberapa bidang opsional yang membantu mengidentifikasi file sumber, urutan segmen, dan pemeriksaan integritas. Di bawah ini adalah rangkaian lengkap parameter tipikal; Anda dapat menghilangkan apa saja yang tidak diperlukan.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Mengapa bidang-bidang ini berguna:**  

| Parameter | Tujuan |
|-----------|--------|
| `Columns` | Mengontrol lebar barcode; lebih sedikit kolom menghasilkan barcode yang lebih tinggi. |
| `MacroPdf417FileID` | Pengidentifikasi unik yang mengikat semua segmen bersama. |
| `MacroPdf417SegmentID` | Posisi segmen ini dalam keseluruhan file. |
| `MacroPdf417SegmentsCount` | Jumlah total segmen; diperlukan untuk rekonstruksi. |
| `MacroPdf417FileName` | Nama yang dapat dibaca manusia dan dapat ditampilkan oleh aplikasi pemindai. |
| `MacroPdf417Checksum` | Membantu penerima memverifikasi integritas data (CCITT‑16). |
| `MacroPdf417FileSize` | Petunjuk ukuran opsional untuk file asli. |
| `MacroPdf417TimeStamp` | Stempel waktu pembuatan file asli. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadata untuk routing atau kepemilikan. |
| `MacroPdf417Terminator` | Menunjukkan apakah ini segmen akhir (`Set`) atau segmen menengah (`Unset`). |

**Kasus tepi:** Jika Anda menghasilkan barcode satu‑segmen, setel `MacroPdf417SegmentsCount` ke `1` dan `MacroPdf417Terminator` ke `Unset`. Pustaka secara otomatis akan menghilangkan bidang terkait segmen yang tidak berlaku.

## Langkah 4: Simpan barcode yang dihasilkan sebagai gambar PNG

Akhirnya, panggil `Save` dengan jalur file dan nilai enum `BarCodeImageFormat.Png`. Metode ini menulis gambar ke disk dalam format PNG lossless.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Mengapa PNG?**  
PNG mempertahankan nilai piksel secara tepat, yang penting bagi pemindai barcode yang mengandalkan kontras tajam. Kompresi JPEG dapat memperkenalkan artefak yang merusak pola barcode.

### Memverifikasi output

Setelah program dijalankan, Anda akan melihat file bernama `ExtPDF417Meta.png` di folder eksekusi. Membukanya dengan penampil gambar apa pun akan menampilkan barcode persegi panjang yang padat. Anda dapat memverifikasi kebenarannya dengan memindai gambar menggunakan pembaca barcode seluler yang mendukung PDF417 macro; aplikasi biasanya akan menampilkan metadata yang disematkan (file ID, nomor segmen, dll.).

## Kesalahan umum dan cara menghindarinya

| Gejala | Penyebab kemungkinan | Solusi |
|--------|----------------------|--------|
| Barcode terlihat buram | X‑dimension terlalu rendah untuk DPI yang dipilih | Tingkatkan `XDimension.Pixels` atau render pada DPI yang lebih tinggi (`generator.Parameters.ImageResolution`). |
| Pemindai melaporkan “checksum error” | Nilai `MacroPdf417Checksum` tidak tepat | Biarkan Aspose menghitung checksum secara otomatis dengan menghilangkan properti tersebut, atau pastikan nilainya sesuai dengan algoritma CCITT‑16. |
| File PNG kosong atau tidak dibuat | Jalur output tidak valid atau izin menulis tidak ada | Gunakan `Path.Combine` dengan folder yang diketahui dapat ditulisi (mis., `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Bidang macro diabaikan | `EncodeTypes` diatur ke `Pdf417` biasa bukan `MacroPdf417` | Pastikan `EncodeTypes.MacroPdf417` digunakan di konstruktor. |

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin ke aplikasi konsol. Program ini dikompilasi dengan .NET 6.0 dan menghasilkan file PNG yang dijelaskan di atas.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Output yang diharapkan (console):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Membuka `ExtPDF417Meta.png` menampilkan barcode Macro PDF417 yang jelas dan siap dipindai.

## Langkah selanjutnya

- **Ubah format gambar** – ganti `BarCodeImageFormat.Png` dengan `Jpeg` atau `Bmp` jika Anda memerlukan tipe file yang berbeda. Ingat bahwa JPEG memperkenalkan artefak kompresi, yang dapat memengaruhi keandalan pemindaian.
- **Sesuaikan resolusi** – gunakan

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara membuat gambar barcode dengan Aspose.Barcode di C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Cara membuat gambar barcode PDF417 di C# dengan opsi Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Cara membaca barcode dari gambar menggunakan C# dengan Aspose.BarCode – panduan langkah demi langkah](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}