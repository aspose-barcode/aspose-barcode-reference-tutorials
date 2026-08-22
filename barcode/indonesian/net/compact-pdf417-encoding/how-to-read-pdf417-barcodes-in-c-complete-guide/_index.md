---
category: general
date: 2026-08-22
description: Cara membaca kode batang PDF417 di C# dengan panduan langkah demi langkah,
  mencakup cara membaca beberapa kode batang dari sebuah gambar dan mengekstrak detail
  MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: id
lastmod: 2026-08-22
og_description: Cara membaca kode batang PDF417 di C# dengan cepat. Tutorial ini menunjukkan
  cara membaca beberapa kode batang dari sebuah gambar dan mengambil informasi tambahan
  MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Cara membaca kode batang PDF417 di C# – panduan pemrograman lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membaca kode batang PDF417 di C# – panduan lengkap
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Kode Bar PDF417 di C# – Panduan Lengkap

Jika Anda perlu **cara membaca PDF417** di aplikasi .NET, tutorial ini memberikan solusi siap‑jalankan. Anda akan belajar cara membaca beberapa kode bar dari satu gambar, mengekstrak set data MacroPdf417 lengkap, dan menampilkannya di konsol. Pendekatan ini bekerja dengan pustaka Aspose.BarCode untuk .NET dan hanya memerlukan beberapa baris kode.

Membaca kode bar dari gambar adalah tugas umum dalam sistem inventaris, validasi tiket, dan manajemen dokumen. Pada akhir panduan ini Anda akan dapat mendekode kode bar PDF417 atau MacroPdf417 apa pun, menangani beberapa kode dalam satu gambar, dan memahami bidang tambahan yang disediakan MacroPdf417.

## Prasyarat

- .NET 6.0 SDK atau yang lebih baru (kode ini juga dapat dikompilasi dengan .NET Framework 4.7+)
- Visual Studio 2022 atau editor C# pilihan Anda
- Paket NuGet Aspose.BarCode untuk .NET (`Install-Package Aspose.BarCode`)
- Gambar contoh yang berisi kode bar MacroPdf417 (misalnya `MacroPdf417.png`)

Tidak ada konfigurasi tambahan yang diperlukan; pustaka menangani pemuatan gambar dan proses dekoding secara internal.

## Cara Membaca Kode Bar PDF417 dari Gambar di C#

Inti solusi adalah kelas `BarCodeReader`. Ia membuka gambar, mendeteksi semua kode bar dari tipe yang ditentukan, dan mengembalikan koleksi objek `BarCodeResult`. Kode berikut menampilkan program konsol lengkap.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Mengapa Setiap Baris Penting

| Langkah | Tujuan |
|------|---------|
| **1️⃣ Inisialisasi** | Membuat `BarCodeReader` yang terikat pada file gambar dan membatasi deteksi hanya pada simbolologi MacroPdf417, sehingga mempercepat proses. |
| **2️⃣ Iterasi** | `ReadBarCodes()` mengembalikan **semua** kode bar yang cocok dengan tipe yang diminta, memungkinkan Anda **membaca beberapa kode bar** tanpa loop tambahan. |
| **3️⃣ Output dasar** | Menampilkan `CodeTypeName` generik dan `CodeText` yang dapat dibaca manusia. Ini berguna untuk pencatatan atau validasi cepat. |
| **4️⃣ Data tambahan** | MacroPdf417 membawa metadata tambahan (ID file, jumlah segmen, cap waktu, dll.). Objek `Extended.Pdf417` mengekspose setiap bidang secara langsung, sehingga Anda dapat menyimpan atau memverifikasi seluruh paket data. |

Menjalankan program terhadap gambar MacroPdf417 yang valid menghasilkan output konsol serupa dengan berikut:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Output tersebut mengonfirmasi bahwa pustaka berhasil membaca kode bar, mengekstrak teks, dan menyediakan setiap bidang MacroPdf417.

## Membaca Beberapa Kode Bar dari Satu Gambar

