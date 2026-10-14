---
category: general
date: 2026-10-05
description: Baca kode batang dari gambar C# menggunakan Aspose.BarCode. Pelajari
  pemindaian kode batang C# langkah demi langkah, dekode Macro PDF417, dan tangani
  properti tambahan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- C# barcode scanning
- Macro PDF417 decoding
- Aspose.BarCode for .NET
- decode barcode image C#
language: id
lastmod: 2026-10-05
og_description: Baca kode batang dari gambar C# dengan Aspose.BarCode. Tutorial ini
  menunjukkan cara memindai kode batang Macro PDF417, mengambil bidang tambahan, dan
  menangani beberapa kode.
og_image_alt: Screenshot of C# console output showing barcode type and Macro PDF417
  properties
og_title: Baca kode batang dari gambar C# – panduan langkah demi langkah lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Read barcode from image C# using Aspose.BarCode. Learn step‑by‑step
    C# barcode scanning, decode Macro PDF417 and handle extended properties.
  headline: Read barcode from image C# – complete guide with Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- image-processing
title: Membaca barcode dari gambar C# – panduan lengkap dengan Macro PDF417
url: /id/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca barcode dari gambar C# – panduan lengkap dengan Macro PDF417

Jika Anda perlu **membaca barcode dari gambar C#**, tutorial ini menunjukkan solusi siap‑jalankan. Dengan menggunakan pustaka Aspose.BarCode for .NET, Anda akan mendekode barcode Macro PDF417, mengekstrak data dasarnya, dan mengambil setiap properti tambahan yang disediakan format tersebut.

Membaca barcode dari gambar adalah kebutuhan umum—baik Anda membangun sistem validasi tiket, memproses label pengiriman, atau mengekstrak metadata dari dokumen yang dipindai. Pada langkah‑langkah berikut Anda akan melihat mengapa kelas `BarCodeReader` adalah pendekatan yang direkomendasikan, cara mengkonfigurasinya untuk Macro PDF417, dan apa yang harus dilakukan dengan hasilnya.

---

## Apa yang akan Anda pelajari

* Instal dan referensikan **Aspose.BarCode for .NET** (pustaka yang mendukung contoh).  
* Buat sebuah `BarCodeReader` yang dikonfigurasi untuk **dekode Macro PDF417**.  
* Iterasi semua barcode dalam sebuah gambar dan keluarkan baik bidang standar maupun bidang tambahan.  
* Tangani beberapa barcode, kelola sumber daya dengan benar, dan selesaikan masalah umum.

**Prasyarat**

* .NET 6.0 SDK atau lebih baru (kode juga bekerja dengan .NET Framework 4.6+).  
* Familiaritas dasar dengan aplikasi konsol C#.  
* File gambar yang berisi barcode Macro PDF417 (misalnya `ExtPDF417Meta.png`).  

---

## Langkah 1: Tambahkan Aspose.BarCode ke proyek Anda (pemindaian barcode C#)

1. Buka terminal di folder solusi Anda.  
2. Jalankan perintah NuGet:

```bash
dotnet add package Aspose.BarCode
```

Paket ini berisi kelas `BarCodeReader`, enumerasi `DecodeType`, dan objek `BarCodeResult` yang digunakan sepanjang tutorial.

> **Pro tip:** Jika Anda menargetkan .NET Framework, gunakan Package Manager Console di Visual Studio:  
> `Install-Package Aspose.BarCode`

---

## Langkah 2: Siapkan program konsol (dekode gambar barcode C#)

Buat proyek konsol baru (atau tambahkan kode ke proyek yang sudah ada):

```csharp
using System;
using Aspose.BarCode;               // Core namespace
using Aspose.BarCode.BarCodeRecognition; // For DecodeType and BarCodeReader

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains a Macro PDF417 barcode.
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 2.1: Initialise the BarCodeReader for Macro PDF417.
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath, DecodeType.MacroPdf417))
            {
                // Step 2.2: Read every barcode present in the image.
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    // Step 2.3: Output basic information.
                    Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                    // Step 2.4: Output Macro PDF417 extended properties.
                    PrintMacroPdf417Properties(barcodeResult);
                }
            }

            // Keep console window open for inspection.
            Console.WriteLine("\nPress any key to exit...");
            Console.ReadKey();
        }

        /// <summary>
        /// Writes all Macro PDF417 extended fields to the console.
        /// </summary>
        /// <param name="result">Result object returned by BarCodeReader.</param>
        private static void PrintMacroPdf417Properties(BarCodeResult result)
        {
            // The Extended property is null if the barcode type does not support it.
            if (result?.Extended?.Pdf417 == null)
            {
                Console.WriteLine("No Macro PDF417 extended data available.");
                return;
            }

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
        }
    }
}
```

