---
category: general
date: 2026-09-26
description: Pelajari cara mendekode PDF417 di C# dengan contoh pembaca kode batang
  langkah demi langkah. Panduan ini menunjukkan cara membaca gambar kode batang di
  C# menggunakan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: id
lastmod: 2026-09-26
og_description: Cara mendekode PDF417 di C# dengan cepat. Ikuti contoh pembaca kode
  batang ini untuk membaca gambar kode batang C# dengan Aspose.BarCode dan mengekstrak
  detail makro.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Cara mendekode PDF417 di C# – panduan lengkap pembaca barcode
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Cara mendekode PDF417 di C# – contoh pembaca barcode
url: /id/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mendekode PDF417 di C# – contoh pembaca barcode

Jika Anda perlu **cara mendekode PDF417** dalam aplikasi .NET, tutorial ini menyediakan solusi lengkap yang siap dijalankan. Anda akan melihat cara membaca gambar barcode C# menggunakan pustaka Aspose.BarCode, mengambil informasi makro PDF417 yang diperluas, dan menampilkan setiap bidang yang relevan.

Mendekode PDF417 tidak terbatas pada teks biasa; format ini dapat membawa data segmentasi file, cap waktu, dan checksum. Panduan ini memandu Anda melalui setiap langkah, menjelaskan mengapa kode disusun seperti itu, dan menyoroti jebakan umum yang mungkin Anda temui saat mengimplementasikan contoh pembaca barcode C#.

## Prerequisites

Sebelum Anda memulai, pastikan Anda memiliki:

