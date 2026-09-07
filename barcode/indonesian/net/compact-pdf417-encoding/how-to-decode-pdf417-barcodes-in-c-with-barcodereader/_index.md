---
category: general
date: 2026-09-07
description: Pelajari cara mendekode barcode PDF417 dalam C# menggunakan BarCodeReader.
  Panduan langkah demi langkah ini juga menjelaskan cara membaca data PDF417 secara
  efisien.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: id
lastmod: 2026-09-07
og_description: Cara mendekode barcode PDF417 di C# menggunakan BarCodeReader. Ikuti
  tutorial ini untuk mempelajari cara membaca data PDF417 dan mengekstrak bidang MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Cara mendekode barcode PDF417 di C# – panduan lengkap
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Cara mendekode barcode PDF417 di C# dengan BarCodeReader
url: /id/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mendekode barcode PDF417 di C# dengan BarCodeReader

Jika Anda perlu **cara mendekode PDF417** barcode dalam aplikasi .NET, panduan ini akan memandu Anda melalui seluruh proses. Anda juga akan menemukan **cara membaca PDF417** data seperti file MacroPdf417 dan pengidentifikasi segmen, semuanya dengan beberapa baris C#.

Mendekode PDF417 umum dilakukan saat bekerja dengan tiket transportasi, SIM, atau label pengiriman. Pada akhir tutorial ini Anda akan memiliki program konsol yang dapat dijalankan dan mencetak setiap bidang MacroPdf417 yang disediakan oleh SDK GroupDocs.Barcode.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau lebih baru (kode dapat dikompilasi dengan .NET Core dan .NET Framework)
* Visual Studio 2022 atau IDE apa pun yang mendukung C#
* Paket NuGet **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* File gambar yang berisi barcode Macro PDF417 (misalnya `ExtPDF417Meta.png`)

> **Pro tip:** Instal paket melalui CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Cara mendekode barcode PDF417 di C#

Bagian‑bagian berikut membagi solusi menjadi langkah‑langkah logis. Setiap langkah menyertakan kode tepat yang Anda perlukan serta penjelasan singkat mengapa hal itu penting.

### Langkah 1: Siapkan proyek dan impor namespace

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Mengapa?*  
`GroupDocs.Barcode` menyediakan kelas `BarCodeReader`, sementara `GroupDocs.Barcode.Common` berisi enumerasi `DecodeType` yang diperlukan untuk dekode PDF417.

### Langkah 2: Tentukan path gambar

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Mengapa?*  
Pembaca dapat bekerja dengan format gambar apa pun yang didukung .NET (`.png`, `.jpg`, `.bmp`). Menyediakan path yang tepat memastikan SDK dapat menemukan file tersebut.

### Langkah 3: Inisialisasi pembaca barcode untuk dekode MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Mengapa?*  
`DecodeType.MacroPdf417` memberi tahu SDK untuk mencari format Macro PDF417 yang diperluas, yang membawa metadata tambahan seperti ID file dan segmen. Menggunakan pernyataan `using` menjamin sumber daya yang tidak dikelola dilepaskan dengan cepat.

### Langkah 4: Baca setiap barcode yang ditemukan dalam gambar

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Mengapa?*  
Sebuah gambar dapat berisi beberapa barcode. Metode `ReadBarCodes()` mengembalikan koleksi, memungkinkan Anda memproses masing‑masing secara individual.

### Langkah 5: Ambil dan tampilkan data khusus Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Mengapa?*  
Objek `Extended.Pdf417` menampilkan semua bidang Macro PDF417 yang didefinisikan dalam spesifikasi. Mencetaknya memungkinkan Anda memverifikasi bahwa operasi dekode berhasil dan memberikan data yang diperlukan untuk pemrosesan lanjutan.

### Contoh lengkap yang dapat dijalankan

Gabungkan potongan kode di atas menjadi satu file `Program.cs`:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Output konsol yang diharapkan** (nilai akan berbeda tergantung pada konten barcode):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Jika gambar tidak berisi barcode Macro PDF417, koleksi `ReadBarCodes()` akan kosong dan tidak ada yang dicetak.

## Variasi umum dan kasus tepi

| Situasi | Cara menyesuaikan kode |
|-----------|----------------------|
| **PDF417 standar (bukan macro)** | Ubah `DecodeType.MacroPdf417` menjadi `DecodeType.Pdf417`. Objek `Extended.Pdf417` akan menjadi `null`, jadi lindungi dari referensi null. |
| **Beberapa gambar** | Bungkus inisialisasi pembaca dalam loop `foreach (var path in imagePaths)`. |
| **Gambar besar** | Setel `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` untuk membatasi penggunaan memori. |
| **Batch kritis performa** | Gunakan kembali satu instance `BarCodeReader` dengan `reader.SetImage(path)` alih‑alih membuat objek baru untuk setiap file. |

## Daftar periksa pemecahan masalah

* **Tidak ada output:** Pastikan `imagePath` mengarah ke file yang valid dan gambar memang berisi barcode PDF417. |
* **`Extended.Pdf417` null:** Kemungkinan Anda menggunakan `DecodeType.Pdf417` alih‑alih `MacroPdf417`. |
* **Exception `FileNotFoundException`:** Pastikan direktori kerja sesuai dengan path atau gunakan path absolut. |
* **Skor kepercayaan rendah:** Tingkatkan kualitas gambar atau sesuaikan pengaturan `reader.Options.Quality`. |

## Kesimpulan

Anda kini tahu **cara mendekode PDF417** barcode di C# dan **cara membaca metadata PDF417** seperti ID file Macro, ID segmen, dan timestamp. Contoh lengkap menunjukkan cara menginisialisasi `BarCodeReader`, memilih tipe dekode yang tepat, mengiterasi hasil, serta mengekstrak setiap bidang MacroPdf417 yang tersedia.

Dari sini Anda dapat:

* Mengintegrasikan data yang diekstrak ke dalam sistem logistik atau validasi tiket.
* Memperluas aplikasi konsol untuk menulis hasil ke basis data atau file JSON.
* Menjelajahi format barcode lain yang didukung oleh GroupDocs.Barcode (QR, DataMatrix, Code128, dll.) dengan mengganti enumerasi `DecodeType`.

Selamat coding, dan jangan ragu bereksperimen dengan gambar serta pengaturan barcode yang berbeda untuk menguasai dekode PDF417 dalam proyek .NET Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membaca PDF417 di C# – Panduan Langkah-demi-Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Cara Membaca PDF417 di C# – Contoh Lengkap Barcode Reader](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Cara Membuat Barcode PDF417 – Panduan Pemrograman Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}