### Mengapa struktur ini?

* `using` statement – menjamin `BarCodeReader` melepaskan sumber daya native (penting untuk gambar besar).  
* `DecodeType.MacroPdf417` – memberi tahu pustaka untuk mencari Macro PDF417 secara khusus; tipe lain (mis., QR, Code128) akan mengabaikan bidang tambahan.  
* `ReadBarCodes()` – mengembalikan enumerable, memungkinkan Anda menangani **beberapa barcode** dalam gambar yang sama tanpa kode tambahan.  
* Metode terpisah `PrintMacroPdf417Properties` – mengisolasi logika bidang tambahan, membuat loop utama lebih mudah dibaca dan menyederhanakan pemeliharaan di masa depan.

---

## Langkah 3: Jalankan program dan verifikasi output (dekode Macro PDF417)

Buka command prompt, arahkan ke folder proyek, dan jalankan:

```bash
dotnet run
```

Anda akan melihat output serupa dengan berikut (nilai akan berbeda tergantung pada barcode sebenarnya):

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B3C4D
Pdf417MacroFileSize: 1048576
Pdf417MacroTimeStamp: 2023-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True

Press any key to exit...
```

Jika gambar tidak mengandung barcode Macro PDF417, konsol akan menampilkan **“No Macro PDF417 extended data available.”** Penanganan yang elegan ini mencegah pengecualian null‑reference.

---

## Langkah 4: Variasi umum dan kasus tepi (tips pemindaian barcode C#)

| Situasi | Penyesuaian yang disarankan |
|-----------|------------------------|
| **Beberapa tipe barcode dalam satu gambar** | Inisialisasi reader dengan `DecodeType.AllSupported` dan periksa `barcodeResult.CodeTypeName` untuk menentukan logika. |
| **Gambar besar (≥10 MP)** | Tingkatkan `barcodeReader.Options.MaxBarCodeCount` atau gunakan `barcodeReader.SetResolution(300)` untuk meningkatkan kecepatan deteksi. |
| **Bidang tambahan hilang** | Beberapa scanner menghapus data Macro; verifikasi gambar sumber berisi bidang tersebut menggunakan alat inspeksi barcode sebelum menulis kode. |
| **Menjalankan di Linux/macOS** | Pastikan binary native untuk Aspose.BarCode tersedia (`Aspose.BarCode.Native` paket NuGet) atau set `Environment.SetEnvironmentVariable("DOTNET_SYSTEM_GLOBALIZATION_INVARIANT", "1")` jika Anda hanya membutuhkan data ASCII. |
| **Loop yang kritis terhadap performa** | Cache instance `BarCodeReader` dan gunakan kembali untuk sekumpulan gambar; dispose hanya setelah batch selesai. |

---

## Langkah 5: Penutup dan langkah selanjutnya (baca barcode dari gambar C#)

Anda kini memiliki **solusi lengkap dan mandiri** untuk membaca barcode Macro PDF417 dari gambar dalam C#. Contoh ini menunjukkan:

* Instalasi **yang tepat** dari pustaka Aspose.BarCode.  
* Pembuatan **`BarCodeReader`** yang dikonfigurasi untuk **Macro PDF417**.  
* Iterasi atas **semua barcode** dalam gambar yang diberikan.  
* Ekstraksi metadata **standar** (`CodeTypeName`, `CodeText`) **dan tambahan** Macro PDF417.  

### Apa yang dapat dijelajahi selanjutnya?

* **Dekode format lain** – ganti `DecodeType.MacroPdf417` dengan `DecodeType.QR`, `DecodeType.Code128`, dll.  
* **Integrasikan dengan ASP.NET Core** – expose endpoint Web API yang menerima unggahan gambar dan mengembalikan JSON dengan data barcode.  
* **Persist hasil** – simpan metadata yang diekstrak ke basis data untuk analitik di kemudian hari.  
* **Kombinasikan dengan OCR** – gunakan Aspose.OCR untuk membaca teks yang tidak dikodekan sebagai barcode.

Silakan bereksperimen dengan gambar contoh, sesuaikan jalur file, atau sematkan logika ke dalam aplikasi yang lebih besar. Kelas **`BarCodeReader`** menyediakan fondasi yang kuat untuk skenario **pemindaian barcode C#** apa pun.

--- 

*Selamat coding! Jika Anda mengalami masalah, periksa kembali bahwa gambar benar‑benar berisi barcode Macro PDF417 dan bahwa versi Aspose.BarCode cocok dengan runtime .NET Anda.*

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Baca barcode dari gambar di C# – tutorial BarCodeReader](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/)
- [Cara Membuat Gambar Barcode PDF417 di C# dengan Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}