* SDK .NET 6.0 (atau lebih baru) terinstal  
* Visual Studio 2022 (atau IDE kompatibel C# lainnya)  
* **Aspose.BarCode for .NET** paket NuGet (`Aspose.BarCode`)  
* Gambar contoh Macro PDF417 (misalnya `ExtPDF417Meta.png`)

Persyaratan ini memastikan kode dapat dikompilasi dan dijalankan tanpa konfigurasi tambahan.

## Langkah 1: Instal paket NuGet Aspose.BarCode

Langkah pertama dalam proyek **read barcode image C#** apa pun adalah menambahkan pustaka barcode. Buka terminal di folder solusi Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menyediakan `BarCodeReader`, `DecodeType`, dan properti `Extended` yang digunakan untuk mengakses data makro. Menginstalnya sekali membuat kelas-kelas tersebut tersedia di seluruh proyek Anda.

## Langkah 2: Buat pembaca barcode untuk gambar Macro PDF417

Sekarang Anda dapat menginstansiasi `BarCodeReader` dengan jalur ke gambar dan menentukan `DecodeType.MacroPdf417`. Ini memberi tahu pustaka untuk mencari format PDF417 yang diperluas yang berisi informasi makro.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Mengapa ini penting:**  
`DecodeType.MacroPdf417` mengaktifkan parser khusus makro. Jika Anda menghilangkannya, pembaca hanya mengembalikan muatan teks biasa dan mengabaikan bidang makro yang mungkin Anda perlukan untuk rekonstruksi file.

## Langkah 3: Baca semua barcode yang ditemukan dalam gambar

Sebuah gambar tunggal dapat berisi beberapa simbol PDF417, terutama ketika data dibagi menjadi beberapa segmen. Melakukan loop melalui `ReadBarCodes()` menjamin Anda menangkap setiap segmen.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Mengapa loop:**  
Data makro PDF417 sering muncul dalam beberapa segmen. Memproses setiap `BarCodeResult` memastikan Anda mengumpulkan seluruh set bidang makro, seperti `MacroPdf417FileID` dan `MacroPdf417SegmentsCount`.

## Langkah 4: Ambil dan tampilkan data barcode dasar

Objek `BarCodeResult` berisi tipe dan teks yang didekodekan. Menampilkan nilai-nilai ini membantu memverifikasi bahwa pembaca telah mengidentifikasi simbol dengan benar sebelum Anda menyelami detail makro.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Tip:** Jika `CodeText` kosong, gambar mungkin rusak atau mode dekode tidak tepat. Periksa kembali `DecodeType` yang digunakan saat inisialisasi.

## Langkah 5: Ekstrak informasi makro PDF417 yang diperluas

Data makro berada di bawah `barcodeResult.Extended.Pdf417`. Setiap properti sesuai dengan bidang yang didefinisikan dalam spesifikasi PDF417.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**Apa arti masing‑masing bidang**

| Property | Description |
|----------|-------------|
| `MacroPdf417FileID` | Pengidentifikasi yang mengelompokkan semua segmen yang termasuk dalam file logis yang sama. |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (dimulai dari 1). |
| `MacroPdf417SegmentsCount` | Jumlah total segmen yang diperlukan untuk merekonstruksi file asli. |
| `MacroPdf417FileName` | Nama file opsional yang disematkan dalam makro. |
| `MacroPdf417Checksum` | Checksum CRC‑16 untuk verifikasi integritas. |
| `MacroPdf417FileSize` | Ukuran yang diharapkan dari file yang direkonstruksi (dalam byte). |
| `MacroPdf417TimeStamp` | Tanggal‑waktu saat makro dihasilkan. |
| `MacroPdf417Addressee` | Identifikasi penerima opsional. |
| `MacroPdf417Sender` | Identifikasi pengirim opsional. |
| `MacroPdf417Terminator` | Bendera terminator; harus `true` pada segmen terakhir. |

Memahami bidang-bidang ini memungkinkan Anda membangun kembali file asli, memvalidasi integritas data, dan mengimplementasikan logika bisnis khusus (misalnya, menolak dokumen yang kedaluwarsa).

## Langkah 6: Tangani beberapa segmen dan bangun kembali file asli (lanjutan)

Ketika `MacroPdf417SegmentsCount` lebih besar dari 1, Anda perlu mengumpulkan setiap segmen, mengurutkannya berdasarkan `MacroPdf417SegmentID`, dan menggabungkan nilai `CodeText`. Berikut adalah implementasi singkat:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Mengapa ini penting:**  
Tanpa pengurutan dan penggabungan, data yang didekodekan akan tidak lengkap atau rusak. Potongan kode ini juga menunjukkan pemrograman defensif dengan memeriksa jumlah segmen.

## Langkah 7: Penutup dengan penanganan kesalahan dan praktik terbaik

Contoh **c# barcode reader** yang siap produksi harus mengantisipasi kesalahan IO, format yang tidak didukung, dan gambar yang rusak.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Daftar periksa praktik terbaik**

* Validasi jalur gambar sebelum membuat `BarCodeReader`.  
* Gunakan pernyataan `using` untuk menjamin pembuangan sumber daya yang tidak dikelola.  
* Catat bidang makro untuk jejak audit—terutama `MacroPdf417Checksum` dan `MacroPdf417TimeStamp`.  
* Saat menangani file besar, pertimbangkan streaming muatan yang digabungkan ke disk alih-alih menyimpannya sepenuhnya di memori.

## Output yang diharapkan

Menjalankan program lengkap terhadap `ExtPDF417Meta.png` yang valid menghasilkan output serupa dengan:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Jika semua tiga segmen hadir, blok rekonstruksi mencetak muatan penuh setelah pesan verifikasi.

## Kesimpulan

Anda sekarang tahu **cara mendekode PDF417** di C# menggunakan contoh pembaca barcode yang kuat. Tutorial ini mencakup instalasi Aspose.BarCode, inisialisasi `BarCodeReader` untuk Macro PDF417, iterasi atas beberapa barcode, mengekstrak bidang makro, membangun kembali data bersegmentasi, dan mengimplementasikan penanganan kesalahan.  

Dari sini Anda dapat:

* Mengintegrasikan pembaca ke dalam API web yang menerima gambar yang diunggah.  
* Menyimpan metadata makro dalam basis data untuk keperluan audit.  
* Memperluas solusi ke simbol 2‑D lainnya dengan mengganti `DecodeType` (e

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Read PDF417 barcode in C# – barcode reader example](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}