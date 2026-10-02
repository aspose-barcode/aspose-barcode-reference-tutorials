---
category: general
date: 2026-09-07
description: Pelajari cara menghasilkan barcode micro PDF417 di C# dengan contoh kode
  lengkap, penyesuaian dimensi X, konfigurasi kolom, dan ekspor PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- C# barcode generator
- MicroPdf417 encode type
- barcode X-dimension
- barcode column configuration
- save barcode as PNG
language: id
lastmod: 2026-09-07
og_description: Buat barcode micro pdf417 di C# dengan tutorial singkat ini. Termasuk
  pengaturan dimensi X, pilihan kolom, dan ekspor PNG untuk penggunaan langsung.
og_image_alt: Screenshot showing a generated micro pdf417 barcode saved as a PNG file
og_title: Buat barcode micro PDF417 di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to generate micro pdf417 barcode in C# with a complete code
    example, X‑dimension tuning, column configuration, and PNG export.
  headline: How to generate micro pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- image export
title: Cara menghasilkan barcode micro PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan micro pdf417 barcode di C# – panduan langkah demi langkah

Jika Anda perlu **menghasilkan micro pdf417 barcode** dalam aplikasi .NET, tutorial ini menunjukkan solusi siap‑jalankan. Anda akan melihat cara mengonfigurasi X‑dimension barcode, memilih jumlah kolom, dan mengekspor hasilnya sebagai gambar PNG—semua dengan library Aspose.BarCode C#.

Menghasilkan micro pdf417 barcode umum dilakukan ketika Anda harus mengkodekan data ringkas untuk tiket seluler, label inventaris, atau dokumen aman. Pada akhir panduan ini Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat disisipkan ke proyek C# mana pun.

## Prerequisites

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 atau lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7+)
* Visual Studio 2022 (atau IDE apa pun yang mendukung C#)
* Paket NuGet **Aspose.BarCode for .NET** (versi 23.9 atau lebih baru)

Anda dapat menginstal paket tersebut dari baris perintah:

```bash
dotnet add package Aspose.BarCode
```

Tidak ada dependensi tambahan yang diperlukan.

## Step 1: Create a barcode generator for MicroPdf417

Tugas pertama adalah menginstansiasi `BarcodeGenerator` dengan nilai enum `EncodeTypes.MicroPdf417` dan teks yang ingin Anda enkode. Teks dapat berisi karakter Unicode, yang ditangani secara otomatis oleh library.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for MicroPdf417 with the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "Åspóse.Barcóde©"
);
```

**Mengapa ini penting:**  
`EncodeTypes.MicroPdf417` memberi tahu library untuk menggunakan simbolik MicroPdf417 yang kompak, yang menyimpan lebih banyak data dalam jejak yang lebih kecil dibandingkan PDF417 penuh. Menyediakan teks pada saat konstruksi memastikan generator mengetahui tepat apa yang harus dienkode.

## Step 2: Adjust the X‑dimension for finer resolution

X‑dimension (lebar modul) mengontrol berapa banyak piksel yang ditempati setiap kolom barcode. Nilai **2 piksel** menghasilkan barcode resolusi tinggi yang tetap dapat dibaca oleh sebagian besar pemindai.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pro tip:**  
Jika Anda menargetkan tampilan atau printer beresolusi rendah, tingkatkan nilai menjadi 3‑4 piksel untuk menghindari tepi yang blur. Sebaliknya, untuk label berkapasitas tinggi, Anda dapat menurunkannya menjadi 1 piksel, tetapi uji hasilnya dengan pemindai Anda.

## Step 3: Choose the number of columns

MicroPdf417 memungkinkan **1 hingga 4 kolom**. Lebih banyak kolom menghasilkan barcode yang lebih pendek tetapi mengurangi kapasitas koreksi error. Untuk kebanyakan skenario tiket, **4 kolom** memberikan bentuk yang kompak sambil tetap kuat.

```csharp
// Step 3: Choose the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Mengapa Anda mungkin mengubah ini:**  
Jika teks yang dienkode lebih panjang daripada kapasitas default, tingkatkan jumlah kolom untuk mencegah kesalahan overflow. Kurangi jumlah kolom ketika Anda membutuhkan barcode sempit karena ruang terbatas.

## Step 4: Define the output folder and file name

Pilih folder tempat gambar yang dihasilkan akan disimpan. Menggunakan `Path.Combine` menjamin pemisah jalur yang benar di Windows, Linux, dan macOS.

```csharp
using System.IO;

// Step 4: Define the output folder and file name
string outputFolder = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Barcodes"
);
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");
```

