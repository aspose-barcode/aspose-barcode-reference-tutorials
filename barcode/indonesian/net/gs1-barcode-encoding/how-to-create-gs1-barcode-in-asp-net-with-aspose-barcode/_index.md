---
category: general
date: 2026-10-24
description: Pelajari cara membuat barcode GS1 di ASP.NET menggunakan Aspose.BarCode.
  Panduan langkah demi langkah untuk menghasilkan barcode dari string dan menampilkan
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: id
lastmod: 2026-10-24
og_description: Cara membuat barcode GS1 di ASP.NET menggunakan Aspose.BarCode. Ikuti
  tutorial ini untuk menghasilkan barcode dari string, mengatur pengaturan visual,
  dan menyimpan file PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Cara membuat barcode GS1 di ASP.NET – panduan lengkap Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Cara membuat kode batang GS1 di ASP.NET dengan Aspose.BarCode
url: /id/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode GS1 di ASP.NET dengan Aspose.BarCode

Jika Anda perlu **cara membuat barcode GS1** dalam aplikasi ASP.NET, panduan ini menunjukkan langkah‑langkah tepatnya. Anda akan melihat cara menghasilkan barcode dari sebuah string, mengonfigurasi tampilan visual, dan menyimpan hasilnya sebagai gambar PNG.

Membuat barcode GS1 tidak memerlukan logika pengkodean khusus. Dengan menggunakan Aspose.BarCode Anda mendapatkan solusi yang andal dan sesuai standar yang bekerja pada .NET 6+ dan kerangka kerja sebelumnya. Tutorial ini mencakup semua hal mulai dari penyiapan proyek hingga memverifikasi output, sehingga Anda dapat menyalin kode langsung ke proyek web Anda sendiri.

## Prasyarat

* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET)
* .NET 6 SDK (atau .NET Framework 4.7.2 ke atas)
* Pengetahuan dasar tentang ASP.NET Core atau ASP.NET Framework
* Lisensi Aspose.BarCode (evaluasi gratis dapat digunakan untuk pengujian)

Tidak diperlukan pustaka pihak ketiga tambahan karena Aspose.BarCode menangani semua pengkodean dan rendering secara internal.

## Langkah 1: Buat proyek ASP.NET baru

Buka Visual Studio dan buat **ASP.NET Core Web App** (pilih templat *Empty*). Untuk proyek Web Forms klasik, kode yang sama dapat digunakan di dalam file code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Menjalankan proyek harus menampilkan *GS1 barcode generator is ready.* di browser. Ini mengonfirmasi bahwa web host berfungsi.

## Langkah 2: Instal Aspose.BarCode via NuGet

Buka **Package Manager Console** dan jalankan:

```powershell
Install-Package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode.Generation`, yang berisi kelas `BarcodeGenerator` yang akan Anda gunakan untuk **generate barcode from string**. Perintah NuGet juga memperbarui file proyek dengan referensi yang diperlukan.

## Langkah 3: Hasilkan barcode sederhana dari sebuah string

Untuk mengilustrasikan penggunaan dasar, buat metode pembantu yang mengembalikan array byte PNG. Metode ini dapat dipanggil dari controller, halaman Razor, atau endpoint apa pun.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Sekarang Anda dapat memanggil `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` dari endpoint mana pun dan menulis byte yang dihasilkan ke respons HTTP. Ini menunjukkan pola **barcode generator asp.net** untuk string apa saja.

## Langkah 4: Cara membuat barcode GS1 – contoh Micro PDF417

Barcode GS1 menyematkan application‑identifiers (AIs) yang menyampaikan informasi produk. Aspose.BarCode mendukung varian Micro PDF417 yang kompatibel dengan GS1, yang ideal untuk representasi data yang kompak.

### 4.1 Siapkan string data GS1

Data GS1 harus dibungkus dalam tanda kurung dengan kode AI. Untuk pengidentifikasi produk (01) dan nomor batch (10) stringnya terlihat seperti:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Tanda kurung merupakan bagian dari standar; Aspose.BarCode memparsenya secara otomatis.

