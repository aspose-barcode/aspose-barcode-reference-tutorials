---
category: general
date: 2026-07-27
description: Buat barcode dengan data di C# dengan cepat. Pelajari cara membuat barcode
  PDF417 c# menggunakan Aspose.BarCode, atur dimensi, dan simpan sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with data
- create pdf417 barcode c#
language: id
lastmod: 2026-07-27
og_description: Buat barcode dengan data di C# menggunakan Aspose.BarCode. Panduan
  ini menunjukkan cara membuat barcode PDF417 dengan C# menggunakan pengaturan khusus
  dan menyimpannya sebagai PNG.
og_image_alt: Screenshot of a barcode created with data in a C# application
og_title: Buat barcode dengan data di C# – Panduan Pemrograman Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  headline: Create barcode with data in C# – Step‑by‑Step Guide
  type: TechArticle
- description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  name: Create barcode with data in C# – Step‑by‑Step Guide
  steps:
  - name: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
    text: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
  - name: Tweaking the X‑dimension for finer resolution.
    text: Tweaking the X‑dimension for finer resolution.
  - name: Limiting columns to keep the barcode compact.
    text: Limiting columns to keep the barcode compact.
  - name: Saving the result as a PNG file.
    text: Saving the result as a PNG file.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Buat barcode dengan data di C# – Panduan Langkah demi Langkah
url: /id/net/compact-pdf417-encoding/create-barcode-with-data-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode dengan data di C# – Panduan Pemrograman Lengkap

Pernah perlu **create barcode with data** dalam aplikasi .NET tetapi tidak yakin panggilan API mana yang harus digunakan? Anda tidak sendirian. Baik Anda menandai inventaris, mencetak tiket, atau menyematkan informasi dalam pemindaian seluler, menguasai pembuatan barcode adalah keterampilan berguna bagi setiap pengembang C#.

Dalam tutorial ini kami akan membahas contoh praktis yang menunjukkan cara **create PDF417 barcode c#** menggunakan pustaka Aspose.BarCode, menyesuaikan lebar modul, membatasi jumlah kolom, dan akhirnya menyimpan hasilnya ke file PNG. Pada akhir tutorial Anda akan memiliki program konsol yang berfungsi penuh, siap dijalankan, yang dapat Anda masukkan ke dalam proyek mana pun.

## Prasyarat — Apa yang Anda Butuhkan

- **.NET 6.0** atau lebih baru (kode ini juga bekerja dengan .NET Framework 4.7+ )  
- Paket NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)  
- Editor kode atau IDE (Visual Studio, VS Code, Rider – pilih yang Anda suka)  
- Izin menulis ke folder tempat PNG akan disimpan  

Tidak diperlukan file konfigurasi tambahan; pustaka ini berdiri sendiri.

## Langkah 1: Siapkan Proyek dan Impor Namespace

Pertama, buat proyek konsol baru (atau buka yang sudah ada) dan tambahkan referensi Aspose.BarCode.

```csharp
// Program.cs – entry point
using System;
using Aspose.BarCode.Generation;   // Core generator classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll place the barcode generation logic here.
        }
    }
}
```

> **Mengapa ini penting:** Mengimpor namespace yang tepat memberi Anda akses ke `BarcodeGenerator` dan pengaturan terkait tanpa harus menyebutkan setiap tipe. Ini juga membuat kode lebih bersih untuk pemeliharaan di masa mendatang.

## Langkah 2: Inisialisasi Barcode Generator dengan Data Anda

Sekarang kita benar‑benar **create barcode with data**. Konstruktor `BarcodeGenerator` menerima dua argumen: simbolologi (`EncodeTypes.MicroPdf417`) dan string yang ingin Anda enkode.

```csharp
// Inside Main()
string dataToEncode = "Åspóse.Barcóde©";   // Example containing Unicode characters
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);
```

> **Tip:** Simbolologi MicroPdf417 adalah versi kompak dari PDF417, sempurna ketika Anda membutuhkan gambar lebih kecil namun tetap menginginkan kapasitas data tinggi. Pustaka ini menangani Unicode secara langsung, sehingga karakter seperti “Å” dan “©” berfungsi dengan baik.

## Langkah 3: Sesuaikan X‑Dimension (Lebar Modul)

Jika Anda membutuhkan gambar yang lebih tajam, beresolusi tinggi, Anda dapat memperkecil lebar modul. Mengaturnya menjadi **2 piksel** memberi Anda grid yang lebih halus tanpa memperbesar ukuran file.

