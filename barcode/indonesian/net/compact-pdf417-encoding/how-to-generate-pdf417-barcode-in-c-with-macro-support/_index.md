---
category: general
date: 2026-10-21
description: Pelajari cara menghasilkan barcode PDF417 dalam C# menggunakan Aspose.BarCode.
  Langkah‑langkah terperinci mencakup pengaturan barcode PDF417, pembuatan barcode
  macro PDF417, dan penyimpanan sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: id
lastmod: 2026-10-21
og_description: Cara menghasilkan barcode PDF417 di C# menggunakan Aspose.BarCode.
  Ikuti tutorial langkah demi langkah ini untuk mengonfigurasi pengaturan barcode
  PDF417, membuat barcode PDF417 makro, dan mengekspor ke PNG.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: Cara membuat kode batang PDF417 di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: Cara menghasilkan barcode PDF417 di C# dengan dukungan makro
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 di C# dengan dukungan makro

Jika Anda perlu menghasilkan barcode PDF417 di C#, panduan ini menunjukkan solusi lengkap yang siap dijalankan. Baik Anda membangun sistem label logistik maupun mengkodekan blok data besar, Anda akan melihat cara mengonfigurasi pengaturan barcode PDF417, membuat barcode Macro PDF417, dan menyimpan hasilnya sebagai gambar PNG.

Membuat barcode PDF417 tidak memerlukan manipulasi bit tingkat rendah. Dengan menggunakan kelas **barcode generator C#** dari Aspose.BarCode Anda dapat fokus pada logika bisnis sementara perpustakaan menangani enkoding, koreksi kesalahan, dan rendering gambar.

## Apa yang Anda perlukan

Sebelum memulai, pastikan Anda memiliki:

- **.NET 6.0** atau yang lebih baru (kode ini juga bekerja dengan .NET Framework 4.6+)
- Paket NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Lingkungan pengembangan seperti Visual Studio 2022 atau Visual Studio Code
- Izin menulis ke folder tempat gambar PNG akan disimpan

Prasyarat ini memastikan contoh dapat dikompilasi dan dijalankan tanpa konfigurasi tambahan.

## Cara menghasilkan barcode PDF417 – ikhtisar langkah demi langkah

Berikut adalah peta jalan singkat prosesnya:

1. **Buat instance `BarcodeGenerator`** menggunakan `EncodeTypes.MacroPdf417`.
2. **Sesuaikan tampilan dasar barcode** (ukuran modul, warna, dll.).
3. **Konfigurasikan pengaturan khusus PDF417**, termasuk bidang makro.
4. **Simpan gambar barcode yang dihasilkan** dengan `BarCodeImageFormat PNG`.

Setiap langkah dijelaskan secara detail, lengkap dengan potongan kode yang dapat Anda salin langsung ke aplikasi console.

## Langkah 1: Siapkan lingkungan pengembangan

Buat proyek console baru dan tambahkan referensi Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Buka `Program.cs` dan tambahkan namespace yang diperlukan:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Impor ini memberi Anda akses ke `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`.

## Langkah 2: Buat generator barcode Macro PDF417

Baris pertama implementasi membuat objek **Macro PDF417 barcode**. Enum `EncodeTypes.MacroPdf417` memberi tahu perpustakaan untuk menggunakan varian makro dari PDF417.

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **Mengapa ini penting:** Menggunakan `EncodeTypes.MacroPdf417` mengaktifkan bidang makro (`FileID`, `SegmentID`, dll.) yang memungkinkan Anda membagi payload besar ke beberapa gambar barcode sambil mempertahankan urutan.

## Langkah 3: Sesuaikan tampilan dasar barcode

Sebelum mengatur parameter khusus PDF417, tetapkan lebar modul (pixel). Nilai `2` memberikan gambar yang jelas dan dapat dipindai tanpa ukuran file yang berlebihan.

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

Anda juga dapat mengubah warna latar depan/latar belakang di sini jika UI Anda memerlukan palet yang berbeda.

## Langkah 4: Konfigurasikan pengaturan khusus PDF417

**Pengaturan barcode PDF417** dapat diakses melalui `generator.Parameters.Barcode.Pdf417`. Bidang makro yang paling penting ditunjukkan di bawah ini:

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### Memahami setiap properti

