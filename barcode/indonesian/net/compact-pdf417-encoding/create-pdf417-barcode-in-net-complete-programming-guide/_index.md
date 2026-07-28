---
category: general
date: 2026-07-27
description: Buat kode batang PDF417 dengan cepat menggunakan .NET. Pelajari cara
  menghasilkan kode batang, menyesuaikan ukuran kode batang, dan menggunakan generator
  kode batang .NET untuk output PDF417 yang kompak.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- barcode generator .net
- how to generate barcode
- adjust barcode size
- generate pdf417 barcode
language: id
lastmod: 2026-07-27
og_description: Buat kode batang PDF417 di .NET hari ini. Ikuti panduan ini untuk
  menghasilkan kode batang, menyesuaikan ukuran kode batang, dan menguasai generator
  kode batang .NET untuk hasil yang kompak.
og_image_alt: Screenshot showing a compact PDF417 barcode generated with .NET code
og_title: Buat Kode Bar PDF417 di .NET – Tutorial Langkah-demi-Langkah Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create PDF417 barcode quickly with .NET. Learn how to generate barcode,
    adjust barcode size, and use a barcode generator .NET for compact PDF417 output.
  headline: Create PDF417 Barcode in .NET – Complete Programming Guide
  type: TechArticle
tags:
- barcode
- pdf417
- .net
- Aspose
title: Buat Kode Bar PDF417 di .NET – Panduan Pemrograman Lengkap
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-in-net-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Kode Batang PDF417 di .NET – Panduan Pemrograman Lengkap

Pernah membutuhkan untuk **create PDF417 barcode** dalam aplikasi .NET tetapi tidak yakin harus mulai dari mana? Anda tidak sendirian—para pengembang terus bertanya *how to generate barcode* yang cocok dengan tata letak tertentu tanpa membuat ukuran file menjadi besar.  

Dalam tutorial ini kami akan membahas contoh langsung yang menunjukkan cara **create PDF417 barcode** menggunakan perpustakaan **barcode generator .NET** yang populer, menyesuaikan dimensi, dan menghasilkan gambar PNG yang kompak. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat dimasukkan ke dalam proyek C# mana pun.

## Apa yang Akan Anda Pelajari

- Instal dan referensikan paket **barcode generator .NET** (Aspose.BarCode)
- Siapkan encoder **PDF417** dengan teks khusus
- **Adjust barcode size** dengan mengubah X‑dimension dan jumlah kolom
- Aktifkan **compact mode** (flag `Truncate`) untuk menjaga ukuran gambar tetap kecil
- Simpan hasilnya sebagai file PNG dan verifikasi output

Tidak diperlukan pengalaman sebelumnya dengan kode batang; pengetahuan dasar C# sudah cukup. Mari kita mulai.

---

## Langkah 1: Siapkan Proyek Anda dan Tambahkan Perpustakaan Kode Batang

Sebelum kita dapat **create PDF417 barcode**, kita memerlukan perpustakaan yang dapat berkomunikasi dengan simbol PDF417. Aspose.BarCode untuk .NET adalah pilihan yang solid karena mendukung semua parameter yang akan kita sesuaikan nanti.

```csharp
// Add the NuGet package (run this in the Package Manager Console)
> Install-Package Aspose.BarCode

// In your C# file, bring the namespaces into scope
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

> **Pro tip:** Jika Anda menggunakan .NET 6 atau yang lebih baru, Anda juga dapat menambahkan paket melalui CLI: `dotnet add package Aspose.BarCode`.

Menyiapkan paket adalah langkah satu kali, dan setelah itu Anda akan siap untuk **generate PDF417 barcode** pada platform apa pun yang menjalankan .NET.

## Langkah 2: Inisialisasi Generator PDF417 dengan Data Anda

Sekarang perpustakaan sudah direferensikan, kita dapat membuat instance `BarcodeGenerator`. Konstruktornya menerima dua argumen: tipe enkoding dan teks yang ingin Anda sematkan. Di sinilah kita benar‑benar **create PDF417 barcode**.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
// Note the special characters – the library handles Unicode out of the box.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Verify that the generator was created successfully
if (generator == null)
{
    throw new InvalidOperationException("Failed to initialise the barcode generator.");
}
```

Mengapa ini penting: PDF417 adalah kode batang linear bertumpuk yang dapat menyimpan banyak data. Dengan memberi Unicode, Anda sudah menunjukkan bahwa **barcode generator .NET** dapat menangani karakter internasional—sesuatu yang banyak perpustakaan lama kesulitan.

## Langkah 3: **Adjust Barcode Size** – X‑Dimension, Kolom, dan Compact Mode

Kesalahan umum saat **how to generate barcode** adalah menghasilkan gambar besar yang tidak muat pada label atau layar. Kabar baiknya, Aspose API memberi Anda kontrol yang sangat detail.

```csharp
// Step 3A: Set the X‑dimension (module width) in pixels – this directly affects barcode width
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module, a good balance for most screens

// Step 3B: Configure PDF417‑specific options
generator.Parameters.Barcode.Pdf417.Columns = 3;    // Fewer columns → narrower barcode
generator.Parameters.Barcode.Pdf417.Truncate = true; // Compact mode – drops empty rows

// Optional: If you need a taller barcode, increase the rows (default is 3‑5)
generator.Parameters.Barcode.Pdf417.Rows = 5;
```

