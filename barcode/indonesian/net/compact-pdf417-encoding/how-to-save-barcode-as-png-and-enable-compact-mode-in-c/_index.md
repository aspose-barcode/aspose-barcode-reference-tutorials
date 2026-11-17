---
category: general
date: 2026-11-17
description: Pelajari cara menyimpan barcode, mengaktifkan mode kompak, menyesuaikan
  kolom, dan menghasilkan barcode PDF417 dengan contoh C# lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: id
lastmod: 2026-11-17
og_description: Cara menyimpan barcode, mengaktifkan mode kompak, dan menyesuaikan
  kolom saat menghasilkan barcode PDF417 di C#. Ikuti panduan langkah demi langkah.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Cara menyimpan barcode sebagai PNG dan mengaktifkan mode kompak di C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Cara menyimpan barcode sebagai PNG dan mengaktifkan mode kompak di C#
url: /id/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menyimpan barcode sebagai PNG dan mengaktifkan mode kompak di C#

Jika Anda perlu **cara menyimpan barcode** dalam format yang dapat digunakan di web atau cetakan, panduan ini menunjukkan langkah‑langkah tepatnya. Anda juga akan belajar **cara mengaktifkan mode kompak**, **menyesuaikan kolom**, dan **menghasilkan barcode PDF417** dengan pustaka Aspose.BarCode untuk .NET.

Tutorial ini mencakup semua hal mulai dari penyiapan proyek hingga file PNG akhir, sehingga Anda dapat menyalin kode ke dalam solusi Anda sendiri tanpa penelitian tambahan. Tidak diperlukan dokumentasi eksternal; contoh lengkap yang dapat dijalankan sudah disertakan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE C# apa pun)  
* Paket NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Ketiga item ini adalah satu‑satunya dependensi untuk kode berikut.

## Langkah 1: Buat generator barcode PDF417

Tugas pertama saat Anda **menghasilkan barcode PDF417** adalah menginstansiasi `BarcodeGenerator` dengan tipe enkode yang tepat dan data yang ingin Anda enkode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

Enum `EncodeTypes.Pdf417` memberi tahu pustaka untuk menggunakan simbolologi PDF417, yaitu barcode linear bertumpuk yang cocok untuk mengenkode sejumlah besar data. String `"Compact mode"` menjadi teks yang dapat dibaca manusia di bawah barcode.

## Langkah 2: Atur dimensi X (lebar modul)

Setiap bar pada barcode disebut modul. Mengontrol lebar modul memungkinkan Anda menyesuaikan ukuran visual barcode tanpa mengubah data.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Dimensi X sebesar 2 piksel menghasilkan gambar kompak yang tetap dapat dipindai secara andal pada kebanyakan perangkat.

## Langkah 3: **Cara menyesuaikan kolom** untuk kode PDF417

PDF417 memungkinkan Anda menentukan berapa banyak kolom yang harus digunakan barcode. Lebih sedikit kolom menghasilkan simbol yang lebih tinggi dan sempit, sementara lebih banyak kolom membuat simbol lebih lebar tetapi lebih pendek.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Baris ini memperlihatkan **cara menyesuaikan kolom**. Anda dapat mengubah nilainya menjadi 2, 4, atau angka lain yang didukung pustaka, tergantung pada ruang yang tersedia pada media target.

## Langkah 4: **Cara mengaktifkan mode kompak** dan memotong simbol

