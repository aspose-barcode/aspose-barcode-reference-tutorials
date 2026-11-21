---
category: general
date: 2026-11-20
description: Pelajari cara membaca barcode macro PDF417 di C# dengan cepat. Panduan
  ini menunjukkan cara membaca barcode dari gambar C# menggunakan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read macro PDF417 barcode
- read barcodes from image C#
- Aspose.BarCode C#
- PDF417 extended data
- barcode decoding .NET
language: id
lastmod: 2026-11-20
og_description: Baca kode batang macro PDF417 dengan C# menggunakan Aspose.BarCode.
  Ikuti tutorial ini untuk membaca kode batang dari gambar C# dan mengekstrak informasi
  lengkap Macro PDF417.
og_image_alt: Screenshot showing a Macro PDF417 barcode being read in a C# console
  application
og_title: Baca kode batang macro PDF417 di C# – panduan lengkap langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to read macro PDF417 barcode in C# quickly. This guide shows
    you how to read barcodes from image C# using Aspose.BarCode.
  headline: How to read macro PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to read macro PDF417 barcode in C# quickly. This guide shows
    you how to read barcodes from image C# using Aspose.BarCode.
  name: How to read macro PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: '**`BarCodeReader` construction** – By passing `DecodeType.MacroPdf417`
      we tell Aspose.BarCode to look specifically for Macro PDF417 symbols and to
      populate the `Extended.Pdf417` object.'
    text: '**`BarCodeReader` construction** – By passing `DecodeType.MacroPdf417`
      we tell Aspose.BarCode to look specifically for Macro PDF417 symbols and to
      populate the `Extended.Pdf417` object.'
  - name: '**`ReadBarCodes()`** – Returns a collection because an image may contain
      more than one barcode. The loop handles each result independently.'
    text: '**`ReadBarCodes()`** – Returns a collection because an image may contain
      more than one barcode. The loop handles each result independently.'
  - name: '**`result.Extended.Pdf417`** – Holds the extended fields defined by the
      Macro PDF417 specification:'
    text: '**`result.Extended.Pdf417`** – Holds the extended fields defined by the
      Macro PDF417 specification:'
  - name: '**Console output** – Shows each field, making it easy to verify that the
      barcode was read correctly.'
    text: '**Console output** – Shows each field, making it easy to verify that the
      barcode was read correctly.'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- Aspose
title: Cara membaca barcode macro PDF417 di C# dengan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca macro PDF417 barcode di C# dengan Aspose.BarCode

Jika Anda perlu **membaca macro PDF417 barcode** dalam aplikasi .NET, tutorial ini menunjukkan solusi lengkap yang siap dijalankan. Anda akan melihat cara **membaca barcode dari gambar C#** menggunakan pustaka Aspose.BarCode, mengekstrak setiap bidang Macro PDF417 yang diperluas, dan menangani kasus tepi umum.

Panduan ini mencakup semua yang perlu Anda ketahui: penyiapan proyek, penjelasan kode, tips pemecahan masalah, dan ide langkah selanjutnya untuk skenario yang lebih maju.

## Apa yang Anda butuhkan

- **.NET 6.0** atau lebih baru (kode juga berfungsi dengan .NET Framework 4.6+)
- **Visual Studio 2022** (atau IDE apa pun yang mendukung .NET)
- Paket NuGet **Aspose.BarCode for .NET** (versi percobaan gratis atau berlisensi)
- File gambar yang berisi barcode Macro PDF417 (misalnya `ExtPDF417Meta.png`)

> **Pro tip:** Jika Anda tidak memiliki contoh gambar barcode, Anda dapat menghasilkan satu dengan kelas `BarcodeGenerator` Aspose.BarCode dan mengatur `EncodeMode = EncodeMode.MacroPdf417`.

## Langkah 1: Instal Aspose.BarCode

Buka terminal di folder proyek Anda dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Perintah ini menambahkan DLL Aspose.BarCode terbaru dan memperbarui file `.csproj` Anda. Tidak ada dependensi native tambahan yang diperlukan.

## Langkah 2: Buat kerangka aplikasi konsol

Buat proyek konsol baru (jika Anda belum memilikinya):

```bash
dotnet new console -n MacroPdf417Reader
cd MacroPdf417Reader
```

Ganti `Program.cs` yang dihasilkan dengan contoh lengkap di bawah ini. Kode ini berdiri sendiri dan dapat dikompilasi tanpa modifikasi setelah paket NuGet diinstal.

