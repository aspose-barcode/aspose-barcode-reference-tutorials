---
category: general
date: 2026-07-15
description: Buat kode batang PDF417 dengan cepat menggunakan C#. Pelajari cara menghasilkan
  kode batang dari teks, menyesuaikan ukuran kode batang, dan mengatur dimensi kode
  batang khusus dalam hitungan menit.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- generate barcode from text
- adjust barcode size
- custom barcode dimensions
language: id
lastmod: 2026-07-15
og_description: Hasilkan kode batang PDF417 dalam C# secara instan. Panduan ini menunjukkan
  cara menghasilkan kode batang dari teks, menyesuaikan ukuran kode batang, dan menerapkan
  dimensi kode batang khusus.
og_image_alt: Screenshot of a PDF417 barcode generated with custom dimensions using
  C# code
og_title: Buat Kode Bar PDF417 di C# – Tutorial Pemrograman Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly with C#. Learn how to generate barcode
    from text, adjust barcode size, and set custom barcode dimensions in minutes.
  headline: Generate PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Membuat Kode Barcode PDF417 di C# – Panduan Lengkap Langkah demi Langkah
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Barcode PDF417 di C# – Panduan Lengkap Langkah‑per‑Langkah

Pernahkah Anda perlu **generate PDF417 barcode** tetapi tidak yakin pengaturan mana yang harus diubah? Anda bukan satu-satunya—banyak pengembang mengalami hal yang sama saat pertama kali bermain dengan barcode 2‑D. Kabar baik? Dengan beberapa baris C# Anda dapat mengubah string apa pun menjadi gambar PDF417 yang dapat dipindai, mengontrol ukuran tepatnya, dan bahkan menentukan tata letak kolom‑baris khusus.

Dalam tutorial ini kami akan menjelaskan cara **generate barcode from text**, menyesuaikan ukuran barcode, dan mengatur dimensi barcode khusus — semua menggunakan library Aspose.BarCode yang populer. Pada akhir tutorial Anda akan memiliki contoh siap‑jalankan yang dapat Anda masukkan ke proyek .NET mana pun.

