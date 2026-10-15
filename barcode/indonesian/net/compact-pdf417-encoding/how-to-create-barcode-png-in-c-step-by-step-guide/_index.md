---
category: general
date: 2026-10-15
description: Buat barcode PNG dalam C# dengan contoh PDF417 yang kompak – pelajari
  cara mengatur kolom, menyesuaikan dimensi, dan menghasilkan gambar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: id
lastmod: 2026-10-15
og_description: Buat barcode PNG dalam C# dengan contoh PDF417 yang kompak. Panduan
  ini menunjukkan cara mengatur kolom, menyesuaikan dimensi, dan menyimpan gambar.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Buat barcode PNG di C# – tutorial pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Cara membuat barcode PNG di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PNG di C# – panduan langkah demi langkah

Jika Anda perlu **membuat barcode PNG** dari kode C#, tutorial ini menunjukkan solusi lengkap dalam beberapa baris saja. Anda akan melihat cara mengatur kolom, menyesuaikan ukuran modul, dan menyimpan barcode PDF417 yang kompak sebagai gambar PNG—semua dengan contoh tunggal yang mudah dibaca.

Men‑generate barcode secara programatik menghilangkan langkah manual menggunakan editor grafis, dan memungkinkan Anda menyematkan barcode langsung ke faktur, tiket, atau label inventaris. Pada bagian berikut kami akan membahas semua yang perlu Anda ketahui untuk **how to create barcode** images, mengapa setiap konfigurasi penting, dan cara menyesuaikan kode untuk berbagai kasus penggunaan.

## Prasyarat

* .NET 6.0 atau lebih baru (kode ini juga bekerja dengan .NET Framework 4.7+)
* Referensi ke pustaka barcode yang mendukung PDF417, seperti **Aspose.BarCode for .NET** atau **IronBarcode**. Contoh ini menggunakan Aspose.BarCode, yang dapat Anda instal melalui NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Familiaritas dasar dengan sintaks C# dan Visual Studio (atau IDE apa pun yang Anda sukai).

> **Pro tip:** Jika Anda lebih suka alternatif gratis, pustaka open‑source **ZXing.Net** juga mendukung PDF417, tetapi nama properti sedikit berbeda. Konsep yang ditunjukkan di sini tetap sama.

## Cara membuat barcode PNG di C# (langkah utama)

Inti solusi adalah objek `BarcodeGenerator` yang dikonfigurasi untuk enkoding PDF417. Bagian‑bagian berikut memecah setiap baris kode, menjelaskan **how to set columns**, dan menunjukkan mengapa pengaturan tersebut memengaruhi ukuran PNG akhir.

### Langkah 1: Inisialisasi generator barcode dengan teks yang diinginkan

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Mengapa ini penting*: Enum `EncodeTypes.Pdf417` memberi tahu pustaka untuk menghasilkan barcode bertumpuk 2‑dimensi. Konstruktor juga menerima data yang ingin Anda enkode, sehingga Anda tidak memerlukan panggilan `SetData` terpisah.

### Langkah 2: Atur dimensi modul (X) dalam piksel

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dimensi X** mengontrol kepadatan visual barcode. Nilai yang lebih kecil menghasilkan gambar yang lebih rapat, yang berguna ketika Anda membutuhkan PNG kompak untuk layar seluler atau ruang cetak terbatas.

### Langkah 3: Tentukan jumlah kolom untuk barcode PDF417

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Baris ini menunjukkan **how to set columns**. PDF417 dapat secara otomatis memilih jumlah kolom optimal, tetapi menetapkannya secara eksplisit memberi Anda lebar yang dapat diprediksi, terutama saat Anda menyematkan PNG dalam tata letak berukuran tetap.

### Langkah 4: Aktifkan tata letak kompak dengan memotong barcode

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Ketika `Truncate` bernilai true, pustaka menghapus baris‑baris akhir yang tidak berisi data, mengurangi tinggi keseluruhan gambar tanpa kehilangan informasi.

### Langkah 5: Simpan gambar barcode sebagai PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Metode `Save` menulis barcode ke disk dalam format yang Anda tentukan. PNG bersifat loss‑less, menjadikannya ideal untuk aplikasi pemindaian yang memerlukan deteksi tepi yang tepat.

### Contoh lengkap yang dapat dijalankan

Menggabungkan semua, berikut adalah program mandiri yang dapat Anda salin, tempel, dan jalankan:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Output yang diharapkan** – Setelah menjalankan program, Anda akan menemukan `CompactPdf417.png` di folder eksekusi. Gambar tersebut berisi barcode PDF417 tiga kolom yang cukup kompak untuk muat pada label standar 2 × 2 cm sekaligus tetap dapat dipindai sepenuhnya.