**Apa yang terjadi di balik layar?**  
- **X‑Dimension** menentukan lebar bar terkecil. Nilai yang lebih kecil memperkecil kode batang tetapi dapat memengaruhi keterbacaan pada printer beresolusi rendah.  
- **Columns** mengontrol berapa banyak irisan vertikal data dibagi. Lebih sedikit kolom = kode batang lebih sempit, tetapi Anda mungkin perlu menambah baris untuk menyimpan semua data.  
- **Truncate (compact mode)** menghapus baris yang tidak terpakai, mengurangi ukuran gambar akhir. Itulah mengapa kita dapat **generate PDF417 barcode** yang muat dalam kotak 200 × 200 px.

## Langkah 4: Simpan Gambar Kode Batang sebagai PNG (atau format lain)

Dengan generator yang dikonfigurasi, langkah terakhir adalah menulis gambar ke disk. PNG bersifat lossless, menjadikannya sempurna untuk kode batang yang tajam.

```csharp
// Step 4: Save the barcode image as PNG
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);

// Quick sanity check – open the file automatically (Windows only)
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
    Process.Start(new ProcessStartInfo(outputPath) { UseShellExecute = true });
}
```

**Expected output:** File PNG 200 × 200 px yang menampilkan PDF417 barcode kompak yang mengenkode string `Åspóse.Barcóde©`. Pindai dengan pembaca PDF417 apa pun (aplikasi seluler berfungsi baik) dan Anda akan mendapatkan teks yang tepat.

---

## Langkah 5: Bungkus Semua – Metode Helper yang Dapat Digunakan Kembali

Jika Anda menemukan diri Anda perlu **create PDF417 barcode** di beberapa tempat, ekstrak logika ke dalam metode helper. Ini juga menunjukkan **how to generate barcode** dengan cara yang bersih dan dapat dipelihara.

```csharp
/// <summary>
/// Generates a compact PDF417 barcode image and returns the file path.
/// </summary>
/// <param name="data">The text to encode (Unicode supported).</param>
/// <param name="outputFile">Full path where the PNG will be saved.</param>
/// <param name="xDimPixels">Desired X‑dimension in pixels (default 2).</param>
/// <param name="columns">Number of columns (default 3).</param>
/// <returns>The absolute path to the generated PNG.</returns>
public static string GenerateCompactPdf417(string data, string outputFile, int xDimPixels = 2, int columns = 3)
{
    // Initialise generator
    var gen = new BarcodeGenerator(EncodeTypes.Pdf417, data);

    // Adjust size
    gen.Parameters.Barcode.XDimension.Pixels = xDimPixels;
    gen.Parameters.Barcode.Pdf417.Columns = columns;
    gen.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

    // Save image
    gen.Save(outputFile, BarCodeImageFormat.Png);
    return Path.GetFullPath(outputFile);
}
```

Anda dapat sekarang memanggil:

```csharp
string path = GenerateCompactPdf417("Sample123", "MyPdf417.png");
Console.WriteLine($"Barcode saved to: {path}");
```

---

## Pertanyaan Umum & Kasus Tepi

| Pertanyaan | Jawaban |
|------------|---------|
| **Bagaimana jika kode batang menjadi tidak terbaca setelah memperkecil X‑dimension?** | Tingkatkan `XDimension` menjadi 3 px atau naikkan DPI gambar output (`generator.Save(..., 300)` untuk resolusi lebih tinggi). |
| **Apakah saya dapat menghasilkan format lain (mis., JPEG atau BMP)?** | Tentu—ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif`. PNG direkomendasikan untuk kualitas lossless. |
| **Apakah saya memerlukan lisensi untuk Aspose.BarCode?** | Perpustakaan berfungsi dalam mode evaluasi dengan watermark. Untuk produksi, beli lisensi untuk menghapus watermark dan membuka fitur lanjutan. |
| **Bagaimana cara menyematkan kode batang ke dalam dokumen PDF?** | Gunakan Aspose.PDF: buat `PdfPage`, tambahkan gambar kode batang sebagai `ImageStamp`, dan simpan PDF. |
| **Bagaimana jika data saya melebihi kapasitas maksimum PDF417?** | PDF417 dapat menampung hingga ~1.850 karakter. Jika Anda melebihi itu, pertimbangkan membagi data ke beberapa kode batang atau menggunakan simbol dengan kapasitas lebih tinggi seperti DataMatrix. |

## Kesimpulan

Kami baru saja **created PDF417 barcode** di .NET dari awal, belajar cara **adjust barcode size**, dan melihat bagaimana perpustakaan **barcode generator .NET** memudahkan penggunaan compact mode. Dengan menyesuaikan X‑dimension, jumlah kolom, dan flag `Truncate`, Anda dapat menyesuaikan kode batang dengan batas visual apa pun sambil tetap menjaga keandalan pemindaian.

Langkah selanjutnya? Coba ganti format output ke SVG untuk skalabilitas tak terbatas, atau sematkan PNG langsung ke dalam laporan PDF menggunakan Aspose.PDF. Anda juga dapat menjelajahi simbol lain—QR, Code128, atau DataMatrix—dengan menggunakan kelas `BarcodeGenerator` yang sama.

Selamat coding, dan silakan tinggalkan komentar jika Anda mengalami kendala saat **how to generate barcode** untuk skenario spesifik Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Kode Batang – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara menghasilkan kode batang Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara Menghasilkan Kode Batang DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}