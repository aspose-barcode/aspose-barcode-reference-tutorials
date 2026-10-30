---
category: general
date: 2026-10-28
description: Buat gambar barcode di C# dan pelajari cara menyesuaikan tinggi menggunakan
  API BarcodeGenerator. Panduan langkah demi langkah untuk mengatur tinggi barcode
  khusus dan mengubah tinggi bar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: id
lastmod: 2026-10-28
og_description: Buat gambar barcode di C# dan langsung lihat cara menyesuaikan tinggi.
  Ikuti contoh lengkap ini untuk mengatur tinggi barcode khusus dengan BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Buat gambar barcode dengan tinggi khusus di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Buat gambar barcode dengan tinggi khusus di C#
url: /id/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat gambar barcode dengan tinggi khusus di C#

Jika Anda perlu **membuat gambar barcode** dan mengontrol dimensinya, panduan ini menunjukkan secara tepat caranya. Dengan menggunakan pustaka Aspose.BarCode .NET Anda dapat menghasilkan barcode GS1‑Databar Omni‑Directional, kemudian **cara menyesuaikan tinggi** untuk memenuhi kebutuhan tata letak apa pun.

Anda akan menjalankan program lengkap yang dapat dijalankan yang mendemonstrasikan **generator barcode c#**, menjelaskan setiap properti yang Anda atur, dan menampilkan dua output berbeda—satu dengan tinggi bar 30 piksel dan satu lagi dengan tinggi bar 60 piksel. Pada akhir tutorial Anda akan dapat **mengubah tinggi barcode** secara programatis untuk jenis barcode apa pun yang didukung oleh pustaka.

## Prasyarat

- .NET 6.0 SDK atau yang lebih baru (kode ini juga bekerja dengan .NET Framework 4.6+)
- Visual Studio 2022 atau editor apa pun yang dapat membangun proyek C#
- Paket NuGet Aspose.BarCode untuk .NET (`Install-Package Aspose.BarCode`)
- Familiaritas dasar dengan sintaks C#

> **Pro tip:** Jika Anda menggunakan pipeline CI, tambahkan paket NuGet ke file `csproj` Anda sehingga proses build akan memulihkannya secara otomatis.

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru dan tambahkan pernyataan `using` yang diperlukan. Namespace memberikan Anda akses ke `BarcodeGenerator`, `EncodeTypes`, dan pembantu format gambar.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Mengapa ini penting:** Mengimpor namespace yang tepat mencegah kesalahan saat kompilasi dan membuat API dapat ditemukan di IntelliSense.

## Langkah 2: Inisialisasi **generator barcode c#** untuk kode GS1‑Databar Omni‑Directional

