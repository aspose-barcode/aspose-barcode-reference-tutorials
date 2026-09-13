---
category: general
date: 2026-09-13
description: Pelajari cara mendekode PDF417 di C# dengan kode langkah demi langkah
  yang dapat membaca beberapa barcode dan menampilkan data barcode untuk aplikasi
  apa pun.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read multiple barcodes
- c# barcode decoding
- display barcode data
language: id
lastmod: 2026-09-13
og_description: Cara mendekode PDF417 di C#? Ikuti panduan ini untuk membaca beberapa
  barcode dan menampilkan data barcode menggunakan Aspose.BarCode.
og_image_alt: Console window showing decoded PDF417 barcode information
og_title: Cara mendekode barcode PDF417 di C# – tutorial cepat dan lengkap
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to decode PDF417 in C# with step‑by‑step code that reads
    multiple barcodes and displays barcode data for any application.
  headline: How to decode PDF417 barcodes in C# – full guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspnet
title: Cara mendekode barcode PDF417 di C# – panduan lengkap
url: /id/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mendekode barcode PDF417 di C# – panduan lengkap

Jika Anda perlu **cara mendekode pdf417** dalam proyek .NET, tutorial ini menunjukkan langkah‑langkah tepatnya. Anda akan melihat cara membaca beberapa barcode dari satu gambar dan menampilkan data barcode dalam output konsol yang jelas. Pada akhir tutorial Anda akan memiliki program C# siap‑jalankan yang menangani dekode Macro PDF417 tanpa ada yang terlewat.

Mendekode PDF417 tidak terbatas pada satu pemindaian; banyak skenario dunia nyata—seperti label pengiriman atau boarding pass—menyisipkan beberapa segmen Macro PDF417 dalam satu gambar. Panduan ini mencakup alur kerja lengkap, mulai dari menginstal pustaka hingga mencetak setiap bidang yang mungkin Anda perlukan, sehingga Anda dapat mengintegrasikan pembacaan barcode ke dalam aplikasi C# apa pun hari ini.

