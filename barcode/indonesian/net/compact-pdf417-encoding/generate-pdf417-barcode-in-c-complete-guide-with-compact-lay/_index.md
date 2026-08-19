---
category: general
date: 2026-08-19
description: Hasilkan kode batang PDF417 dalam C# dengan cepat. Pelajari cara menghasilkan
  kode batang PDF417 C# menggunakan Aspose.BarCode dengan mode kompak dan pengaturan
  khusus.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: id
lastmod: 2026-08-19
og_description: Hasilkan kode batang PDF417 dalam C# dengan Aspose.BarCode. Tutorial
  ini menunjukkan cara menghasilkan kode batang PDF417 C# dalam mode kompak, mengatur
  dimensi X, dan menyimpan sebagai PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Buat kode batang PDF417 di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Menghasilkan barcode PDF417 di C# – panduan lengkap dengan tata letak kompak
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan barcode PDF417 di C# – panduan lengkap

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, tutorial ini menunjukkan secara tepat cara melakukannya. Anda akan melihat contoh singkat yang siap produksi yang membuat barcode PDF417 yang kompak, menyesuaikan dimensi X, dan menyimpan hasilnya sebagai gambar PNG.

Membuat barcode PDF417 umum dilakukan ketika Anda harus mengkodekan sejumlah besar data—seperti informasi tiket, manifest pengiriman, atau dokumen identitas—dalam format yang dapat dibaca mesin. Menggunakan Aspose.BarCode membuat prosesnya sederhana, dan kode tersebut bekerja dengan .NET 6+ atau .NET Framework 4.7.2 dan yang lebih baru.

Dalam panduan ini Anda akan:

