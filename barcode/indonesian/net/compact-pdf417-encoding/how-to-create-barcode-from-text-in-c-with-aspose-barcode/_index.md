---
category: general
date: 2026-10-02
description: Buat barcode dari teks di C# menggunakan Aspose.BarCode. Pelajari cara
  menghasilkan barcode PDF417 dan lihat cara menghasilkan barcode PDF417 dalam mode
  kompak.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: id
lastmod: 2026-10-02
og_description: Buat barcode dari teks di C# dengan Aspose.BarCode. Panduan ini menunjukkan
  cara menghasilkan barcode PDF417 dan cara menghasilkan barcode PDF417 dalam mode
  kompak.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Buat barcode dari teks di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cara membuat barcode dari teks di C# dengan Aspose.BarCode
url: /id/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode dari teks di C# dengan Aspose.BarCode

Jika Anda perlu **membuat barcode dari teks** dalam aplikasi .NET, panduan ini akan memandu Anda melalui proses lengkap. Anda akan melihat contoh siap‑jalankan yang **menghasilkan barcode PDF417** dan juga menjawab **cara menghasilkan barcode PDF417** dalam tata letak kompak.

Membuat barcode secara programatik menghilangkan langkah manual dan menjamin konsistensi di semua dokumen. Pada akhir tutorial ini Anda akan memiliki file PNG yang berisi barcode PDF417 yang dapat Anda sematkan dalam faktur, tiket, atau kartu identitas.

## Apa yang Anda butuhkan

- .NET 6.0 SDK atau lebih baru (kode juga berfungsi dengan .NET Framework 4.7.2+)
- Visual Studio 2022 atau editor apa pun yang mendukung C#
- Lisensi NuGet untuk **Aspose.BarCode for .NET** (versi percobaan gratis dapat digunakan untuk pengujian)

> **Tip pro:** Tambahkan paket NuGet melalui CLI untuk menjaga proyek tetap bersih:  
> `dotnet add package Aspose.BarCode`

## Langkah 1: Siapkan proyek konsol

Buat aplikasi konsol baru dan referensikan pustaka Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Perintah `dotnet new console` menghasilkan file `Program.cs` yang akan kami ganti dengan contoh lengkap di bawah.

## Langkah 2: Cara membuat barcode dari teks – kode inti

Buka `Program.cs` dan ganti isinya dengan kode berikut. Setiap baris dikomentari untuk menjelaskan mengapa kode tersebut ada.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Mengapa setiap pengaturan penting

| Setting | Purpose |
|--------|----------|
| `EncodeTypes.Pdf417` | Memilih simbol PDF417, yang dapat menyimpan sejumlah besar data dalam matriks dua‑dimensi. |
| `XDimension.Pixels = 2` | Mengontrol lebar setiap modul; nilai 2 piksel menyeimbangkan keterbacaan dan ukuran file. |
| `Pdf417.Columns = 3` | Mengurangi jumlah kolom, membuat barcode lebih kompak tanpa kehilangan data. |
| `Pdf417.Truncate = true` | Mengaktifkan mode kompak, menghapus padding yang tidak diperlukan dan memendekkan barcode. |
| `BarCodeImageFormat.Png` | PNG mempertahankan kualitas lossless, ideal untuk pemrosesan lebih lanjut atau pencetakan. |

## Langkah 3: Hasilkan barcode PDF417 – menjalankan contoh

Bangun dan jalankan proyek:

```bash
dotnet run
```

Saat eksekusi selesai Anda akan melihat:

```
Barcode saved to CompactPdf417.png
```

Buka `CompactPdf417.png` untuk melihat hasilnya. Gambar tersebut berisi barcode PDF417 yang mengenkode string **Åspóse.Barcóde©**.

![Create barcode from text example](barcode-example.png)

*Alt text: membuat barcode dari teks – barcode PDF417 disimpan sebagai PNG*

## Langkah 4: Cara menghasilkan barcode PDF417 dengan koreksi error khusus (opsional)

Jika lingkungan pemindaian Anda berisik, Anda dapat meningkatkan level koreksi error:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Meningkatkan level error membuat barcode lebih besar tetapi meningkatkan ketahanan terhadap kerusakan.

## Langkah 5: Kesalahan umum dan penanganan kasus tepi

1. **Karakter tidak valid** – PDF417 mendukung Unicode, tetapi beberapa pemindai lama mungkin menolak simbol non‑ASCII. Uji dengan perangkat keras target Anda.
2. **Izin jalur file** – Pastikan direktori tempat Anda menulis dapat ditulisi; jika tidak `Save` akan melempar `UnauthorizedAccessException`.
3. **Ukuran gambar** – Nilai `XDimension` yang sangat tinggi menghasilkan file PNG besar. Jaga ukuran piksel antara 1 dan 4 untuk kebanyakan skenario tampilan layar.

## Ringkasan

Anda sekarang tahu cara **membuat barcode dari teks** di C# menggunakan Aspose.BarCode, cara **menghasilkan barcode PDF417** dengan tata letak kompak, dan langkah tepat untuk **cara menghasilkan barcode PDF417** dengan pengaturan khusus. Kode lengkap yang dapat dijalankan di atas dapat disalin ke proyek .NET apa pun dan disesuaikan dengan input teks atau format output yang berbeda (mis., JPEG, BMP).

## Langkah Selanjutnya

- Jelajahi simbol lain seperti QR Code atau Code128 dengan mengubah `EncodeTypes`.
- Integrasikan PNG yang dihasilkan ke dalam PDF menggunakan Aspose.PDF untuk pembuatan dokumen end‑to‑end.
- Bereksperimen dengan `generator.Parameters.Barcode.Pdf417.Rows` untuk mengontrol kepadatan vertikal.

Silakan modifikasi contoh, sematkan barcode dalam aplikasi Anda sendiri, dan bagikan hasil Anda dengan komunitas. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara menghasilkan barcode PDF417 di C# – contoh kompak](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [Cara membuat barcode PDF417 di C# dengan mode kompak](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Cara menghasilkan barcode PDF417 di C# – panduan langkah‑demi‑langkah](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}