![Create barcode PNG example](placeholder.png){alt="Create barcode PNG using C#"}

## Cara mengatur kolom untuk ukuran data yang berbeda (kata kunci sekunder)

Jumlah kolom memengaruhi baik lebar maupun keterbacaan barcode:

| Kolom | Lebar perkiraan (px) | Kasus penggunaan umum |
|--------|-------------------|------------------|
| 1‑2    | Sempit, tinggi      | Tag kecil, cetakan mirip RFID |
| 3‑5    | Seimbang          | Label umum |
| 6‑9    | Lebar, pendek       | Poster besar atau kemasan |

Jika string data Anda bertambah, pustaka mungkin secara otomatis meningkatkan jumlah baris untuk menjaga barcode tetap dalam batas kolom. Namun, memaksa jumlah kolom yang terlalu rendah dapat menyebabkan barcode menjadi terlalu tinggi, yang mungkin tidak muat pada printer struk. Sesuaikan jumlah kolom berdasarkan batas fisik media output Anda.

## Cara membuat gambar barcode dalam format lain (kata kunci sekunder)

Meskipun PNG adalah format paling umum untuk web dan seluler, Anda mungkin memerlukan gambar **how to create barcode** dalam JPEG, BMP, atau SVG untuk alur kerja khusus:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Memilih format yang tepat tergantung pada konsumen downstream:

* **PNG** – lossless, ideal untuk pemindai.
* **JPEG** – ukuran file lebih kecil, dapat diterima ketika artefak kompresi ringan dapat ditoleransi.
* **SVG** – sempurna untuk cetakan resolusi tinggi atau skala UI.

## Contoh barcode C#: menangani error dan kasus tepi

Contoh **c# barcode example** yang kuat harus mengantisipasi masalah runtime:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Mengapa membungkus dengan `try/catch`?* Karakter tidak valid dalam teks, dimensi yang tidak didukung, atau masalah izin menulis akan melemparkan pengecualian. Menangani mereka dengan baik mencegah aplikasi Anda crash selama pemrosesan batch.

## Memperluas contoh: menambahkan logo atau latar belakang

Banyak skenario dunia nyata memerlukan overlay logo atau latar belakang berwarna. API Aspose.BarCode memungkinkan Anda menggabungkan barcode dengan bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Teknik ini menjaga alur kerja **create barcode PNG** tetap utuh sambil memperkaya branding visual gambar akhir.

## Ringkasan

Dalam panduan ini kami mendemonstrasikan cara **create barcode PNG** file di C# menggunakan konfigurasi PDF417 yang kompak. Anda telah mempelajari:

* Kode tepat yang diperlukan untuk menginisialisasi `BarcodeGenerator`.
* **How to set columns** dan mengapa jumlah kolom penting untuk ukuran dan keterbacaan.
* Cara menyesuaikan dimensi X dan mengaktifkan pemotongan untuk PNG yang lebih rapat.
* Cara menyimpan gambar dalam PNG, JPEG, atau SVG.
* Pola penanganan error untuk **c# barcode example** siap produksi.
* Ekstensi opsional seperti overlay logo dan kustomisasi latar belakang.

Anda kini memiliki potongan kode siap‑jalankan yang dapat Anda integrasikan ke dalam generator faktur, sistem tiket, atau alat manajemen inventaris. Bereksperimenlah dengan nilai kolom yang berbeda, ukuran modul, atau tipe barcode (mis., QR, Code128) untuk melihat bagaimana gambar berubah.

## Langkah selanjutnya

* Jelajahi tipe enkoding lain (`EncodeTypes.QR`, `EncodeTypes.Code128`) untuk mencakup lebih banyak kasus penggunaan.
* Gabungkan pembuatan barcode dengan pustaka pembuatan PDF (mis., **iTextSharp**) untuk menyematkan PNG langsung ke dalam dokumen.
* Selidiki penentuan ukuran dinamis: hitung jumlah kolom optimal berdasarkan panjang string input dan dimensi label target.

Selamat coding, dan nikmati kesederhanaan menghasilkan barcode PNG yang tajam secara programatik di C#!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat barcode PDF417 dan menyimpannya sebagai PNG di C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Cara membuat barcode PDF417 dan mengatur ukurannya di C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Cara membuat barcode PDF417 di C# dengan mode kompak](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}