**Penanganan kasus tepi:**  
Jika jalur folder tidak valid atau aplikasi tidak memiliki izin menulis, `Directory.CreateDirectory` akan melempar pengecualian. Bungkus logika penyimpanan dalam blok `try/catch` untuk kode produksi.

## Step 5: Save the barcode as a PNG image

Akhirnya, ekspor barcode ke file PNG. PNG mempertahankan tepi tajam dan mendukung transparansi, menjadikannya ideal untuk rendering UI atau pencetakan.

```csharp
using Aspose.BarCode;

// Step 5: Save the generated barcode as a PNG image
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Setelah dijalankan, Anda akan menemukan **MicroPdf417.png** di folder `Barcodes` pada desktop Anda. Membuka file tersebut menampilkan barcode micro pdf417 resolusi tinggi yang siap dipindai.

### Expected output

Gambar yang disimpan akan terlihat serupa dengan ilustrasi di bawah (pola aktual tergantung pada teks yang dienkode).

![Generated micro pdf417 barcode saved as PNG](https://example.com/placeholder-micro-pdf417.png "Screenshot of a generated micro pdf417 barcode saved as a PNG file")

*Alt text:* generate micro pdf417 barcode saved as PNG image

## Full, runnable example

Menggabungkan semua langkah memberikan Anda program tunggal yang berdiri sendiri:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create generator with MicroPdf417 and Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // 2️⃣ Set X‑dimension for high‑resolution output
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose 4 columns to keep the barcode compact
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4️⃣ Prepare output folder on the desktop
        string outputFolder = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "Barcodes"
        );
        Directory.CreateDirectory(outputFolder);
        string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");

        // 5️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Jalankan program (`dotnet run` dari folder proyek) dan verifikasi bahwa file PNG muncul seperti yang diharapkan.

## Common questions and troubleshooting

| Question | Answer |
|----------|--------|
| **Can I generate the barcode as JPEG instead of PNG?** | Ya. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`. JPEG mengompresi gambar tetapi dapat memperkenalkan artefak yang memengaruhi keterbacaan pemindai. |
| **What if the text contains characters not supported by MicroPdf417?** | MicroPdf417 mendukung seluruh rentang Unicode. Jika Anda menerima `ArgumentException`, pastikan string dienkode dengan benar (misalnya, hindari pasangan surrogate yang melebihi kapasitas simbol). |
| **How do I change the foreground color?** | Gunakan `generator.Parameters.Barcode.BarColor = Color.Blue;` sebelum memanggil `Save`. |
| **Is there a way to embed the barcode directly into a PDF?** | Ya. Gunakan `generator.Save(stream, BarCodeImageFormat.Pdf);` atau tambahkan gambar ke dokumen PDF dengan library PDF seperti Aspose.PDF. |
| **My scanner cannot read the barcode—what should I check?** | Pastikan X‑dimension setidaknya 2 piksel untuk kebanyakan pemindai, verifikasi jumlah kolom sesuai rentang yang didukung pemindai, dan pastikan ukuran cetak memenuhi ukuran modul minimum pemindai (biasanya 0.5 mm). |

## Conclusion

Anda kini tahu cara **menghasilkan micro pdf417 barcode** di C# dari awal hingga akhir. Panduan ini mencakup pembuatan `BarcodeGenerator`, mengonfigurasi X‑dimension dan jumlah kolom, menyiapkan jalur output, serta menyimpan hasilnya sebagai PNG. Dengan menyesuaikan pengaturan sekunder—seperti warna bar, format gambar, atau tingkat koreksi error—Anda dapat menyesuaikan barcode untuk aplikasi apa pun, mulai dari tiket seluler hingga label inventaris.

### Next steps

* Bereksperimen dengan nilai **barcode X-dimension** untuk menyeimbangkan ukuran dan keterbacaan.  
* Jelajahi simbolik lain (mis., `EncodeTypes.Pdf417`, `EncodeTypes.QR`) menggunakan pola generator yang sama.  
* Integrasikan PNG yang dihasilkan ke dalam laporan PDF dengan **Aspose.PDF** atau sematkan langsung ke UI WinForms/WPF.  

Happy coding, and enjoy the flexibility that the Aspose.BarCode library brings to barcode generation in C#!

## What Should You Learn Next?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Tutorial Generator Barcode: Cara Menghasilkan PDF417 Barcode di C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Cara Menyimpan Barcode di C# – Menghasilkan PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Cara Menghasilkan PDF417 Barcode – Panduan Pemrograman Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}