---
category: general
date: 2026-09-19
description: Buat barcode PDF417 di C# dan pelajari cara menghasilkan gambar barcode,
  mengatur dimensi barcode, serta menyimpannya sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: id
lastmod: 2026-09-19
og_description: Buat barcode PDF417 di C# dan temukan cara menghasilkan gambar barcode,
  mengatur dimensi barcode, serta menyimpannya sebagai file PNG.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: Buat kode batang PDF417 dan ekspor PNG di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: Cara membuat barcode PDF417 dan mengekspor PNG di C#
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PDF417 dan mengekspor PNG di C#

Jika Anda perlu **membuat barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan cara menghasilkan gambar barcode, menyesuaikan dimensinya, dan menyimpannya sebagai file PNG. Anda akan melihat contoh lengkap yang dapat dijalankan yang menggunakan pustaka Aspose.BarCode, sehingga Anda dapat menyalin kode langsung ke proyek Anda.

Men‑generate gambar barcode merupakan kebutuhan umum untuk sistem tiket, pelacakan inventaris, dan boarding pass mobile. Pada akhir tutorial ini Anda akan memahami **cara menghasilkan gambar barcode**, **cara mengatur dimensi barcode**, dan **cara membuat file PNG barcode** yang memenuhi standar kualitas visual Anda.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+).
* Lingkungan pengembangan seperti Visual Studio 2022 atau VS Code.
* Lisensi yang valid untuk pustaka **Aspose.BarCode for .NET** (versi percobaan gratis dapat digunakan untuk contoh ini).
* Familiaritas dasar dengan sintaks C#.

Instal paket NuGet dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Siapkan proyek dan impor namespace

Buat aplikasi konsol baru atau tambahkan kode ke proyek yang sudah ada. Impor namespace yang diperlukan di bagian atas file:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Namespace ini memberi Anda akses ke kelas `BarcodeGenerator` dan enumerasi `EncodeTypes`.

## Langkah 2: Cara membuat barcode PDF417 – konfigurasi generator dasar

Operasi pertama adalah membuat instance `BarcodeGenerator` dengan tipe enkode `Pdf417` dan teks yang ingin Anda enkode. Objek ini mewakili barcode yang akan Anda render nanti.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Mengapa ini penting*: `EncodeTypes.Pdf417` memberi tahu pustaka untuk menggunakan simbol PDF417, yang merupakan barcode linear bertumpuk yang dapat menyimpan sejumlah besar data. Argumen kedua (“Sample”) adalah payload yang akan muncul saat barcode dipindai.

## Langkah 3: Cara mengatur dimensi barcode – penyetelan halus kepadatan dan tata letak

Barcode PDF417 terdiri dari baris dan kolom modul. Menyesuaikan X‑dimension (lebar modul) dan jumlah baris/kolom memungkinkan Anda mengontrol kepadatan visual dan ukuran keseluruhan gambar.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*Mengapa ini penting*:  
* **X‑dimension** menentukan seberapa lebar setiap kotak kecil (modul). Nilai yang lebih kecil menghasilkan barcode yang lebih kompak tetapi mungkin lebih sulit dipindai oleh scanner beresolusi rendah.  
* **Columns** dan **Rows** memengaruhi kapasitas data dan bentuk fisik. Menambah kolom membuat barcode lebih lebar; menambah baris membuatnya lebih tinggi. Anda dapat bereksperimen dengan nilai hingga batas yang ditunjukkan dalam komentar.

**Tips Pro**: Jika barcode terlihat terlalu padat pada layar ber‑DPI tinggi, tingkatkan `XDimension.Pixels` menjadi 3 atau 4. Sebaliknya, untuk label kecil, Anda dapat mengatur menjadi 1 piksel dan mengurangi jumlah kolom.

## Langkah 4: Cara menghasilkan gambar barcode – merender ke bitmap dalam memori