### 4.2 Bangun generator GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Ekspose generator melalui endpoint ASP.NET

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Mengunjungi `https://localhost:5001/gs1barcode` sekarang akan mengalirkan PNG yang dihasilkan. Gambar tersebut sesuai dengan spesifikasi GS1, dan file juga disimpan di disk untuk penggunaan selanjutnya.

## Langkah 5: Merender tipe barcode tambahan

Pendekatan **create barcode with aspose** yang sama bekerja untuk simbol lainnya. Berikut contoh singkat yang membuat QR code dari sebuah URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Anda dapat mengganti `EncodeTypes.QR` dengan `EncodeTypes.Code128`, `EncodeTypes.DataMatrix`, atau tipe lain yang didukung. Parameter visual (`XDimension`, `Resolution`, `Color`) dapat dikonfigurasi melalui objek `Parameters`.

## Langkah 6: Kesalahan umum dan tips praktik terbaik

| Masalah | Mengapa terjadi | Cara menghindarinya |
|-------|----------------|-----------------|
| **Format AI tidak benar** | Kurung yang hilang atau panjang AI yang salah menyebabkan kesalahan pengkodean. | Selalu bangun string GS1 persis seperti yang ditentukan standar. Gunakan metode pembantu untuk menggabungkan AI. |
| **Terlalu banyak kolom** | Micro PDF417 hanya mendukung 1‑4 kolom; mengatur 5 akan menghasilkan pengecualian. | Validasi nilai kolom sebelum menetapkan: `if (columns < 1 || columns > 4) throw …` |
| **Resolusi gambar rendah** | Nilai `XDimension` kecil dapat membuat barcode tidak terbaca pada printer. | Untuk barcode siap cetak, tingkatkan `Resolution` (misalnya, `generator.Parameters.Image.Resolution = 300`). |
| **Masalah jalur file di Linux** | Backslash yang ditulis keras akan rusak pada host non‑Windows. | Gunakan `Path.Combine` untuk membangun jalur file; ia menangani pemisah khusus OS. |
| **Lisensi tidak diterapkan** | Evaluasi gratis menambahkan watermark setelah 30 hari. | Terapkan lisensi Anda lebih awal: `new License().SetLicense("Aspose.BarCode.lic");` |

## Langkah 7: Verifikasi barcode yang dihasilkan

Setelah Anda menjalankan endpoint, buka PNG di penampil gambar apa pun. Untuk memastikan data GS1 terkodekan dengan benar, Anda dapat menggunakan pemindai seluler gratis yang mendukung GS1 Micro PDF417 (banyak aplikasi pemindai barcode mencantumkan simbol ini). Pindai gambar; aplikasi harus mengembalikan:

```
(01)12345678901234
(10)ABCD
```

Jika pemindai melaporkan kesalahan, periksa kembali format AI dan jumlah kolom.

## Kesimpulan

Anda sekarang tahu **cara membuat barcode GS1** dalam lingkungan ASP.NET menggunakan Aspose.BarCode. Tutorial ini mencakup:

* Menyiapkan proyek ASP.NET dan menginstal paket NuGet Aspose.BarCode.  
* Menggunakan **generate barcode from string** untuk barcode umum.  
* Menerapkan **create barcode with aspose** untuk menghasilkan gambar GS1‑compatible Micro PDF417.  
* Menyimpan gambar ke disk dan mengalirkannya melalui endpoint HTTP.  

Dari sini Anda dapat menjelajahi simbol GS1 lainnya (mis., GS1 DataMatrix) atau mengintegrasikan generator ke dalam alur kerja pemrosesan pesanan yang lebih besar. Bereksperimenlah dengan nilai `XDimension` yang berbeda, warna, dan tingkat koreksi kesalahan untuk menyesuaikan merek dan lingkungan pemindaian Anda.

Selamat coding, dan biarkan aplikasi Anda berbicara dalam bahasa universal barcode!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara membuat barcode code 128 dengan GS1 menggunakan Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Cara Membuat Zona Tenang Barcode untuk ITF-14 Menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cara Membuat Barcode ITF-14 .NET – Tutorial Aspose.BarCode Komprehensif](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}