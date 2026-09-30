---
category: general
date: 2026-08-22
description: Cara menghasilkan barcode di C# menggunakan Aspose.BarCode. Pelajari
  cara membuat gambar barcode C# langkah demi langkah, menonaktifkan komponen 2‑D,
  dan menyimpan file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: id
lastmod: 2026-08-22
og_description: Cara menghasilkan barcode di C# dengan Aspose.BarCode. Tutorial ini
  menunjukkan cara membuat gambar barcode di C# menggunakan DataBar Expanded, mengaktifkan
  komponen 2‑D, dan menyimpan file PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Cara membuat barcode di C# – panduan lengkap untuk membuat gambar barcode
  C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Cara menghasilkan barcode di C# – buat gambar barcode C# dengan DataBar Expanded
url: /id/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode di C# – membuat gambar barcode c# dengan DataBar Expanded

Menghasilkan barcode di C# adalah kebutuhan yang sering muncul ketika Anda perlu menyematkan data yang dapat dibaca mesin ke dalam aplikasi Anda. Panduan ini menunjukkan cara membuat gambar barcode c# menggunakan pustaka Aspose.BarCode, menonaktifkan komponen komposit 2‑D, dan menyimpan hasilnya sebagai file PNG.

Anda akan melihat program lengkap yang dapat dijalankan, penjelasan tentang setiap opsi konfigurasi, dan tip untuk menyesuaikan output. Tidak diperlukan dokumentasi eksternal—hanya kode di bawah ini dan lingkungan pengembangan .NET.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET)  
* Paket NuGet Aspose.BarCode untuk .NET (`Aspose.BarCode`)  

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

Pustaka ini menyediakan kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini.

## Langkah 1: Siapkan proyek dan impor namespace

Buat aplikasi console baru dan impor namespace yang diperlukan:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

Namespace `Aspose.BarCode.Generation` berisi semua kelas yang diperlukan untuk mengkonfigurasi dan merender barcode.

## Langkah 2: Inisialisasi generator barcode DataBar Expanded

Baris fungsional pertama membuat `BarcodeGenerator` untuk simbol **DataBar Expanded** dan menyediakan string data mentah. String data mengikuti format GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Membuat generator mengalokasikan kanvas bitmap internal, sehingga Anda dapat menyesuaikan ukuran dan tampilan sebelum merender.

## Langkah 3: Tentukan lebar modul (X‑dimension)

X‑dimension mengontrol lebar elemen barcode terkecil. Menetapkannya dalam piksel memberi Anda kontrol yang tepat atas ukuran gambar akhir.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nilai `2` piksel bekerja baik untuk tampilan layar; tingkatkan nilai tersebut untuk cetakan dengan resolusi lebih tinggi.

## Langkah 4: Nonaktifkan komponen komposit 2‑D

DataBar Expanded dapat secara opsional menyertakan komponen 2‑D yang membawa informasi tambahan. Untuk menghasilkan barcode **tanpa** komponen ini, setel flag menjadi `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Menonaktifkan komponen mengurangi kompleksitas visual dan menghasilkan file PNG yang lebih kecil.

## Langkah 5: Simpan gambar barcode tanpa komponen 2‑D

Pilih direktori output dan tulis gambar ke disk. Enum `BarCodeImageFormat.Png` memastikan file PNG lossless.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Setelah pemanggilan ini, `Databar2DComponentDisabled.png` berisi barcode DataBar Expanded yang bersih.

## Langkah 6: Aktifkan komponen komposit 2‑D

Jika Anda memerlukan lapisan data tambahan, aktifkan kembali flag tersebut. Instansi generator yang sama dapat digunakan kembali, sehingga menghindari pembuatan objek kedua.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Langkah 7: Simpan gambar barcode dengan komponen 2‑D diaktifkan

Render gambar kedua menggunakan pengaturan yang sama, kecuali flag 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Sekarang `Databar2DComponentEnabled.png` menampilkan barcode dengan pola 2‑D tambahan.

## Kode sumber lengkap

Salin seluruh potongan kode di bawah ini ke dalam `Program.cs` dan jalankan proyek. Program akan membuat kedua file PNG di folder yang Anda tentukan.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Output yang diharapkan

Menjalankan program akan mencetak:

```
Barcode images generated successfully.
```

dan membuat dua file:

* `Databar2DComponentDisabled.png` – barcode tanpa komponen 2‑D  
* `Databar2DComponentEnabled.png` – barcode dengan komponen 2‑D  

Buka PNG tersebut di penampil gambar apa pun untuk memverifikasi perbedaan visual.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian |
|-----------|------------|
| **Simbol berbeda** | Ganti `EncodeTypes.DatabarExpanded` dengan nilai lain, misalnya `EncodeTypes.Code128`. |
| **Resolusi lebih tinggi** | Tingkatkan `XDimension.Pixels` menjadi 4 atau 5, atau setel `Resolution` di `barcodeGenerator.Parameters.Image`. |
| **Format gambar lain** | Gunakan `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, atau `BarCodeImageFormat.Svg`. |
| **Menjalankan di aplikasi web** | Alirkan byte gambar langsung ke respons HTTP alih-alih menyimpannya ke disk. |
| **Manajemen memori** | Bungkus generator dalam blok `using` jika Anda menargetkan .NET Framework untuk memastikan sumber daya tak terkelola dilepaskan. |

## Tips profesional

* **Gunakan kembali generator** – Mengubah hanya flag 2‑D menghindari pembuatan ulang objek, yang menghemat siklus CPU.  
* **Validasi data** – Data GS1 harus mengikuti aturan panjang dan checksum yang tepat; input tidak valid akan melempar `ArgumentException`.  
* **Pemrosesan batch** – Loop (iterasi) atas koleksi string data, ubah flag 2‑D sesuai kebutuhan, dan simpan setiap gambar dengan nama file yang unik.  

## Kesimpulan

Anda sekarang tahu cara menghasilkan barcode di C# dan membuat gambar barcode c# dengan kontrol penuh atas komponen komposit 2‑D. Contoh ini menunjukkan inisialisasi generator, konfigurasi X‑dimension, mengubah status komponen, dan menyimpan file PNG. Dari sini Anda dapat menjelajahi simbol lain, menyematkan gambar ke dalam PDF, atau mengintegrasikan pembuatan barcode ke dalam layanan ASP.NET Core.

--- 

*Langkah selanjutnya*: coba menghasilkan QR code, bereksperimen dengan resolusi gambar yang berbeda, atau sematkan PNG yang dihasilkan ke dalam PDF menggunakan Aspose.PDF. Ekstensi ini dibangun di atas API `BarcodeGenerator` yang sama dan menjaga alur kerja Anda tetap konsisten.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah‑per‑Langkah](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cara Menghasilkan dan Menyesuaikan Tinggi Barcode untuk Databar Satu Dimensi menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}