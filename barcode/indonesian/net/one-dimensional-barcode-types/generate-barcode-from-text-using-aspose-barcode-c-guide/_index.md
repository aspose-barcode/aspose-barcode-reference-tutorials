---
category: general
date: 2026-07-15
description: Hasilkan kode batang dari teks menggunakan Aspose.BarCode di C#. Pelajari
  cara mengubah jumlah kolom, menyimpan gambar kode batang, dan membuat solusi kode
  batang Aspose dengan cepat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- how to change column count
- save barcode image
- create barcode aspose
language: id
lastmod: 2026-07-15
og_description: Hasilkan kode batang dari teks menggunakan Aspose.BarCode. Panduan
  ini menunjukkan cara mengubah jumlah kolom, menyimpan gambar kode batang, dan membuat
  kode batang Aspose dalam beberapa baris kode.
og_image_alt: Generate barcode from text example – MicroPdf417 PNG output
og_title: Buat kode batang dari teks dengan Aspose.BarCode – Panduan Cepat C#
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate barcode from text using Aspose.BarCode in C#. Learn how to
    change column count, save barcode image, and create barcode Aspose solutions fast.
  headline: Generate barcode from text using Aspose.BarCode – C# Guide
  type: TechArticle
- description: Generate barcode from text using Aspose.BarCode in C#. Learn how to
    change column count, save barcode image, and create barcode Aspose solutions fast.
  name: Generate barcode from text using Aspose.BarCode – C# Guide
  steps:
  - name: What if my text is longer than the default capacity?
    text: MicroPdf417 automatically switches to a multi‑row layout when the data exceeds
      the maximum per row. You can still control the column count, but the library
      may add extra rows behind the scenes. No extra code needed—just keep an eye
      on the resulting image dimensions.
  - name: How do I change the image format to JPEG or BMP?
    text: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` (or `Bmp`).
      Remember that JPEG introduces compression artifacts, which can affect scanning
      reliability. PNG is the safest default.
  - name: I’m seeing a watermark in the output—what’s wrong?
    text: That’s the evaluation version of Aspose.BarCode. To **create barcode Aspose**
      without watermarks, load a valid license file as shown in the commented line
      of Step 2.
  - name: Can I generate other symbologies (QR, Code128, etc.)?
    text: Absolutely. Just swap `EncodeTypes.MicroPdf417` with any other value from
      the `EncodeTypes` enum, e.g., `EncodeTypes.QR` or `EncodeTypes.Code128`. The
      rest of the code stays the same, which makes the approach highly reusable.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-processing
title: Buat kode batang dari teks menggunakan Aspose.BarCode – Panduan C#
url: /id/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan barcode dari teks menggunakan Aspose.BarCode – Panduan C#

Menghasilkan barcode dari teks menggunakan Aspose.BarCode ternyata sangat mudah. Pada tutorial ini kita akan membahas **cara menghasilkan barcode**, menyesuaikan tata letak kolom, dan akhirnya **menyimpan gambar barcode** sebagai file PNG. Baik Anda sedang membangun sistem tiket, printer label gudang, atau sekadar bereksperimen dengan kode bergaya QR, langkah‑langkah di bawah ini akan membawa Anda ke sana dengan cepat.

## Apa yang Akan Anda Pelajari

- Membuat barcode dari string Unicode apa pun (ya, bahkan “Åspóse.Barcóde©” berfungsi).
- Menyesuaikan **jumlah kolom** untuk MicroPdf417 agar cocok dengan label yang sempit atau lebar.
- Menyimpan hasil ke disk dengan format gambar yang tepat.
- Tips menangani karakter khusus dan jebakan umum saat Anda **membuat barcode Aspose**.

Tanpa alat eksternal, tanpa hack baris perintah—hanya C# biasa dan pustaka Aspose.BarCode.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

1. **.NET 6.0** atau yang lebih baru terpasang (kode ini juga bekerja pada .NET Framework 4.7+).  
2. **Lisensi** untuk Aspose.BarCode, atau Anda dapat memulai dengan versi evaluasi gratis.  
3. Sebuah folder yang dapat ditulisi – kami akan menyebutnya `YOUR_DIRECTORY` dalam contoh.

Jika Anda belum memiliki salah satu dari ini, unduh paket NuGet sekarang:

```bash
dotnet add package Aspose.BarCode
```

Itu saja—tidak ada DLL tambahan yang harus disalin secara manual.

## Langkah 1 – Siapkan Proyek dan Impor

Pertama, buat aplikasi console (atau letakkan kode ini ke proyek C# apa pun). Bagian pentingnya adalah mengimpor namespace yang tepat:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeImageFormat; // for the image format enum
```

Mengapa menggunakan pernyataan `using` ini? `BarcodeGenerator` berada di `Aspose.BarCode.Generation`, sementara enum `BarCodeImageFormat` berada di `Aspose.BarCode`. Menjaga impor tetap rapi membuat kode selanjutnya terbaca seperti bahasa Inggris biasa.

## Langkah 2 – Buat Barcode Generator (cara menghasilkan barcode)

Sekarang kita benar‑benar **menghasilkan barcode dari teks**. Enum `EncodeTypes` memberi tahu Aspose simbol apa yang akan dipakai; di sini kita pilih `MicroPdf417` karena dapat menangani string panjang dalam grid yang kompak.

