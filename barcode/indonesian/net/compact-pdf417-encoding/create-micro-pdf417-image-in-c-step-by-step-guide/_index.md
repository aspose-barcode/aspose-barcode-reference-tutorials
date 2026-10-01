---
category: general
date: 2026-08-12
description: Buat gambar micro PDF417 di C# dengan cepat. Pelajari cara menghasilkan
  barcode PDF417 di C# dengan kode lengkap, opsi, dan tips pemecahan masalah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 image
- how to generate PDF417 barcode C#
- barcode generator C#
- PDF417 column settings
- barcode image format PNG
language: id
lastmod: 2026-08-12
og_description: Buat gambar micro PDF417 di C# dengan tutorial terperinci ini. Ikuti
  langkah-langkah untuk menghasilkan barcode PDF417 C# dan sesuaikan output.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Buat gambar micro PDF417 di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create micro PDF417 image in C# quickly. Learn how to generate PDF417
    barcode C# with full code, options, and troubleshooting tips.
  headline: Create micro PDF417 image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- imaging
title: Buat gambar micro PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/create-micro-pdf417-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat gambar micro PDF417 di C# – panduan langkah demi langkah

Jika Anda perlu **membuat gambar micro PDF417** dalam aplikasi .NET, tutorial ini menunjukkan cara melakukannya dengan beberapa baris C#. Anda akan melihat kode tepat untuk menghasilkan barcode PDF417 C# dan cara menyesuaikan ukuran, jumlah kolom, serta format file.

Panduan ini mencakup semua hal mulai dari menginstal pustaka yang diperlukan hingga menangani karakter Unicode dan menyimpan hasilnya sebagai file PNG. Pada akhir tutorial, Anda akan memiliki metode yang dapat digunakan kembali yang menghasilkan barcode micro PDF417 berkualitas tinggi untuk label inventaris, tiket, atau solusi pemindaian seluler.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru (kode ini juga berfungsi dengan .NET Core dan .NET Framework)
* Visual Studio 2022 atau IDE apa pun yang kompatibel dengan C#
* Paket NuGet **Aspose.BarCode** (atau pustaka barcode kompatibel lain yang mendukung `EncodeTypes.MicroPdf417`)

Anda dapat menambahkan paket tersebut dengan .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

> **Tips profesional:** Gunakan versi stabil terbaru dari pustaka untuk mendapatkan perbaikan bug dan fitur enkoding baru.

## Langkah 1: Membuat instance generator barcode

Langkah pertama adalah menginstansiasi `BarcodeGenerator` dengan tipe enkode `MicroPdf417` dan data yang ingin Anda enkode. Pustaka secara otomatis menangani karakter UTF‑8, sehingga Anda dapat menyertakan huruf beraksen atau simbol.

```csharp
using Aspose.BarCode.Generation;

// Data to encode – Unicode characters are supported out of the box
string data = "Åspóse.Barcóde©";

// Create a MicroPdf417 barcode generator
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417, data);
```

**Mengapa ini penting:** `EncodeTypes.MicroPdf417` menghasilkan barcode 2‑D yang kompak yang cocok untuk label kecil sambil mempertahankan kemampuan koreksi kesalahan. Menyampaikan data saat konstruksi memastikan generator memvalidasi konten lebih awal.

## Langkah 2: Mengonfigurasi dimensi X (lebar modul)

Dimensi X menentukan seberapa lebar setiap modul barcode (piksel). Nilai yang lebih kecil menghasilkan gambar yang lebih rapat, tetapi dapat menjadi tidak terbaca pada pemindai beresolusi rendah. Titik awal yang umum adalah 2 piksel.

```csharp
// Set module width to 2 pixels (adjustable per printer DPI)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Kasus khusus:** Jika Anda menargetkan printer beresolusi tinggi (≥300 dpi), Anda dapat meningkatkan nilai piksel menjadi 3‑4 untuk meningkatkan keterbacaan tanpa memperbesar gambar secara keseluruhan.

## Langkah 3: Memilih jumlah kolom

Micro PDF417 memungkinkan Anda menentukan berapa banyak kolom yang harus dimiliki matriks (1‑4). Lebih banyak kolom membuat barcode lebih lebar tetapi lebih pendek, yang dapat berguna ketika ruang vertikal terbatas.

```csharp
// Use 4 columns to keep the barcode compact vertically
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Kapan menyesuaikan:**  
* Gunakan **1‑2 kolom** untuk label sempit (mis., tag gelang).  
* Gunakan **3‑4 kolom** ketika Anda memiliki ruang horizontal lebih banyak dan menginginkan barcode yang lebih pendek.

## Langkah 4: Menetapkan jalur file output

Tentukan di mana gambar yang dihasilkan akan disimpan. Gunakan `Path.Combine` untuk membangun jalur yang independen platform.

```csharp
using System.IO;

string outputDirectory = @"C:\Barcodes";
Directory.CreateDirectory(outputDirectory); // Ensure the folder exists
string outputPath = Path.Combine(outputDirectory, "MicroPdf417.png");
```

