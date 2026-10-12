---
category: general
date: 2026-10-12
description: Buat barcode PNG dalam C# dengan cepat menggunakan panduan langkah demi
  langkah ini untuk menghasilkan barcode PDF417 dan menyimpannya sebagai gambar PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- generate pdf417 barcode
- pdf417 barcode image
- how to generate pdf417
- c# pdf417 generator
language: id
lastmod: 2026-10-12
og_description: Buat barcode PNG dalam C# dengan contoh generator PDF417 lengkap.
  Pelajari cara menghasilkan barcode PDF417, menyesuaikannya, dan menyimpan gambar
  barcode sebagai PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Buat barcode PNG di C# – tutorial lengkap generator PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Create barcode png in C# quickly with this step‑by‑step guide to generate
    PDF417 barcodes and save them as PNG images.
  headline: Create barcode png in C# using a PDF417 generator
  type: TechArticle
- description: Create barcode png in C# quickly with this step‑by‑step guide to generate
    PDF417 barcodes and save them as PNG images.
  name: Create barcode png in C# using a PDF417 generator
  steps:
  - name: Why each line matters
    text: '* **Initialize the generator** – This tells the library you want a PDF417
      barcode (`EncodeTypes.Pdf417`) and supplies the text to encode. * **XDimension**
      – Controls the width of the smallest bar (the “module”). Setting it to `2` pixels
      keeps the image compact while retaining readability. * **Column'
  - name: Changing the image format
    text: If you need a different format (e.g., JPEG or BMP), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Bmp`. The same code still
      **creates barcode png** when you keep the PNG enum.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels from 0 to 8. Higher levels increase
      resilience to damage but also enlarge the barcode.
  - name: Adding a quiet zone (margin)
    text: 'Some scanners require a white border around the barcode. You can add it
      like this:'
  - name: Generating multiple barcodes in a loop
    text: When you need to **generate pdf417 barcode** images for a list of values,
      wrap the generator logic in a `foreach` loop and change the `EncodeTypes.Pdf417`
      data each iteration.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Buat barcode PNG di C# menggunakan generator PDF417
url: /id/net/compact-pdf417-encoding/create-barcode-png-in-c-using-a-pdf417-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat barcode png di C# menggunakan generator PDF417

Jika Anda perlu **membuat barcode png** file dari kode C#, tutorial ini menunjukkan secara tepat cara menghasilkan barcode PDF417 dan menyimpannya sebagai gambar PNG. Baik Anda sedang membangun sistem tiket, printer label gudang, atau aplikasi pemindaian seluler, Anda akan mendapatkan contoh siap‑jalankan yang menghasilkan barcode PNG yang bersih.

Anda juga akan belajar cara menyesuaikan ukuran barcode, jumlah kolom, dan mode kompak, sehingga **gambar barcode pdf417** yang dihasilkan memenuhi persyaratan tepat proyek Anda. Panduan ini mencakup alur kerja lengkap mulai dari menginstal pustaka hingga memverifikasi output.

## Apa yang Anda butuhkan

* .NET 6.0 SDK atau yang lebih baru (kode juga dapat bekerja dengan .NET Framework 4.6+)
* Visual Studio 2022, VS Code, atau IDE C# apa pun yang Anda sukai
* Paket NuGet Aspose.BarCode untuk .NET (atau pustaka lain yang mendukung PDF417)
* Izin menulis ke folder tempat file PNG akan disimpan

Prasyarat ini minimal, dan langkah-langkahnya bekerja di Windows, Linux, dan macOS.

## Langkah 1: Instal pustaka barcode

Cara paling umum untuk **menghasilkan barcode pdf417** di C# adalah dengan menggunakan pustaka Aspose.BarCode. Instal melalui .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menyediakan kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini. Jika Anda lebih suka vendor lain, cari kelas yang mendukung `EncodeTypes.Pdf417`.

## Langkah 2: Buat program konsol C# lengkap

Berikut adalah program mandiri yang **membuat barcode png** file. Simpan file sebagai `Program.cs` dan jalankan dengan `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

// Namespace and class are optional for a single‑file program, but they improve readability.
namespace Pdf417PngDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text.
            // This is the core of how to generate pdf417 barcodes.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,          // PDF417 symbology
                "Compact example"           // Data encoded in the barcode
            );

            // 2️⃣ Set the module (X) dimension in pixels.
            // A smaller X dimension produces a tighter barcode, which is useful for compact images.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns.
            // Fewer columns make the barcode taller; more columns make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact mode by truncating the barcode data.
            // Compact mode reduces the overall size of the barcode image.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output path and save the barcode as a PNG.
            // This step completes the create barcode png workflow.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode PNG created at: {outputPath}");
        }
    }
}
```

### Mengapa setiap baris penting

* **Initialize the generator** – Ini memberi tahu pustaka bahwa Anda menginginkan barcode PDF417 (`EncodeTypes.Pdf417`) dan menyediakan teks yang akan dienkode.  
* **XDimension** – Mengontrol lebar bar terkecil (“module”). Menetapkannya ke `2` piksel membuat gambar tetap kompak sambil mempertahankan keterbacaan.  
* **Columns** – PDF417 dapat membagi data ke beberapa kolom. Nilai `3` menyeimbangkan tinggi dan lebar untuk kebanyakan printer label.  
* **Truncate** – Mengaktifkan mode kompak menghapus padding yang tidak diperlukan, yang penting ketika Anda menginginkan **gambar barcode pdf417** kecil.  
* **Save** – Metode `Save` menulis barcode ke disk dalam format PNG, mencapai tujuan **membuat barcode png**.

## Langkah 3: Jalankan program dan verifikasi output

Jalankan program:

```bash
dotnet run
```

Anda akan melihat pesan konfirmasi di konsol, dan file bernama `CompactPdf417.png` akan muncul di folder root proyek.

Buka PNG dengan penampil gambar apa pun. Anda akan melihat barcode PDF417 kompak yang mengenkode string *Compact example*. Gambar ini dapat langsung digunakan di HTML, dicetak pada label, atau disematkan dalam PDF.

## Langkah 4: Menyesuaikan barcode untuk berbagai skenario

### Mengubah format gambar

Jika Anda memerlukan format lain (mis., JPEG atau BMP), ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp`. Kode yang sama masih **membuat barcode png** ketika Anda tetap menggunakan enum PNG.