Setelah mengkonfigurasi generator, Anda dapat merender barcode ke objek gambar. Langkah ini opsional jika Anda hanya perlu menyimpan file secara langsung, tetapi mengekspose bitmap memungkinkan Anda melakukan pemrosesan lebih lanjut (mis., menambahkan logo atau menggambar border).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` mengembalikan `System.Drawing.Image` yang dapat Anda manipulasi dengan GDI+ jika diinginkan.

## Langkah 5: Cara membuat PNG barcode – menyimpan file gambar akhir

Terakhir, tulis gambar ke disk dalam format PNG. PNG mempertahankan kualitas lossless, yang ideal untuk aplikasi pemindaian.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Mengapa ini penting*: Metode `Save` menangani enkoding dan I/O file untuk Anda. Menggunakan `BarCodeImageFormat.Png` memastikan output berupa gambar portable lossless yang berfungsi di semua browser dan perangkat seluler.

### Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda tempel ke `Program.cs` dan jalankan. Ganti `YOUR_DIRECTORY` dengan folder yang ada di mesin Anda.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

Menjalankan program menghasilkan file PNG yang terlihat seperti ini:

![Contoh barcode PDF417 yang dihasilkan](https://example.com/placeholder-image.png "Barcode PDF417 yang dihasilkan dengan dimensi khusus disimpan sebagai PNG")

*Teks alternatif*: **Contoh barcode PDF417 yang dihasilkan dengan C# menampilkan dimensi khusus yang disimpan sebagai PNG** – ini memenuhi persyaratan **membuat barcode PDF417** untuk aksesibilitas gambar.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian yang disarankan |
|-----------|------------------------|
| **Label sangat kecil** (mis., 1 cm × 2 cm) | Atur `XDimension.Pixels = 1` dan kurangi `Columns` menjadi 2‑3. Verifikasi keterbacaan scanner. |
| **Cetakan resolusi tinggi** (300 dpi atau lebih) | Tingkatkan `XDimension.Pixels` menjadi 3‑4 dan secara opsional naikkan `Rows` untuk kapasitas data lebih besar. |
| **Butuh format gambar lain** (JPEG, BMP) | Ubah `BarCodeImageFormat.Png` menjadi `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp`. |
| **Menyisipkan dalam PDF** | Gunakan `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` alih-alih PNG. |
| **Data dinamis** (input pengguna) | Ganti string statis `"Sample"` dengan variabel, mis., `userInput`. Pastikan panjang teks tidak melebihi batas PDF417 (≈ 1 800 karakter). |

## Daftar periksa pemecahan masalah

* **Gambar kosong** – Pastikan direktori output ada dan aplikasi memiliki izin menulis.  
* **Barcode tidak dapat dipindai** – Tingkatkan `XDimension.Pixels` atau tambahkan lebih banyak kolom/baris; latar belakang dengan kontras rendah juga dapat menyebabkan kegagalan.  
* **Ukuran tidak terduga** – Periksa kembali nilai `Columns` dan `Rows`; pustaka menghormati batas maksimum yang ditunjukkan dalam komentar.  

## Langkah selanjutnya

Setelah Anda dapat **membuat barcode PDF417**, pertimbangkan untuk menjelajahi topik terkait berikut:

* **Cara menghasilkan gambar barcode** dalam format lain seperti SVG untuk grafik web‑skalabel.  
* **Cara mengatur dimensi barcode** untuk kode QR dan simbol DataMatrix.  
* **Cara membuat PNG barcode** dengan warna khusus atau logo tersemat menggunakan `System.Drawing`.  

Ekstensi ini memungkinkan Anda membangun layanan generasi barcode lengkap yang dapat melayani aplikasi seluler, portal web, dan utilitas desktop secara bersamaan.

---

*Anda telah belajar cara membuat barcode PDF417, menyesuaikan dimensinya, merender gambar barcode, dan menyimpannya sebagai file PNG menggunakan C#. Terapkan pola yang ditunjukkan di sini ke jenis barcode lain dan format gambar untuk memperluas kemampuan otomatisasi Anda.*

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Gambar Barcode PDF417 di C# dengan Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cara Membuat Barcode PDF417 dengan Aspose – Panduan Lengkap Langkah‑per‑Langkah](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Cara Menyimpan Barcode di C# – Menghasilkan Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}