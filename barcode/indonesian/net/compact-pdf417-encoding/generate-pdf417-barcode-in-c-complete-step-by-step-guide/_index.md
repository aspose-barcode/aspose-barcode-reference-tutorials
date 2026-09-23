---
category: general
date: 2026-09-23
description: Pelajari cara menghasilkan barcode PDF417 di C# dengan cepat, sesuaikan
  ukurannya, dan atur dimensi khusus dengan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate pdf417 barcode c#
- adjust barcode size c#
- custom barcode dimensions
lastmod: 2026-09-23
og_description: Cara menghasilkan barcode PDF417 di C# dalam hitungan menit. Panduan
  ini menunjukkan cara mengkodekan teks, mengontrol dimensi X, dan menyesuaikan tata
  letak kolom‑baris dengan Aspose.BarCode.
og_image_alt: 'Developer guide: generate PDF417 barcode with custom dimensions using
  C#'
og_title: Cara menghasilkan barcode PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate PDF417 barcode quickly with C#. Includes text
    encoding, size adjustment, and custom dimensions.
  headline: How to generate PDF417 barcode in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
- Aspose.BarCode
title: Cara menghasilkan barcode PDF417 di C# – panduan lengkap langkah demi langkah
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 di C# – panduan lengkap langkah demi langkah

Pernah perlu **menghasilkan barcode PDF417** tetapi tidak yakin pengaturan mana yang harus diubah? Anda tidak sendirian—banyak pengembang mengalami kebuntuan yang sama saat pertama kali bermain dengan barcode 2‑D. Kabar baik? Dengan beberapa baris kode C# Anda dapat mengubah string apa pun menjadi gambar PDF417 yang dapat dipindai, mengontrol ukuran tepatnya, dan bahkan menentukan tata letak kolom‑baris khusus.

Dalam tutorial ini kami akan menunjukkan cara **menghasilkan barcode dari teks**, menyesuaikan ukuran barcode, dan mengatur dimensi barcode khusus — semua menggunakan pustaka Aspose.BarCode yang populer. Pada akhir tutorial Anda akan memiliki contoh siap‑jalankan yang dapat Anda masukkan ke proyek .NET mana pun.

