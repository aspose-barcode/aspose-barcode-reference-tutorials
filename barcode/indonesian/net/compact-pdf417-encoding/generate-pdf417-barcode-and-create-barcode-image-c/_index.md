---
category: general
date: 2026-10-08
description: Hasilkan kode batang PDF417 dalam C# dan pelajari cara menghasilkan gambar
  PDF417 secara efisien dengan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: id
lastmod: 2026-10-08
og_description: Hasilkan kode batang PDF417 dalam C# dengan panduan langkah demi langkah.
  Pelajari cara menghasilkan PDF417 dan menyimpan gambar kode batang sebagai PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Hasilkan kode batang PDF417 dan buat gambar kode batang di C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Hasilkan kode batang PDF417 dan buat gambar kode batang C#
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan barcode PDF417 dan buat gambar barcode C#

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, tutorial ini menunjukkan secara tepat cara melakukannya. Anda akan melihat contoh lengkap yang dapat dijalankan yang membuat barcode, menyesuaikan tata letaknya, dan menyimpan hasilnya sebagai gambar PNG.

Membuat barcode PDF417 adalah kebutuhan umum untuk label pengiriman, boarding pass, dan sistem inventaris. Pada akhir panduan ini Anda akan dapat **menghasilkan PDF417** dengan kontrol detail atas ukuran dan tata letak, serta Anda juga akan belajar cara **membuat gambar barcode C#** yang dapat ditampilkan di UI atau dikirim ke printer.

## Prasyarat

- .NET 6.0 atau lebih baru (kode juga berfungsi dengan .NET Framework 4.7.2+)
- Visual Studio 2022 atau IDE kompatibel C# apa pun
- Aspose.BarCode untuk .NET (versi percobaan gratis atau berlisensi)  
  Instal melalui NuGet:

```bash
dotnet add package Aspose.BarCode
```

Tidak ada konfigurasi tambahan yang diperlukan; pustaka menangani enkoding PNG secara internal.

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru dan tambahkan direktif `using` yang diperlukan. Blok ini mencakup semua yang Anda perlukan untuk mengompilasi contoh.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Mengapa langkah ini penting*: Mengimpor namespace `Aspose.BarCode.Generation` memberi Anda akses ke `BarcodeGenerator`, `EncodeTypes`, dan objek parameter yang digunakan untuk menyesuaikan barcode.

## Langkah 2: Hasilkan barcode PDF417 dengan teks yang diinginkan

Di dalam `Main`, buat instance `BarcodeGenerator` dengan `EncodeTypes.Pdf417`. Konstruktor menerima tipe barcode dan teks yang ingin Anda enkode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Penjelasan*: `EncodeTypes.Pdf417` memberi tahu pustaka untuk menghasilkan simbol PDF417. String `"Layout demo"` menjadi muatan data yang dienkode dalam barcode.

## Langkah 3: Sesuaikan ukuran barcode menggunakan X‑dimension

X‑dimension mengontrol lebar satu modul (kotak hitam/putih terkecil). Menetapkannya dalam piksel memberikan kontrol presisi atas ukuran gambar akhir.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Mengapa ini penting*: X‑dimension yang lebih kecil menghasilkan barcode yang lebih kompak, yang berguna ketika Anda memiliki ruang terbatas pada label atau elemen UI.

## Langkah 4: Sesuaikan tata letak PDF417 (kolom dan baris)

PDF417 memungkinkan Anda menentukan jumlah kolom dan baris. Menyesuaikan nilai-nilai ini mengubah rasio aspek barcode.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Penjelasan*: Dengan 4 kolom dan 9 baris, barcode menjadi lebih tinggi daripada lebarnya, cocok dengan banyak format pencetakan tiket.

## Langkah 5: Simpan barcode yang dihasilkan sebagai gambar PNG

Akhirnya, tulis barcode ke sebuah file. Enum `BarCodeImageFormat.Png` memastikan kompresi tanpa kehilangan.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Apa yang terjadi di sini*: `Save` membuat file gambar di disk. Anda dapat mengganti `BarCodeImageFormat.Png` dengan `Jpeg` atau `Bmp` jika format lain diperlukan.

### Contoh lengkap dalam satu blok

Berikut adalah program lengkap yang siap dijalankan. Ganti `YOUR_DIRECTORY` dengan jalur folder yang sebenarnya di mesin Anda.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Jalankan program (`dotnet run`) dan buka `LayoutPdf417.png` yang dihasilkan. Anda akan melihat barcode PDF417 yang bersih yang mengenkode teks *Layout demo*.

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="Barcode PDF417 yang dihasilkan disimpan sebagai PNG"}

*Output yang diharapkan*: File PNG berukuran kira-kira 150 × 300 piksel (ukuran bervariasi dengan X‑dimension) yang berisi barcode PDF417 yang dapat dipindai.

## Variasi umum dan kasus tepi

| Skenario | Cara menyesuaikan kode |
|----------|------------------------|
| **Payload data berbeda** | Ubah argumen kedua `BarcodeGenerator` (`"Layout demo"` → string apa pun, hingga 1 800 karakter). |
| **Resolusi lebih tinggi** | Tingkatkan `XDimension.Pixels` (mis., `4`) atau atur `Resolution` melalui `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Latar belakang transparan** | Gunakan `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Menyematkan dalam Windows Forms PictureBox** | Alih-alih `Save`, panggil `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Penanganan error** | Bungkus kode generasi dalam blok `try…catch` untuk menangkap `BarCodeException` pada karakter yang tidak didukung. |

## Tips profesional

- **Validasi barcode**: Setelah disimpan, Anda dapat memuat PNG dengan SDK pemindai barcode untuk memastikan data cocok dengan string asli.
- **Kinerja**: Menggunakan kembali satu instance `BarcodeGenerator` untuk beberapa barcode mengurangi overhead alokasi.
- **Keamanan**: Jika data yang dienkode berisi informasi sensitif, pertimbangkan untuk mengenkripsinya sebelum mengirim ke generator.

## Kesimpulan

Anda sekarang tahu cara **menghasilkan barcode PDF417** dalam C# dan **membuat file gambar barcode C#** yang memenuhi persyaratan tata letak khusus. Contoh lengkap menunjukkan inisialisasi generator, menyesuaikan ukuran dan tata letak, serta menyimpan hasilnya sebagai PNG. Dari sini Anda dapat menjelajahi fitur tambahan seperti penyesuaian warna, menyematkan logo, atau menghasilkan barcode secara batch untuk pencetakan massal.

---

*Langkah selanjutnya*:
- Bereksperimen dengan simbol lain (Code128, QR) menggunakan kelas `BarcodeGenerator` yang sama.
- Pelajari cara membaca barcode PDF417 dengan `BarCodeReader` dari Aspose.BarCode.
- Integrasikan PNG yang dihasilkan ke dalam tampilan ASP.NET Core MVC untuk rendering barcode secara langsung.

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menyimpan barcode dan menghasilkan PDF417 dengan Aspose di C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Cara Menghasilkan Barcode PDF417 dengan Aspose – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cara menghasilkan barcode PDF417 di C# dengan dimensi khusus](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}