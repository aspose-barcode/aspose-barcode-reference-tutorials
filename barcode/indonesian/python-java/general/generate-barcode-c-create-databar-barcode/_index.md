---
category: general
date: 2026-07-21
description: Buat barcode C# dengan cepat menggunakan Aspose.BarCode. Pelajari cara
  membuat barcode DataBar, menyesuaikan ukuran barcode, dan mengekspor gambar barcode
  dalam beberapa langkah saja.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: id
lastmod: 2026-07-21
og_description: Buat barcode C# menggunakan Aspose.BarCode. Buat barcode DataBar,
  sesuaikan ukurannya, dan ekspor gambar secara instan.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Menghasilkan barcode C# – Membuat Barcode DataBar dengan Ukuran Kustom
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Menghasilkan barcode C# – Membuat barcode DataBar
url: /id/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan barcode C# – Buat DataBar barcode

Ingin **generate barcode C#** tanpa harus menyelam ke dalam dokumentasi yang tak berujung? Anda berada di tempat yang tepat. Pada panduan ini kami akan menunjukkan cara membuat **DataBar barcode**, menyesuaikan dimensinya, dan akhirnya **mengekspor gambar barcode**—semua dengan beberapa baris kode C#.

Bayangkan Anda memerlukan label produk yang kompak dan dapat dipasang pada tag rak yang sangat kecil. Simbol DataBar Expanded Stacked dapat menyelesaikannya, dan dengan Aspose.BarCode Anda dapat mengontrol berapa banyak kolom atau baris yang digunakan. Siap? Mari kita mulai.

## Apa yang akan Anda capai

- **Buat DataBar barcode** (varian “expanded stacked”) dari awal.  
- **Sesuaikan ukuran barcode** dengan mengatur kolom atau baris secara langsung.  
- **Ubah dimensi barcode** secara dinamis tanpa harus membangun ulang generator.  
- **Ekspor gambar barcode** ke PNG (atau format apa pun yang didukung Aspose).  

Tanpa layanan eksternal, tanpa konfigurasi berantakan—hanya kode C# yang bersih dan dapat dijalankan.

## Prasyarat

- .NET 6.0 atau lebih baru (kode ini juga berfungsi pada .NET Framework 4.7+).  
- Lisensi Aspose.BarCode untuk .NET yang valid (atau Anda dapat menjalankannya dalam mode percobaan).  
- IDE pilihan Anda—Visual Studio, Rider, atau VS Code sudah cukup.  

Jika Anda belum menginstal paket NuGet, jalankan:

```bash
dotnet add package Aspose.BarCode
```

Itu saja—tidak ada dependensi lain.

## Langkah 1: Siapkan generator barcode (Cara **generate barcode C#**)

Pertama, kita memerlukan instance `BarcodeGenerator` yang mengacu pada simbol **DataBar Expanded Stacked**. Objek ini adalah mesin yang akan membuat gambar nanti.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Mengapa ini penting*: Enum `EncodeTypes.DatabarExpandedStacked` memberi tahu Aspose bahwa kita menginginkan versi stacked, yang ideal untuk ruang sempit. Teks yang kita berikan menjadi nilai yang akan dienkode; Anda dapat menggantinya dengan string numerik apa pun yang dibutuhkan aplikasi Anda.

## Langkah 2: **Sesuaikan ukuran barcode** – atur kolom

Barcode DataBar memungkinkan Anda memengaruhi kepadatan visual dengan menentukan jumlah **kolom** *atau* **baris**. Mari mulai dengan kolom. Jumlah baris akan dihitung otomatis agar barcode tetap valid.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Tips profesional*: Kolom memengaruhi lebar barcode. Lebih banyak kolom → barcode lebih lebar, yang dapat meningkatkan keandalan pemindaian pada printer beresolusi rendah.

## Langkah 3: **Ekspor gambar barcode** dengan pengaturan kolom

Sekarang kita menulis gambar ke disk. Anda dapat memilih PNG, JPEG, BMP, atau bahkan SVG. Berikut contoh PNG untuk output yang tajam dan lossless.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Hasil yang diharapkan** – Buka `DatabarCols4.png` dan Anda akan melihat DataBar yang ditumpuk rapi dengan empat kolom. Tampaknya seperti tumpukan batang vertikal yang padat, sempurna untuk label kecil.

## Langkah 4: **Ubah dimensi barcode** – atur baris sebagai gantinya

Kadang‑kadang Anda memerlukan barcode yang lebih tinggi daripada yang lebih lebar. Beralih ke kontrol baris; Aspose akan menghitung ulang kolom secara otomatis.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Mengapa beralih?* Baris memengaruhi tinggi barcode. Lebih banyak baris membuat simbol menjadi lebih tinggi, yang berguna ketika Anda memiliki ruang vertikal tetapi lebar terbatas.

## Langkah 5: **Ekspor gambar barcode** dengan pengaturan baris

Simpan variasi kedua. Perhatikan nama file yang mencerminkan perubahan; Anda juga dapat menyimpan kedua gambar untuk perbandingan.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Hasil** – `DatabarRows3.png` kini menampilkan versi yang lebih tinggi dari data yang sama, tetap dapat dipindai dengan sempurna.

## Contoh kerja lengkap

Menggabungkan semuanya, berikut adalah aplikasi konsol mandiri yang dapat Anda salin‑tempel dan jalankan langsung:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Jalankan program, lalu buka dua file PNG. Anda kini **generate barcode C#**, **sesuaikan ukuran barcode**, **ubah dimensi barcode**, dan **ekspor gambar barcode**—semua dalam kurang dari satu menit.

## Pertanyaan umum & kasus tepi

- **Bagaimana jika saya membutuhkan format gambar lain?**  
  Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, `Gif`, atau `Svg`. API akan menangani konversi secara otomatis.

- **Apakah saya dapat mengubah baris dan kolom sekaligus?**  
  Secara teknis Anda dapat mengatur keduanya, tetapi Aspose akan memberi prioritas pada properti yang terakhir Anda ubah. Lebih aman untuk mengatur *satu* dimensi dan membiarkan perpustakaan menghitung yang lain agar DataBar tetap valid.

- **Bagaimana cara menerapkan warna latar depan/latar belakang?**  
  Gunakan `barcodeGen.Parameters.Barcode.ForegroundColor` dan `BackgroundColor`. Contoh:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Apakah ada batas ukuran untuk data yang dienkode?**  
  DataBar Expanded Stacked mendukung hingga 74 karakter numerik (atau 30 alfanumerik). Melebihi batas tersebut akan menyebabkan pengecualian.

## Langkah selanjutnya

Setelah Anda menguasai dasar **create databar barcode**, pertimbangkan:

- Menambahkan **anotasi teks** di bawah barcode (`barcodeGen.Parameters.CaptionAbove.Text`).
- Menyematkan PNG langsung ke PDF menggunakan Aspose.PDF.
- Menghasilkan barcode secara massal dengan melakukan loop pada file CSV berisi ID produk.

Setiap topik ini dibangun di atas objek `BarcodeGenerator` yang sama, sehingga Anda tidak perlu memulai dari nol.

---

**Intinya**: Anda kini tahu cara **generate barcode C#**, **sesuaikan ukuran barcode**, **ubah dimensi barcode**, dan **ekspor gambar barcode** dengan Aspose.BarCode. Bereksperimenlah dengan nilai kolom/baris, ganti format gambar, dan integrasikan kode ke dalam sistem inventaris atau POS Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Hasilkan gambar barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hasilkan Barcode DataMatrix – Panduan Pro dengan Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}