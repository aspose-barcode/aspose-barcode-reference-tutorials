---
category: general
date: 2026-09-28
description: Baca barcode PDF417 c# dengan cepat menggunakan Aspose.BarCode. Dekode
  beberapa barcode dari satu gambar, ekstrak bidang Macro‑PDF417, dan tangani rotasi
  atau pemrosesan batch.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Baca barcode PDF417 c# dengan cepat menggunakan Aspose.BarCode. Panduan
  ini menunjukkan cara mendekode beberapa barcode dari satu gambar, mengekstrak semua
  properti Macro‑PDF417, dan menangani gambar yang diputar atau batch.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Baca barcode PDF417 c# – contoh kode lengkap & panduan
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Cara membaca barcode PDF417 c# – panduan lengkap langkah demi langkah
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca PDF417 barcode c# – panduan langkah demi langkah lengkap

Pernah bertanya-tanya **cara membaca PDF417** dari sebuah gambar menggunakan C#? Anda tidak sendirian. Kebanyakan pengembang menemui kendala ketika harus mengambil bidang Macro‑PDF417 yang diperluas dari dokumen yang dipindai. Kabar baik? Dengan hanya beberapa baris kode Anda dapat **read PDF417 barcode c#**, mendekode banyak barcode dalam satu gambar, dan mengambil setiap properti tersembunyi yang ditawarkan spesifikasi.

## Jawaban cepat
- **Apakah Aspose.BarCode dapat mendekode Macro‑PDF417?** Ya – cukup aktifkan `DecodeType.MacroPdf417` dan perpustakaan mengembalikan semua bidang tambahan.  
- **Berapa banyak barcode yang dapat dibaca dari satu gambar?** Tak terbatas; API mengembalikan koleksi objek `BarCodeResult`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **Apakah barcode yang diputar akan terdeteksi?** Kompensasi rotasi bawaan berfungsi untuk barcode yang menutupi setidaknya 30 % lebar gambar.  
- **Apakah pemrosesan batch didukung?** Tentu – bungkus pembaca dalam loop `foreach` dan buang setiap instance dengan `using`.

## Apa itu read PDF417 barcode c#?
`read pdf417 barcode c#` mengacu pada proses menggunakan perpustakaan .NET untuk mendekode simbol PDF417 (termasuk Macro‑PDF417) dari file gambar secara langsung dalam kode C#. SDK Aspose.BarCode menyediakan API satu panggilan yang menangani pemuatan gambar, deteksi barcode, dan ekstraksi semua bidang yang didefinisikan ISO.

## Mengapa menggunakan Aspose.BarCode untuk dekode PDF417?
Aspose.BarCode mendukung **lebih dari 30 simbol barcode** dan dapat memproses gambar hingga **5000 × 5000 px** dalam kurang dari **0,1 s** pada perangkat keras server tipikal. Ia juga menawarkan penanganan rotasi, distorsi, dan barcode terbalik secara langsung, menghilangkan kebutuhan pra‑pemrosesan gambar khusus. Selain itu, perpustakaan menyertakan dukungan bawaan untuk membaca bidang tambahan Macro‑PDF417, menjadikannya solusi satu atap untuk skenario pemindaian kompleks.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru (kode ini juga bekerja dengan .NET Core dan .NET Framework).  
* Visual Studio 2022 (atau editor apa pun yang Anda sukai).  
* Paket NuGet **Aspose.BarCode for .NET** – ini adalah perpustakaan yang sebenarnya mem‑parsing PDF417.  
* Gambar contoh yang berisi barcode Macro‑PDF417 (misalnya `ExtPDF417Meta.png`).  

Tidak diperlukan konfigurasi tambahan; perpustakaan sudah menyertakan semua decoder yang Anda butuhkan.

## Cara membaca PDF417 barcode c#?

Muat gambar dengan `BarCodeReader`, tentukan `DecodeType.MacroPdf417`, dan iterasi koleksi `BarCodeResult` yang dikembalikan – itulah solusi lengkap dalam kurang dari sepuluh baris kode. Pembaca secara otomatis mengekstrak baik simbol PDF417 biasa maupun data tambahan Macro‑PDF417, sehingga Anda mendapatkan identifier file, nomor segmen, timestamp, dan checksum tanpa parsing ekstra.

### Langkah 1: instal Aspose.BarCode

Buka folder proyek Anda di terminal dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah tersebut mengambil versi stabil terbaru (per Juli 2026 versi 23.12). Jika Anda lebih suka Package Manager Console di dalam Visual Studio, gunakan:

```powershell
Install-Package Aspose.BarCode
```

> **Tip profesional:** kunci versi (`23.12.0`) di file `.csproj` Anda untuk menghindari perubahan yang merusak secara tidak sengaja di kemudian hari.

### Langkah 2: buat kerangka aplikasi console

Buat proyek console baru jika belum ada:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Ganti `Program.cs` yang dihasilkan secara otomatis dengan kode di bawah ini. Kami akan menjelaskan setiap blok pada bagian selanjutnya.

### Langkah 3: tulis kode lengkap “cara membaca PDF417”

`BarCodeReader` adalah kelas inti yang mem‑stream gambar, mendeteksi barcode, dan mengembalikan koleksi objek `BarCodeResult`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