**Tip:** Simpan barcode dalam folder khusus untuk menjaga proyek Anda tetap rapi dan mempermudah pemrosesan batch di kemudian hari.

## Langkah 5: Menyimpan barcode sebagai file PNG

Akhirnya, tulis barcode ke disk. PNG mempertahankan kualitas lossless, yang penting untuk pemindaian yang dapat diandalkan.

```csharp
// Save the barcode image in PNG format
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Jika Anda memerlukan format lain (mis., JPEG untuk pengiriman web), ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`.

### Output yang diharapkan

Setelah menjalankan kode, Anda akan menemukan `MicroPdf417.png` di `C:\Barcodes`. Membuka file tersebut menampilkan barcode persegi panjang yang tajam yang mengenkode string **Åspóse.Barcóde©**. Memindai gambar dengan pembaca PDF417 mengembalikan teks asli, mengonfirmasi bahwa proses **membuat gambar micro PDF417** berhasil.

## Metode lengkap yang dapat digunakan kembali

Berikut adalah satu metode yang dapat Anda masukkan ke dalam kelas C# mana pun. Metode ini mengabstraksi langkah-langkah di atas dan memungkinkan Anda mengirimkan data khusus, jumlah kolom, serta lokasi output.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

public static class BarcodeHelper
{
    /// <summary>
    /// Generates a micro PDF417 barcode image.
    /// </summary>
    /// <param name="data">Text to encode (Unicode supported).</param>
    /// <param name="columns">Number of columns (1‑4). Default is 4.</param>
    /// <param name="pixelWidth">Module width in pixels. Default is 2.</param>
    /// <param name="outputPath">Full file path, including file name and extension.</param>
    public static void CreateMicroPdf417Image(
        string data,
        int columns = 4,
        int pixelWidth = 2,
        string outputPath = "MicroPdf417.png")
    {
        // Validate column range
        if (columns < 1 || columns > 4)
            throw new ArgumentOutOfRangeException(nameof(columns), "Columns must be between 1 and 4.");

        // Initialize generator
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

        // Apply settings
        generator.Parameters.Barcode.XDimension.Pixels = pixelWidth;
        generator.Parameters.Barcode.Pdf417.Columns = columns;

        // Ensure directory exists
        string directory = Path.GetDirectoryName(outputPath);
        if (!string.IsNullOrEmpty(directory))
            Directory.CreateDirectory(directory);

        // Save as PNG (change format if needed)
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

**Cara menggunakan metode:**

```csharp
BarcodeHelper.CreateMicroPdf417Image(
    data: "Åspóse.Barcóde©",
    columns: 4,
    pixelWidth: 2,
    outputPath: @"C:\Barcodes\MyMicroPdf417.png");
```

Versi terenkapsulasi ini memudahkan **cara menghasilkan barcode PDF417 C#** di berbagai proyek.

## Kesalahan umum dan pemecahan masalah

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| Barcode tidak terbaca pada pemindai | Dimensi X terlalu rendah untuk DPI printer | Tingkatkan `XDimension.Pixels` menjadi 3‑4 untuk printer beresolusi tinggi |
| Teks terpotong | Input melebihi kapasitas Micro PDF417 (≈ 150 karakter) | Gunakan PDF417 biasa (`EncodeTypes.Pdf417`) untuk data yang lebih panjang |
| Karakter Unicode muncul sebagai � | Versi pustaka tidak mendukung UTF‑8 | Perbarui ke paket Aspose.BarCode terbaru |
| File tidak dibuat | Direktori output tidak ada atau izin ditolak | Panggil `Directory.CreateDirectory` sebelum menyimpan dan pastikan akses menulis |

## Memperluas contoh

* **Ubah format gambar:** Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp`.
* **Tambahkan margin:** `generator.Parameters.Barcode.Margins.All = 5;` menambahkan batas putih 5 piksel.
* **Terapkan warna:** `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Blue;` mengubah warna latar depan barcode.

Ekstensi ini memungkinkan Anda menyesuaikan alur kerja **membuat gambar micro PDF417** untuk branding atau lingkungan pemindaian tertentu.

## Kesimpulan

Anda kini tahu cara **membuat gambar micro PDF417** di C# dari awal hingga akhir, termasuk enkoding data, lebar modul, pemilihan kolom, dan output file. Metode yang dapat digunakan kembali menunjukkan praktik terbaik untuk **cara menghasilkan barcode PDF417 C#**, menangani kasus khusus dan menawarkan titik kustomisasi untuk proyek dunia nyata.

Selanjutnya, jelajahi topik terkait seperti **menghasilkan barcode PDF417 standar**, **menyematkan barcode dalam laporan PDF**, atau **mengoptimalkan keterbacaan barcode untuk kamera seluler**. Bereksperimenlah dengan berbagai jumlah kolom dan lebar piksel untuk menemukan keseimbangan ideal bagi ukuran label dan kemampuan pemindai Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Menghasilkan Barcode PDF417 – Enkoding Compact PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Membuat gambar barcode C# – Contoh GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}