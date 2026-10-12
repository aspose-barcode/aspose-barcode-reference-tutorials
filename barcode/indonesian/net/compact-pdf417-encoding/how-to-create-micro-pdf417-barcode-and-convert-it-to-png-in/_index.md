---
category: general
date: 2026-10-12
description: Pelajari cara membuat barcode micro PDF417 dan mengonversi barcode ke
  PNG menggunakan C#. Panduan langkah demi langkah dengan kode lengkap dan tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: id
lastmod: 2026-10-12
og_description: Buat kode batang micro PDF417 dan konversi kode batang ke PNG dengan
  C#. Ikuti panduan lengkap ini untuk menghasilkan versi standar dan GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Buat kode batang micro PDF417 dan konversi ke PNG – tutorial C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cara membuat barcode micro PDF417 dan mengonversinya ke PNG dalam C#
url: /id/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat micro PDF417 barcode dan mengonversinya ke PNG dalam C#

Jika Anda perlu **membuat micro PDF417 barcode** dalam aplikasi .NET, tutorial ini menunjukkan secara tepat caranya. Anda akan melihat contoh lengkap yang dapat dijalankan yang menghasilkan baik barcode Micro PDF417 standar maupun versi yang mematuhi GS1, kemudian **mengonversi barcode ke PNG** untuk penggunaan selanjutnya seperti pencetakan atau tampilan web.

Membuat barcode lebih dari sekadar memanggil satu metode—memilih ukuran modul, jumlah kolom, dan format enkoding yang tepat menentukan keandalan pemindaian. Pada akhir panduan ini Anda akan memahami mengapa setiap pengaturan penting dan bagaimana menyesuaikannya untuk proyek Anda sendiri.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

| Persyaratan | Alasan |
|-------------|--------|
| .NET 6.0 SDK atau lebih baru | Menyediakan runtime untuk aplikasi konsol C# |
| Visual Studio 2022 (atau IDE C# apa pun) | Memudahkan pengeditan dan debugging |
| **Aspose.BarCode for .NET** NuGet package | Menyediakan kelas `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat` |
| Izin menulis ke folder output | Diperlukan untuk pemanggilan `Save` yang membuat file PNG |

Anda dapat menambahkan paket Aspose.BarCode melalui CLI:

```bash
dotnet add package Aspose.BarCode
```

## Langkah 1: Siapkan proyek konsol minimal

Buat proyek konsol baru dan referensikan pustaka barcode. `Program.cs` berikut berisi semua kode yang Anda perlukan; tidak ada file eksternal yang dibutuhkan.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Mengapa setiap baris penting

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Yang pertama membuat barcode Micro PDF417 biasa, sedangkan yang kedua mengikuti standar GS1 dengan menyisipkan Application Identifiers (AIs). Pilih berdasarkan apakah sistem downstream Anda mengharapkan data GS1.
* **`XDimension.Pixels = 2`** – Mengontrol lebar modul. Nilai yang lebih kecil menghasilkan gambar lebih padat tetapi dapat menjadi tidak terbaca pada pemindai beresolusi rendah. Dua piksel adalah nilai aman untuk kebanyakan printer label.
* **`Pdf417.Columns = 4`** – Micro PDF417 memungkinkan Anda membatasi kolom, mengurangi lebar keseluruhan. Empat kolom menjaga barcode tetap kompak tanpa mengorbankan kapasitas data untuk payload pendek.
* **`BarCodeImageFormat.Png`** – PNG mempertahankan kualitas lossless, penting untuk kejernihan barcode. Itulah mengapa kami **mengonversi barcode ke PNG** alih-alih JPEG.

## Langkah 2: Jalankan program dan verifikasi output

1. Bangun proyek: `dotnet build`.
2. Jalankan: `dotnet run`.

Anda akan melihat pesan konsol serupa dengan:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Buka file PNG yang dihasilkan dengan penampil gambar apa pun. Kedua gambar menampilkan barcode yang tajam dan kontras tinggi, siap untuk dipindai.

### Hasil visual yang diharapkan

| Jenis Barcode | Penampilan |
|--------------|------------|
| **Micro PDF417** | Pola persegi panjang kecil dengan 4 kolom, dapat dibaca oleh sebagian besar pemindai barcode 2‑D. |
| **GS1 Micro PDF417** | Ukuran sama tetapi mengkodekan AI GS1; pemindai yang memahami GS1 akan mengembalikan GTIN dan nomor seri. |

Jika pemindai gagal membaca gambar, coba tingkatkan `XDimension.Pixels` menjadi **3** atau **4**, atau kurangi jumlah kolom untuk Micro PDF417 standar.

## Kesulitan umum dan cara menghindarinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| Barcode buram setelah pencetakan | Pengaturan printer DPI rendah | Ekspor PNG pada 300 dpi atau lebih tinggi, atau biarkan driver printer menangani skala. |
| Pemindai mengembalikan “data tidak valid” | Format AI GS1 yang hilang atau tidak tepat | Pastikan setiap AI dibungkus dalam tanda kurung dan mengikuti spesifikasi GS1 (misalnya `(01)` untuk GTIN‑14). |
| File gambar tidak dibuat | Folder output tidak memiliki izin menulis | Jalankan program dengan hak istimewa lebih tinggi atau pilih folder seperti `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Barcode terlalu besar untuk label | Jumlah kolom default terlalu tinggi | Kurangi `Pdf417.Columns` (misalnya menjadi **3**) atau tingkatkan `XDimension` untuk memperkecil ukuran keseluruhan. |

## Memperluas contoh

* **Format gambar berbeda** – Ganti `BarCodeImageFormat.Png` dengan `Jpeg` atau `Bmp` jika alur kerja Anda memerlukannya. PNG tetap pilihan terbaik untuk kualitas lossless.
* **Data dinamis** – Kirimkan input pengguna atau nilai basis data ke konstruktor `BarcodeGenerator` untuk membuat barcode secara langsung.
* **Pembuatan batch** – Bungkus logika pembuatan dalam loop yang membaca baris dari file CSV dan menyimpan setiap barcode dengan nama file unik.

## Kesimpulan

Anda kini tahu cara **membuat micro PDF417 barcode** dalam C# dan **mengonversi barcode ke PNG** untuk skenario standar maupun yang mematuhi GS1. Kode lengkap yang dapat dijalankan memperlihatkan pengaturan penting—dimensi X, jumlah kolom, dan tipe enkoding—sehingga Anda dapat menyesuaikan solusi ini untuk proyek .NET apa pun yang membutuhkan barcode 2‑D yang kompak dan berkualitas tinggi.

*Langkah selanjutnya*: jelajahi simbol lain yang didukung oleh Aspose.BarCode (misalnya QR, DataMatrix), bereksperimen dengan nilai `XDimension` yang berbeda untuk pencetakan resolusi tinggi, atau integrasikan PNG yang dihasilkan ke dalam API web yang menyajikan barcode sesuai permintaan.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara membuat micro pdf417 barcode di C# dan menyimpannya sebagai PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Buat barcode PNG di C# – panduan lengkap untuk GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Hasilkan Micro PDF417 Barcode di C# – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}