![Generate PDF417 barcode example](https://example.com/og-image.png "Generate PDF417 barcode example")

## Apa yang Akan Anda Bangun

- Sebuah barcode PDF417 yang mengkodekan string `Åspóse.Barcóde©`.
- Kontrol presisi atas X‑dimension (lebar piksel setiap modul).
- Tata letak khusus dengan 4 kolom dan 9 baris.
- File PNG yang disimpan ke disk.

Tanpa layanan eksternal, tanpa trik tongkat sihir—hanya kode C# biasa yang dapat Anda kompilasi sekarang juga.

## Prasyarat

- .NET 6.0 atau lebih baru (kode ini juga berfungsi pada .NET Framework 4.8).
- Visual Studio 2022 atau IDE apa pun yang mendukung C#.
- Aspose.BarCode untuk .NET (versi percobaan gratis atau berlisensi). Instal melalui NuGet:

```bash
dotnet add package Aspose.BarCode
```

Itu saja—setelah paket direferensikan Anda siap melanjutkan.

## Langkah 1 – Generate PDF417 Barcode dengan Data Teks

Hal pertama yang kita butuhkan adalah sebuah instance `BarcodeGenerator` yang mengetahui bahwa kita menggunakan simbol PDF417 dan teks tepat yang ingin kita enkode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Mengapa ini penting:**  
> `EncodeTypes.Pdf417` memberi tahu library untuk menggunakan format PDF417 2‑D, sementara argumen kedua adalah payload **generate barcode from text**. Apa pun yang Anda berikan di sini menjadi data yang disimpan dalam matriks barcode.

## Langkah 2 – Sesuaikan Ukuran Barcode (X‑Dimension)

Jika Anda pernah mencetak barcode yang terlihat terlalu kecil pada struk, Anda tahu frustrasi ketika pemindai tidak dapat menemukannya. Properti `XDimension` mengontrol lebar satu modul (kotak hitam atau putih terkecil) dalam piksel.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Tip pro:**  
> Nilai 2 px bekerja dengan baik untuk kebanyakan skenario tampilan layar. Untuk cetakan resolusi tinggi Anda dapat meningkatkan menjadi 3 atau 4 px. Ingatlah bahwa X‑dimension yang lebih besar meningkatkan ukuran gambar secara keseluruhan.

## Langkah 3 – Atur Dimensi Barcode Kustom (Kolom & Baris)

PDF417 memungkinkan Anda menentukan berapa banyak kolom dan baris yang harus ditempati barcode. Di sinilah **custom barcode dimensions** berperan. Mengubah nilai-nilai ini dapat membantu Anda menyesuaikan barcode ke ruang UI yang sempit atau memenuhi ukuran label tertentu.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Apa yang terjadi di balik layar?**  
> Library mendistribusikan ulang data yang dienkode ke seluruh grid yang ditentukan. Lebih sedikit kolom berarti barcode lebih tinggi; lebih banyak baris membuatnya lebih pendek. Bereksperimenlah dengan angka-angka hingga keseimbangan visual terasa tepat untuk aplikasi Anda.

## Langkah 4 – Simpan Gambar Barcode

Sekarang setelah kami mengonfigurasi semuanya, kami cukup meminta generator untuk menulis file PNG. PNG bersifat lossless, sehingga ketajaman modul tetap terjaga.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

Saat Anda menjalankan program, Anda akan melihat file di `C:\Barcodes\CustomLayout.png` yang tampak mirip dengan tangkapan layar di atas. Memindainya dengan pembaca yang kompatibel dengan PDF417 apa pun akan mengembalikan string asli `Åspóse.Barcóde©`.

## Contoh Lengkap yang Berfungsi

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke aplikasi console. Program ini mencakup semua direktif using dan penanganan error yang Anda harapkan dalam kode produksi.

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

### Output yang Diharapkan

Menjalankan kode akan mencetak:

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…dan membuat PNG yang dapat dibuka di penampil gambar apa pun. Jika Anda memindainya dengan aplikasi seluler (mis., “Barcode Scanner” di iOS/Android), teks yang terdekripsi harus persis **Åspóse.Barcóde©**.

## Pertanyaan Umum & Kasus Tepi

| Question | Answer |
|----------|--------|
| **Bisakah saya menggunakan format gambar yang berbeda?** | Ya—`BarCodeImageFormat.Jpeg`, `Bmp`, `Gif`, atau `Svg` semuanya didukung. Cukup ubah argumen kedua dari `Save`. |
| **Bagaimana jika teks saya mengandung karakter Unicode?** | Aspose.BarCode sepenuhnya mendukung UTF‑8, jadi contoh dengan `Å` dan `©` langsung berfungsi. |
| **Bagaimana cara mengubah tingkat koreksi kesalahan?** | Gunakan `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (tingkat 0‑8). Tingkat yang lebih tinggi meningkatkan redundansi tetapi juga ukuran. |
| **Saya membutuhkan latar belakang transparan—apakah bisa?** | Setel `generator.Parameters.Barcode.Image.TransparentBackground = true;` sebelum menyimpan. |
| **Apakah ada cara untuk menyematkan barcode langsung ke PDF?** | Tentu saja. Ganti pemanggilan `Save` dengan `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` dan Anda akan mendapatkan PDF satu halaman yang berisi barcode. |

## Kesimpulan

Anda kini tahu cara **generate PDF417 barcode** di C# dari string apa pun, **menyesuaikan ukuran barcode**, dan menerapkan **custom barcode dimensions** untuk memenuhi kebutuhan tata letak Anda. Alur empat langkah—inisialisasi, ukuran, tata letak, simpan—mencakup alur kerja inti untuk kebanyakan skenario barcode 2‑D.

Apa selanjutnya? Coba ganti `EncodeTypes.Pdf417` dengan `EncodeTypes.QR` atau `EncodeTypes.Code128` untuk melihat bagaimana API beradaptasi. Bereksperimenlah dengan nilai `XDimension` yang berbeda, mainkan matriks kolom/baris, atau sematkan gambar ke dalam laporan PDF. Kemungkinannya hampir tak terbatas, dan kini Anda memiliki fondasi yang kuat untuk membangun.

Ada pertanyaan lebih lanjut, atau menemukan trik cerdas saat bermain dengan PDF417? Tinggalkan komentar di bawah—mari teruskan diskusi. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara Menghasilkan Barcode - Jenis Barcode Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/)
- [Menghasilkan Barcode DataMatrix – Panduan Pro dengan Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}