## Apa yang Anda perlukan

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru (kode ini juga bekerja dengan .NET Framework 4.7+)
* Visual Studio 2022 (atau IDE apa pun yang mendukung C#)
* Paket NuGet **Aspose.BarCode for .NET** – menyediakan `BarCodeReader` dan `DecodeType.MacroPdf417`
* Gambar PNG/JPEG yang berisi satu atau lebih simbol Macro PDF417 (misalnya `MacroPdf417.png`)

> **Tips pro:** Jika Anda tidak memiliki gambar contoh, Anda dapat membuatnya dengan situs demo gratis Aspose.BarCode atau menggunakan pemindai apa pun yang menghasilkan gambar ber‑kode PDF417.

## Langkah 1: Instal pustaka barcode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah NuGet menambahkan versi stabil terbaru **Aspose.BarCode for .NET** ke proyek Anda dan memulihkan semua dependensi yang diperlukan.

## Langkah 2: Buat proyek konsol (jika belum ada)

```bash
dotnet new console -n Pdf417Decoder
cd Pdf417Decoder
```

File `Program.cs` yang dihasilkan akan menjadi tempat logika dekode yang akan kita bahas selanjutnya.

## Langkah 3: Tulis kode dekode – baca beberapa barcode

Ganti isi `Program.cs` dengan contoh lengkap di bawah ini. Setiap baris dijelaskan, sehingga Anda memahami **c# barcode decoding** secara menyeluruh.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains one or more Macro PDF417 symbols
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Initialize the BarCodeReader for Macro PDF417 decoding.
            //    The DecodeType.MacroPdf417 flag tells the library to expect
            //    Macro PDF417 symbols, which contain extra fields like FileID.
            using (var barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes present in the image.
                //    The ReadBarCodes() method returns an IEnumerable<BarCodeResult>,
                //    allowing us to iterate over each detected barcode.
                foreach (var barcodeResult in barcodeReader.ReadBarCodes())
                {
                    // 3️⃣ Display the raw text of the barcode.
                    Console.WriteLine($"Decoded Text : {barcodeResult.CodeText}");

                    // 4️⃣ Access Macro PDF417‑specific extended information.
                    //    These properties are only populated when DecodeType.MacroPdf417 is used.
                    var macroInfo = barcodeResult.Extended?.Pdf417?.MacroPdf417;
                    if (macroInfo != null)
                    {
                        Console.WriteLine($"FileID      : {macroInfo.FileID}");
                        Console.WriteLine($"SegmentID   : {macroInfo.SegmentID}");
                        Console.WriteLine($"FileName    : {macroInfo.FileName}");
                        Console.WriteLine($"FileSize    : {macroInfo.FileSize}");
                        Console.WriteLine($"Checksum    : {macroInfo.Checksum}");
                        // Add any other fields you need here.
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 extended data found.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // Keep the console window open when debugging locally.
            Console.WriteLine("Decoding finished. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Mengapa setiap bagian penting

* **`using (var barcodeReader = new BarCodeReader(...))`** – Menjamin bahwa sumber daya tak terkelola dilepaskan dengan cepat, mencegah kebocoran memori pada layanan yang berjalan lama.
* **`DecodeType.MacroPdf417`** – Memerintahkan mesin untuk mencari bidang Macro PDF417 yang diperluas; tanpa ini Anda hanya akan mendapatkan payload teks biasa.
* **`ReadBarCodes()`** – Mengembalikan *semua* barcode dalam gambar, yang memenuhi kebutuhan **read multiple barcodes**. Bahkan jika gambar hanya berisi satu simbol, metode ini tetap mengembalikan koleksi, menjaga kode tetap seragam.
* **`barcodeResult.Extended.Pdf417.MacroPdf417`** – Memberikan akses ke metadata tambahan (FileID, SegmentID, dll.) yang membedakan Macro PDF417 dari PDF417 biasa. Inilah inti dari **display barcode data** secara bermakna.
* **Output konsol** – Dengan mencetak setiap bidang, Anda dapat memverifikasi bahwa decoder berfungsi dengan benar dan kemudian menyalurkan data ke basis data, file, atau API.

## Langkah 4: Bangun dan jalankan program

```bash
dotnet build
dotnet run
```

Dengan asumsi `MacroPdf417.png` ada dan berisi dua simbol Macro PDF417, konsol akan menampilkan sesuatu yang mirip dengan:

```
Decoded Text : https://example.com/page1
FileID      : 12
SegmentID   : 1
FileName    : document_part1.pdf
FileSize    : 1048576
Checksum    : 0x1A2B3C4D
----------------------------------------
Decoded Text : https://example.com/page2
FileID      : 12
SegmentID   : 2
FileName    : document_part2.pdf
FileSize    : 1048576
Checksum    : 0x5E6F7A8B
----------------------------------------
Decoding finished. Press any key to exit.
```

Jika gambar hanya berisi satu segmen PDF417, loop tetap dijalankan sekali, memenuhi logika **read multiple barcodes** tanpa perubahan kode apa pun.

## Langkah 5: Variasi umum dan kasus tepi

| Situasi | Apa yang harus diubah |
|-----------|----------------|
| **Non‑Macro PDF417** (PDF417 biasa) | Gunakan `DecodeType.Pdf417` alih‑alih `MacroPdf417`. Properti `Extended` akan `null`, jadi beri pengecekan seperti yang ditunjukkan. |
| **Berbagai format gambar** | Konstruktor `BarCodeReader` menerima format gambar apa pun yang didukung .NET (`.png`, `.jpg`, `.tif`). Cukup berikan path yang sesuai. |
| **Batch gambar besar** | Bungkus logika pembacaan dalam loop `foreach (var file in Directory.GetFiles(folder, "*.png"))` dan gunakan satu instance `BarCodeReader` per file untuk meningkatkan throughput. |
| **Optimasi performa** | Setel `barcodeReader.Options.Pdf417.Pdf417CompactionMode = Pdf417CompactionMode.Auto` agar mesin memilih mode dekode tercepat untuk setiap barcode. |
| **Penanganan error** | Tangkap `BarCodeException` di sekitar pemanggilan `ReadBarCodes()` untuk menangani gambar yang rusak dengan elegan. |

## Langkah 6: Praktik terbaik untuk dekode barcode C#

* **Dispose objek** – Selalu gunakan pernyataan `using` untuk `BarCodeReader` dan kelas disposable lainnya.
* **Validasi hasil** – Periksa `barcodeResult.CodeText` apakah `null` atau string kosong sebelum diproses.
* **Log data tambahan** – Simpan bidang seperti `FileID` dan `SegmentID` dalam format terstruktur (JSON, basis data) bukan hanya mencetaknya.
* **Unit test** – Buat proyek tes yang memuat gambar barcode yang sudah diketahui dan memastikan setiap bidang tambahan cocok dengan nilai yang diharapkan. Ini membantu menangkap regresi saat Anda memperbarui pustaka Aspose.

## Kesimpulan

Sekarang Anda tahu **cara mendekode pdf417** barcode di C# menggunakan Aspose.BarCode, cara **membaca beberapa barcode** dari satu gambar, dan cara **menampilkan data barcode** seperti FileID, SegmentID, dan FileName. Contoh lengkap yang dapat dijalankan menunjukkan setiap langkah—dari menginstal paket NuGet hingga menangani kasus tepi—sehingga Anda dapat menyisipkan kode ini ke dalam aplikasi .NET apa pun dan mulai memproses simbol PDF417 segera.

**Langkah selanjutnya**

* Jelajahi opsi **c# barcode decoding** untuk simbol lain (QR, Code128, DataMatrix) dengan mengubah `DecodeType`.
* Integrasikan bidang yang telah didekode ke dalam API web yang mengembalikan JSON untuk konsumsi front‑end.
* Gabungkan decoder ini dengan layanan file‑watcher untuk secara otomatis memproses pemindaian yang masuk secara real time.

Selamat coding, dan nikmati mengubah barcode mentah menjadi data yang dapat ditindaklanjuti!

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}