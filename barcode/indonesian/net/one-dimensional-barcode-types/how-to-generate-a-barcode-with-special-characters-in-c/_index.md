---
category: general
date: 2026-10-02
description: barcode dengan karakter khusus di C# – pelajari cara menghasilkan barcode
  dengan karakter khusus menggunakan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate barcode c#
language: id
lastmod: 2026-10-02
og_description: barcode dengan karakter khusus di C# – tutorial ini menunjukkan cara
  menghasilkan barcode C# yang mencakup simbol aksen dan merek dagang, lengkap dengan
  kode dan penjelasan.
og_image_alt: barcode with special characters example output
og_title: Buat kode batang dengan karakter khusus di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  headline: How to generate a barcode with special characters in C#
  type: TechArticle
- description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  name: How to generate a barcode with special characters in C#
  steps:
  - name: Why this works
    text: '* **Unicode support** – `BarcodeGenerator` accepts a `string` containing
      any Unicode glyph, so characters like **Å**, **ó**, and **©** are encoded without
      extra steps. * **MacroPdf417** – This format allows you to attach file‑level
      metadata (file ID, segment ID, checksum, etc.) that many enterprise '
  - name: Pro tip
    text: If you target a high‑density label printer, increase `XDimension.Pixels`
      to `3` or `4` to avoid pixel‑level distortion.
  - name: Edge case handling
    text: '* **Large file IDs** – The `FileID` property accepts a 32‑bit integer.
      If your system uses GUIDs, hash the GUID into a 32‑bit value before assignment.
      * **Timestamp precision** – The property stores a `DateTime`. If you need sub‑second
      precision, include it in the filename instead, as the standard d'
  - name: Expected output
    text: '* A PNG file approximately 300 × 150 pixels (size varies with column count).
      * When scanned with a PDF417‑compatible reader, the decoded text displays exactly
      **Åspóse.Barcóde©** and the scanner can reconstruct the original file using
      the macro fields.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membuat barcode dengan karakter khusus di C#
url: /id/net/one-dimensional-barcode-types/how-to-generate-a-barcode-with-special-characters-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode dengan karakter khusus di C#

Jika Anda perlu menghasilkan barcode dengan karakter khusus di C#, panduan ini menunjukkan solusi lengkap yang siap dijalankan. Baik Anda mengkodekan huruf beraksen seperti **Å** atau simbol seperti **©**, langkah-langkah di bawah ini memungkinkan Anda membuat barcode MacroPdf417 yang mempertahankan setiap karakter persis seperti yang Anda ketik.

Anda akan belajar cara menghasilkan barcode c# menggunakan pustaka Aspose.BarCode, mengonfigurasi metadata khusus MacroPdf417, dan menyimpan hasilnya sebagai gambar PNG. Tidak diperlukan alat eksternal—hanya lingkungan pengembangan .NET dan paket NuGet Aspose.BarCode.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Visual Studio 2022 (atau IDE apa pun yang mendukung C#)  
* Aspose.BarCode untuk .NET ditambahkan ke proyek Anda (`dotnet add package Aspose.BarCode`)  

Persyaratan ini memastikan kode dapat dikompilasi tanpa dependensi tambahan.

## Menghasilkan barcode dengan karakter khusus di C#