Konstruktor menerima dua argumen: tipe barcode (`EncodeTypes.DatabarOmniDirectional`) dan string data. String data harus mengikuti format GS1 Application Identifier, misalnya `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Penjelasan:** Objek `BarcodeGenerator` adalah titik masuk untuk semua pengaturan terkait barcode. Setelah Anda memiliki instance ini, Anda dapat menyesuaikan dimensi, warna, dan format output.

## Langkah 3: Tentukan X‑dimension umum (lebar piksel bar paling sempit)

X‑dimension 2 piksel adalah titik awal yang baik untuk kebanyakan skenario tampilan layar.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Mengapa mengatur X‑dimension?** Ini mengontrol lebar keseluruhan barcode. Menjaganya konsisten memastikan bahwa mengubah tinggi bar tidak merusak keseimbangan visual.

## Langkah 4: **Buat gambar barcode** dengan tinggi bar 30 piksel

Sekarang kami mengonfigurasi tinggi bar, menyimpan gambar pertama, lalu mengubah tinggi untuk gambar kedua.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Hasil:** Anda mendapatkan file PNG di mana setiap bar vertikal memiliki tinggi 30 piksel. X‑dimension tetap 2 piksel, sehingga lebar keseluruhan tidak berubah.

## Langkah 5: **Cara menyesuaikan tinggi** – ubah tinggi bar menjadi 60 piksel

Untuk mendemonstrasikan **tinggi barcode khusus**, cukup tetapkan nilai baru ke properti yang sama dan simpan lagi.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Wawasan utama:** Properti `BarHeight` dapat diubah; Anda tidak perlu membuat ulang instance `BarcodeGenerator`. Ini membuatnya murah untuk menghasilkan beberapa ukuran dalam loop atau proses batch.

## Langkah 6: Verifikasi output

Jalankan program konsol (`dotnet run`). Setelah eksekusi Anda akan melihat dua file PNG di folder output proyek:

- `DatabarBarHeight30Pixels.png` – bar pendek (30 px)
- `DatabarBarHeight60Pixels.png` – bar tinggi (60 px)

Kedua gambar berisi data yang sama, tetapi tinggi visualnya berbeda, yang berguna saat mengintegrasikan barcode ke dalam formulir, label produk, atau komponen UI dengan batas ruang yang bervariasi.

![Buat gambar barcode dengan tinggi khusus](barcode-example.png){.align-center width="600" alt="Buat gambar barcode dengan tinggi khusus"}

> **Tip:** Buka file PNG di penampil gambar apa pun. Barcode yang lebih tinggi seharusnya tepat dua kali ukuran vertikal yang lebih pendek, sementara jarak horizontal tetap identik.

## Langkah 7: Variasi umum dan kasus tepi

| Situasi | Pengaturan yang disarankan |
|-----------|---------------------|
| **Mencetak pada printer label resolusi tinggi** | Gunakan X‑dimension yang lebih besar (mis., 4 px) dan tingkatkan `BarHeight` secara proporsional. |
| **Menampilkan pada layar low‑dpi** | Pertahankan `XDimension` pada 1 px dan `BarHeight` antara 20‑40 px untuk keterbacaan. |
| **Membuat kode QR atau barcode 2‑D** | Properti `BarHeight` diabaikan; gunakan `EncodeTypes.QR` dan sesuaikan `ImageHeight` sebagai gantinya. |
| **Membuat batch banyak tinggi** | Lakukan loop pada array tinggi dan panggil `Save` di dalam loop; tidak perlu membuat ulang generator setiap iterasi. |

### Menangani tinggi tidak valid

Pustaka akan melempar `ArgumentOutOfRangeException` jika Anda menetapkan `BarHeight` ke nilai non‑positif. Lindungi dari hal ini dengan pemeriksaan sederhana:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Kode sumber lengkap (siap disalin)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Mengapa ini berhasil:** Semua pengaturan yang diperlukan (`EncodeTypes`, `XDimension`, `BarHeight`) diterapkan sebelum setiap pemanggilan `Save`. Instance `BarcodeGenerator` yang sama digunakan kembali, yang efisien memori dan mudah dibaca.

## Kesimpulan

Anda sekarang tahu cara **membuat file gambar barcode** di C# dan secara tepat **mengubah tinggi barcode** menggunakan API `BarcodeGenerator`. Dengan menyesuaikan `BarHeight.Pixels` Anda memperoleh **tinggi barcode khusus** tanpa membangun ulang generator, menjadikan solusi ini ideal untuk pembuatan label dinamis, rendering UI, atau pipeline pemrosesan batch.

Selanjutnya, jelajahi topik terkait seperti **cara menyesuaikan lebar**, **menambahkan teks yang dapat dibaca manusia**, atau **mengekspor ke SVG untuk penggunaan web yang skalabel**. Pola yang sama—atur properti, panggil `Save`—berlaku di semua skenario tersebut, memungkinkan Anda memperluas contoh ini dengan percaya diri.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Mengubah Tinggi Barcode di C# – Panduan Lengkap](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Contoh generator barcode – buat barcode Planet dan RM4SCC dengan tinggi khusus](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Cara membuat barcode rm4scc dan mengontrol tingginya di C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}