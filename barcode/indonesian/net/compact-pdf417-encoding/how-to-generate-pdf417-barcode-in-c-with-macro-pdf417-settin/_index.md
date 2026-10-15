---
category: general
date: 2026-10-15
description: Pelajari cara menghasilkan barcode PDF417 di C# menggunakan parameter
  Macro‑PDF417, mengatur dimensi barcode, dan menyimpannya sebagai PNG. Contoh kode
  lengkap disertakan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: id
lastmod: 2026-10-15
og_description: Cara menghasilkan barcode PDF417 di C# dengan konfigurasi Macro‑PDF417
  lengkap, kontrol dimensi, dan output PNG. Ikuti contoh lengkapnya.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Cara menghasilkan barcode PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Cara menghasilkan barcode PDF417 di C# dengan pengaturan Macro‑PDF417
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan PDF417 barcode di C# dengan pengaturan Macro‑PDF417

Jika Anda perlu **cara menghasilkan PDF417 barcode** untuk alur kerja dokumen, panduan ini menunjukkan langkah‑langkah tepatnya. Anda akan melihat cara mengonfigurasi parameter Macro‑PDF417, mengatur dimensi barcode, dan mengekspor hasilnya sebagai gambar PNG—semua dalam satu program C# yang dapat dijalankan.

Menhasilkan barcode PDF417 tidak memerlukan banyak pustaka atau pemrosesan lanjutan yang rumit. Dengan menggunakan Aspose.Barcode untuk .NET Anda dapat mengontrol setiap aspek barcode, mulai dari lebar modul hingga checksum, dan menghasilkan gambar berkualitas tinggi yang siap dicetak atau dipindai.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 (atau lebih baru) SDK terpasang  
* Visual Studio 2022 atau IDE C# apa pun yang Anda sukai  
* Paket NuGet Aspose.Barcode untuk .NET (`Install-Package Aspose.Barcode`)  

Prasyarat ini memastikan kode dapat dikompilasi tanpa konfigurasi tambahan.

## Langkah 1: Buat generator barcode untuk barcode Macro‑PDF417

Operasi pertama membuat instance `BarcodeGenerator` yang menargetkan format `EncodeTypes.MacroPdf417`. Konstruktor menerima data yang ingin Anda enkode—dalam contoh ini, string `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Membuat generator menyiapkan objek internal `Parameters`, yang akan Anda gunakan untuk menyesuaikan properti **C# PDF417 barcode**.

## Langkah 2: Atur tampilan dasar barcode – atur dimensi barcode

Mengontrol ukuran visual barcode meningkatkan keandalan pemindaian. Properti `XDimension.Pixels` menentukan lebar modul (titik), sedangkan `Pdf417.Columns` menentukan berapa banyak kolom yang akan dimiliki barcode.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Mengatur dimensi ini memastikan barcode cocok dengan ukuran label umum dan memenuhi spesifikasi pemindai.

## Langkah 3: Berikan identifikasi file Macro‑PDF417

Macro‑PDF417 memperluas barcode PDF417 standar dengan metadata tingkat file. Anda harus menetapkan ID file unik, ID segmen, total jumlah segmen, dan nama file yang dapat dibaca manusia.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

**Parameter Macro PDF417** ini memungkinkan sistem hilir untuk merekonstruksi file asli dari beberapa segmen barcode.

## Langkah 4: Tambahkan metadata makro tambahan – sertakan checksum barcode

Selain identifikasi, Macro‑PDF417 dapat menyimpan checksum, ukuran file, timestamp, penerima, pengirim, dan flag terminator. Menyediakan checksum meningkatkan pemeriksaan integritas data selama proses dekode.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Menyertakan **checksum barcode** dan metadata lainnya membuat barcode dapat menjelaskan dirinya sendiri, yang berharga untuk alur kerja pemrosesan dokumen otomatis.

## Langkah 5: Simpan barcode yang dihasilkan sebagai gambar PNG – pilih format gambar barcode

Langkah terakhir menulis barcode ke file. Metode `Save` menerima jalur file dan enum `BarCodeImageFormat`. PNG menyediakan kompresi lossless, mempertahankan tepi tajam untuk pemindaian yang dapat diandalkan.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Setelah dijalankan, file `MacroPdf417.png` berisi barcode PDF417 yang tajam dan siap untuk disisipkan dalam PDF, dicetak pada label, atau ditampilkan di layar.

## Output yang Diharapkan

Membuka `C:/Barcodes/MacroPdf417.png` menampilkan barcode persegi panjang dengan teks yang dienkode “Sample text”. Barcode tersebut mencakup metadata makro yang Anda tetapkan, yang dapat Anda verifikasi dengan pemindai PDF417 apa pun yang mendukung Macro‑PDF417. Dimensi gambar mencerminkan lebar modul (2 px) dan jumlah kolom (5), menghasilkan barcode yang kompak namun dapat dibaca.

## Variasi Umum dan Kasus Tepi

| Situasi | Penyesuaian |
|-----------|------------|
| **Panjang data berbeda** | Ganti `"Sample text"` dengan string UTF‑8 apa pun; generator secara otomatis menyesuaikan ukuran barcode. |
| **Resolusi lebih tinggi** | Tingkatkan `XDimension.Pixels` menjadi 3 atau 4 untuk modul yang lebih besar, berguna untuk printer beresolusi rendah. |
| **Lebih banyak segmen** | Ubah `MacroPdf417SegmentsCount` agar sesuai dengan total bagian barcode yang ingin Anda hasilkan. |
| **Format gambar alternatif** | Gunakan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp` jika sistem hilir Anda lebih menyukai format tersebut. |
| **Koreksi kesalahan khusus** | Modifikasi `generator.Parameters.Barcode.Pdf417.ErrorLevel` (rentang 0‑8) untuk menyeimbangkan kepadatan data dengan toleransi kesalahan. |

**Tips profesional:** Selalu validasi barcode yang dihasilkan dengan pemindai fisik sebelum menggunakannya di produksi. Pemindai mungkin memiliki batas spesifik firmware pada lebar modul atau jumlah kolom.

## Kode sumber lengkap

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Menjalankan program ini membuat `MacroPdf417.png` di folder `C:/Barcodes`. Konsol menampilkan konfirmasi bahwa pembuatan berhasil.

## Kesimpulan

Anda kini mengetahui **cara menghasilkan PDF417 barcode** di C# dengan kontrol Macro‑PDF417 penuh, cara **mengatur dimensi barcode**, cara menyematkan **checksum barcode** dan metadata makro lainnya, serta cara mengekspor hasilnya menggunakan **format gambar barcode** pilihan. Contoh lengkap ini dapat disalin ke proyek .NET apa pun, dimodifikasi untuk payload data yang berbeda, dan diintegrasikan ke dalam alur kerja otomatisasi dokumen yang lebih besar.

### Langkah Selanjutnya

* Jelajahi tingkat koreksi kesalahan **C# PDF417 barcode** untuk meningkatkan keandalan pemindaian.  
* Gabungkan beberapa segmen Macro‑PDF417 untuk mengenkripsi file besar seperti PDF atau gambar.  
* Ganti **format gambar barcode** ke SVG untuk grafik vektor yang dapat diskalakan dalam aplikasi web.  

Silakan bereksperimen dengan parameter-parameter tersebut, dan bagikan hasil Anda di kolom komentar atau forum komunitas. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Hasilkan barcode C# dengan Macro PDF417 – contoh lengkap](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [Cara Menghasilkan PDF417 Barcode – Panduan Pemrograman Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [Cara menghasilkan PDF417 barcode di C# dengan dimensi khusus](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}