Inti dari solusi ini adalah membuat instance `BarcodeGenerator` yang menggunakan format `EncodeTypes.MacroPdf417`. Generator ini menerima string Unicode apa pun, sehingga Anda dapat menyematkan karakter khusus secara langsung.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MacroPdf417 with special characters
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Step 2: Set basic barcode appearance
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 3: Configure MacroPdf417 specific metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode with special characters generated successfully.");
    }
}
```

### Mengapa ini berhasil

* **Unicode support** – `BarcodeGenerator` menerima `string` yang berisi glyph Unicode apa pun, sehingga karakter seperti **Å**, **ó**, dan **©** dapat dikodekan tanpa langkah tambahan.  
* **MacroPdf417** – Format ini memungkinkan Anda melampirkan metadata tingkat file (file ID, segment ID, checksum, dll.) yang diharapkan oleh banyak sistem pemindaian perusahaan.  
* **Pixel‑level control** – Mengatur `XDimension.Pixels` mengontrol lebar modul, yang memengaruhi keterbacaan pada printer beresolusi rendah.

## Atur tampilan dasar barcode

Menyesuaikan `XDimension` dan jumlah kolom memengaruhi baik ukuran visual maupun jumlah data yang muat dalam satu baris. Nilai `2` piksel memberikan barcode yang kompak namun dapat dipindai, sementara `Columns = 5` menjaga simbol tetap cukup sempit untuk kebanyakan label.

### Tips profesional

Jika Anda menargetkan printer label berdensitas tinggi, tingkatkan `XDimension.Pixels` menjadi `3` atau `4` untuk menghindari distorsi pada tingkat piksel.

## Konfigurasikan metadata MacroPdf417

MacroPdf417 memperluas spesifikasi PDF417 standar dengan bidang yang menjelaskan cara file multi‑segmen harus direkonstruksi. Properti yang Anda atur dalam contoh sesuai dengan kasus penggunaan tipikal:

| Property | Purpose |
|----------|---------|
| `MacroPdf417FileID` | Pengidentifikasi unik untuk seluruh file |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (dimulai dari 1) |
| `MacroPdf417SegmentsCount` | Jumlah total segmen dalam file |
| `MacroPdf417FileName` | Nama logis file (digunakan oleh beberapa pemindai) |
| `MacroPdf417Checksum` | Checksum CCITT‑16 untuk integritas data |
| `MacroPdf417FileSize` | Ukuran yang diharapkan dalam byte – membantu pemindai memvalidasi kelengkapan |
| `MacroPdf417TimeStamp` | Stempel waktu pembuatan untuk jejak audit |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Informasi routing opsional |
| `MacroPdf417Terminator` | Menunjukkan apakah ini segmen terakhir (`Set`) atau segmen menengah (`Unset`) |

### Penanganan kasus tepi

* **Large file IDs** – Properti `FileID` menerima integer 32‑bit. Jika sistem Anda menggunakan GUID, hash GUID menjadi nilai 32‑bit sebelum penugasan.  
* **Timestamp precision** – Properti menyimpan `DateTime`. Jika Anda memerlukan presisi sub‑detik, sertakan dalam nama file sebagai gantinya, karena standar tidak mendukung milidetik.  

## Simpan gambar barcode

Metode `Save` menulis barcode yang dirender ke sistem file. Anda dapat memilih format lain (`Jpeg`, `Bmp`, `Svg`) dengan mengganti `BarCodeImageFormat.Png`. PNG bersifat lossless, menjadikannya ideal untuk pemrosesan lebih lanjut atau penyematan dalam PDF.

```csharp
barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
```

Setelah menjalankan program, Anda akan menemukan `ExtPDF417Meta.png` di direktori output. Membuka gambar menampilkan barcode padat multi‑baris yang berisi teks **Åspóse.Barcóde©** bersama dengan metadata makro yang Anda konfigurasikan.

### Output yang diharapkan

* File PNG berukuran kira-kira 300 × 150 piksel (ukuran bervariasi tergantung jumlah kolom).  
* Saat dipindai dengan pembaca kompatibel PDF417, teks yang didekode menampilkan tepat **Åspóse.Barcóde©** dan pemindai dapat merekonstruksi file asli menggunakan bidang makro.

## Cara menghasilkan barcode c# – jebakan umum

Meskipun kode ini sederhana, pengembang sering menemui masalah berikut:

1. **Missing NuGet package** – Lupa menginstal `Aspose.BarCode` menyebabkan error pada waktu kompilasi. Verifikasi referensi paket di `.csproj` Anda.  
2. **Invalid characters for the chosen symbology** – Beberapa jenis barcode (misalnya Code 128) menolak rentang Unicode tertentu. MacroPdf417 menerima seluruh set Unicode, menjadikannya pilihan paling aman untuk karakter khusus.  
3. **Incorrect file path** – Menggunakan path relatif tanpa izin yang tepat dapat menyebabkan `UnauthorizedAccessException` pada runtime. Berikan path absolut atau pastikan aplikasi memiliki akses menulis ke folder target.  

Mengatasi poin-poin ini memastikan bahwa cara menghasilkan barcode c# tetap berjalan lancar.

## Contoh lengkap yang berfungsi

Salin program lengkap di bawah ini ke dalam proyek konsol baru dan jalankan. Tidak ada konfigurasi tambahan yang diperlukan selain paket NuGet.



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Barcode dengan Karakter Khusus – Panduan Lengkap untuk Menghasilkan PDF417 Menggunakan](/barcode/english/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/)
- [Cara menghasilkan gambar barcode dengan Aspose.BarCode di C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)
- [Cara Menghasilkan Gambar Barcode PDF417 di C# dengan Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}