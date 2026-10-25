---
category: general
date: 2026-10-24
description: Pelajari cara membaca barcode PDF417 di C# menggunakan Aspose.BarCode.
  Tutorial ini mencakup membaca gambar barcode, mengekstrak bidang Macro PDF417, dan
  menangani skenario umum.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: id
lastmod: 2026-10-24
og_description: Cara membaca barcode PDF417 di C# menggunakan Aspose.BarCode. Ikuti
  tutorial lengkap ini untuk mendekode gambar, mengambil metadata Macro PDF417, dan
  menghindari jebakan umum.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Cara membaca barcode PDF417 di C# dengan Aspose – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Cara membaca kode batang PDF417 di C# dengan Aspose – panduan langkah demi
  langkah
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca barcode PDF417 di C# dengan Aspose – panduan langkah‑demi‑langkah

Jika Anda perlu **cara membaca PDF417 barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara membaca PDF417 barcode di C# menggunakan pustaka Aspose.BarCode. Baik Anda memproses dokumen yang dipindai, hasil tangkapan seluler, atau gambar yang di‑import secara batch, kode di bawah ini akan mendekode barcode dan mengekstrak setiap properti Macro PDF417 yang mungkin Anda perlukan.

Membaca gambar barcode di C# dapat terasa menakutkan, terutama ketika barcode berisi metadata yang diperluas. Tutorial ini menghilangkan dugaan dengan menyediakan contoh lengkap yang dapat dijalankan, menjelaskan setiap baris, dan mencakup kasus tepi seperti segmen macro yang hilang atau gambar yang rusak. Pada akhir tutorial, Anda akan dapat mengintegrasikan dekoding PDF417 ke dalam proyek C# mana pun dengan percaya diri.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE apa pun yang mendukung .NET)  
* Lisensi atau evaluasi gratis **Aspose.BarCode for .NET** – Anda dapat memperoleh kunci sementara dari situs web Aspose  
* File gambar yang berisi barcode Macro PDF417 (misalnya `ExtPDF417Meta.png`)

> **Pro tip:** Jika Anda hanya ingin bereksperimen, Aspose menawarkan percobaan 30‑hari yang mencakup semua fungsi untuk pembacaan barcode.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Buka folder proyek Anda di terminal dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode.ReadRecognition`, yang berisi kelas `BarCodeReader` yang digunakan untuk mendekode gambar.

## Langkah 2: Buat BarCodeReader untuk gambar PDF417

Konstruktor `BarCodeReader` menerima dua argumen: path ke file gambar dan `DecodeType` yang ingin Anda targetkan. Menentukan `DecodeType.MacroPdf417` memberi tahu Aspose untuk mencari simbol Macro PDF417 dan secara otomatis mengisi properti yang diperluas.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Mengapa menggunakan `DecodeType.MacroPdf417`?

* **Macro PDF417** menyimpan bidang tambahan (file ID, jumlah segmen, timestamp, dll.) yang tidak ada pada PDF417 standar.  
* Properti `Extended` dari `BarCodeResult` hanya terisi ketika Anda meminta tipe macro, sehingga menghemat langkah parsing terpisah.

## Langkah 3: Iterasi semua barcode yang terdeteksi

Sebuah gambar tunggal dapat berisi beberapa simbol PDF417 (misalnya, ketika dokumen dibagi menjadi beberapa halaman). Metode `ReadBarCodes()` mengembalikan `IEnumerable<BarCodeResult>` yang dapat Anda loop.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Jika gambar tidak mengandung barcode apa pun, loop tidak akan pernah dijalankan, dan program akan keluar dengan elegan. Perilaku ini membuat kode aman untuk pemrosesan batch di mana beberapa file mungkin tidak memiliki barcode.

## Langkah 4: Keluarkan properti ekstended Macro PDF417

Properti `Extended.Pdf417` mengelompokkan semua bidang khusus macro. Setiap bidang dipetakan langsung ke spesifikasi PDF417, sehingga Anda dapat menyimpannya ke basis data, mencatatnya, atau menggunakannya untuk validasi lebih lanjut.

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### Apa arti masing‑masing properti

| Property | Description |
|----------|-------------|
| **MacroPdf417FileID** | Pengidentifikasi unik untuk seluruh dokumen multi‑segmen. |
| **MacroPdf417SegmentID** | Indeks segmen saat ini (dimulai dari 0). |
| **MacroPdf417SegmentsCount** | Jumlah total segmen yang termasuk dalam file. |
| **MacroPdf417FileName** | Nama file opsional yang disematkan dalam barcode. |
| **MacroPdf417Checksum** | Checksum CRC‑16 untuk blok data macro. |
| **MacroPdf417FileSize** | Ukuran file asli dalam byte. |
| **MacroPdf417TimeStamp** | Timestamp saat barcode macro dibuat. |
| **MacroPdf417Addressee** | Penerima yang dimaksudkan dari dokumen. |
| **MacroPdf417Sender** | Pengirim dokumen. |
| **MacroPdf417Terminator** | Flag terminator yang menandakan akhir urutan macro. |

Bidang‑bidang ini sangat berguna ketika Anda merekonstruksi PDF atau gambar besar yang dibagi menjadi beberapa simbol PDF417 untuk pencetakan pada media beresolusi rendah.

## Langkah 5: Tangani kasus tepi umum

### Bidang macro yang hilang

Kadang‑kadang barcode PDF417 dihasilkan tanpa bidang macro opsional. Mengakses properti yang tidak ada akan mengembalikan `null` atau `0`. Lindungi kode Anda jika Anda berencana menyimpan nilai‑nilai tersebut:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Gambar yang rusak atau beresolusi rendah

Jika gambar blur, Anda dapat meningkatkan deteksi dengan mengaktifkan opsi kualitas `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Pengaturan ini opsional tetapi dapat secara dramatis meningkatkan tingkat keberhasilan untuk dokumen yang dipindai.

