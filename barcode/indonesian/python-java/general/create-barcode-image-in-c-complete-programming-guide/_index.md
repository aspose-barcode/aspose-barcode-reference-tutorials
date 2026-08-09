---
category: general
date: 2026-08-09
description: Buat gambar barcode di C# dengan panduan langkah demi langkah ini. Pelajari
  cara menghasilkan barcode, mengatur tinggi barcode dalam piksel, dan membuat banyak
  barcode secara efisien.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: id
lastmod: 2026-08-09
og_description: Buat gambar barcode di C# dengan cepat. Ikuti tutorial ini untuk belajar
  cara menghasilkan barcode, mengatur tinggi pixel barcode, dan menghasilkan banyak
  barcode.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Buat gambar barcode di C# – panduan lengkap untuk pengembang
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Buat gambar barcode di C# – panduan pemrograman lengkap
url: /id/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat gambar barcode di C# – panduan pemrograman lengkap

Jika Anda perlu **membuat gambar barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat **cara menghasilkan barcode** menggunakan pustaka Aspose.BarCode. Anda akan melihat cara mengontrol **pixel tinggi barcode**, menyimpan gambar, dan menghasilkan **beberapa barcode** tanpa menduplikasi kode.

Tutorial ini mencakup semua hal mulai dari menginstal paket hingga menyesuaikan dimensi, sehingga Anda dapat menyalin‑tempel contoh siap‑jalankan ke dalam proyek Anda hari ini.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terinstal  
* Visual Studio 2022 (atau IDE C# apa pun)  
* Paket NuGet `Aspose.BarCode` – instal dengan  

```bash
dotnet add package Aspose.BarCode
```

Tidak ada dependensi tambahan yang diperlukan.

## Cara menghasilkan gambar barcode dengan BarcodeGenerator C#

Kelas inti untuk membuat gambar barcode adalah `BarcodeGenerator`. Kelas ini mengenkapsulasi tipe enkoding, string data, dan semua parameter rendering.

### Langkah 1: Tentukan folder output

Pilih folder tempat file PNG yang dihasilkan akan disimpan. Menggunakan jalur absolut menghindari kejutan izin.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Mengapa?** Membuat folder secara programatik menjamin bahwa pemanggilan `Save` berikutnya berhasil bahkan pada mesin baru.

### Langkah 2: Buat instance barcode generator

Untuk barcode DataBar Omnidirectional, berikan `EncodeTypes.DatabarOmniDirectional` dan string data GS1‑128.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Catatan:** Objek `BarcodeGenerator` dapat digunakan kembali; Anda dapat mengubah parameternya di antara penyimpanan untuk **membuat beberapa barcode** dari data yang sama.

### Langkah 3: Atur parameter barcode umum

Penyesuaian visual yang paling umum adalah X‑dimension (lebar modul) dan tinggi bar. Keduanya dinyatakan dalam pixel.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Mengapa mengatur X‑dimension?** X‑dimension yang lebih kecil menghasilkan resolusi lebih tinggi, yang penting ketika gambar akan dicetak atau ditampilkan pada layar ber‑DPI tinggi.

### Langkah 4: Simpan gambar barcode pertama

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

File `DatabarBarHeight30Pixels.png` kini berisi barcode DataBar Omnidirectional dengan tinggi 30 pixel.

### Langkah 5: Sesuaikan pixel tinggi barcode

Mengubah tinggi tidak memerlukan instance `BarcodeGenerator` baru—cukup ubah parameternya.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Langkah 6: Simpan gambar barcode kedua

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG dengan **pixel tinggi barcode** yang berbeda, menunjukkan betapa mudahnya **membuat variasi gambar barcode**.

## Mengatur pixel tinggi barcode secara dinamis

Seringkali Anda membutuhkan serangkaian barcode dengan tinggi yang sesuai dengan elemen UI atau label cetak. Metode bantu berikut mengabstraksi perubahan tinggi:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Anda kini dapat memanggil `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` untuk **membuat gambar barcode** dengan tinggi 45 pixel dalam satu baris.

## Membuat beberapa barcode dalam loop

Ketika Anda memiliki kumpulan identifier produk, loop `foreach` menghilangkan kode berulang. Contoh ini menunjukkan cara **membuat beberapa barcode** dari array GTIN.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

Loop tersebut menghasilkan tiga file PNG, masing‑masing dengan nilai **pixel tinggi barcode** yang berbeda. Karena helper `SaveBarcodeWithHeight` mengenkapsulasi perubahan tinggi, loop utama tetap bersih dan terfokus pada data.

### Output yang diharapkan

Setelah menjalankan contoh lengkap, folder `Barcodes` berisi:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Membuka PNG mana pun menampilkan barcode DataBar Omnidirectional yang tajam dan dapat dipindai oleh aplikasi seluler standar.

## Kesalahan umum dan tip pro

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Wrong EncodeTypes** | Menggunakan tipe 1D untuk DataBar akan menghasilkan gambar yang tidak dapat dibaca. | Selalu pilih `EncodeTypes.DatabarOmniDirectional` (atau varian DataBar lainnya) untuk payload GS1‑128. |
| **Insufficient X‑dimension** | X‑dimension yang sangat rendah dapat membuat bar tipis menghilang pada monitor beresolusi rendah. | Pertahankan `XDimension.Pixels` ≥ 2 untuk tampilan layar; tingkatkan menjadi 3‑4 untuk pencetakan. |
| **File path errors** | Jalur relatif mungkin mengarah ke direktori yang tidak terduga. | Gunakan `Path.Combine` dan `Environment.CurrentDirectory` untuk membangun jalur absolut. |
| **Overwriting images** | Menggunakan nama file yang sama dalam loop akan menimpa hasil sebelumnya. | Sertakan identifier unik (mis., GTIN atau timestamp) dalam nama file. |
| **Missing NuGet package** | Kode berhasil dikompilasi tetapi melempar `FileNotFoundException` saat runtime. | Pastikan `Aspose.BarCode` terinstal dan proyek merujuknya. |

## Contoh lengkap yang berfungsi

Berikut adalah program lengkap yang dapat Anda salin ke aplikasi console. Program ini mencakup semua langkah, metode bantu, dan penanganan error.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Menjalankan program ini


## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Buat Tinggi Kustom Barcode – Barcode Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Buat gambar barcode C# – Contoh GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Buat gambar barcode DotCode – baris & kolom (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}