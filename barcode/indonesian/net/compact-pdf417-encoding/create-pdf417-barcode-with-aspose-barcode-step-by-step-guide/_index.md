---
category: general
date: 2026-08-25
description: Buat kode batang PDF417 menggunakan Aspose.BarCode di C#. Tutorial ini
  menjelaskan cara menghasilkan kode batang PDF417 dengan cepat menggunakan contoh
  kode yang jelas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- create barcode with aspose
language: id
lastmod: 2026-08-25
og_description: Buat kode batang PDF417 menggunakan Aspose.BarCode di C#. Pelajari
  cara menghasilkan kode batang PDF417 dengan contoh lengkap yang dapat dijalankan.
og_image_alt: Screenshot of a generated PDF417 barcode created with Aspose.BarCode
og_title: Buat kode batang PDF417 dengan Aspose.BarCode – panduan singkat
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create PDF417 barcode using Aspose.BarCode in C#. This tutorial explains
    how to generate PDF417 barcode quickly with clear code examples.
  headline: Create PDF417 barcode with Aspose.BarCode – step-by-step guide
  type: TechArticle
tags:
- Aspose.BarCode
- PDF417
- C#
title: Membuat kode batang PDF417 dengan Aspose.BarCode – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat barcode PDF417 dengan Aspose.BarCode – panduan langkah demi langkah

Jika Anda perlu **membuat barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan cara menghasilkan barcode PDF417 dengan Aspose.BarCode. Anda akan melihat contoh lengkap yang siap dijalankan, memahami mengapa setiap pengaturan penting, dan belajar cara menyesuaikan kode untuk berbagai skenario.

Tutorial ini mencakup:

* Menambahkan paket Aspose.BarCode ke proyek Anda  
* Mengonfigurasi generator barcode (teks, X‑dimension, kolom)  
* Menyimpan barcode sebagai file PNG  
* Menangani karakter Unicode dan jebakan umum  

Tidak diperlukan dokumentasi eksternal—semua yang Anda butuhkan sudah disertakan di bawah ini.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
* Versi terbaru paket **Aspose.BarCode for .NET** NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* IDE atau editor pilihan Anda (Visual Studio, VS Code, Rider, dll.)

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru dan impor namespace Aspose.BarCode yang diperlukan.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts here.
```

*`Aspose.BarCode`* berisi kelas inti, sementara *`Aspose.BarCode.Generation`* menyediakan `BarcodeGenerator` yang digunakan untuk membuat barcode.

## Langkah 2: Buat generator barcode PDF417 dengan teks yang diinginkan

Baris pertama membangun `BarcodeGenerator` untuk simbolologi PDF417 dan menetapkan data yang ingin Anda enkode.

```csharp
            // Step 2: Create a PDF417 barcode generator with the desired text
            // Unicode characters such as Å, ó, and © are supported out of the box.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Mengapa ini penting:**  
PDF417 dapat menyimpan hingga 1 850 karakter, menjadikannya cocok untuk dokumen, tiket, atau ID. Mengirimkan teks langsung ke konstruktor memastikan data dienkode dengan benar sebelum pengaturan visual apa pun diterapkan.

## Langkah 3: Konfigurasikan parameter visual (X‑dimension dan kolom)

Penyetelan tampilan meningkatkan keandalan pemindaian dan menyesuaikan dengan kebutuhan tata letak.

```csharp
            // Step 3: Set the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 4: Define the number of columns for the PDF417 barcode
            // Fewer columns produce a taller barcode; more columns make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
```

* **X‑dimension** – Mengontrol lebar satu modul barcode. Nilai `2` piksel merupakan keseimbangan yang baik antara keterbacaan dan ukuran file untuk kebanyakan layar.  
* **Columns** – Menentukan berapa banyak kolom data yang akan dimiliki barcode. Sesuaikan nilai ini berdasarkan jumlah data dan ruang yang tersedia pada media target.

## Langkah 4: Simpan gambar barcode

Pilih format gambar yang sesuai dengan alur kerja Anda selanjutnya. PNG mempertahankan kualitas lossless, yang ideal untuk pemrosesan atau pencetakan lebih lanjut.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

Metode `Save` menulis gambar ke jalur yang ditentukan. Jika Anda memerlukan format lain (JPEG, BMP, SVG), ganti `BarCodeImageFormat.Png` dengan nilai enum yang sesuai.