![Generate PDF417 barcode example](https://example.com/og-image.png "Generate PDF417 barcode example")
[Generate PDF417 barcode example](https://example.com/og-image.png "Generate PDF417 barcode example")

## Jawaban Cepat
- **Perpustakaan apa yang membuat barcode PDF417 di .NET?** Aspose.BarCode untuk .NET.
- **Berapa baris kode yang dibutuhkan untuk barcode dasar?** Hanya tiga baris: buat generator, atur X‑dimension, simpan gambar.
- **Bisakah saya menyesuaikan kolom dan baris?** Ya, Anda dapat mengatur `Columns` dan `Rows` pada parameter PDF417.
- **Format gambar apa yang didukung?** PNG, JPEG, BMP, GIF, SVG, dan PDF.
- **Apakah karakter Unicode berfungsi?** Tentu saja; API sepenuhnya mendukung enkoding UTF‑8.

## Apa itu cara menghasilkan PDF417?
Frasa “cara menghasilkan PDF417” mengacu pada proses membuat gambar barcode PDF417 2‑D dari data teks menggunakan pustaka pemrograman. Dengan Aspose.BarCode Anda dapat menyelesaikannya dalam kurang dari satu menit. Prosesnya melibatkan mengambil string teks biasa, memberikannya ke generator barcode yang mengimplementasikan spesifikasi PDF417, dan menghasilkan matriks modul hitam‑putih yang dapat dirender sebagai gambar atau disematkan dalam dokumen.

## Mengapa menggunakan Aspose.BarCode untuk menghasilkan PDF417?
Aspose.BarCode mendukung **lebih dari 50 format input dan output** serta dapat memproses **dokumen ratusan halaman tanpa memuat seluruh file ke memori**. Pustaka ini berjalan pada **.NET 6+, .NET Framework 4.8, dan .NET Core**, memberi Anda fleksibilitas di lingkungan desktop, server, dan cloud.

## Prasyarat
- .NET 6.0 atau lebih baru (kode ini juga berfungsi pada .NET Framework 4.8).
- Visual Studio 2022 atau IDE apa pun yang kompatibel dengan C#.
- Aspose.BarCode untuk .NET (versi percobaan gratis atau berlisensi). Instal melalui NuGet:

```bash
dotnet add package Aspose.BarCode
```

Itu saja—setelah paket direferensikan Anda siap melanjutkan.

## Cara menghasilkan barcode PDF417 di C#?

Muat teks Anda, konfigurasikan generator, dan simpan gambar dalam tiga langkah sederhana. Jawaban langsung ini memberi Anda alur kerja lengkap sebelum penjelasan tambahan. Pertama, buat instance `BarcodeGenerator` dengan simbol PDF417 dan data Anda. Selanjutnya, sesuaikan parameter visual seperti X‑dimension, kolom, dan baris. Akhirnya, panggil `Save` untuk menulis gambar ke disk dalam format yang diinginkan.

### Langkah 1 – menghasilkan barcode PDF417 dengan data teks

Kelas `BarcodeGenerator` membuat gambar barcode berdasarkan simbolologi dan data yang ditentukan.  
Hal pertama yang kita butuhkan adalah sebuah instance `BarcodeGenerator` yang mengetahui bahwa kita menggunakan simbolologi PDF417 dan teks tepat yang ingin kita enkode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Mengapa ini penting:**  
> `EncodeTypes.Pdf417` memberi tahu pustaka untuk menggunakan format PDF417 2‑D, sementara argumen kedua adalah payload **menghasilkan barcode dari teks**. Apa pun yang Anda berikan di sini menjadi data yang disimpan dalam matriks barcode.

### Langkah 2 – sesuaikan ukuran barcode (X‑dimension)

Properti `XDimension` menentukan lebar piksel dari satu modul (kotak hitam atau putih terkecil) dalam gambar barcode.  

`XDimension` mengontrol lebar satu modul (kotak hitam atau putih terkecil) dalam piksel.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Pro tip:**  
> Nilai 2 px bekerja dengan baik untuk kebanyakan skenario tampilan layar. Untuk cetakan resolusi tinggi Anda mungkin meningkatkan nilai ini menjadi 3 atau 4 px. Ingat bahwa X‑dimension yang lebih besar meningkatkan ukuran gambar secara keseluruhan.

### Langkah 3 – atur dimensi barcode khusus (kolom & baris)

PDF417 memungkinkan Anda menentukan berapa banyak kolom dan baris yang harus ditempati barcode. Inilah saat **dimensi barcode khusus** berperan.  

Parameter `Pdf417` memungkinkan Anda menentukan grid kolom‑baris yang tepat untuk barcode.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Apa yang terjadi di balik layar?**  
> Pustaka mendistribusikan ulang data yang telah dienkode ke seluruh grid yang ditentukan. Lebih sedikit kolom berarti barcode lebih tinggi; lebih banyak baris membuatnya lebih pendek. Bereksperimenlah dengan angka-angka tersebut hingga keseimbangan visual terasa tepat untuk aplikasi Anda.

### Langkah 4 – simpan gambar barcode

Sekarang semua telah dikonfigurasi, kami cukup meminta generator menulis file PNG. PNG bersifat lossless, sehingga ketajaman modul tetap terjaga.  
`Save` menulis barcode yang dihasilkan ke file dalam format gambar yang dipilih.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

Saat Anda menjalankan program, Anda akan melihat file di `C:\Barcodes\CustomLayout.png` yang tampak serupa dengan tangkapan layar di atas. Memindainya dengan pembaca PDF417 apa pun akan mengembalikan string asli `Åspóse.Barcóde©`.

## Contoh kerja lengkap

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke aplikasi konsol. Program ini mencakup semua direktif `using` dan penanganan error yang biasanya Anda temui dalam kode produksi.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Output yang diharapkan

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…dan menghasilkan PNG yang dapat dibuka di penampil gambar apa pun. Jika Anda memindainya dengan aplikasi seluler (misalnya “Barcode Scanner” di iOS/Android), teks yang didekode akan persis **Åspóse.Barcóde©**.

## Pertanyaan umum & kasus tepi

| Pertanyaan | Jawaban |
|----------|--------|
| **Bisakah saya menggunakan format gambar lain?** | Ya—`BarCodeImageFormat.Jpeg`, `Bmp`, `Gif`, atau `Svg` semuanya didukung. Cukup ubah argumen kedua pada `Save`. |
| **Bagaimana jika teks saya mengandung karakter Unicode?** | Aspose.BarCode sepenuhnya mendukung UTF‑8, jadi contoh dengan `Å` dan `©` berfungsi langsung. |
| **Bagaimana cara mengubah tingkat koreksi kesalahan?** | Gunakan `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (tingkat 0‑8). Tingkat yang lebih tinggi meningkatkan redundansi tetapi juga ukuran. |
| **Saya membutuhkan latar belakang transparan—apakah bisa?** | Atur `generator.Parameters.Barcode.Image.TransparentBackground = true;` sebelum menyimpan. |
| **Apakah ada cara menyematkan barcode langsung ke PDF?** | Tentu. Ganti pemanggilan `Save` dengan `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` dan Anda akan mendapatkan PDF satu halaman yang berisi barcode. |

## Pertanyaan yang sering diajukan

**T: Apakah pustaka ini bekerja di .NET Core dan .NET 5/6?**  
J: Ya, Aspose.BarCode untuk .NET mendukung .NET Core 3.1, .NET 5, .NET 6, dan versi selanjutnya.

**T: Bisakah saya menghasilkan beberapa barcode dalam loop?**  
J: Tentu. Buat instance baru `BarcodeGenerator` untuk setiap string atau gunakan kembali instance yang sama setelah mengubah properti `CodeText`.

**T: Seberapa besar gambar yang dapat dihasilkan?**  
J: API dapat membuat gambar hingga **10.000 × 10.000 piksel**; konsumsi memori meningkat seiring X‑dimension dan pengaturan kolom/baris.

**T: Apakah lisensi diperlukan untuk penggunaan produksi?**  
J: Ya, lisensi komersial menghapus watermark evaluasi dan membuka semua fitur. Versi percobaan gratis tersedia untuk pengujian.

**T: Apakah saya harus membuang (dispose) generator secara manual?**  
J: `BarcodeGenerator` mengimplementasikan `IDisposable`. Bungkus dalam blok `using` atau panggil `Dispose()` untuk membebaskan sumber daya tak terkelola dengan cepat.

## Apa yang harus Anda pelajari selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara Menghasilkan Barcode - Jenis Barcode Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/)
- [Hasilkan Barcode DataMatrix – Panduan Pro dengan Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

---

**Terakhir Diperbarui:** 2026-09-23  
**Diuji dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose  






```bash
dotnet add package Aspose.BarCode
```

## Tutorial Terkait

- [Panduan C Menyesuaikan Ukuran Barcode untuk Menghasilkan Barcode Pdf417](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Contoh Aspose Barcode Menghasilkan Macro Pdf417 di C](/barcode/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Menghasilkan Barcode Micro Pdf417 di C Panduan Lengkap](/barcode/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}