Banyak skenario dunia nyata menempatkan beberapa simbol PDF417 pada satu label—misalnya manifest pengiriman yang berisi kode carrier, nomor pelacakan, dan deklarasi bea cukai. Blok kode yang sama di atas sudah **membaca beberapa kode bar** karena `ReadBarCodes()` mengembalikan enumerable dari semua kecocokan. Tidak ada konfigurasi tambahan yang diperlukan; Anda hanya perlu melakukan loop melalui hasil, seperti yang ditunjukkan.

Jika Anda ingin membatasi pembaca hanya pada PDF417 standar (non‑macro) sambil tetap menangani beberapa kode, ganti `DecodeType.MacroPdf417` dengan `DecodeType.Pdf417`. Logika lainnya tetap tidak berubah.

## Memahami Data Tambahan MacroPdf417

MacroPdf417 adalah ekstensi dari spesifikasi PDF417 biasa. Ia membagi muatan besar menjadi beberapa segmen dan menambahkan header kecil yang mendeskripsikan seluruh file. Bidang paling relevan meliputi:

- **MacroPdf417FileID** – pengidentifikasi unik yang dibagikan oleh semua segmen dari file yang sama.
- **MacroPdf417SegmentID** – nomor urut segmen saat ini.
- **MacroPdf417SegmentsCount** – total jumlah segmen yang diharapkan.
- **MacroPdf417FileName** – nama file opsional yang dikirim bersama kode bar.
- **MacroPdf417Checksum** – nilai pemeriksaan kesalahan untuk file lengkap.
- **MacroPdf417FileSize** – ukuran muatan biner asli.
- **MacroPdf417TimeStamp** – cap waktu ISO‑8601 saat kode bar dibuat.
- **MacroPdf417Addressee / Sender** – bidang teks opsional untuk routing.
- **MacroPdf417Terminator** – menunjukkan apakah segmen ini adalah yang terakhir.

Ketika Anda menerima semua segmen, Anda dapat merekonstruksi file asli dengan mengurutkan mereka berdasarkan `MacroPdf417SegmentID` dan menggabungkan nilai `CodeText`. Logika ini mudah diimplementasikan setelah bidang-bidang tersedia.

## Kesalahan Umum dan Tips Profesional

- **Kualitas gambar penting** – file PNG/JPEG beresolusi rendah atau terkompresi berat dapat menyebabkan deteksi terlewat. Gunakan DPI minimal 300 dpi untuk kode bar yang dicetak.
- **Simbolologi campuran** – jika gambar berisi baik MacroPdf417 maupun PDF417 biasa, buat dua pembaca (satu untuk tiap `DecodeType`) atau gunakan `DecodeType.AllSupported` dan filter hasil berdasarkan `result.CodeTypeName`.
- **Penggunaan memori** – pernyataan `using` membuang `BarCodeReader` dengan cepat, mencegah buffer gambar besar tetap berada di memori.
- **Keamanan thread** – `BarCodeReader` tidak thread‑safe. Buat instance terpisah per thread jika Anda mendekode gambar secara paralel.
- **Penanganan error** – bungkus pemanggilan `ReadBarCodes()` dalam blok try/catch untuk menangkap `BarCodeException` pada gambar yang rusak.

## Ringkasan Contoh Kerja Lengkap

Berikut adalah program lengkap yang dapat Anda salin ke proyek konsol baru. Program ini mencakup semua direktif `using`, konstanta untuk jalur gambar, dan pola disposisi.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Kompilasi dengan `dotnet build` dan jalankan dengan `dotnet run`. Konsol akan mencetak data dasar setiap kode bar serta payload MacroPdf417 lengkap.

## Langkah Selanjutnya

- **Merekonstruksi file multipart** – kumpulkan semua segmen, urutkan berdasarkan `MacroPdf417SegmentID`, dan gabungkan `CodeText` ke


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Kode Bar PDF417 – Enkoding PDF417 Kompak](/barcode/english/net/compact-pdf417-encoding/)
- [Cara Membaca Kode Bar PDF417 dengan Karakter Turki di Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Cara Menggunakan Aspose untuk Kode Bar PDF417 (Cina) di Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}