* `BarCodeReader` — kelas utama yang bertanggung jawab membaca dan mendekode barcode dari gambar.  
* `DecodeType.MacroPdf417` — bendera yang memberi tahu SDK untuk memperlakukan Macro‑PDF417 secara khusus sekaligus tetap mengembalikan simbol PDF417 biasa.  
* `Extended.Pdf417.MacroPdf417` — objek yang menyimpan setiap bidang opsional yang didefinisikan oleh ISO/IEC 15438, seperti `FileID`, `SegmentID`, dan `Checksum`.

Blok `using` menjamin sumber daya native dibebaskan, mencegah kebocoran memori pada layanan yang berjalan lama.

### Langkah 4: jalankan aplikasi dan verifikasi output

Dari terminal:

```bash
dotnet run
```

Anda akan melihat sesuatu seperti:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Jika gambar berisi lebih dari satu barcode, loop akan mencetak baris pemisah (`----------------------------------------`) dan melanjutkan ke hasil berikutnya—tepat seperti **read multiple barcodes** dalam praktik.

## Pertanyaan umum & kasus tepi

### Bagaimana jika gambar memiliki simbol Macro‑PDF417 dan PDF417 biasa?

Pemanggilan `BarCodeReader` yang sama akan mengembalikan keduanya. Anda dapat membedakannya dengan memeriksa `result.CodeType` (`MacroPdf417` vs `Pdf417`). Properti tambahan akan `null` untuk PDF417 biasa, sehingga guard `if (macro != null)` mencegah `NullReferenceException`.

### Barcode saya diputar atau miring—apakah pembaca masih berfungsi?

Aspose.BarCode menyertakan kompensasi rotasi dan distorsi bawaan. Selama barcode menutupi setidaknya 30 % lebar gambar, decoder biasanya berhasil. Untuk kasus ekstrim Anda dapat mengaktifkan `reader.Options.AllowInvertedBarcodes = true;` sebelum memanggil `ReadBarCodes()`.

### Bagaimana cara menangani batch gambar yang besar?

Bungkus logika pembacaan dalam loop `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Pola `using` memastikan sumber daya native tiap gambar dibebaskan sebelum iterasi berikutnya, menjaga penggunaan memori tetap rendah.

## Daftar sumber lengkap (siap salin‑tempel)

Berikut seluruh program dalam satu blok untuk salin‑tempel cepat. Tidak ada dependensi tersembunyi—hanya paket NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Ringkasan – apa yang telah dibahas

* **Cara membaca PDF417 barcode c#** menggunakan Aspose.BarCode.  
* Langkah tepat untuk **read multiple barcodes** dari satu gambar.  
* Cara **read barcode image c#** dan mengekstrak setiap bidang Macro‑PDF417.  
* Tips untuk rotasi, pemrosesan batch, dan penanganan data tambahan yang hilang.

## Langkah selanjutnya & topik terkait

* **Encode PDF417** – buat barcode Macro‑PDF417 Anda sendiri dengan `BarCodeBuilder`.  
* **Baca simbol 2‑D lainnya** – QR, DataMatrix, Aztec – menggunakan kelas `BarCodeReader` yang sama.  
* **Integrasi dengan ASP.NET Core** – buat endpoint web yang menerima gambar unggahan dan mengembalikan JSON berisi bidang yang didekode.  

### Tautan berguna tambahan
- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Baca barcode DataMatrix C# – Hasilkan Mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Silakan bereksperimen: ubah jalur gambar, letakkan PDF417 biasa di folder yang sama, atau ubah flag `DecodeType` untuk melihat bagaimana perpustakaan berperilaku. Semakin sering Anda mencoba, semakin nyaman Anda akan menjadi dengan skenario **read barcode image c#**.

Mendapatkan gambar sulit yang tidak dapat didekode? Tinggalkan komentar di bawah atau buka isu di repositori GitHub proyek contoh. Selamat coding!

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan ini dalam aplikasi komersial?**  
A: Ya, Anda dapat menggunakan Aspose.BarCode dalam proyek komersial selama Anda memiliki lisensi yang valid; versi percobaan gratis tersedia untuk evaluasi.

**Q: Apakah pembaca mendukung gambar yang dilindungi kata sandi?**  
A: SDK bekerja dengan format gambar standar; perlindungan kata sandi tidak berlaku untuk gambar raster, hanya untuk PDF, yang ditangani oleh komponen Aspose.PDF terpisah.

**Q: Versi .NET apa yang didukung?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, dan .NET 6+ semuanya didukung penuh oleh rilis Aspose.BarCode saat ini.

**Q: Bagaimana cara meningkatkan performa untuk batch gambar yang sangat besar?**  
A: Aktifkan `reader.Options.Quality = QualityMode.HighPerformance` dan proses gambar secara paralel menggunakan `Parallel.ForEach` sambil tetap membungkus setiap `BarCodeReader` dalam blok `using`.

**Q: Apakah ada cara untuk mendapatkan hanya bidang Macro‑PDF417 tanpa mengiterasi semua hasil?**  
A: Ya – setelah memanggil `ReadBarCodes()`, filter koleksi dengan `result => result.CodeType == DecodeType.MacroPdf417` dan kemudian akses properti `Extended.Pdf417.MacroPdf417`.

---

**Terakhir diperbarui:** 2026-09-28  
**Diuji dengan:** Aspose.BarCode 23.12 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat Gambar Barcode Pdf417 di C Dengan Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)  
- [Buat Barcode Pdf417 dengan Aspose Barcode Panduan Langkah demi Langkah](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)  
- [Baca Banyak Barcode C Panduan Lengkap Dengan Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}