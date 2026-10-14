---
category: general
date: 2026-10-09
description: Pelajari cara membuat barcode PDF417 di C# menggunakan Aspose.BarCode
  – hasilkan Macro PDF417 dengan dukungan metadata lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Pelajari cara membuat barcode PDF417 di C# menggunakan Aspose.BarCode
  – hasilkan Macro PDF417 dengan dukungan metadata lengkap, termasuk file ID, segment
  data, timestamp, dan lainnya.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Cara membuat barcode PDF417 di C# dengan Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Cara membuat barcode PDF417 di C# dengan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PDF417 di C# dengan Aspose.BarCode

Jika Anda perlu **membuat barcode PDF417 C#** dengan cepat dan andal, tutorial ini akan memandu Anda melalui proses lengkap menggunakan Aspose.BarCode. Anda akan melihat setiap pengaturan yang diperlukan, mulai dari dimensi dasar hingga seluruh set bidang metadata Macro PDF417, dan Anda akan selesai dengan gambar PNG yang siap diproses lebih lanjut.

## Jawaban cepat
- **Perpustakaan mana yang menghasilkan barcode PDF417?** Aspose.BarCode untuk .NET.  
- **Format apa yang dihasilkan contoh ini?** Gambar PNG tanpa kehilangan kualitas.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk contoh; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET 6.0 atau yang lebih baru.  
- **Bisakah saya menambahkan metadata ke barcode?** Ya – Macro PDF417 mendukung ID file, jumlah segmen, cap waktu, dan lainnya.

## Apa itu barcode PDF417?
Barcode PDF417 adalah simbol linear bertumpuk yang dapat mengkodekan hingga sekitar 1 KB data per simbol dan mendukung metadata makro opsional untuk file multi‑segmen. Ia terdiri dari beberapa baris pola linear bertumpuk, memungkinkan kapasitas data tinggi sambil tetap dapat dibaca oleh pemindai 2‑D standar. Format ini juga mencakup tingkat koreksi kesalahan untuk meningkatkan keandalan, dan fitur makro opsional memungkinkan pemecahan file besar menjadi beberapa barcode dengan metadata yang membantu menyusunnya kembali.

## Mengapa menggunakan Aspose.BarCode untuk PDF417?
Aspose.BarCode mendukung **lebih dari 50 simbol barcode** dan dapat menghasilkan barcode Macro PDF417 dengan hingga **2 000 kolom**, menangani file lebih besar dari **10 MB** tanpa memuat seluruh muatan ke memori. Kemampuan terkuantifikasi ini memastikan skenario perusahaan berkecepatan tinggi berjalan lancar, dan menyediakan opsi kustomisasi yang luas.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- .NET 6.0 (atau yang lebih baru) terpasang  
- Visual Studio 2022 atau IDE kompatibel C# lainnya  
- Lisensi yang valid untuk **Aspose.BarCode untuk .NET** (versi percobaan gratis cukup untuk contoh ini)  

Tambahkan paket NuGet Aspose.BarCode ke proyek Anda:

```bash
dotnet add package Aspose.BarCode
```

## Cara membuat barcode PDF417 di C#?

`BarcodeGenerator` adalah kelas utama untuk membuat gambar barcode.  
`EncodeTypes.MacroPdf417` memilih simbol Macro PDF417 untuk pembuatan barcode.  
`Save` menulis barcode yang dihasilkan ke file gambar.

Muat `BarcodeGenerator` dengan enum `EncodeTypes.MacroPdf417` dan teks target Anda, lalu panggil `Save` – itulah alur pembuatan lengkap dalam tiga baris. Generator menangani Unicode secara otomatis, dan pernyataan `using` menjamin sumber daya tak terkelola dibebaskan setelah gambar disimpan.

### Langkah 1: buat instance generator barcode C#

Kelas `BarcodeGenerator` membuat dan mengonfigurasi gambar barcode.  

Instansiasi `BarcodeGenerator` dengan nilai enum `EncodeTypes.MacroPdf417` dan teks yang ingin Anda enkode. Teks dapat berisi karakter Unicode, yang ditangani perpustakaan secara otomatis.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Mengapa ini penting*: `EncodeTypes.MacroPdf417` memberi tahu mesin untuk menghasilkan simbol Macro PDF417, yang mendukung data tersegmentasi dan metadata tingkat‑file tambahan. Pernyataan `using` menjamin sumber daya tak terkelola dibebaskan setelah gambar disimpan.

### Langkah 2: definisikan tampilan dasar barcode

`XDimension.Pixels` mengatur ukuran setiap modul barcode dalam piksel.

Barcode Macro PDF417 terdiri dari modul persegi. Mengontrol ukuran modul dan jumlah kolom memengaruhi baik keterbacaan maupun ukuran file.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Mengapa ini penting*: `XDimension.Pixels` menentukan kepadatan visual; nilai 2 piksel bekerja baik untuk tampilan layar sambil menjaga gambar tetap kecil. Sesuaikan jumlah kolom agar sesuai dengan batasan tata letak Anda—lebih banyak kolom menghasilkan barcode yang lebih lebar dan lebih pendek.