* Menginstal paket NuGet Aspose.BarCode.
* Menulis program C# mandiri yang **menghasilkan barcode PDF417** dengan jumlah kolom kecil dan mode kompak (dipotong).
* Menyesuaikan lebar bar (dimensi X) untuk tampilan yang lebih tajam.
* Menyimpan barcode sebagai file PNG.
* Menjelajahi variasi, kasus tepi, dan tip praktik terbaik.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* Visual Studio 2022 (atau IDE C# apa pun) dengan .NET 6 SDK terinstal.
* Akses internet untuk mengunduh paket NuGet **Aspose.BarCode**.
* Izin menulis ke folder tempat file PNG akan disimpan.

Tidak ada pustaka tambahan yang diperlukan; Aspose.BarCode menangani enkoding gambar secara internal.

## Langkah 1: Tambahkan paket Aspose.BarCode

Buka proyek Anda di Visual Studio, klik kanan solusi, dan pilih **Manage NuGet Packages**. Cari `Aspose.BarCode` dan instal versi stabil terbaru.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Jaga paket tetap terbaru. Rilis baru sering menyertakan peningkatan performa dan dukungan untuk runtime .NET terbaru.

## Langkah 2: Buat aplikasi konsol minimal

Buat proyek konsol C# baru jika Anda belum memilikinya:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Ganti isi `Program.cs` dengan contoh lengkap di bawah ini. Program ini menunjukkan **cara menghasilkan barcode PDF417 C#** dari awal hingga akhir.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Mengapa setiap baris penting

* **`EncodeTypes.Pdf417`** – memilih simbolologi PDF417, yang mendukung hingga ~1,1 KB data.
* **`XDimension.Pixels = 2`** – mengatur lebar bar dasar. Nilai yang lebih kecil membuat barcode lebih tipis; nilai yang lebih besar meningkatkan keterbacaan pada perangkat beresolusi rendah.
* **`Pdf417.Columns = 3`** – membatasi jumlah kolom, memaksa generator menggunakan lebih banyak baris, yang menghasilkan barcode lebih tinggi tetapi lebih sempit.
* **`Pdf417.Truncate = true`** – mengaktifkan mode kompak, menghapus pola berhenti dan memperkecil gambar tanpa kehilangan integritas data.
* **`Save(..., BarCodeImageFormat.Png)`** – menulis file PNG. Anda juga dapat memilih `Jpeg`, `Bmp`, atau `Svg` tergantung kebutuhan downstream.

Jalankan program:

```bash
dotnet run
```

Anda akan melihat output konsol yang mengonfirmasi lokasi file, dan folder akan berisi `CompactPdf417.png`. Membuka PNG menampilkan barcode PDF417 yang jelas dan kompak yang mengenkode string Unicode.

## Langkah 3: Verifikasi barcode (opsional tetapi disarankan)

Untuk memastikan barcode dapat dibaca, Anda dapat menggunakan aplikasi pemindai PDF417 standar pada smartphone atau pustaka decoder desktop. Teks yang dienkode harus cocok persis dengan string `data` asli, termasuk karakter khusus.

Jika Anda mengalami masalah decoding:

* Tingkatkan `XDimension` menjadi 3 atau 4 piksel.
* Kurangi jumlah kolom (misalnya, set `Columns = 2`).
* Nonaktifkan `Truncate` (`Truncate = false`) untuk menambahkan pola berhenti.

Penyesuaian ini menukar ukuran dengan keterbacaan, yang berguna untuk printer atau pemindai beresolusi rendah.

## Langkah 4: Jelajahi variasi umum

### 4️⃣ Hasilkan PDF417 berkecepatan tinggi untuk pencetakan

Jika Anda memerlukan barcode yang muat pada label kecil, tingkatkan jumlah kolom dan turunkan dimensi X:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Ubah format output ke SVG untuk penskalaan vektor

Output SVG dapat diskalakan tanpa kehilangan kualitas, sempurna untuk halaman web responsif.

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

### 6️⃣ Enkode data biner (mis., array byte)

Jika Anda perlu menyematkan muatan biner, konversikan terlebih dahulu ke string Base64:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Barcode kini membawa informasi biner, dan decoder harus membalikkan langkah Base64.

## Pertanyaan yang sering diajukan

| Pertanyaan | Jawaban |
|------------|---------|
| **Apakah saya dapat menghasilkan PDF417 tanpa Aspose?** | Ya, pustaka lain seperti ZXing.Net atau Dynamsoft ada, tetapi Aspose.BarCode menawarkan kontrol tata letak yang lebih kaya (kolom, pemotongan) dan penanganan Unicode yang lebih baik. |
| **Berapa panjang data maksimum?** | PDF417 dapat mengenkode hingga 1.108 byte (≈ 1 KB) data biner. Jika Anda melebihi ini, pertimbangkan membagi data ke beberapa barcode. |
| **Apakah mode kompak sesuai standar?** | PDF417 yang dipotong merupakan bagian dari spesifikasi ISO/IEC 15438 dan didukung secara luas, tetapi pastikan pemindai target Anda secara eksplisit mendukungnya. |
| **Bagaimana cara mengubah warna latar belakang?** | Setel `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` dan `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` sebelum menyimpan. |

## Kesimpulan

Anda kini tahu **cara menghasilkan barcode PDF417 C#** menggunakan Aspose.BarCode, cara menyesuaikan dimensi X, mengaktifkan mode kompak, dan mengekspor hasilnya sebagai gambar PNG. Contoh lengkap yang dapat dijalankan dapat disalin ke proyek .NET apa pun, dan variasi yang ditunjukkan memungkinkan Anda menyesuaikan barcode untuk pencetakan, web, atau skenario muatan biner.

Langkah selanjutnya yang dapat Anda jelajahi:

* Mengintegrasikan pembuatan barcode ke dalam API ASP.NET Core yang mengembalikan gambar sesuai permintaan.
* Menggabungkan PDF417 dengan kode QR pada label yang sama untuk pemindaian format ganda.
* Menggunakan kelas `Reader` Aspose.BarCode untuk mendekode gambar yang dihasilkan dan memverifikasi data secara programatik.

Selamat coding, dan nikmati fleksibilitas yang dibawa solusi **menghasilkan barcode PDF417** ke aplikasi Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang erat dengan teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Menghasilkan Gambar Barcode dengan Kustomisasi Ruang Tambahan menggunakan Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}