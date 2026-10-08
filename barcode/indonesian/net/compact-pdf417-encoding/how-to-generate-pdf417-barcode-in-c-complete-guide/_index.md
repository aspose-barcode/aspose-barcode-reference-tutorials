---
category: general
date: 2026-09-26
description: Hasilkan kode batang PDF417 dalam C# dengan Aspose.BarCode. Ikuti tutorial
  langkah demi langkah ini untuk mengatur kolom, mengaktifkan mode kompak, dan menyimpan
  sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- pdf417 barcode generator c#
- Aspose.BarCode C#
- barcode image format PNG
- compact PDF417 mode
language: id
lastmod: 2026-09-26
og_description: Buat kode batang PDF417 di C# menggunakan Aspose.BarCode. Panduan
  ini menunjukkan cara mengatur kolom, mengaktifkan mode kompak, dan mengekspor hasilnya
  sebagai gambar PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Buat kode batang PDF417 di C# – tutorial langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Generate PDF417 barcode in C# with Aspose.BarCode. Follow this step‑by‑step
    tutorial to configure columns, enable compact mode, and save as PNG.
  headline: How to generate PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
- PDF417
title: Cara menghasilkan barcode PDF417 di C# – panduan lengkap
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan PDF417 barcode di C# – panduan lengkap

Jika Anda perlu **menghasilkan PDF417 barcode** dalam aplikasi .NET, tutorial ini menunjukkan solusi siap‑jalankan. Anda akan melihat cara mengatur ukuran barcode, jumlah kolom, dan mode kompak, kemudian menyimpan hasilnya sebagai file PNG berkualitas tinggi.

Membuat barcode adalah kebutuhan umum untuk sistem inventaris, platform tiket, dan pengkodean dokumen. Pada akhir panduan ini Anda akan memiliki program C# yang berdiri sendiri yang menghasilkan barcode PDF417 kompak menggunakan perpustakaan **pdf417 barcode generator C#** dari Aspose.

## Apa yang Anda perlukan

- .NET 6.0 SDK atau yang lebih baru (kode juga berfungsi dengan .NET Framework 4.7+)
- Lisensi Aspose.BarCode for .NET yang valid (evaluasi gratis dapat digunakan untuk pengujian)
- IDE atau editor seperti Visual Studio 2022, Rider, atau VS Code
- Familiaritas dasar dengan proyek konsol C#

> **Pro tip:** Jika Anda menggunakan evaluasi gratis, gambar yang dihasilkan akan berisi watermark Aspose kecil. Lisensi yang dibeli menghapus watermark dan membuka semua fitur.

## Langkah 1: Siapkan perpustakaan Aspose.BarCode

Buat proyek konsol baru dan tambahkan paket NuGet Aspose.BarCode.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Paket ini menyediakan kelas `BarcodeGenerator`, yang merupakan inti dari alur kerja **pdf417 barcode generator C#**.

## Langkah 2: Tulis program lengkap untuk menghasilkan barcode

Buka `Program.cs` dan gantikan isinya dengan kode berikut. Program ini menunjukkan setiap langkah yang diperlukan, mulai dari menginisialisasi generator hingga menyimpan gambar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 2.1: Create a generator for PDF417 with Unicode text.
            // The text contains special characters to prove Unicode handling.
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Step 2.2: Define the module (pixel) size of each barcode element.
            // XDimension controls the width of a single bar; 2 pixels gives a clear image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.3: Set the number of columns.
            // PDF417 can automatically choose columns, but fixing it to 3 produces a compact layout.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.4: Enable compact mode.
            // Truncate reduces the amount of data stored, making the barcode smaller.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.5: Choose the output format and file path.
            // PNG preserves the exact pixel dimensions without compression artifacts.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Mengapa setiap baris penting

| Baris | Tujuan |
|------|---------|
| `new BarcodeGenerator(EncodeTypes.Pdf417, "...")` | Membuat instance generator PDF417 dan menetapkan teks yang akan dienkode. PDF417 mendukung kumpulan data besar dan Unicode, sehingga cocok untuk pengidentifikasi yang kompleks. |
| `XDimension.Pixels = 2` | Mengontrol kepadatan visual. Nilai yang lebih kecil menghasilkan bar yang lebih halus; nilai yang lebih besar meningkatkan keterbacaan pada layar beresolusi rendah. |
| `Pdf417.Columns = 3` | Mengesampingkan perhitungan kolom otomatis. Kolom tetap berguna ketika Anda harus menyesuaikan barcode ke dalam ruang yang telah ditentukan. |
| `Pdf417.Truncate = true` | Mengaktifkan mode kompak, yang menghapus padding yang tidak diperlukan dan mengurangi ukuran keseluruhan. |
| `Save(..., BarCodeImageFormat.Png)` | Menulis barcode ke file PNG, format loss‑less yang ideal untuk pemrosesan lebih lanjut atau penyematan dalam PDF. |