```csharp
// Adjust the module (X‑dimension) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Mengapa menyesuaikan X‑Dimension?** X‑dimension yang lebih kecil membuat setiap bar menjadi lebih sempit, yang meningkatkan keterbacaan pada pemindai beresolusi tinggi sambil menjaga ukuran keseluruhan barcode tetap wajar.

## Langkah 4: Batasi Kolom PDF417 (Opsional namun Umum)

PDF417 memungkinkan Anda menentukan jumlah kolom. Untuk MicroPdf417 maksimum adalah **4**, yang membuat barcode pendek dan lebar.

```csharp
// Set the column count to the maximum allowed (4)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **Kasus tepi:** Jika Anda menetapkan jumlah kolom lebih tinggi dari maksimum yang diizinkan, Aspose akan secara otomatis menyesuaikannya, tetapi praktik terbaik adalah tetap berada dalam rentang yang didokumentasikan untuk menghindari skala yang tidak terduga.

## Langkah 5: Simpan Barcode sebagai Gambar PNG

Akhirnya, tulis gambar yang dihasilkan ke disk. Metode `Save` menerima jalur lengkap dan format gambar yang diinginkan.

```csharp
// Define output path – adjust as needed
string outputPath = @"C:\Temp\MicroPdf417.png";

// Save as PNG (lossless, widely supported)
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Pro tip:** PNG mempertahankan data piksel yang tepat, yang penting untuk barcode. Jika Anda membutuhkan format vektor untuk skala, Anda dapat mengganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Svg`.

### Contoh Kerja Lengkap

Menggabungkan semuanya, berikut program lengkap yang siap disalin‑tempel:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Data we want to encode – includes special characters
            string dataToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Initialise generator with MicroPdf417 symbology
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);

            // 3️⃣ Fine‑tune resolution – 2‑pixel modules
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Use the maximum of 4 columns for a compact barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 5️⃣ Save the image
            string outputPath = @"C:\Temp\MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode created successfully! Saved at: {outputPath}");
        }
    }
}
```

Menjalankan program ini menghasilkan file PNG yang kira‑kira terlihat seperti ini:

![Barcode yang dibuat dengan data di C#](barcode-sample.png "Tangkapan layar barcode yang dibuat dengan data dalam aplikasi C#")

*Gambar di atas adalah placeholder—barcode Anda yang sebenarnya akan berisi string tepat “Åspóse.Barcóde©”.*

## Pertanyaan Umum & Kasus Tepi

| Pertanyaan | Jawaban |
|------------|---------|
| *Bagaimana jika data saya melebihi kapasitas MicroPdf417?* | Ganti ke `EncodeTypes.Pdf417` (PDF417 reguler) yang mendukung hingga 1 800 karakter. |
| *Apakah saya dapat mengubah format gambar ke JPEG?* | Ya—ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`. Ingat JPEG bersifat lossy; dapat memengaruhi keandalan pemindai. |
| *Apakah saya perlu menangani Unicode secara manual?* | Tidak. Aspose.BarCode secara otomatis mengenkode karakter Unicode, tetapi pastikan file sumber Anda disimpan dengan encoding UTF‑8. |
| *Bagaimana jika saya membutuhkan latar belakang transparan?* | Setel `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;` sebelum menyimpan. |
| *Apakah ada cara untuk menghasilkan barcode di memori?* | Panggil `generator.GenerateBarCodeImage()` untuk mendapatkan objek `System.Drawing.Image` yang dapat Anda alirkan langsung. |

## Ringkasan – Apa yang Telah Kita Pelajari

Kami telah mendemonstrasikan cara **create barcode with data** di C# dengan:

1. Menginisialisasi `BarcodeGenerator` dengan MicroPdf417 dan string Unicode.  
2. Menyesuaikan X‑dimension untuk resolusi yang lebih halus.  
3. Membatasi kolom untuk menjaga barcode tetap kompak.  
4. Menyimpan hasil sebagai file PNG.  

Semua langkah ini bersama‑sama menjawab pertanyaan utama “how to **create PDF417 barcode c#**” sekaligus menunjukkan cara menyesuaikan parameter umum.

## Langkah Selanjutnya & Topik Terkait

- **Tambahkan teks yang dapat dibaca manusia** di bawah barcode menggunakan `generator.Parameters.Barcode.CodeTextParameters`.  
- **Sematkan PNG dalam PDF** dengan `Aspose.Pdf` untuk laporan yang dapat dicetak.  
- **Hasilkan simbolologi lain** (QR, Code128, DataMatrix) dengan mengganti `EncodeTypes`.  
- **Pemrosesan batch** – iterasi melalui CSV ID produk dan keluarkan folder berisi barcode.  

Silakan bereksperimen dengan jumlah kolom, tingkat koreksi kesalahan, dan skema warna. Setelah Anda merasa nyaman, Anda dapat membangun solusi pelabelan lengkap yang terintegrasi mulus dengan sistem inventaris atau tiket.

Selamat coding, semoga pemindaian Anda selalu bebas error!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Buat gambar barcode DotCode – baris & kolom (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Buat Barcode PNG – Rasio Aspek DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}