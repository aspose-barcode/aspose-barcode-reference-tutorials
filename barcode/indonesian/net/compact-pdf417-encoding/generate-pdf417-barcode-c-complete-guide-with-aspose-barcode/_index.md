---
category: general
date: 2026-08-03
description: Hasilkan kode batang PDF417 C# menggunakan Aspose.BarCode. Pelajari langkah
  demi langkah cara menambahkan metadata Macro PDF417 dan menyimpannya sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: id
lastmod: 2026-08-03
og_description: Buat kode batang PDF417 dengan C# menggunakan Aspose.BarCode. Tutorial
  ini menunjukkan cara menyematkan metadata Macro PDF417 dan mengekspor hasilnya sebagai
  gambar PNG.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: Menghasilkan barcode PDF417 C# – tutorial Aspose.BarCode langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Menghasilkan barcode PDF417 C# – panduan lengkap dengan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan Barcode PDF417 C# – panduan lengkap

Jika Anda perlu **menghasilkan barcode PDF417 C#** untuk sistem logistik atau manajemen dokumen, tutorial ini menunjukkan secara tepat cara melakukannya dengan Aspose.BarCode. Anda akan melihat cara mengonfigurasi barcode, menyematkan metadata Macro PDF417, dan menyimpan hasilnya sebagai gambar PNG hanya dalam beberapa baris kode.

Membuat barcode PDF417 di C# sering berarti menangani informasi tambahan seperti pengidentifikasi file, nomor segmen, atau cap waktu. Panduan ini mencakup detail tersebut, sehingga Anda tidak perlu mencari melalui dokumentasi yang tersebar. Pada akhir artikel Anda akan memiliki program siap‑jalan yang menghasilkan gambar barcode Macro PDF417 yang sesuai standar.

## Apa yang Anda butuhkan

- .NET 6.0 atau lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
- Aspose.BarCode untuk .NET (v23.9 atau lebih baru) – instal melalui NuGet `Install-Package Aspose.BarCode`
- Lingkungan pengembangan seperti Visual Studio 2022 atau Visual Studio Code
- Pemahaman dasar tentang sintaks C#

> **Tips pro:** Gunakan versi Aspose.BarCode terbaru untuk mendapatkan perbaikan bug dan dukungan untuk spesifikasi PDF417 terbaru.

## Cara menghasilkan barcode PDF417 C# dengan Aspose.BarCode

Proses ini terdiri dari empat langkah logis. Setiap langkah dibungkus dalam blok kode yang jelas sehingga Anda dapat menyalin, menempel, dan menjalankannya segera.

### Langkah 1: Buat generator barcode Macro PDF417

Pertama, buat instance `BarcodeGenerator` dengan enum `EncodeTypes.MacroPdf417`. Konstruktor juga menerima teks yang ingin Anda enkode – dalam contoh ini kami menggunakan string yang berisi karakter Unicode untuk mendemonstrasikan dukungan lebar penuh.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Mengapa ini penting*: Tipe `MacroPdf417` memberi tahu Aspose.BarCode untuk memperlakukan simbol sebagai barcode makro, yang dapat membawa metadata tingkat file tambahan. Tanpa flag ini, bidang ekstra yang Anda atur nanti akan diabaikan.

### Langkah 2: Sesuaikan tampilan dasar barcode

Selanjutnya, tentukan ukuran visual barcode. `XDimension.Pixels` mengontrol lebar satu modul (kotak hitam/putih terkecil), sementara `Pdf417.Columns` memengaruhi bentuk keseluruhan dengan mengatur jumlah kolom.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Mengapa ini penting*: `XDimension` yang lebih kecil menghasilkan gambar beresolusi lebih tinggi, yang berguna ketika barcode harus dipindai dari layar. Mengubah jumlah kolom dapat membantu menyesuaikan barcode ke ruang terbatas tanpa mengorbankan kapasitas data.

### Langkah 3: Isi metadata Macro PDF417

Macro PDF417 memungkinkan Anda menyematkan informasi tingkat file yang banyak sistem back‑office andalkan (misalnya, ID file, ID segmen, cap waktu). Properti berikut menggambarkan bidang paling umum.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Mengapa ini penting*: Setiap bidang langsung memetakan ke segmen spesifikasi barcode makro. Misalnya, `MacroPdf417FileID` secara unik mengidentifikasi file logis, sementara `MacroPdf417SegmentsCount` memberi tahu pemindai berapa banyak bagian yang diharapkan. Menyediakan metadata yang akurat memastikan sistem hilir dapat merekonstruksi dokumen asli tanpa kesalahan.