| Properti | Tujuan | Rentang tipikal |
|----------|--------|-----------------|
| `Columns` | Mengontrol berapa banyak kolom data yang ada di setiap baris. Lebih banyak kolom mengurangi jumlah baris tetapi menambah lebar. | 1 – 30 |
| `MacroPdf417FileID` | Pengidentifikasi 32‑bit yang mengelompokkan semua segmen dari file logis yang sama. Harus sama untuk setiap segmen. | Bilangan bulat positif apa saja |
| `MacroPdf417SegmentID` | Indeks berbasis nol dari segmen saat ini. Naikkan untuk setiap barcode berikutnya. | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | Jumlah total segmen yang membentuk file lengkap. Semua segmen harus dihasilkan. | ≥ 1 |
| `MacroPdf417FileName` | Nama deskriptif opsional (maks 255 karakter). Berguna untuk debugging. | String alfanumerik |

> **Tips profesional:** Jaga `Columns` antara 3 dan 7 untuk kebanyakan printer label. Nilai yang lebih besar dapat melebihi lebar cetak pada perangkat beresolusi rendah.

## Langkah 5: Simpan barcode sebagai gambar PNG

Akhirnya, tulis barcode ke disk menggunakan `BarCodeImageFormat PNG`. PNG mempertahankan kualitas lossless, yang penting untuk pemindaian yang dapat diandalkan.

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Saat program selesai, Anda akan menemukan `MacroPdf417.png` di folder proyek. Membuka file tersebut menampilkan barcode Macro PDF417 yang bersih dan siap dicetak.

### Output yang diharapkan

Gambar yang dihasilkan terlihat serupa dengan contoh di bawah (hanya ilustrasi):

![Contoh barcode Macro PDF417](macro-pdf417-barcode.png "Barcode Macro PDF417 yang dihasilkan oleh kode C#")

*Teks alt gambar adalah “Barcode Macro PDF417 yang dihasilkan dengan kode C#”, memenuhi persyaratan aksesibilitas dan SEO.*

## Kesalahan umum dan pemecahan masalah

| Masalah | Gejala | Solusi |
|---------|--------|--------|
| **EncodeTypes tidak tepat** | Barcode muncul sebagai QR code atau teks biasa. | Pastikan Anda menggunakan `EncodeTypes.MacroPdf417` (bukan `EncodeTypes.Pdf417`). |
| **ID segmen tidak cocok** | Scanner melaporkan “segment missing”. | Tingkatkan `MacroPdf417SegmentID` secara berurutan dan jaga konsistensi `SegmentsCount` di semua file. |
| **Ukuran modul terlalu besar** | Barcode menjadi terlalu lebar untuk label. | Kurangi `XDimension.Pixels` atau turunkan `Columns`. |
| **Kesalahan path file** | `UnauthorizedAccessException` saat menyimpan. | Simpan ke folder yang Anda miliki, misalnya `Environment.CurrentDirectory`. |
| **Paket NuGet belum ada** | Error kompilasi: `BarcodeGenerator` tidak ditemukan. | Jalankan `dotnet add package Aspose.BarCode` sebelum membangun. |

Menangani masalah ini sejak awal menghemat waktu saat mengintegrasikan pembuatan barcode ke alur kerja yang lebih besar.

## Memperluas contoh

Setelah Anda dapat menghasilkan satu barcode Macro PDF417, pertimbangkan langkah selanjutnya berikut:

- **Pembuatan batch**: Loop melalui koleksi potongan data, memperbarui `MacroPdf417SegmentID` setiap iterasi.
- **Format gambar lain**: Ganti `BarCodeImageFormat.Png` dengan `Jpeg` atau `Bmp` jika sistem downstream Anda lebih menyukainya.
- **Menyisipkan ke PDF**: Gunakan Aspose.PDF untuk menempatkan PNG ke dalam laporan PDF untuk distribusi.
- **Verifikasi pemindaian**: Uji barcode yang dihasilkan dengan scanner hardware atau aplikasi mobile yang mendukung Macro PDF417.

Variasi ini mempertahankan **pengaturan barcode PDF417** inti sambil menyesuaikan output dengan kebutuhan proyek Anda.

## Kesimpulan

Anda kini tahu **cara menghasilkan barcode PDF417** di C# menggunakan Aspose.BarCode, mulai dari membuat `BarcodeGenerator` dengan `EncodeTypes.MacroPdf417` hingga mengonfigurasi bidang makro dan menyimpan hasilnya sebagai `BarCodeImageFormat PNG`. Kode lengkap yang dapat dijalankan menunjukkan pendekatan yang direkomendasikan, menjelaskan mengapa setiap pengaturan penting, dan menyoroti kesalahan umum yang mungkin Anda temui.

Jangan ragu bereksperimen dengan jumlah kolom, warna, atau format output, serta mengintegrasikan generator ke dalam aplikasi Anda untuk enkoding data berkapasitas tinggi yang andal.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menghasilkan barcode PDF417 di C# dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Cara membuat barcode Macro PDF417 di C# menggunakan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cara menyimpan barcode dan menghasilkan PDF417 dengan Aspose di C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}