### Langkah 3: atur metadata khusus Macro PDF417

`MacroPdf417FileID` mengidentifikasi file tempat semua segmen barcode berada.

Macro PDF417 memperluas format PDF417 standar dengan bidang yang memungkinkan rekonstruksi file besar dari beberapa segmen barcode. Setiap bidang bersifat opsional, tetapi mengaturnya menunjukkan kemampuan penuh API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Mengapa ini penting*:  
- `MacroPdf417FileID` mengaitkan semua segmen yang termasuk dalam file logis yang sama.  
- `MacroPdf417SegmentID` dan `MacroPdf417SegmentsCount` memungkinkan decoder mengurutkan fragmen dengan benar.  
- `MacroPdf417Checksum` memberikan pemeriksaan integritas cepat tanpa mendekode seluruh muatan.  
- `MacroPdf417FileSize` dan `MacroPdf417TimeStamp` memungkinkan sistem hilir memverifikasi bahwa file yang direkonstruksi cocok dengan aslinya.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` berguna dalam skenario logistik atau pertukaran dokumen.  
- Menetapkan `MacroPdf417Terminator` ke `Set` menandai barcode ini sebagai segmen akhir, yang menyederhanakan algoritma rekonstruksi.

### Langkah 4: simpan gambar barcode yang dihasilkan

`Save` menulis gambar barcode ke jalur file yang ditentukan.

Akhirnya, tulis barcode ke file PNG. Anda dapat memilih format apa pun yang didukung (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Mengapa ini penting*: PNG mempertahankan data piksel lossless, memastikan pemindai membaca pola modul tepat yang Anda konfigurasikan. Mengubah format dapat memengaruhi kualitas visual dan ukuran file.

#### Output yang diharapkan

Menjalankan program lengkap menghasilkan file bernama **ExtPDF417Meta.png**. Membuka gambar menampilkan barcode Macro PDF417 berbentuk persegi panjang dengan teks “Åspóse.Barcóde©” yang terenkode, dan kepadatan visual cocok dengan dimensi X 2‑piksel yang Anda setel. Memindai gambar dengan pembaca kompatibel PDF417 mengembalikan semua bidang metadata yang didefinisikan pada Langkah 3.

## Contoh kerja penuh

Salin kode di bawah ke proyek konsol baru (`dotnet new console`) dan ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang ada di mesin Anda.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Jalankan program (`dotnet run`). Setelah eksekusi, pastikan file PNG muncul di lokasi yang Anda tentukan. Gunakan aplikasi pembaca barcode apa pun yang mendukung Macro PDF417 untuk mengonfirmasi bahwa metadata telah tertanam dengan benar.

## Variasi umum dan kasus tepi

- **Format gambar berbeda**: Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Tiff` jika sistem hilir Anda lebih menyukai format lain.  
- **Mengubah ukuran modul**: Nilai `XDimension.Pixels` yang lebih besar meningkatkan keandalan pemindaian pada pemindai beresolusi rendah tetapi menambah ukuran gambar.  
- **Beberapa segmen**: Untuk menghasilkan file multi‑segmen, buat serangkaian barcode, tingkatkan `MacroPdf417SegmentID` untuk masing‑masing, dan pertahankan `MacroPdf417FileID` konstan. Hanya segmen terakhir yang harus memiliki `MacroPdf417Terminator` diatur.  
- **Dukungan Unicode**: Generator secara otomatis mengenkode karakter Unicode; pastikan string sumber Anda menggunakan enkoding UTF‑8 jika dibaca dari file eksternal.  
- **Penanganan kesalahan**: Bungkus blok `using` dalam try‑catch untuk menangkap `BarCodeException` bila parameter tidak valid (misalnya, jumlah kolom di luar jangkauan).

## Tips profesional

- **Kinerja**: Gunakan kembali satu instance `BarcodeGenerator` saat membuat banyak barcode dengan pengaturan yang sama; cukup ubah properti `CodeText` di antara penyimpanan.  
- **Perkiraan ukuran file**: Bidang `MacroPdf417FileSize` harus cocok dengan jumlah byte muatan asli; ketidaksesuaian dapat menyebabkan kegagalan validasi di hilir.  
- **Pengujian**: Validasi barcode yang dihasilkan dengan decoder bawaan Aspose (`BarCodeReader`) serta pemindai pihak ketiga untuk memastikan interoperabilitas.

## Kesimpulan

Contoh **Aspose.BarCode** ini menunjukkan cara **membuat barcode PDF417 C#** dengan dukungan metadata Macro lengkap, memberi Anda fondasi yang kuat untuk membangun pipeline pertukaran data berbasis barcode yang andal.

## Apa yang harus Anda pelajari selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara membuat zona tenang barcode untuk Code 16K menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cara Membuat Zona Tenang Barcode untuk ITF-14 Menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**Terakhir Diperbarui:** 2026-10-09  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menghasilkan Gambar Barcode Pdf417 di C# dengan Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Tutorial Generator Barcode Cara Menghasilkan Barcode Pdf417 di](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}