```csharp
// Step 2: Create a barcode generator for MicroPdf417 with the desired text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

// Optional: If you have a license, load it now to avoid the evaluation watermark
// generator.License = new License(); // generator.License.SetLicense("Aspose.Total.NET.lic");
```

Perhatikan bahwa string mengandung karakter aksen dan simbol hak cipta. Aspose.BarCode secara otomatis meng‑encode Unicode, jadi Anda tidak perlu memproses teks terlebih dahulu.

## Langkah 3 – Sesuaikan Penampilan (cara mengubah jumlah kolom)

MicroPdf417 memungkinkan Anda mengontrol jumlah kolom, yang secara langsung memengaruhi lebar barcode. Tata letak yang lebih rapat cocok untuk label sempit; tata letak yang lebih lebar meningkatkan keterbacaan pada cetakan besar.

```csharp
// Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3b: Define the number of columns for the PDF417 layout (e.g., 4 columns)
generator.Parameters.Barcode.Pdf417.Columns = 4; // <-- how to change column count
```

Mengapa modul 2‑pixel? Itu menghasilkan gambar yang tajam tanpa memperbesar ukuran file. Silakan bereksperimen—nilai antara 1 dan 4 biasanya bekerja dengan baik. Jika Anda perlu jumlah kolom yang berbeda, cukup ubah properti `Columns`; Aspose akan menghitung ulang tata letak secara otomatis.

## Langkah 4 – Simpan Gambar Barcode (simpan gambar barcode)

Setelah generator dikonfigurasi, kita siap **menyimpan gambar barcode**. Metode `Save` menerima jalur file dan enum format gambar. PNG bersifat loss‑less, sehingga barcode tetap tajam meski di‑scale.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Tip cepat: selalu gunakan jalur absolut atau pastikan direktori kerja sesuai harapan; jika tidak, file mungkin berakhir di folder bin dan Anda akan kebingungan mengapa tidak dapat menemukannya.

## Contoh Lengkap yang Dapat Dijalankan

Menggabungkan semuanya, berikut program mandiri yang dapat Anda salin‑tempel ke `Program.cs` dan jalankan:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with Unicode text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Adjust visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // finer modules
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // how to change column count

            // 3️⃣ Choose output location
            string outputPath = @"C:\Temp\MicroPdf417.png";

            try
            {
                // 4️⃣ Persist the image (save barcode image)
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"✅ Barcode generated and saved to: {outputPath}");
            }
            catch (Exception ex)
            {
                // Pro tip: handle I/O errors gracefully
                Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
            }
        }
    }
}
```

**Output yang diharapkan** (console):

```
✅ Barcode generated and saved to: C:\Temp\MicroPdf417.png
```

Dan jika Anda membuka `MicroPdf417.png`, Anda akan melihat barcode MicroPdf417 yang tajam yang meng‑encode string asli, lengkap dengan karakter khusus yang kami masukkan.

## Pertanyaan Umum & Kasus Pinggir

### Bagaimana jika teks saya lebih panjang dari kapasitas default?

MicroPdf417 secara otomatis beralih ke tata letak multi‑baris ketika data melebihi maksimum per baris. Anda masih dapat mengontrol jumlah kolom, tetapi pustaka mungkin menambahkan baris ekstra di belakang layar. Tidak perlu kode tambahan—cukup perhatikan dimensi gambar yang dihasilkan.

### Bagaimana cara mengubah format gambar ke JPEG atau BMP?

Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` (atau `Bmp`). Ingat bahwa JPEG menambahkan artefak kompresi, yang dapat memengaruhi keandalan pemindaian. PNG adalah pilihan default yang paling aman.

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg);
```

### Saya melihat watermark pada output—apa yang salah?

Itu adalah versi evaluasi Aspose.BarCode. Untuk **membuat barcode Aspose** tanpa watermark, muat file lisensi yang valid seperti yang ditunjukkan pada baris komentar di Langkah 2.

### Bisakah saya menghasilkan simbol lain (QR, Code128, dll.)?

Tentu saja. Cukup ganti `EncodeTypes.MicroPdf417` dengan nilai lain dari enum `EncodeTypes`, misalnya `EncodeTypes.QR` atau `EncodeTypes.Code128`. Sisanya tetap sama, sehingga pendekatan ini sangat dapat digunakan kembali.

## Tips Profesional untuk Generasi Barcode Siap Produksi

- **Cache generator** jika Anda membuat banyak barcode dengan pengaturan yang sama; ini mengurangi beban pembuatan objek.
- **Validasi string input** untuk batas panjang yang spesifik pada simbol yang dipilih (Aspose akan melempar `ArgumentException` jika terlalu panjang).
- **Gunakan pernyataan `using`** atau panggil `Dispose` pada generator setelah selesai untuk membebaskan sumber daya native dengan cepat.
- **Atur DPI** melalui `generator.Parameters.ImageResolution.DpiX/DpiY` jika Anda memerlukan cetakan resolusi tinggi untuk label besar.

## Kesimpulan

Sekarang Anda sudah tahu **cara menghasilkan barcode dari teks** dengan Aspose.BarCode, **cara mengubah jumlah kolom**, dan cara **menyimpan gambar barcode** sebagai PNG dengan benar. Contoh lengkap yang dapat dijalankan di atas memperlihatkan implementasi bersih yang siap produksi.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang memperluas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}