## Langkah 3: Jalankan program dan verifikasi output

Bangun dan jalankan proyek:

```bash
dotnet run
```

Anda akan melihat pesan konsol yang mengonfirmasi lokasi file, dan sebuah file bernama **CompactPdf417.png** akan muncul di folder proyek.

![Contoh barcode PDF417 yang dihasilkan](images/compact-pdf417.png){.img-responsive alt="Contoh barcode PDF417 yang dihasilkan"}

*Gambar ini menampilkan barcode PDF417 kompak yang mengkodekan string “Åspóse.Barcóde©”.*  

Jika Anda membuka PNG di penampil gambar, Anda akan melihat tiga kolom blok data yang ditumpuk, setiap bar berukuran 2 piksel lebar. Memindai barcode dengan pembaca PDF417 standar mengembalikan teks asli, mengonfirmasi bahwa generator berfungsi sebagaimana mestinya.

## Kesalahan umum dan cara menghindarinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Barcode terlihat buram | XDimension diatur terlalu rendah untuk DPI target | Tingkatkan `XDimension.Pixels` menjadi 3 atau 4, atau render pada resolusi lebih tinggi menggunakan `generator.Save(..., BarCodeImageFormat.Tiff)` |
| Karakter Unicode hilang | String input tidak dienkode sebagai UTF‑8 | Pastikan file sumber disimpan dengan enkoding UTF‑8; generator secara otomatis menangani Unicode ketika tipe string adalah `string`. |
| Truncate menghasilkan pengecualian | Ukuran data melebihi maksimum untuk jumlah kolom yang dipilih | Tingkatkan `Pdf417.Columns` atau set `Pdf417.Truncate = false` agar generator menyediakan ruang yang cukup. |
| Lisensi tidak diterapkan | Versi evaluasi menambahkan watermark | Terapkan file lisensi yang valid melalui `Aspose.BarCode.License` sebelum membuat generator. |

## Memperluas solusi

Setelah Anda memiliki alur dasar **generate PDF417 barcode**, Anda dapat menjelajahi fitur tambahan:

- **Error correction level** – Sesuaikan `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel` untuk meningkatkan ketahanan terhadap kerusakan.
- **Color customization** – Gunakan `generator.Parameters.Barcode.ForegroundColor` dan `BackgroundColor` untuk menyesuaikan dengan pedoman merek.
- **Embedding in PDFs** – Gabungkan Aspose.PDF dengan Aspose.BarCode untuk menempatkan barcode langsung di dalam dokumen PDF.
- **Batch generation** – Lakukan perulangan atas koleksi identifier untuk menghasilkan beberapa file PNG dalam satu kali jalankan.

Semua opsi ini didokumentasikan dalam referensi API Aspose.BarCode dan mengikuti pola yang sama seperti yang ditunjukkan di atas.

## Kesimpulan

Anda sekarang tahu cara **generate PDF417 barcode** di C# menggunakan Aspose.BarCode, mengonfigurasi kolom, mengaktifkan mode kompak, dan mengekspor hasilnya sebagai gambar PNG. Contoh lengkap ini dapat dijalankan langsung dan dapat disesuaikan untuk proyek yang lebih besar, seperti sistem tiket, label inventaris, atau pengkodean dokumen yang aman.

Selanjutnya, coba pengaturan lanjutan **pdf417 barcode generator C#** seperti koreksi kesalahan dan penyesuaian warna, atau integrasikan barcode ke dalam laporan PDF dengan Aspose.PDF. Bereksperimenlah dengan nilai `XDimension` dan jumlah kolom yang berbeda untuk menemukan keseimbangan optimal antara ukuran dan keandalan pemindaian untuk kasus penggunaan Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Hasilkan barcode PDF417 di C# – panduan lengkap dengan tata letak kompak](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/)
- [Contoh barcode Aspose: hasilkan Macro PDF417 di C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Cara Menyimpan Barcode di C# – Hasilkan Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}