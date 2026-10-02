---
category: general
date: 2026-10-02
description: Pelajari cara membaca barcode dari gambar C# dengan contoh lengkap yang
  menunjukkan cara mendekode barcode PDF417 menggunakan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: id
lastmod: 2026-10-02
og_description: Baca kode batang dari gambar C# dengan Aspose.BarCode. Tutorial ini
  menjelaskan cara mendekode kode batang PDF417 dan mengekstrak metadata tambahan.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Baca kode batang dari gambar C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membaca barcode dari gambar C# menggunakan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca barcode dari gambar c# menggunakan Aspose.BarCode

Jika Anda perlu **membaca barcode dari gambar c#**, panduan ini akan memandu Anda melalui solusi lengkap yang dapat dijalankan. Anda akan belajar cara mendekode barcode PDF417, mengakses data makro yang diperluas, dan mencetak hasilnya ke konsol.

Membaca barcode dari gambar adalah kebutuhan umum untuk sistem inventaris, validasi tiket, dan pemrosesan dokumen. Tutorial ini mencakup semua yang Anda perlukan: paket yang diperlukan, penjelasan kode, penanganan kasus tepi, dan output yang diharapkan. Tidak diperlukan dokumentasi eksternal; contoh ini langsung dapat dijalankan dengan Aspose.BarCode .NET.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE C# apa pun)  
* Referensi NuGet ke **Aspose.BarCode** (versi 23.10 atau lebih baru)  
* File gambar yang berisi barcode PDF417 – misalnya `ExtPDF417Meta.png`

Jika ada yang belum ada, instal .NET SDK, tambahkan paket NuGet dengan `dotnet add package Aspose.BarCode`, dan letakkan gambar di folder yang dapat Anda referensikan dari proyek.

## Cara membaca barcode dari gambar c# – langkah demi langkah

Bagian-bagian berikut memecah implementasi menjadi langkah-langkah logis. Setiap langkah menyertakan cuplikan kode, penjelasan **mengapa** langkah tersebut penting, dan tip yang dapat Anda terapkan pada proyek dunia nyata.

### Langkah 1: Buat `BarCodeReader` untuk gambar PDF417

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Mengapa ini penting** – Konstruktor `BarCodeReader` menerima path gambar dan tipe barcode yang diharapkan. Menentukan `MacroPdf417` mempersempit pencarian, yang meningkatkan kinerja dan mengurangi false positive ketika gambar berisi banyak simbol.

**Tip profesional:** Jika Anda tidak yakin dengan tipe barcode, gunakan `DecodeType.AllSupportedTypes` dan filter hasilnya nanti.

### Langkah 2: Iterasi semua barcode yang terdeteksi

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Mengapa ini penting** – Gambar macro PDF417 dapat berisi beberapa segmen. Metode `ReadBarCodes()` mengembalikan koleksi, memungkinkan Anda memproses setiap segmen secara terpisah.

**Kasus tepi:** Jika gambar tidak mengandung simbol PDF417 apa pun, koleksinya kosong dan tubuh loop tidak pernah dijalankan. Pertimbangkan menambahkan pemeriksaan setelah loop untuk memberi tahu pengguna.

### Langkah 3: Akses metadata macro PDF417 yang diperluas

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Mengapa ini penting** – Properti `Extended.Pdf417` menampilkan bidang-bidang yang didefinisikan oleh spesifikasi PDF417, seperti file ID, segment ID, dan file name. Data ini penting ketika Anda perlu merekonstruksi dokumen multi‑halaman dari pemindaian barcode terpisah.

**Tip profesional:** Selalu pastikan `barcodeResult.Extended` tidak null sebelum mengakses `Pdf417`. Library mengembalikan `null` untuk simbol yang tidak mendukung data diperluas.

### Langkah 4: Cetak teks barcode dan detail macro

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Mengapa ini penting** – Output konsol memberi Anda visibilitas langsung ke teks yang didekode serta metadata macro. Ini berguna untuk debugging dan pemrosesan lanjutan, seperti menyimpan informasi ke basis data.

**Output yang diharapkan** (asumsi gambar contoh berisi satu segmen macro):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Jika gambar berisi tiga segmen, loop akan mencetak tiga blok, masing‑masing dengan `Segment ID` yang berbeda.

### Langkah 5: Tangani error dan bersihkan sumber daya

Pernyataan `using` secara otomatis membuang `BarCodeReader`. Namun, Anda tetap harus menangkap pengecualian yang mungkin muncul karena file yang hilang atau format yang tidak didukung:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Mengapa ini penting** – Aplikasi yang kuat tidak pernah crash karena file tidak ada atau gambar rusak. Menyediakan pesan error yang jelas membantu Anda atau tim dukungan mendiagnosa masalah dengan cepat.

## Cara mendekode barcode PDF417 dengan Aspose.BarCode

Kata kunci sekunder **how to decode pdf417 barcode** muncul secara alami di bagian ini. Mendekode barcode PDF417 mengikuti pola yang sama seperti di atas, tetapi Anda dapat menghilangkan flag `MacroPdf417` jika hanya membutuhkan teks biasa:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Mengapa Anda mungkin memilih varian ini** – Ketika barcode tidak membawa informasi macro, menggunakan `DecodeType.Pdf417` mengurangi beban pemrosesan dan menyederhanakan penanganan hasil.

**Pertanyaan umum:** *Bagaimana jika barcode diputar?*  
Aspose.BarCode secara otomatis mendeteksi rotasi dan memperbaikinya, jadi Anda tidak memerlukan kode pra‑pemrosesan gambar tambahan.

## Contoh lengkap yang dapat dijalankan

Salin seluruh program di bawah ini ke proyek konsol baru (`dotnet new console`) dan ganti `YOUR_DIRECTORY/ExtPDF417Meta.png` dengan path sebenarnya ke gambar Anda.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

Menjalankan program akan mencetak tipe barcode, teks yang didekode, dan metadata macro apa pun. Jika gambar tidak mengandung macro PDF417, program akan memberi tahu Anda dengan elegan.

## Kesimpulan

Anda kini tahu cara **membaca barcode dari gambar c#** dengan Aspose.BarCode, cara **mendekode PDF417 barcode**, dan cara mengekstrak bidang diperluas macro‑PDF417. Solusi ini mencakup inisialisasi, iterasi, akses metadata, penanganan error, serta varian untuk dekode PDF417 biasa.

Dari sini Anda dapat:

* Menyimpan data yang diekstrak ke basis data SQL untuk diambil nanti.  
* Menggabungkan beberapa segmen untuk membangun kembali dokumen asli.  
* Menjelajahi simbol lain yang didukung oleh Aspose.BarCode, seperti

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang dapat dijalankan dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}