### Beberapa format barcode dalam satu gambar

Jika Anda menduga ada tipe barcode lain, gunakan `DecodeType.AllSupported` dan filter hasilnya:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Contoh lengkap yang dapat dijalankan

Salin program berikut ke dalam proyek konsol baru (`dotnet new console`) dan jalankan. Ganti variabel `imagePath` dengan lokasi gambar Macro PDF417 Anda sendiri.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Output yang diharapkan** (nilai akan berbeda tergantung gambar Anda):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Jika gambar tidak mengandung simbol Macro PDF417, program tidak menulis apa‑apa dan keluar secara diam‑diam—sempurna untuk pekerjaan batch yang memproses banyak file.

## Pertanyaan yang sering diajukan

**T: Bisakah saya membaca PDF417 standar (non‑macro) dengan kode yang sama?**  
J: Ya. Ubah `DecodeType.MacroPdf417` menjadi `DecodeType.Pdf417`. Properti `Extended` akan kosong, tetapi `CodeText` dan `CodeTypeName` tetap tersedia.

**T: Apakah Aspose.BarCode mendukung pembacaan dari stream alih‑alih path file?**  
J: Tentu. Gunakan overload `new BarCodeReader(Stream, DecodeType)` dan berikan `FileStream` atau `MemoryStream`. Ini berguna ketika gambar berasal dari API web.

**T: Bagaimana cara memvalidasi checksum?**  
J: Field `MacroPdf417Checksum` berisi nilai CRC‑16 mentah. Anda dapat menghitung ulang checksum pada file yang telah direkonstruksi dan membandingkannya untuk memastikan integritas data.

## Langkah selanjutnya dan topik terkait

* **Write PDF417 barcodes** – jelajahi `BarCodeGenerator` untuk membuat barcode macro untuk pengujian.  
* **Combine multiple segments** – setelah membaca semua segmen, urutkan berdasarkan `MacroPdf417SegmentID` dan gabungkan `CodeText` untuk merekonstruksi payload asli.  
* **Performance tuning** – untuk skenario throughput tinggi, gunakan kembali satu instance `BarCodeReader` untuk banyak gambar dan

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik yang sangat terkait dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang dapat dijalankan dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}