## Contoh lengkap yang dapat dijalankan

Salin seluruh blok kode di bawah ini ke dalam `Program.cs` pada proyek konsol baru, jalankan `dotnet run`, dan Anda akan menemukan `Pdf417Basic.png` di folder proyek.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with Unicode text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Adjust visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Save as PNG
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Output yang diharapkan

Menjalankan program menghasilkan file PNG yang mirip dengan ilustrasi di bawah ini.

![Create PDF417 barcode example](https://example.com/images/pdf417-sample.png "Create PDF417 barcode example")

*Gambar menunjukkan barcode PDF417 yang jelas dengan tiga kolom dan lebar modul 2 px.*

## Cara menghasilkan barcode PDF417 dengan panjang data khusus

Jika data Anda melebihi kapasitas default, Anda mungkin perlu menyesuaikan parameter tambahan:

| Parameter | Pengaturan yang disarankan | Alasan |
|-----------|----------------------------|--------|
| `Pdf417.Rows` | `0` (otomatis) | Biarkan Aspose menghitung jumlah baris optimal. |
| `Pdf417.ErrorLevel` | `2` (default) | Level yang lebih tinggi meningkatkan redundansi, memperbaiki keandalan pemindaian pada media yang rusak. |
| `Pdf417.SecurityLevel` | `0`–`8` | Gunakan hanya bila Anda memerlukan koreksi kesalahan di atas default. |

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 0;          // Auto‑calculate rows
generator.Parameters.Barcode.Pdf417.ErrorLevel = 2;   // Standard error correction
generator.Parameters.Barcode.Pdf417.SecurityLevel = 5; // Optional extra security
```

**Tip:** Selalu uji barcode yang dihasilkan dengan perangkat pemindai yang dituju. Level kesalahan yang lebih tinggi dapat membuat gambar menjadi lebih besar, yang mungkin memengaruhi batasan tata letak.

## Jebakan umum dan cara menghindarinya

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| Barcode tampak buram | Menyimpan sebagai PNG beresolusi rendah | Tingkatkan `XDimension.Pixels` atau ekspor ke SVG (`BarCodeImageFormat.Svg`) |
| Karakter diganti oleh � | String input tidak dienkode sebagai UTF‑8 | Pastikan file sumber disimpan dengan enkoding UTF‑8 (sebagian besar IDE menggunakan ini secara default) |
| Pemindai tidak dapat membaca barcode | Kolom terlalu sedikit untuk jumlah data | Tingkatkan `Pdf417.Columns` atau biarkan Aspose menentukan kolom secara otomatis dengan menghilangkan pengaturan tersebut |

## Membuat barcode dengan Aspose – selain PDF417

Aspose.BarCode mendukung banyak simbolologi (QR, Code128, DataMatrix, dll.). Beralih ke tipe lain hanya memerlukan perubahan nilai enum `EncodeTypes`:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
qrGenerator.Save("QRCode.png", BarCodeImageFormat.Png);
```

Ini menunjukkan pola **create barcode with Aspose**: instantiate `BarcodeGenerator` dengan nilai `EncodeTypes` yang diinginkan, konfigurasikan parameter, lalu panggil `Save`.

## Kesimpulan

Anda kini tahu cara **membuat barcode PDF417** dalam C# menggunakan Aspose.BarCode, mulai dari penyiapan proyek hingga penyetelan parameter visual dan penanganan data Unicode. Contoh lengkap yang dapat dijalankan dapat disesuaikan untuk set data yang lebih besar, format gambar berbeda, atau simbolologi alternatif.

Langkah selanjutnya yang dapat Anda jelajahi:

* **Cara menghasilkan PDF417 barcode** dalam web API (ASP.NET Core) – berguna untuk pembuatan on‑demand.  
* Menyematkan barcode ke dalam dokumen PDF dengan Aspose.PDF.  
* Menggunakan `Pdf417.Rows` dan `Pdf417.ErrorLevel` untuk memenuhi standar pemindaian tertentu.

Silakan bereksperimen dengan jumlah kolom, nilai X‑dimension, dan format output untuk menyesuaikan dengan kebutuhan spesifik Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to read barcode from PDF in Java using Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}