### Langkah 4: Simpan gambar barcode sebagai PNG

Akhirnya, panggil `Save` untuk menulis barcode ke disk. PNG bersifat lossless, menjadikannya ideal untuk pemindaian berkualitas tinggi.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Mengapa ini penting*: Enum `BarCodeImageFormat.Png` menjamin bahwa file output berisi data piksel tepat seperti yang Anda konfigurasikan. Jika Anda memerlukan format vektor untuk penskalaan, ganti `Png` dengan `Svg` – Aspose.BarCode mendukungnya secara langsung.

#### Output yang Diharapkan

Menjalankan program lengkap menghasilkan file bernama **ExtPDF417Meta.png**. Gambar tersebut menampilkan simbol PDF417 padat, multi‑baris yang mencakup teks “Åspóse.Barcóde©” dan metadata makro yang Anda berikan. Memindai barcode dengan pembaca kompatibel PDF417 mengembalikan teks asli plus blok data terstruktur yang berisi ID file, ID segmen, cap waktu, dan bidang lainnya.

![Tangkapan layar barcode PDF417 yang dihasilkan](/images/pdf417-example.png){: .center-image alt="contoh output generate barcode PDF417 C#"}

## Kode sumber lengkap (siap salin‑tempel)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Cara memverifikasi hasilnya

1. Buka `ExtPDF417Meta.png` di penampil gambar apa pun.  
2. Gunakan aplikasi pemindai PDF417 (misalnya *Zebra Scanner* atau *BarCode Reader* di Android/iOS).  
3. Pastikan payload yang didekode mencakup teks asli dan blok mirip JSON dengan bidang makro yang Anda atur.

## Pertanyaan umum dan penanganan kasus tepi

| Pertanyaan | Jawaban |
|------------|---------|
| **Apakah saya dapat menghasilkan gambar vektor alih‑alih PNG?** | Ya. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Svg`. Sisanya tetap tidak berubah. |
| **Bagaimana jika data saya melebihi kapasitas default?** | Tingkatkan `Pdf417.Columns` atau atur `Pdf417.Rows` secara manual. Nilai yang lebih besar memungkinkan lebih banyak codeword per segmen. |
| **Apakah Unicode didukung dalam teks yang dienkode?** | Tentu saja. Contoh menggunakan “Åspóse.Barcóde©”. Aspose.BarCode secara otomatis beralih ke enkoding UTF‑8 bila diperlukan. |
| **Apakah saya perlu menandatangani lisensi untuk Aspose.BarCode?** | Untuk produksi Anda harus menerapkan lisensi agar tidak muncul watermark evaluasi. Panggil `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` sebelum membuat generator. |
| **Bagaimana cara menangani error saat menyimpan file?** | Bungkus pemanggilan `Save` dalam blok try/catch dan log `IOException` atau `BarCodeException` untuk pemecahan masalah. |

## Kesimpulan

Anda kini tahu cara **menghasilkan barcode PDF417 C#** menggunakan Aspose.BarCode, menyematkan metadata Macro PDF417 lengkap, dan mengekspor hasilnya sebagai gambar PNG berkualitas tinggi. Langkah‑langkah—membuat generator, menyesuaikan tampilan, mengisi metadata, dan menyimpan gambar—merupakan pola yang dapat digunakan kembali dan dapat disesuaikan untuk faktur, label pengiriman, atau skenario apa pun yang memerlukan data barcode kaya.

### Langkah selanjutnya

- Bereksperimen dengan format barcode lain (mis., QR, Code128) dengan mengubah `EncodeTypes`.  
- Jelajahi `Pdf417.ErrorCorrectionLevel` untuk meningkatkan keandalan pemindaian dalam pencahayaan buruk.  
- Integrasikan gambar yang dihasilkan ke dalam laporan PDF menggunakan Aspose.PDF untuk otomatisasi dokumen end‑to‑end.  

Silakan modifikasi bidang metadata agar sesuai dengan aturan bisnis Anda, dan biarkan pembuatan barcode menjadi bagian mulus dari aplikasi C# Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Perpustakaan barcode Java – Menambahkan barcode ke PDF menggunakan Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}