## Langkah 3: Contoh kode lengkap – membaca barcode macro PDF417

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace MacroPdf417Reader
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that holds the Macro PDF417 barcode.
            // Use an absolute path or place the image in the project folder and set
            // "Copy to Output Directory" = "Copy always" in Visual Studio.
            string imagePath = "ExtPDF417Meta.png";

            // Initialize the BarCodeReader for MacroPdf417 decoding.
            // DecodeType.MacroPdf417 tells the library to look for the extended
            // Macro PDF417 fields (FileID, SegmentID, FileName, etc.).
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Read all barcodes found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // The Extended property contains PDF417‑specific information.
                    var pdf417Info = result.Extended?.Pdf417;

                    if (pdf417Info != null)
                    {
                        Console.WriteLine($"Pdf417MacroFileID   : {pdf417Info.MacroPdf417FileID}");
                        Console.WriteLine($"Pdf417MacroSegmentID: {pdf417Info.MacroPdf417SegmentID}");
                        Console.WriteLine($"Pdf417MacroFileName : {pdf417Info.MacroPdf417FileName}");
                        Console.WriteLine($"Pdf417MacroFileSize : {pdf417Info.MacroPdf417FileSize}");
                        Console.WriteLine($"Pdf417MacroChecksum : {pdf417Info.MacroPdf417Checksum}");
                        // Add any other fields you need here.
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 information was found in this barcode.");
                    }
                }
            }

            Console.WriteLine("\nFinished reading macro PDF417 barcode.");
        }
    }
}
```

### Cara kerja kode

1. **`BarCodeReader` construction** – Dengan memberikan `DecodeType.MacroPdf417` kami memberi tahu Aspose.BarCode untuk secara khusus mencari simbol Macro PDF417 dan mengisi objek `Extended.Pdf417`.
2. **`ReadBarCodes()`** – Mengembalikan koleksi karena sebuah gambar dapat berisi lebih dari satu barcode. Loop menangani setiap hasil secara independen.
3. **`result.Extended.Pdf417`** – Menyimpan bidang yang diperluas yang didefinisikan oleh spesifikasi Macro PDF417:
   - `MacroPdf417FileID` – Pengidentifikasi seluruh file (berguna ketika data dibagi menjadi beberapa simbol).
   - `MacroPdf417SegmentID` – Indeks segmen tertentu ini.
   - `MacroPdf417FileName` – Nama file opsional yang disematkan dalam barcode.
   - `MacroPdf417FileSize` – Ukuran total file asli dalam byte.
   - `MacroPdf417Checksum` – Nilai pemeriksaan integritas.
4. **Console output** – Menampilkan setiap bidang, memudahkan verifikasi bahwa barcode telah dibaca dengan benar.

> **Mengapa menggunakan `MacroPdf417` alih-alih `Pdf417` biasa?**  
> Macro PDF417 menambahkan metadata yang memungkinkan pemecahan muatan data besar menjadi beberapa simbol. Jika Anda hanya mendekode `Pdf417` biasa, bidang tambahan tersebut diabaikan, dan Anda kehilangan informasi yang diperlukan untuk merekonstruksi file asli.

## Langkah 4: Verifikasi output

Jalankan program:

```bash
dotnet run
```

Output konsol tipikal terlihat seperti:

```
Pdf417MacroFileID   : 12
Pdf417MacroSegmentID: 3
Pdf417MacroFileName : invoice_2026_11.pdf
Pdf417MacroFileSize : 45231
Pdf417MacroChecksum : 0x1A2B3C4D

Finished reading macro PDF417 barcode.
```

Jika gambar tidak mengandung simbol Macro PDF417, program akan mencetak *“No Macro PDF417 information was found in this barcode.”* Pesan ini membantu Anda membedakan antara barcode yang tidak didukung dan kegagalan decoding.

## Langkah 5: Kesalahan umum saat Anda **membaca barcode dari gambar C#**

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| `reader.ReadBarCodes()` mengembalikan koleksi kosong | Path gambar salah atau file tidak disalin ke folder output. | Gunakan path absolut atau atur properti **Copy to Output Directory** file gambar menjadi **Copy always**. |
| `result.Extended.Pdf417` is `null` | Barcode bukan simbol Macro PDF417 (misalnya PDF417 biasa atau format lain). | Pastikan barcode dihasilkan dengan `EncodeMode = EncodeMode.MacroPdf417`. |
| Dekoding gagal pada gambar beresolusi rendah | Barcode blur atau terlalu kecil untuk pengaturan default pustaka. | Tingkatkan resolusi gambar, atau aktifkan `reader.Parameters.BarcodeReaderOptions` seperti `AutoRotate` dan penyesuaian `Quality`. |
| Checksum tidak cocok | Gambar rusak selama transport atau penyimpanan. | Buat ulang barcode atau verifikasi integritas file sumber. |

Menangani masalah ini lebih awal menghemat waktu saat Anda **membaca barcode dari gambar C#** dalam sistem produksi.

## Langkah 6: Opsi lanjutan dan langkah selanjutnya

- **Batch processing** – Bungkus logika pembaca dalam metode yang menerima path folder dan memproses setiap file PNG/JPG secara otomatis.
- **Asynchronous decoding** – Gunakan `Task.Run` untuk mendekode batch besar tanpa memblokir thread UI pada aplikasi desktop atau web.
- **Saving extracted data** – Tulis bidang macro ke file JSON untuk pemrosesan selanjutnya:

  ```csharp
  var json = System.Text.Json.JsonSerializer.Serialize(pdf417Info);
  File.WriteAllText($"metadata_{pdf417Info.MacroPdf417SegmentID}.json", json);
  ```

- **Integration with other Aspose products** – Gabungkan data yang didekode dengan Aspose.PDF untuk merekonstruksi dokumen asli dari segmen macro-nya.

## Kesimpulan

Anda sekarang tahu cara **membaca barcode macro PDF417** di C# menggunakan Aspose.BarCode, dan Anda memahami cara **membaca barcode dari gambar C#** sambil mengekstrak setiap bidang Macro PDF417 yang diperluas. Contoh lengkap yang dapat dijalankan menunjukkan penyiapan proyek, eksekusi kode, dan tips pemecahan masalah.

Dari sini Anda dapat menjelajahi dekoding batch, pemrosesan asinkron, atau mengintegrasikan metadata yang diekstrak dengan pustaka penanganan dokumen lainnya. Bereksperimenlah dengan kualitas gambar yang berbeda, file multi‑segmen, dan penanganan error khusus untuk menyesuaikan dengan kasus penggunaan Anda.

--- 

*Siap mencobanya sendiri? Clone repositori, ganti `ExtPDF417Meta.png` dengan gambar barcode Anda sendiri, dan jalankan program. Jika Anda mengalami masalah, tabel pemecahan masalah di atas akan mengarahkan Anda ke arah yang benar.*

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Baca barcode dari gambar C# – panduan lengkap dengan Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Cara membuat barcode macro PDF417 di C# menggunakan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cara membaca barcode PDF417 di C# dengan Aspose – panduan langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}