### Menyesuaikan tingkat koreksi kesalahan

PDF417 mendukung tingkat koreksi kesalahan dari 0 hingga 8. Tingkat yang lebih tinggi meningkatkan ketahanan terhadap kerusakan tetapi juga memperbesar barcode.

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // medium‑high correction
```

### Menambahkan zona tenang (margin)

Beberapa pemindai memerlukan batas putih di sekitar barcode. Anda dapat menambahkannya seperti ini:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2;
generator.Parameters.Barcode.Pdf417.Pdf417Margin = 10; // 10 pixels of quiet zone
```

### Menghasilkan banyak barcode dalam loop

Ketika Anda perlu **menghasilkan barcode pdf417** gambar untuk daftar nilai, bungkus logika generator dalam loop `foreach` dan ubah data `EncodeTypes.Pdf417` setiap iterasi.

```csharp
string[] values = { "Item001", "Item002", "Item003" };
int index = 0;
foreach (var val in values)
{
    generator.CodeText = val;
    string fileName = $"Barcode_{index}.png";
    generator.Save(fileName, BarCodeImageFormat.Png);
    index++;
}
```

## Kesalahan umum dan cara menghindarinya

| Gejala | Penyebab yang mungkin | Solusi |
|---------|--------------|-----|
| Barcode muncul buram | XDimension terlalu rendah (mis., 1 piksel) | Tingkatkan `XDimension.Pixels` menjadi setidaknya 2 |
| Scanner tidak dapat membaca barcode | Tidak ada zona tenang atau koreksi kesalahan tidak cukup | Atur `Pdf417Margin` dan tingkatkan `ErrorLevel` |
| File PNG kosong atau rusak | Folder output tidak ada atau tidak memiliki izin menulis | Pastikan direktori ada atau gunakan path absolut |
| Ukuran barcode tidak terduga | Nilai Columns tidak cocok dengan panjang data | Sesuaikan `Columns` atau biarkan pustaka menghitung otomatis dengan menghilangkan properti tersebut |

Menangani masalah ini sejak awal memastikan setiap **gambar barcode pdf417** yang Anda hasilkan berfungsi secara andal di produksi.

## Cara menghasilkan barcode pdf417 dalam bahasa lain (referensi cepat)

* **Java** – Gunakan `BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "text");` dan panggil `generator.save("file.png", BarCodeImageFormat.Png);`
* **Python** – Dengan SDK `aspose-barcode-cloud`, panggil `generator.save("file.png", BarCodeImageFormat.Png)`.
* **JavaScript** – Pustaka Aspose.BarCode untuk JavaScript menyediakan kelas `Pdf417` serupa.

Potongan kode ini menunjukkan bahwa pola **c# pdf417 generator** konsisten di seluruh platform, memudahkan penggunaan kembali pengetahuan.

## Kesimpulan

Anda kini tahu cara **membuat barcode png** file di C# dengan mengonfigurasi generator PDF417, menyesuaikan dimensi, mengaktifkan mode kompak, dan menyimpan hasilnya sebagai gambar PNG. Contoh lengkap menunjukkan alur kerja standar untuk **c# pdf417 generator**, dan tip tambahan memungkinkan Anda menyesuaikan solusi untuk tingkat koreksi kesalahan yang berbeda, format gambar, serta skenario pemrosesan batch.

Selanjutnya, pertimbangkan untuk menjelajahi:

* Menambahkan teks yang dapat dibaca manusia di bawah barcode (`Generator.Parameters.Barcode.BarcodeImageFormat`).
* Menyematkan PNG langsung ke dalam PDF menggunakan `Aspose.Pdf`.
* Mengintegrasikan pembuatan barcode ke dalam API ASP.NET Core sehingga klien dapat meminta barcode sesuai permintaan.

Selamat coding, dan nikmati fleksibilitas menghasilkan PNG barcode PDF417 berkualitas tinggi dalam aplikasi .NET Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat barcode PDF417 di C# dan menyimpannya sebagai PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-and-save-it-as-png/)
- [Cara menghasilkan barcode PDF417 di C# – panduan langkah‑demi‑langkah](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Cara membuat barcode micro pdf417 di C# dan menyimpannya sebagai PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}