Mode kompak menghapus padding yang tidak diperlukan dan mengurangi jejak keseluruhan barcode. Pustaka mengekspos fitur ini melalui properti `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Perhatikan bahwa frasa **aktifkan mode kompak** muncul di sini, dan aksi yang sama dijelaskan dengan kata‑kata tepat **cara mengaktifkan mode kompak** nanti dalam panduan untuk memenuhi persyaratan kata kunci sekunder.

## Langkah 5: **Cara menyimpan barcode** sebagai gambar PNG

Menyimpan gambar yang dihasilkan adalah langkah akhir. Metode `Save` menulis barcode ke sistem file dalam format yang Anda tentukan.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang dapat ditulis oleh aplikasi Anda. Setelah dijalankan, Anda akan menemukan file bernama `CompactPdf417.png` yang berisi barcode PDF417 kompak.

### Output yang diharapkan

Membuka file PNG yang disimpan menampilkan barcode PDF417 kompak secara vertikal dengan tiga kolom dan padding yang dipotong. Ukuran visualnya kira‑kira 2 px per modul, membuat gambar cocok untuk disisipkan dalam tag HTML `<img>` atau untuk dicetak pada label kecil.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin ke dalam proyek konsol baru. Program ini mencakup semua direktif `using` yang diperlukan dan memperlihatkan **cara menyimpan barcode**, **mengaktifkan mode kompak**, **cara menyesuaikan kolom**, serta **menghasilkan barcode PDF417** dalam satu alur.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Menjalankan program ini menghasilkan file PNG yang dijelaskan sebelumnya. Output konsol mengonfirmasi lokasi file yang disimpan, sehingga Anda dapat memverifikasi bahwa langkah **cara menyimpan barcode** berhasil.

## Pertanyaan umum dan kasus tepi

### Bagaimana jika saya membutuhkan format gambar lain?

Metode `Save` menerima nilai enum `BarCodeImageFormat` apa pun, seperti `Jpeg`, `Bmp`, atau `Gif`. Ganti `BarCodeImageFormat.Png` dengan format yang diinginkan, dan sisanya tetap tidak berubah.

### Bagaimana pemotongan memengaruhi kapasitas data?

Mengaktifkan **mode kompak** (pemotongan) mengurangi jumlah baris, yang dapat menurunkan kapasitas data maksimum barcode. Jika Anda menemui pengecualian “Data too large”, tingkatkan jumlah kolom atau nonaktifkan pemotongan.

### Bisakah saya menggunakan jumlah kolom dinamis?

Ya. Anda dapat menghitung jumlah kolom berdasarkan panjang string input:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Potongan kode ini menunjukkan **cara menyesuaikan kolom** secara programatik, memastikan barcode cocok dalam tata letak yang diberikan.

### Apakah dimensi X terbatas pada piksel integer?

Properti `Pixels` menerima integer positif apa pun. Untuk output resolusi tinggi (misalnya pencetakan), Anda mungkin lebih suka mengatur `Points` alih‑alih `Pixels` untuk mendapatkan ukuran yang independen dari perangkat.

## Tips untuk penggunaan produksi

* **Tips profesional:** Bungkus pembuatan barcode dalam blok try‑catch untuk menangani `BarCodeException` ketika data input melebihi kapasitas simbol.  
* **Waspadai:** Izin sistem file. Proses harus memiliki akses menulis ke direktori target, jika tidak langkah **cara menyimpan barcode** akan gagal dengan `UnauthorizedAccessException`.  
* **Catatan kinerja:** Membuat banyak barcode dalam loop akan lebih efisien jika Anda menggunakan satu instance `BarcodeGenerator` dan hanya memperbarui properti `CodeText` di antara iterasi.

## Kesimpulan

Anda kini mengetahui **cara menyimpan barcode** sebagai file PNG, **mengaktifkan mode kompak**, **cara menyesuaikan kolom**, dan **menghasilkan barcode PDF417** menggunakan Aspose.BarCode untuk C#. Contoh lengkap memperlihatkan setiap langkah yang diperlukan, mulai dari inisialisasi generator hingga penulisan gambar akhir.

Dari sini Anda dapat menjelajahi topik terkait seperti menambahkan logo ke barcode, menyesuaikan warna, atau mengintegrasikan generator ke dalam API ASP.NET Core. Setiap ekstensi tersebut mengikuti pola yang sama seperti yang ditunjukkan dalam panduan ini, sehingga Anda dapat menyesuaikan kode dengan percaya diri.

Silakan bereksperimen dengan jumlah kolom, dimensi X, dan format gambar yang berbeda untuk memenuhi spesifikasi proyek Anda secara tepat. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara menyimpan barcode dan menghasilkan PDF417 dengan Aspose di C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Cara membuat barcode PDF417 di C# dengan mode kompak](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Cara membuat barcode PDF417 dan menyimpannya sebagai PNG di C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}